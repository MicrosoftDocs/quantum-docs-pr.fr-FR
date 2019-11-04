---
title: 'Q # bibliothèques standard-contrôle et Flow | Microsoft Docs'
description: 'Q # bibliothèques standard-contrôle et Flow'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5e865dbb48029724b6f507ecb63b85d10d80c9a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185645"
---
# <a name="higher-order-control-flow"></a>Contrôle de l’ordre supérieur #

L’un des principaux rôles de la bibliothèque standard est de faciliter l’expression d’idées algorithmiques de haut niveau en tant que [programmes quantiques](https://en.wikipedia.org/wiki/Quantum_programming).
Par conséquent, la commande Q # Canon fournit une variété de constructions de contrôle de Flow, chacune implémentée à l’aide d’une application partielle de fonctions et d’opérations.
Si vous sautez immédiatement dans un exemple, considérez le cas dans lequel vous souhaitez construire une « échelle CNOTIN » sur un registre :

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

Nous pouvons exprimer ce modèle à l’aide de boucles d’itération et de `for` :

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

En termes de <xref:microsoft.quantum.canon.applytoeachca> et de fonctions de manipulation de tableau comme <xref:microsoft.quantum.arrays.zip>, toutefois, cette opération est beaucoup plus rapide et plus facile à lire :

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

Dans le reste de cette section, nous vous fournirons un certain nombre d’exemples d’utilisation des diverses opérations et fonctions de contrôle de workflow fournies par Canon pour exprimer les programmes Quantum de manière compacte.

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>Application d’opérations et de fonctions sur des tableaux et des plages ##

L’une des abstractions principales fournies par Canon est celle de l’itération.
Par exemple, considérez une unité de la forme $U \otimes U \otimes \cdots \otimes U $ pour une $U unitaire $.
Dans Q #, nous pouvons utiliser <xref:microsoft.quantum.arrays.indexrange> pour représenter cela comme une boucle `for` sur un registre :

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation HAll(register : Qubit[]) : Unit 
is Adj + Ctl {

    for (qubit in register) {
        H(qubit);
    }
}
```

Nous pouvons ensuite utiliser cette nouvelle opération comme `HAll(register)` pour appliquer $H \otimes H \otimes \cdots \otimes H $.

Cette opération est lourde, cependant, en particulier dans un algorithme plus grand.
En outre, cette approche est spécialisée pour l’opération particulière que nous souhaitons appliquer à chaque qubit.
Nous pouvons utiliser le fait que les opérations sont de première classe pour exprimer ce concept algorithmique plus explicitement :

```qsharp
ApplyToEachCA(H, register);
```

Ici, le suffixe `CA` indique que l’appel à `ApplyToEach` est lui-même adjointable et contrôlable.
Par conséquent, si `U` prend en charge `Adjoint` et `Controlled`, les lignes suivantes sont équivalentes :

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

En particulier, cela signifie que les appels à `ApplyToEachCA` peuvent apparaître dans les opérations pour lesquelles une spécialisation voisine est générée automatiquement.
De même, <xref:microsoft.quantum.canon.applytoeachindex> est utile pour représenter les modèles de la `U(0, targets[0]); U(1, targets[1]); ...`de formulaire et offre des versions pour chaque combinaison d’functors prise en charge par son entrée.

> [!TIP]
> `ApplyToEach` est paramétrée par type de sorte qu’elle puisse être utilisée avec des opérations qui prennent des entrées autres que `Qubit`.
> Par exemple, supposons que `codeBlocks` est un tableau de valeurs <xref:microsoft.quantum.errorcorrection.logicalregister> qui doivent être récupérées.
> Ensuite `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` appliquera le code de correction des erreurs `code` et la fonction de récupération `recoveryFn` à chaque bloc indépendamment.
> Cela est également valable pour les entrées classiques : `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` appliquera une rotation de $ \pi/$2 sur $X $ suivie d’une rotation de $pi/$3 à propos de $Y $.

Le moteur Q # Canon fournit également la prise en charge des modèles d’énumération classiques familiers à la programmation fonctionnelle.
Par exemple, <xref:microsoft.quantum.arrays.fold> implémente le modèle $f (f (f (s\_{\text{initial}}, x\_0), x\_1), \dots) $ pour réduire une fonction sur une liste.
Ce modèle peut être utilisé pour implémenter des sommes, des produits, des minima, des maxima et d’autres fonctions de ce type :

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

De même, les fonctions comme <xref:microsoft.quantum.arrays.mapped> et <xref:microsoft.quantum.arrays.mappedbyindex> peuvent être utilisées pour exprimer les concepts de programmation fonctionnelle dans Q #.

## <a name="composing-operations-and-functions"></a>Composer des opérations et des fonctions ##

Les constructions de workflow de contrôle offertes par Canon prennent les opérations et fonctionnent comme entrées, de sorte qu’il est utile de pouvoir composer plusieurs opérations ou fonctions en un seul appelable.
Par exemple, le modèle $UVU ^ {\dagger} $ est extrêmement courant dans la programmation quantique, de sorte que Canon fournit l’opération <xref:microsoft.quantum.canon.applywith> comme une abstraction pour ce modèle.
Cette abstraction permet également une meilleure conformité dans les circuits, comme `Controlled` agissant sur la séquence `U(qubit); V(qubit); Adjoint U(qubit);` n’a pas besoin d’agir sur chaque `U`.
Pour le voir, $c (U) $ est l’unité qui représente `Controlled U([control], target)` et Let $c (V) $ doit être définie de la même façon.
Ensuite, pour un état arbitraire $ \ket{\Psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{1} \otimes \ket{\Psi} & = \ket{1} \otimes (UVU ^ {\dagger} \ket{\Psi}) \\\\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ Ket{1} \otimes \ket{\Psi}.
\end{align} par la définition de `Controlled`.
En revanche, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{0} \otimes \ket{\Psi} & = \ket{0} \otimes \ket{\Psi} \\\\ & = \ket{0} \otimes (UU ^ \dagger \ket{\Psi}) \\\\ & = (\boldone \otimes U) (c ( V)) (\boldone \otimes U ^ \dagger) \ket{0} \otimes \ket{\Psi}.
\end{align} par linéarité, nous pouvons conclure que nous pouvons factoriser $U $ Out de cette manière pour tous les États d’entrée.
Autrement dit, $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.
Étant donné que les opérations de contrôle peuvent être coûteuses en général, l’utilisation de variantes contrôlées telles que `WithC` et `WithCA` peut aider à réduire le nombre d’functors de contrôle qui doivent être appliqués.

> [!NOTE]
> Une autre conséquence de la factorisation $U $ est que nous n’avons même pas besoin de savoir comment appliquer le `Controlled` functor à `U`.
> `ApplyWithCA` a donc une signature plus faible que celle qui est attendue :
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

De même, <xref:microsoft.quantum.canon.bind> produit des opérations qui appliquent successivement une séquence d’autres opérations.
Par exemple, les éléments suivants sont équivalents :

```qsharp
H(qubit); X(qubit);
Bind([H, X], qubit);
```

La combinaison avec les modèles d’itération peut s’avérer particulièrement utile :

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bind([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>Composition chronologique ###

Nous pouvons continuer en pensant au contrôle de Flow en termes d’application partielle et de fonctions classiques, et peuvent modéliser des concepts de Quantum encore plus sophistiqués en termes de contrôle de la fluidité classique.
Cette analogie est rendue précise par la reconnaissance selon laquelle les opérateurs d’unités correspondent exactement aux effets secondaires des opérations d’appel, de telle sorte que toute décomposition des opérateurs unitaires en termes d’autres opérateurs unitaires corresponde à la construction d’un séquence d’appel pour les sous-routines classiques qui émettent des instructions pour agir en tant qu’opérateurs unitaires particuliers.
Dans cette vue, `Bind` est précisément la représentation du produit de la matrice, car `Bind([A, B])(target)` équivaut à `A(target); B(target);`, qui à son tour correspond à la séquence d’appel correspondant à $BA $.

Un exemple plus sophistiqué est l' [expansion Trotter – Suzuki](https://arxiv.org/abs/math-ph/0506007v1).
Comme indiqué dans la section relative à la représentation du générateur dynamique des [structures de données](xref:microsoft.quantum.libraries.data-structures), l’expansion Trotter – Suzuki offre un moyen particulièrement utile d’exprimer des exponentiels de matrice.
Par exemple, l’application de l’expansion à son ordre le plus bas donne à tous les opérateurs $A $ et $B $ de telle sorte que $A = A ^ \dagger $ et $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ : Trotter-Suzuki-0} \exp (i [A + B] t) = \lim_{n\to\infty} \left (\exp (i A t/n) \exp ) \right) ^ n.
\end{align} en commun, cela signifie que nous pouvons approximativement faire évoluer un État sous $A + B $ en évoluant alternativement sous $A $ et $B $ seul.
Si nous représentons l’évolution sous $A $ par une opération `A : (Double, Qubit[]) => Unit` qui applique $e ^ {t A} $, la représentation de l’expansion Trotter – Suzuki en termes de réorganisation des séquences d’appel devient évidente.
Concrètement, étant donné une opération `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` telle que `A = U(0, _, _)` et `B = U(1, _, _)`, nous pouvons définir une nouvelle opération représentant l’intégrale de `U` à l’heure $t $ en générant des séquences de la forme

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

À ce stade, nous pouvons maintenant expliquer l’expansion Trotter – Suzuki *sans référence à la mécanique des quantums*.
L’expansion est effectivement un modèle d’itération très particulier motivé par $ \eqref{EQ : Trotter-Suzuki-0} $.
Ce modèle d’itération est implémenté par <xref:microsoft.quantum.canon.decomposeintotimestepsca>:

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

La signature de `DecomposeIntoTimeStepsCA` suit un modèle courant dans Q #, où les collections qui peuvent être sauvegardées par tableau ou par un élément qui calcule des éléments à la volée sont représentées par des tuples dont les premiers éléments sont `Int` des valeurs indiquant leurs longueurs.

## <a name="putting-it-together-controlling-operations"></a>Ensemble : contrôle des opérations ##

Enfin, Canon s’appuie sur l' `Controlled` functor en fournissant des méthodes supplémentaires pour conditionner les opérations de Quantum.
Il est courant, surtout dans le cas de l’arithmétique quantique, de conditionner les opérations sur les États de base de calcul autres que $ \ket{0\cdots 0} $.
À l’aide des opérations de contrôle et des fonctions présentées ci-dessus, nous pouvons obtenir des conditions de Quantum plus générales dans une instruction unique.
Passons à la façon dont <xref:microsoft.quantum.canon.controlledonbitstring> le fait (paramètres de type sans paramètre), puis nous décomposons les éléments un par un.
La première chose à faire est de définir une opération qui fait réellement le gros du levage de l’implémentation du contrôle sur des États de base de calcul arbitraires.
Nous n’appellerons pas cette opération directement, mais nous ajoutons donc `_` au début du nom pour indiquer qu’il s’agit d’une implémentation d’une autre construction ailleurs.

```qsharp
operation _ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl),
        controlRegister : Qubit[],
        targetRegister: Qubit[]) 
: Unit 
is Adj + Ctl {
```

Notez que nous prenons une chaîne de bits, représentée sous la forme d’un tableau de `Bool`, que nous utilisons pour spécifier le conditionnement que nous souhaitons appliquer à l’opération `oracle` que nous avons donnée.
Dans la mesure où cette opération fait directement l’application, nous devons également prendre les registres de contrôle et cibles, représentés ici comme `Qubit[]`.

Ensuite, nous constatons que le contrôle de l’état de la base de calcul $ \ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n-1}} $ pour une chaîne de bits $ \vec{s} $ peut être réalisé en transformant $ \ket{\vec{s}} $ en $ \ket{0\cdots 0} $.
En particulier, $ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $.
Depuis $X ^ {\dagger} = X $, cela implique que $ \ket{0\dots 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $.
Par conséquent, nous pouvons appliquer $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} $, appliquer `Controlled oracle`et transformer en $ \vec{s} $.
Cette construction est `ApplyWith`précisément. nous écrivons donc le corps de notre nouvelle opération en conséquence :

```qsharp
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

Ici, nous avons utilisé <xref:microsoft.quantum.canon.applypaulifrombitstring> pour appliquer $P $, partiellement appliqué sur sa cible pour une utilisation avec `ApplyWith`.
Notez, toutefois, que nous avons besoin de transformer le registre de *contrôle* au format souhaité. nous appliquons donc partiellement l’opération interne `(Controlled oracle)` sur la *cible*.
Cela laisse `ApplyWith` agir pour délimiter le registre de contrôle avec $P $, exactement comme nous l’avons souhaité.

À ce stade, nous avons pu le faire, mais cela ne suffit pas à ce que notre nouvelle opération ne semble pas « s’intéresser » à l’application du `Controlled` functor.
Par conséquent, nous avons fini de définir notre nouveau concept de workflow en écrivant une fonction qui prend le contrôle Oracle et qui retourne une nouvelle opération.
De cette façon, notre nouvelle fonction ressemble beaucoup à `Controlled`, illustrant que nous pouvons facilement définir de nouvelles constructions puissantes de contrôle de contrôle en utilisant Q # et Canon ensemble :

```qsharp
function ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl)) 
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
