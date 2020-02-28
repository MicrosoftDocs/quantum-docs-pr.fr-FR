---
title: 'Diagnostics dans les bibliothèques standard Q #'
description: 'Découvrez les fonctions et opérations de diagnostic dans les bibliothèques standard Q # utilisées pour détecter les erreurs ou les erreurs dans les programmes Quantum.'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: ba2f248327bb3db4ee895f8e65ea31c17e42b5f4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906234"
---
# <a name="diagnostics"></a>Diagnostics #

Comme pour le développement classique, il est important de pouvoir diagnostiquer les erreurs et les erreurs dans les programmes Quantum.
Les bibliothèques standard Q # offrent différentes méthodes pour garantir l’exactitude des programmes quantiques, comme indiqué dans <xref:microsoft.quantum.techniques.testing-and-debugging>.
En grande partie, cette prise en charge est fournie sous la forme de fonctions et d’opérations qui demandent à l’ordinateur cible de fournir des informations de diagnostic supplémentaires au programme hôte ou au développeur, ou d’appliquer l’exactitude des conditions et invariants exprimés. par l’appel de fonction ou d’opération.

## <a name="machine-diagnostics"></a>Diagnostics de l’ordinateur ##

Les diagnostics sur les valeurs classiques peuvent être obtenus à l’aide de la fonction <xref:microsoft.quantum.intrinsic.message> pour consigner un message de façon dépendante de l’ordinateur.
Par défaut, cette valeur écrit la chaîne dans la console.
Utilisé avec les chaînes interpolées, <xref:microsoft.quantum.intrinsic.message> permet de créer facilement des informations de diagnostic sur les valeurs classiques :

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` a des `(String -> Unit)`de signature, indiquant de nouveau que l’émission d’un message de journal de débogage ne peut pas être observée à partir de Q #.

Le <xref:microsoft.quantum.diagnostics.dumpmachine> et <xref:microsoft.quantum.diagnostics.dumpregister> callables indiquent aux machines cibles de fournir des informations de diagnostic sur tous les qubits actuellement alloués ou sur un registre spécifique de qubits, respectivement.
Chaque ordinateur cible varie selon les informations de diagnostic fournies en réponse à une instruction de vidage.
L’ordinateur cible du [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator) , par exemple, fournit au programme hôte le vecteur d’État qu’il utilise en interne pour représenter un registre de qubits.
Par comparaison, la machine cible du [simulateur Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) fournit un seul bit classique pour chaque qubit.

 Pour en savoir plus sur la sortie `DumpMachine` [du simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator) , consultez la section fonctions de vidage de notre article sur le [test et le débogage](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions).


## <a name="facts-and-assertions"></a>Faits et assertions ##

Comme indiqué dans la section [test et débogage](xref:microsoft.quantum.techniques.testing-and-debugging), une fonction ou une opération avec signature `Unit -> Unit` ou `Unit => Unit`, respectivement, peut être marquée comme un *test unitaire*.
Chaque test unitaire se compose généralement d’un petit programme Quantum, avec une ou plusieurs conditions qui vérifient l’exactitude de ce programme.
Ces conditions peuvent se présenter sous la forme de _faits_, qui vérifient les valeurs de leurs entrées, ou _assertions_, qui vérifient les États d’un ou plusieurs qubits passés comme entrée.

Par exemple, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` représente le fait mathématique de $1 + 1 = $2, tandis que `AssertQubit(One, qubit)` représente la condition selon laquelle la mesure `qubit` renverra une `One` avec certitude.
Dans le premier cas, nous pouvons vérifier l’exactitude de la condition en fonction de ses valeurs, tandis que dans ce dernier, nous devons connaître l’état du qubit afin d’évaluer l’assertion.

Les bibliothèques standard Q # fournissent différentes fonctions pour représenter des faits, notamment :

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>Test des États qubit ###

Dans la pratique, les assertions reposent sur le fait que les simulations classiques de mécanismes quantiques n’ont pas besoin de respecter le principe de [non-clonage](https://arxiv.org/abs/quant-ph/9607018), de sorte que nous pouvons effectuer des mesures et des assertions inphysiques lors de l’utilisation d’un simulateur pour notre ordinateur cible.
Par conséquent, nous pouvons tester des opérations individuelles sur un simulateur classique avant de procéder au déploiement sur le matériel.
Sur les ordinateurs cibles qui n’autorisent pas l’évaluation des assertions, les appels à <xref:microsoft.quantum.intrinsic.assert> peuvent être ignorés sans risque.

Plus généralement, l’opération <xref:microsoft.quantum.intrinsic.assert> déclare que la mesure de la qubits donnée dans la base Pauli donnée aura toujours le résultat donné.
Si l’assertion échoue, l’exécution se termine en appelant `fail` avec le message donné.
Par défaut, cette opération n’est pas implémentée. les simulateurs qui peuvent prendre en charge le service informatique doivent fournir une implémentation qui effectue la vérification de l’exécution.
`Assert` contient des `((Pauli[], Qubit[], Result, String) -> ())`de signature.
Étant donné que `Assert` est une fonction avec un tuple vide comme type de sortie, aucun effet n’ayant été appelé `Assert` ne peut être observé dans un programme Q #.

La fonction d’opération <xref:microsoft.quantum.intrinsic.assertprob> déclare que la mesure de la qubits donnée dans la base Pauli donnée aura le résultat donné avec la probabilité donnée, dans une certaine tolérance.
La tolérance est additive (par exemple, `abs(expected-actual) < tol`).
Si l’assertion échoue, l’exécution se termine en appelant `fail` avec le message donné.
Par défaut, cette opération n’est pas implémentée. les simulateurs qui peuvent prendre en charge le service informatique doivent fournir une implémentation qui effectue la vérification de l’exécution.
`AssertProb` contient des `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`de signature. La première des `Double` paramètres donne la probabilité souhaitée du résultat, et la seconde la tolérance.

Nous pouvons faire plus que déclarer une mesure unique, en utilisant le fait que les informations classiques utilisées par un simulateur pour représenter l’état interne d’un qubit sont susceptibles d’être copiées, de sorte que nous n’avons pas besoin d’effectuer une mesure pour tester notre assertion.
En particulier, cela nous permet d’obtenir des informations sur les mesures *incompatibles* qui seraient impossibles sur le matériel réel.

Supposons que `P : Qubit => Unit` est une opération destinée à préparer l’État $ \ket{\Psi} $ quand son entrée se trouve dans l’État $ \ket{0}$.
Laissez $ \ket{\Psi'} $ être l’état réel préparé par `P`.
Ensuite, $ \ket{\Psi} = \ket{\Psi'} $ si et seulement si la mesure de $ \ket{\Psi'} $ dans l’axe décrit par $ \ket{\Psi} $ retourne toujours `Zero`.
Autrement dit, \begin{align} \ket{\Psi} = \ket{\Psi'} \text{si et seulement si} \braket{\Psi | \Psi'} = 1.
\end{align} à l’aide des opérations primitives définies dans le préambule destiné à, nous pouvons effectuer directement une mesure qui retourne `Zero` si $ \ket{\Psi} $ est un eigenstate de l’un des opérateurs Pauli.


L’opération <xref:microsoft.quantum.diagnostics.assertqubit> fournit un raccourci particulièrement utile pour le faire dans le cas où nous souhaitons tester l’assertion $ \ket{\Psi} = \ket{0}$.
C’est souvent le cas, par exemple, lorsque nous avons uncalculed pour retourner Ancilla qubits à $ \ket{0}$ avant de les libérer.
L’assertion par rapport à $ \ket{0}$ est également utile lorsque vous souhaitez déclarer que deux opérations de préparation d’État `P` et `Q` les opérations préparent le même État et lorsque `Q` prend en charge `Adjoint`.
En particulier,

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

En général, toutefois, nous ne pouvons pas avoir accès à des assertions sur les États qui ne coïncident pas avec les eigenstates d’opérateurs Pauli.
Par exemple, $ \ket{\Psi} = (\ket{0} + e ^ {i \pi/8} \ket{1})/\sqrt{2}$ n’est pas une eigenstate d’un opérateur Pauli, de sorte que nous ne pouvons pas utiliser <xref:microsoft.quantum.intrinsic.assertprob> pour déterminer de façon unique qu’un État $ \ket{\Psi'} $ est égal à $ \ket{\Psi} $.
Au lieu de cela, nous devons décomposer l’assertion $ \ket{\Psi'} = \ket{\Psi} $ en hypothèses qui peuvent être testées directement à l’aide des primitives prises en charge par notre simulateur.
Pour ce faire, laissez $ \ket{\Psi} = \alpha \ket{0} + \beta \ket{1}$ pour les nombres complexes $ \alpha = a\_r + a\_i et $ \beta $.
Notez que cette expression requiert quatre nombres réels $\{un\_r, a\_i, b\_r, b\_i\}$ pour spécifier, car chaque nombre complexe peut être exprimé comme la somme d’une partie réelle et imaginaire.
En raison de la phase globale, toutefois, nous pouvons choisir $a\_i = $0, de sorte que nous avons uniquement besoin de trois chiffres réels pour spécifier de manière unique un État à qubit unique.

Par conséquent, nous devons spécifier trois assertions indépendantes les unes des autres afin de déclarer l’État attendu.
Pour ce faire, nous constatons la probabilité d’observer `Zero` pour chaque mesure Pauli en fonction de $ \alpha $ et $ \beta $ et en déclarant chacun séparément.
Laissez $x $, $y $ et $z $ `Result` respectivement des valeurs pour Pauli $X $, $Y $ et $Z $ Measurements.
Puis, à l’aide de la fonction vraisemblance pour les mesures quantiques, \begin{align} \Pr (x = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_r + a\_i b\_i \\\\ \Pr (y = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_i-a\_i b\_r \\\\ \Pr (z = \texttt{Zero} | \alpha, \beta) & = \frac12\left (1 + a\_r ^ 2 + a\_i ^ 2 + b\_r ^ 2 + b\_i ^ 2 \right).
\end{align}

L’opération <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> implémente ces assertions pour les représentations données de $ \alpha $ et $ \beta $ en tant que valeurs de type <xref:microsoft.quantum.math.complex>.
Cela est utile lorsque l’État attendu peut être calculé de façon mathématique.

### <a name="asserting-equality-of-quantum-operations"></a>Assertion de l’égalité des opérations de Quantum ###

Jusqu’ici, nous nous intéressons aux opérations de test qui visent à préparer des États particuliers.
Toutefois, il est souvent intéressant de savoir comment une opération agit pour des entrées arbitraires plutôt que pour une seule entrée fixe.
Supposons, par exemple, que nous ayons implémenté une opération `U : ((Double, Qubit[]) => () : Adjoint)` correspondant à une famille d’opérateurs unitaires $U (t) $ et que vous ayez fourni un bloc `adjoint` explicite au lieu d’utiliser `adjoint auto`.
Il peut être intéressant de déclarer que $U ^ \dagger (t) = U (-t) $, comme prévu si $t $ représente une heure d’évolution.

Globalement, il existe deux stratégies différentes que nous pouvons suivre pour faire de l’assertion que deux opérations `U` et `V` agiront de la même manière.
Tout d’abord, nous pouvons vérifier que `U(target); (Adjoint V)(target);` conserve chaque État dans une base donnée.
Deuxièmement, nous pouvons vérifier que `U(target); (Adjoint V)(target);` agissant à la moitié d’un État enchevêtré préserve Cet enchevêtrement.
Ces stratégies sont implémentées par les opérations Canon <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> et <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>, respectivement.

> [!NOTE]
> L’assertion référencée présentée ci-dessus fonctionne en fonction de l' [Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), une infrastructure mathématique qui lie les opérations sur $n $ qubits aux États enchevêtrés sur $2n $ qubits.
> En particulier, l’opération d’identité sur $n $ qubits est représentée par $n $ copies de l’État enchevêtréd $ \ket{\ beta_{00}} \mathrel{ : =} (\ket{00} + \ket{11})/\sqrt{2}$.
> L’opération <xref:microsoft.quantum.preparation.preparechoistate> implémente ce isomorphism, en préparant un État qui représente une opération donnée.

En gros, ces stratégies se distinguent par un compromis d’espace.
L’itération au sein de chaque État d’entrée prend du temps supplémentaire, tandis que l’utilisation de l’enchevêtrement comme référence requiert le stockage de qubits supplémentaires.
Dans les cas où une opération implémente une opération classique réversible, de telle sorte que nous sommes uniquement intéressés par son comportement sur les États de base de calcul, <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> teste l’égalité sur ce jeu restreint d’entrées.

> [!TIP]
> L’itération sur les États d’entrée est gérée par les opérations d’énumération <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> et <xref:microsoft.quantum.canon.iteratethroughcartesianpower>.
> Ces opérations sont plus généralement utiles pour appliquer une opération à chaque élément du produit cartésien entre deux jeux ou plus.

Plus critique, toutefois, les deux approches testent différentes propriétés des opérations en cours d’examen.
Étant donné que l’assertion sur place appelle chaque opération plusieurs fois, une fois pour chaque État d’entrée, les choix aléatoires et les résultats de mesure peuvent changer d’un appel à l’autre.
En revanche, l’assertion référencée appelle chaque opération une seule fois, de telle sorte qu’elle vérifie que les opérations sont égales *dans une seule capture*.
Ces deux tests sont utiles pour garantir l’exactitude des programmes quantiques.


## <a name="further-reading"></a>Pour aller plus loin ##

- <xref:microsoft.quantum.techniques.testing-and-debugging>
- <xref:microsoft.quantum.diagnostics>
