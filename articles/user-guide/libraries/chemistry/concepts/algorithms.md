---
title: Simulation de Dynamics Hamilton
description: Découvrez comment utiliser des formules Trotter-Suzuki et qubitization pour travailler avec des simulations de Hamilton.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: 40f79a66ae95e20a8b1c19af735eedca5e3c15ef
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869526"
---
# <a name="simulating-hamiltonian-dynamics"></a>Simulation de Dynamics Hamilton

Une fois que le nom de la base de l’environnement Hamilton a été exprimé sous la forme d’une somme d’opérateurs élémentaires, la dynamique peut ensuite être compilée en opérations de porte fondamentale à l’aide d’un hôte de techniques bien connues.
Trois approches efficaces sont les suivantes : Trotter – Suzuki Formulas, Linear combinaisons of Units and qubitization.
Nous expliquons ces trois approches ci-dessous et fournissons Q# des exemples concrets montrant comment implémenter ces méthodes à l’aide de la bibliothèque de simulation de la Hamilton.


## <a name="trottersuzuki-formulas"></a>Trotter – formules Suzuki
L’idée sous-jacente des formules Trotter – Suzuki est simple : Exprimez le sous-plan Hamilton comme une somme de Hamiltonians faciles à simuler, puis rapprochez l’évolution totale sous la forme d’une séquence de ces évolutions plus simples.
En particulier, laissez $H = \ sum_ {j = 1} ^ m H_j $ est le lieu de la Hamilton.
Puis, $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, ce qui signifie que, si $t \ll $1, l’erreur de cette approximation devient négligeable.
Notez que si $e ^ {-i H t} $ étaient une valeur exponentielle ordinaire, l’erreur de cette approximation ne serait pas $O (m ^ 2 t ^ 2) $ : il s’agit de zéro.
Cette erreur se produit car $e ^ {-iHt} $ est un opérateur exponentiel et, par conséquent, une erreur est survenue lors de l’utilisation de cette formule en raison du fait que les $H _j $ Terms ne sont pas inactives (par*exemple*, $H _J H_k \ne H_k H_j $ en général).

Si $t $ est large, les formules Trotter – Suzuki peuvent toujours être utilisées pour simuler la dynamique avec précision en la fractionnant en une séquence d’étapes courtes.
$R $ étant le nombre d’étapes effectuées dans l’évolution du temps, chaque étape s’exécute pendant l’heure $t/r $. Ensuite, nous avons le signe $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ Right) ^ r + O (m ^ 2 t ^ 2/r), $ $, ce qui signifie que si $r $ se met à l’échelle comme $m ^ 2 t ^ 2/\ Epsilon $, l’erreur peut être effectuée au plus de $ \epsilon $ pour n’importe quel $ \epsilon>$0.

Des approximations plus précises peuvent être générées en construisant une séquence de exponentiels d’opérateur de façon à ce que les termes d’erreur s’annulent.
La plus simple, la formule suivante, la formule Trotter-Suzuki, prend la forme $ $ U_2 (t) = \left (\ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2R} \ prod_ {j = m} ^ 1 e ^ {-iH_j t/2R} \ Right) ^ r = e ^ {-iHt} + O (m ^ 3 t ^ 3/r ^ 2), $ $ l’erreur de qui peut être effectuée moins de $ \epsilon $ pour un $ \epsilon>$0 en choisissant $r $ pour mettre à l’échelle le $m ^ {3/2} t ^ {3/2}/\sqrt {\ Epsilon} $.

Même les formules dont l’ordre est plus élevé, en particulier ($ 2k $) th-ordre pour $k>$0, peut être construite de manière récursive : $ $ U_ {2k} (t) = [U_ {2KO-2} (s_k \~ t)] ^ 2 U_ {2k-2} ([1-4s_k] t) [U_ {2k-2} (S_k \~ t)] ^ 2 = e ^ {-iHt} + O ((m t) ^ {2k + 1}/r ^ {2k}), $ $ où $s _K = (4-4 ^ {1/(2k-1)}) ^ {-1} $.

La plus simple est la formule suivante ($k = $2), introduite à l’origine par Suzuki : $ $ U_4 (t) = [U_2 (s_2 \~ t)] ^ 2 U_2 ([1-4s_2] t) [U_2 (s_2 \~ t)] ^ 2 = e ^ {-iHt} + O (m ^ 5t ^ 5/r ^ 4), $ $ where $s _2 = (4-4 ^ {1/3}) ^ {-1} $.
En général, les formules de poids fort arbitraires peuvent être construites de la même façon ; Toutefois, les coûts engendrés par l’utilisation d’intégrateurs plus complexes compensent souvent les avantages supérieurs au quatrième ordre pour les problèmes les plus pratiques.

Pour que les stratégies ci-dessus fonctionnent, nous avons besoin d’une méthode pour simuler une classe étendue de $e ^ {-iH_j t} $.
La famille de Hamiltonians la plus simple, et sans doute la plus utile, que nous pourrions utiliser ici sont les opérateurs Pauli.
Les opérateurs Pauli peuvent être facilement simulés, car ils peuvent être diagonés à l’aide d’opérations Clifford (qui sont des portes standard dans Quantum Computing).
De plus, une fois qu’ils ont été mis en diagonale, leur valeurs propres peut être trouvé en calculant la parité du qubits sur lequel ils agissent.

Par exemple, $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ où $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0\\\
        0 & e ^ {i t} & 0 & 0\\\
        0 & 0 & e ^ {IT} & 0\\\
        0 & 0 & 0 & e ^ {-IT} \end{bmatrix}.
$ $ Here, $e ^ {-iHt} \ket {00} = e ^ {IT} \ket {00} $ et $e ^ {-iHt} \ket {01} = e ^ {-IT} \ket {01} $, qui peuvent être consultées directement à la suite du fait que la parité de $0 $ est $0 $, tandis que la parité de la chaîne de bits $1 $ est $1 $.

Les exponentiels des opérateurs Pauli peuvent être implémentés directement dans Q# à l’aide de l' <xref:microsoft.quantum.intrinsic.exp> opération :
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

Pour Fermionic Hamiltonians, la [décomposition de Jordanie – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) mappe facilement le sein de la Communauté au sein d’une somme d’opérateurs Pauli.
Cela signifie que l’approche ci-dessus peut facilement être adaptée pour simuler la chimie.
Au lieu de boucler manuellement sur tous les termes de Pauli dans la représentation Jordanie-Wigner, vous trouverez ci-dessous un exemple simple de la façon dont l’exécution d’une telle simulation dans la chimie.
Notre point de départ est un [encodage de Jordanie – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) du Fermionic Hamilton, exprimé en code en tant qu’instance de la `JordanWignerEncoding` classe.

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

Ce format de la représentation Jordanie – Wigner qui est consommable par les Q# algorithmes de simulation est un type défini par l’utilisateur `JordanWignerEncodingData` .
Au sein de Q# , ce format est passé à une fonction pratique `TrotterStepOracle` qui retourne un opérateur d’évolution du temps à l’aide de l’intégrateur Trotter — Suzuki, en plus des autres paramètres requis pour son exécution.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

Important, cette implémentation applique des optimisations décrites dans la [simulation de la structure électronique Hamiltonians à l’aide d’ordinateurs Quantum et l'](https://arxiv.org/abs/1001.3855) [amélioration des algorithmes quantiques pour la chimie quantique](https://arxiv.org/abs/1403.1539) afin de réduire le nombre de rotations à qubit unique requis, ainsi que de réduire les erreurs de simulation.

## <a name="qubitization"></a>Qubitization

Qubitization est une autre approche de la simulation qui utilise des idées de parcours quantiques pour simuler la dynamique quantique.
Bien que qubitization requière plus de qubits de formules Trotter, la méthode promet une mise à l’échelle optimale avec l’heure d’évolution et la tolérance d’erreur.
Pour ces raisons, il s’agit d’une méthode privilégiée pour simuler la dynamique de la Hamilton en général et pour résoudre le problème de structure électronique en particulier.

À un niveau élevé, qubitization effectue les étapes suivantes.
Tout d’abord, laissez $H = \ sum_j h_j H_j $ pour Unity et Hermitian $H _J $ et $h _j \ge $0.
En exécutant une paire de réflexions, qubitization implémente un opérateur qui est équivalent à $ $W = e ^ {\pm i \cos ^ {-1} (h/| H | _ 1)}, $ $ where $ | H | _ 1 = \ sum_j | h_j | $.
L’étape suivante consiste à transformer le valeurs propres de l’opérateur de parcours de $e ^ {i\pm \cos ^ {-1} (E_k/| h | _ 1)} $, où $E _K $ est le valeurs propres de $H $ à $e ^ {-iE_k t} $.
Pour ce faire, vous pouvez utiliser une variété de méthodes de transformation de valeur singulière Quantum, notamment le [traitement des signaux quantiques](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).

En guise d’alternative, si seules des quantités statiques sont souhaitées (par exemple, l’énergie de l’état du sol de la région Hamilton), il suffit d’appliquer l' [estimation de phase](xref:microsoft.quantum.libraries.characterization) directement à $W $ pour estimer l’énergie de l’état du sol en utilisant le cosinus du résultat.
Cela est important, car elle permet à la transformation spectrale d’être exécutée de manière classique plutôt que d’utiliser une méthode de transformation de valeur singulière quantique.

À un niveau plus détaillé, l’implémentation de qubitization nécessite deux sous-routines qui fournissent les interfaces pour le niveau de la Hamilton.
Contrairement aux méthodes Trotter – Suzuki, ces sous-routines sont Quantum not Classic et leur implémentation nécessite l’utilisation d’un plus grand nombre de qubits que nécessaire pour une simulation basée sur trotter.

La première sous-routine Quantum utilisée par qubitization est appelée $ \operatorname{Select} $ et elle est prévue pour produire \begin{Equation} \operatorname{Select} \ket{j} \ket{\Psi} = \ket{j} H_j \ket{\Psi}, \end{Equation} où chaque $H _j $ est supposé être Hermitian et unitaire.
Bien que cela puisse paraître restrictif, rappelez-vous que les opérateurs Pauli sont Hermitian et unitaires, de sorte que les applications telles que la simulation de la chimie quantique tombent naturellement dans cette infrastructure.
L’opération $ \operatorname{Select} $, peut-être étonnamment, est en fait une opération de réflexion.
Cela peut être vu par le fait que $ \operatorname{Select} ^ 2 \ Ket {j} \ket{\Psi} = \ket{j} \ket{\Psi} $ étant donné que chaque $H _j $ est unitaire et Hermitian et a donc valeurs propres $ \pm $1.

La deuxième sous-routine est appelée $ \operatorname{Prepare} $.
Tandis que l’opération Select fournit un moyen d’accéder de manière cohérente aux termes de la $H _j $ la sous-routine prepare donne une méthode pour accéder aux coefficients $h _j $, \begin{Equation} \operatorname{Prepare}\ket {0} = \ sum_j \sqrt{\frac{h_j} {| H | _ 1}} \ket{j}.
\end{Equation} ensuite, en utilisant une porte de phase contrôlée par multiplication, nous voyons que $ $ \Lambda\ket {0} ^ {\otimes n} = \begin{cases} \- \ket{x} & \text{If} x = 0\\\
        \ket{x} & \text{otherwise} \end{cases}.
$$

L’opération $ \operatorname{prepare} $ n’est pas utilisée directement dans qubitization, mais elle est utilisée pour implémenter une réflexion sur l’État dans lequel $ \operatorname{prepare} $ crée $ $ \begin{align} R &amp; = 1-2 \ operatorName {prepare} \ket {0} \bra {0} \operatorname{prepare} ^ {-1} \\ \\ &amp; = \operatorname{prepare} \Lambda \operatorname{prepare} ^ {-1} .
\end{align} $ $

L’opérateur de parcours, $W $, peut être exprimé en termes des opérations $ \operatorname{Select} $ et $R $ en tant que $ $ W = \operatorname{Select} R, $ $ qui peut encore être vu pour implémenter un opérateur équivalent (jusqu’à une isométrie) à $e ^ {\pm i \cos ^ {-1} (h/| h | _ 1)} $.

Ces sous-routines sont faciles à configurer dans Q# .
À titre d’exemple, considérez le simple qubit transversal-Ising Hamilton où $H = X_1 + X_2 + Z_1 Z_2 $.
Dans ce cas, le Q# code qui implémenterait l’opération $ \operatorname{Select} $ est appelé par <xref:microsoft.quantum.canon.multiplexoperations> , tandis que l’opération $ \operatorname{prepare} $ peut être implémentée à l’aide de <xref:microsoft.quantum.preparation.preparearbitrarystate> .
Vous trouverez un exemple qui implique de simuler le modèle Hubbard en tant qu' [ Q# exemple](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).

La spécification manuelle de ces étapes pour les problèmes de chimie arbitraire nécessiterait un effort considérable, ce qui est évité à l’aide de la bibliothèque chimie.
À l’instar de l’algorithme de simulation Trotter – Suzuki ci-dessus, `JordanWignerEncodingData` est passé à la fonction pratique `QubitizationOracle` qui retourne l’opérateur de parcours, en plus des autres paramètres requis pour son exécution.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

Important, l’implémentation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> s’applique aux Hamiltonians arbitraires spécifiés comme une combinaison linéaire de chaînes Pauli.
Une version optimisée pour les simulations de chimie est appelée à l’aide de <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle> .
Cette version est optimisée pour réduire le nombre de grilles T à l’aide de techniques décrites dans [encodage des spectres électroniques dans des circuits quantiques avec une complexité T linéaire](https://arxiv.org/abs/1805.03662).
