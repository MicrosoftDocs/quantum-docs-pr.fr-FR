---
title: Deuxième quantification | Microsoft Docs
description: Documentation conceptuelle sur la deuxième quantification
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: 4b7b5a6be6d0c1f3520128609e6b9fa83e5460d5
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036421"
---
# <a name="second-quantization"></a>Deuxième quantification

La deuxième quantification examine le problème de la structure électronique par le biais d’une autre lentille.
Au lieu d’affecter chaque $N _e $ électron à un état spécifique (ou orbital), une deuxième quantification effectue le suivi de chaque orbital et stocke si un électron est présent dans chacun d’eux et, en même temps, garantit automatiquement les propriétés de symétrie du fonction Wave correspondante.
Cela est important, car il permet de spécifier des modèles de chimie Quantum sans avoir à se soucier de l’état d’entrée symmetrizing (comme requis pour fermions) et également parce que la deuxième quantification permet de simuler ces modèles à l’aide de Small Quantum serveurs.

En guise d’exemple de deuxième quantification en action, supposons que la valeur de $ \ psi_0 \cdots \ psi_ {N-1} $ est un ensemble orthonormal d’orbites spatiales.
Ces orbites sont choisies pour représenter le système aussi précisément que possible dans l’ensemble de base fini pris en compte.
Un exemple courant d’orbites est l’orbite atomique qui forme un eigenbasis pour l’Atom hydrogène.
Étant donné que les électrons ont deux États de rotation, deux électrons peuvent être sursubmergés dans chaque orbital spatial.
Autrement dit, les États de base valides se présentent sous la forme $ \ psi_ {0, \uparrow}, \ldots, \ psi_ {N-1, \uparrow}, \ psi_ {0, \downarrow}, \ldots, \ psi_ {N-1, \downarrow} $ où $ \uparrow $ et $ \downarrow $ sont des étiquettes qui spécifient les deux eigenstates du degré de rotation de libert.
Cet index combiné de $ (j, \sigma) $ pour $ \sigma \Dans \{\uparrow, \downarrow\}$ est appelé spin-orbital, car il stocke à la fois l’spatial et le degré de liberté de spin.
Dans la bibliothèque chimie, les orbites sont stockées dans une structure de données `SpinOrbital` et sont créées comme suit.

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

Cela signifie que nous pouvons considérer officiellement la base pour la partie de rotation et spatiale de la fonction Wave en tant que $ \ psi_{0} \cdots \ psi_ {2N-1} $ où chacun des index est maintenant une énumération d’un $ (j, \sigma) $.
Une énumération possible est $g (j, \sigma) = j + N\sigma' $.
Une autre énumération possible est $h (j, \sigma) = 2 * j + \sigma $.
La bibliothèque de chimie quantique peut utiliser ces conventions, et les orbites dans ce type d’encodage peuvent être instanciées comme suit.

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

Pour les systèmes fermionic, le principe d’exclusion Pauli empêche la présence de plusieurs électrons dans n’importe quel spin-orbital en même temps.
Cela signifie que nous pouvons écrire les deux États légaux pour $ \ psi_1 $ As \begin{Equation} \ psi_1 \rightarrow \begin{cases} \ket{0}_ 1 & \text{if $ \ psi_1 $ n’est pas occupé,} \\\
\ket{1}_ 1 & \text{if $ \ psi_1 $ est occupé.} \end{cases} \end{Equation} cet encodage est parfait pour les ordinateurs Quantum, car cela signifie que nous pouvons stocker l’occupation électronique comme un bit Quantum unique.

Les États de la profession pour les orbites de type « $ 2N $ » peuvent être stockés de la même façon dans $2N $ qubits.
Par exemple, si $N = $2, alors l’État $ $ \ket{0} \ket{1} \ket{1} \ket{0}, $ $

correspondrait aux orbites de rotation $1 $ et $2 $ en cours d’emploi avec le reste vide.
De même, l’État $ $ \ket{0} \equiv \ket{0} _{0} \cdots \ket{0}_ {N-1}, $ $

n’a aucun électron et est appelé « état de dépression ».

L’un des effets secondaires de la seconde quantification est que nous n’avons plus besoin de suivre explicitement l’anti-symétrie de l’État Quantum.
Cela est dû au fait que, comme nous le verrons, l’anti-symétrie de l’état représente lui-même à l’aide des règles anti-commutant des opérateurs qui créent et détruisent les occupations électroniques d’un spin orbital.

## <a name="fermionic-operators"></a>Fermionic, opérateurs

Les deux opérateurs fondamentaux qui agissent sur les vecteurs de base de deuxième quantification sont appelés opérateurs de création et de annihilation.
Ces opérateurs insèrent ou détruisent des électrons à un emplacement particulier.
Celles-ci sont dénotées $a ^ \ dagger_j $ et $a _j $ respectivement.

Par exemple, \begin{align} a ^ \ dagger_1 \ket{0}_ 1 = \ket{1}_ 1, \quad a ^ \ dagger_1 \ket{1}_ 1 = 0, \quad a_1 \ket{0}_ 1 = 0, \quad a_1 \ket{1}_ 1 = \ket{0}_ 1.
\end{align} Notez que $a ^ \ dagger_1 \ket{1}_ 1 = 0 $ et $a _ 1 \ket{0}_ 1 $ génère le vecteur zéro non $ \ket{0}_ 1 $.
Par conséquent, ces opérateurs ne sont ni Hermitian ni Unity.
Nous représentons les opérateurs de création générale et annihilation à l’aide du type de <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1>.
Par exemple, un opérateur de création unique est représenté comme suit.

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

En outre, l’utilisation de ces opérateurs nous permet d’exprimer $ $ \ket{0} \ket{1} \ket{1} \ket{0} = a ^ \ dagger_1 a ^ \ dagger_2 \ket{0}^ {\otimes 4}.
$ $ Cette séquence d’opérateurs serait construite au sein de la bibliothèque de simulation de C# Hamilton à l’aide d’un code similaire au cas orbital à simple vrille considéré ci-dessus :
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

Pour un système de $k $ fermions, dans la seconde quantification, l’action de l’opérateur de création $a ^ \ dagger_i $ est donnée par $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_i , \ldots, n_k}, $ $ et $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k} = 0, $ $ où $S _i = \ sum_ {j < i} a ^ \ dagger_j a_j $ mesure le nombre total de fermions qui sont dans l’état d’une seule particule et qui ont un index $j < i $.

Un troisième opérateur est également souvent utilisé dans les deux représentations quantifiées.
Cet opérateur est appelé opérateur de nombre et est défini par \begin{Equation} n_i = a ^ \ dagger_i a_i.
\end{Equation} cet opérateur compte l’occupation d’un spin orbital donné, c’est-à-dire \begin{align} n_i \ket{0}_i & = 0 \ nonumber\\\
n_i \ket{1}_i & = \ket{1}_i.
\end{align} similaire aux exemples ci-dessus `FermionTerm`, cet opérateur de nombre est construit comme suit.
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

Une subtilité émerge cependant lors de l’utilisation d’opérateurs de création ou de annihilation dans les systèmes fermionic.
Nous exigeons que tout état Quantum valide soit anti-symétrique dans le cadre de l’échange d’étiquettes.
Cela signifie que $ $ a ^ \ dagger_2 un ^ \ dagger_1 \ket{0} =-a ^ \ dagger_1 a ^ \ dagger_2 \ket{0}.
Les opérateurs $ $ sont dits « anti-muet » et, en général, pour tout $i, j $ nous avons \begin{align} a ^ \ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) ^ \ dagger_j a ^ \ dagger_i, \quad a ^ \ dagger_i a_j = \ delta_ {i, j}-a_j a ^ \ dagger_i.
\end{align} donc les deux instances de <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> suivantes sont considérées comme inéquivalentes
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

L’exigence que chacun des opérateurs de création anti-piratage signifie que l’utilisation d’une seconde représentation quantifiée permet d’éviter les défis liés à l’anti-symétrie de fermions.
Au lieu de cela, le défi émerge à nouveau dans la définition des opérateurs de création. 

À l’aide des règles anti-commutation, certaines instances de `LadderSequence` correspondent en fait à la même séquence d’opérateurs fermionic, parfois jusqu’à un signe moins.
Par exemple, considérez la $a de la _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 $.
Cela nous incite à définir un classement canonique pour chaque `FermionTerm`.
Tout `FermionTerm` est automatiquement placé dans l’ordre canonique comme suit.
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a>Deuxième Fermionic Hamilton

Il est peut-être trop surprenant que les [modèles quantiques pour les systèmes électroniques](xref:microsoft.quantum.chemistry.concepts.quantummodels) puissent être écrits en termes de création et d’opérateurs de annihilation.
En particulier, si $ \Psi\_j $ sont les orbites de spin qui forment la base,

\begin{Equation} \hat{H} = \sum\_{PQ} H\_{PQ} a ^ \dagger\_p a\_q + \frac{1}{2}\sum\_{PQRS} H\_{PQRS} a ^ \dagger\_p a ^ \dagger\_q a\_RA\_s + H\_{\textrm NUC}, \label{EQ : totalHam} \end{Equation} où $h\_{\textrm NUC} $ est l’énergie nucléaire (qui est une constante sous la approximation Oppenheimer) et

\begin{align} h\_{PQ} & = \int\_{-\infty} ^ \infty \Psi ^\*\_p (x\_1) \left (-\frac{\nabla ^ 2}{2} + V (x\_1) \right) \Psi\_q (x\_1) \mathrm{d} ^ 3x\_1, \end{align}

où $V (x) $ est le potentiel du champ de moyenne, et

\begin{align} h\_{PQRS} & = \int\_{-\infty} ^ \infty \int\_{-\infty} ^ \infty\psi\_p ^\*(x\_1) \Psi\_q ^\*(x\_2) \left (\frac{1}{| x_1-x_2 |} \right) \Psi\_r (x\_2) \Psi\_s (x\_1) \mathrm{d} ^ 3x\_1 \ mathrm {d} ^ 3x\_2. \ étiquette {EQ : intégrales} \end{align}

Les termes $h\_{PQ} $ sont appelés intégrales à un seul électron, car tous ces termes impliquent uniquement des électrons uniques et, de même $h\_{PQRS} $ sont les intégrales à deux électrons.
Ils sont appelés des intégraux, car le calcul des valeurs de ces coefficients requiert un intégral.
Les termes d’un électron décrivent l’énergie cinétique des électrons individuels et leurs interactions avec les champs électriques du noyau.
Les deux intégrales d’électrons, quant à eux, décrivent les interactions entre les électrons.

Une intuition pour ce que ces termes signifie peuvent être collectées à partir des opérateurs de création et de annihilation qui composent chacun d’eux.
Par exemple, $h _ {PQ} a ^ \ dagger_p a_q $ décrit les sauts d’électrons de spin orbital $q $ à spin orbital $p $.
De même, le terme $h _ {PQRS} a ^ \ dagger_p un ^ \ dagger_q a_r a_s $ (pour distinct $p, q, r, s $) décrit deux électrons dans des orbites de spins $r $ et $s $ Dispersing et se terminant par des orbites de rotation $p $ et $q $.
Si $r = q $ et $p = s $ Then $h _ {PRRP} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {PRRP} n_p n_r $ donne la pénalité d’énergie associée aux deux électrons proches les uns des autres, mais ne décrit pas un processus dynamique.

Nous pouvons représenter ces Hamiltonians à l’aide de la classe `FermionHamiltonian`, qui est essentiellement une liste contenant toutes les instances de `FermionTerm` souhaitées.
Comme les Hamiltonians sont Hermitian par définition, nous indexons les termes à l’aide du type `HermitianFermionTerm` plus spécialisé qui utilise également la symétrie Hermitian pour vérifier si les termes sont équivalents.

Créons quelques exemples illustrant cet exemple.
Considérez le \hat{H} de Hamilton $ = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $.
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
Nous pouvons simplifier cette construction en utilisant les opérateurs de Hermitian.
Lors de l’ajout de termes à la `Add`à l’aide de, tout terme non Hermitian comme `fermionTerm0` est supposé être associé à son conjugué Hermitian.
Ainsi, l’extrait de code suivant représente également le même Hamilton :
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

À l’aide des règles de protection contre la permutation, certaines instances de `FermionTerm` dans le sein de la Hamilton correspondent en fait à la même séquence d’opérateurs fermionic, parfois jusqu’à un signe moins.
Par exemple, considérez le $H Hamiltony = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $, qui est une somme des termes construits ci-dessus.
Il n’est pas toujours évident pour l’utilisateur qu’il s’agit de termes équivalents, et par conséquent, ils peuvent être ajoutés séparément à la Hamilton.
Vous pouvez également être intéressé par la modification de termes déjà existants dans le même lieu.
Dans ces cas-là, nous pouvons combiner les termes équivalents comme suit.
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
En associant des coefficients de termes équivalents, nous réduisons le nombre total de termes dans le même niveau de Hamilton.
Plus tard, cela réduit le nombre de portes de Quantum nécessaires pour simuler le niveau de la Hamilton.

### <a name="internal-representation"></a>Représentation interne

Un fermionic Hamilton avec des interactions d’un et de deux corps est représenté par une seconde notation quantifiée comme

$ $ \begin{align} H = \sum\_{PQ} H\_{PQ} a ^ \dagger\_{p} a\_{q} + \frac{1}{2}\sum\_{PQRS} H\_{PQRS} a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s}.
\end{align} $ $

Dans cette notation, il existe au maximum $N ^ 2 + N ^ 4 $ coefficients.
Toutefois, un grand nombre de ces coefficients peuvent être collectés, car ils correspondent au même opérateur.
Par exemple, dans le cas où $p, q, r, s $ sont des index distincts, nous pouvons utiliser les règles anti-commutation pour indiquer que : $ $ a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} =-a ^ \dagger\_{q} a ^ \dagger\_{p} a\_{r} a\_{s} =-a ^ \dagger\_{p} ^ \dagger\_{q} a\_{s} a\_{r} = a ^ \dagger\_{q} a ^ \dagger\_{p} a\_{s} a\_{r}.
$$

En outre, comme $H $ est Hermitian, chaque opérateur fermionic non-Hermitian, par exemple $h\_{PQRS} a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} $, a un conjugué Hermitian qui se trouve également dans $H $. Afin d’indexer de manière unique des groupes de termes caractérisés par ces Symmetries, nous définissons un classement canonique sur les index $ (i\_1, \cdots, i\_n, j\_1, \cdots, j\_m) $ de toute séquence d’opérateurs $n + m $ fermionic $a ^ \dagger\_{i\_1} \cdots a ^ \dagger\_{i\_n} a\_{j\_1} \cdots a\_{j\_m} $as suit :
-   Tous les opérateurs de création $a ^ \dagger\_{i\_\cdot} $ sont placés avant que tous les opérateurs annihilation $a\_{j\_\cdot} $.
-   Tous les index d’opérateur de création sont triés par ordre croissant, c’est-à-dire $i\_1 < i\_2 < \cdots < i\_n $.
-   Tous les index d’opérateur annihilation sont triés par ordre décroissant, c’est-à-dire $j\_1 > j\_2 \cdots > j\_m $.
-   L’index le plus à gauche est inférieur ou égal à l’index le plus à droite, c’est-à-dire $i\_1 \ le j\_m $.

Nous allons identifier cet ensemble d’index ordonnés de manière canonique comme $ $ \begin{align} (i\_1, \cdots, i\_n, j\_1, \cdots, j\_m) \Dans S\_{n, m}.
\end{align} $ $

Avec ce classement canonique, le fermionic Hamilton peut être exprimé sous la forme $ $ \begin{align} H = \sum\_{(p, q) \Dans S\_{1,1}} H'\_{PQ} \frac{a ^ \dagger\_{p} a\_{q} + a ^ \dagger\_{q} a\_{p}}{2}+ \sum\_{(p, q, r, S) \Dans S\_{2,2}} H'\_{PQRS} \frac{a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{S} + a ^ \dagger\_{S} a ^ \ poignard\_{r} a\_{q} a\_{p}}{2}, \end{align} $ $ avec adaptation appropriée des intégrales One-and-électron $h'\_{PQ} $ and $h'\_{PQRS} $, respectivement.

