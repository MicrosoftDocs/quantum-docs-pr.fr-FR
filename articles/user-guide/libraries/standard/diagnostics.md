---
title: Diagnostics dans les Q# bibliothèques standard
description: Découvrez les fonctions et opérations de diagnostic dans les Q# bibliothèques standard utilisées pour détecter les erreurs ou les erreurs dans les programmes Quantum.
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4a98795b2459adaa4e47c888751121fffdc70971
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868540"
---
# <a name="diagnostics"></a>Diagnostics #

Comme pour le développement classique, il est important de pouvoir diagnostiquer les erreurs et les erreurs dans les programmes Quantum.
Les Q# bibliothèques standard offrent différentes méthodes pour garantir l’exactitude des programmes Quantum, comme indiqué dans <xref:microsoft.quantum.guide.testingdebugging> .
En grande partie, cette prise en charge est fournie sous la forme de fonctions et d’opérations qui demandent à l’ordinateur cible de fournir des informations de diagnostic supplémentaires au programme hôte ou au développeur, ou d’appliquer l’exactitude des conditions et invariants exprimées par la fonction ou l’appel d’opération.

## <a name="machine-diagnostics"></a>Diagnostics de l’ordinateur ##

Les diagnostics sur les valeurs classiques peuvent être obtenus à l’aide de la <xref:microsoft.quantum.intrinsic.message> fonction pour enregistrer un message selon une méthode dépendante de l’ordinateur.
Par défaut, cette valeur écrit la chaîne dans la console.
Utilisé avec les chaînes interpolées, permet <xref:microsoft.quantum.intrinsic.message> de signaler facilement les informations de diagnostic sur les valeurs classiques :

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message`possède `(String -> Unit)` une signature, indiquant de nouveau que l’émission d’un message du journal de débogage ne peut pas être observée à partir de Q# .

Les <xref:microsoft.quantum.diagnostics.dumpmachine> <xref:microsoft.quantum.diagnostics.dumpregister> callables et indiquent aux machines cibles de fournir des informations de diagnostic sur tous les qubits actuellement alloués ou sur un registre spécifique de qubits, respectivement.
Chaque ordinateur cible varie selon les informations de diagnostic fournies en réponse à une instruction de vidage.
L’ordinateur cible du [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator) , par exemple, fournit au programme hôte le vecteur d’État qu’il utilise en interne pour représenter un registre de qubits.
Par comparaison, la machine cible du [simulateur Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) fournit un seul bit classique pour chaque qubit.

 Pour en savoir plus sur la sortie [du simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` , jetez un coup d’œil à la section relative aux fonctions de vidage de notre article sur le [test et le débogage](xref:microsoft.quantum.guide.testingdebugging#dump-functions).


## <a name="facts-and-assertions"></a>Faits et assertions ##

Comme indiqué dans [test et débogage](xref:microsoft.quantum.guide.testingdebugging), une fonction ou une opération avec signature `Unit -> Unit` ou `Unit => Unit` , respectivement, peut être marquée comme un *test unitaire*.
Chaque test unitaire se compose généralement d’un petit programme Quantum, avec une ou plusieurs conditions qui vérifient l’exactitude de ce programme.
Ces conditions peuvent se présenter sous la forme de _faits_, qui vérifient les valeurs de leurs entrées, ou _assertions_, qui vérifient les États d’un ou plusieurs qubits passés comme entrée.

Par exemple, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` représente le fait mathématique que $1 + 1 = $2, tandis que `AssertQubit(One, qubit)` représente la condition selon laquelle la mesure `qubit` renverra un `One` avec certitude.
Dans le premier cas, nous pouvons vérifier l’exactitude de la condition en fonction de ses valeurs, tandis que dans ce dernier, nous devons connaître l’état du qubit afin d’évaluer l’assertion.

Les Q# bibliothèques standard fournissent différentes fonctions pour représenter des faits, notamment :

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>Test des États qubit ###

Dans la pratique, les assertions reposent sur le fait que les simulations classiques de mécanismes quantiques n’ont pas besoin de respecter le principe de [non-clonage](https://arxiv.org/abs/quant-ph/9607018), de sorte que nous pouvons effectuer des mesures et des assertions inphysiques lors de l’utilisation d’un simulateur pour notre ordinateur cible.
Par conséquent, nous pouvons tester des opérations individuelles sur un simulateur classique avant de procéder au déploiement sur le matériel.
Sur les ordinateurs cibles qui n’autorisent pas l’évaluation des assertions, les appels à <xref:microsoft.quantum.diagnostics.assertmeasurement> peuvent être ignorés sans risque.

Plus généralement, l' <xref:microsoft.quantum.diagnostics.assertmeasurement> opération déclare que la mesure de la qubits donnée dans la base Pauli donnée aura toujours le résultat donné.
Si l’assertion échoue, l’exécution se termine en appelant `fail` avec le message donné.
Par défaut, cette opération n’est pas implémentée. les simulateurs qui peuvent prendre en charge le service informatique doivent fournir une implémentation qui effectue la vérification de l’exécution.
`AssertMeasurement`a une signature `((Pauli[], Qubit[], Result, String) -> ())` .
Étant donné que `AssertMeasurement` est une fonction avec un tuple vide comme type de sortie, aucun effet à partir de n' `AssertMeasurement` est observable dans un Q# programme.

La <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> fonction d’opération déclare que la mesure du qubits donné dans la base Pauli donnée aura le résultat donné avec la probabilité donnée, dans une certaine tolérance.
La tolérance est additive (par exemple `abs(expected-actual) < tol` ,).
Si l’assertion échoue, l’exécution se termine en appelant `fail` avec le message donné.
Par défaut, cette opération n’est pas implémentée. les simulateurs qui peuvent prendre en charge le service informatique doivent fournir une implémentation qui effectue la vérification de l’exécution.
`AssertMeasurementProbability`a une signature `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)` . Le premier `Double` paramètre donne la probabilité souhaitée du résultat, et le deuxième la tolérance.

Nous pouvons faire plus que déclarer une mesure unique, en utilisant le fait que les informations classiques utilisées par un simulateur pour représenter l’état interne d’un qubit sont susceptibles d’être copiées, de sorte que nous n’avons pas besoin d’effectuer une mesure pour tester notre assertion.
En particulier, cela nous permet d’obtenir des informations sur les mesures *incompatibles* qui seraient impossibles sur le matériel réel.

Supposons que `P : Qubit => Unit` est une opération destinée à préparer l’État $ \ket{\Psi} $ quand son entrée est dans l’État $ \ket {0} $.
Let $ \ket{\Psi'} $ est l’état réel préparé par `P` .
Ensuite, $ \ket{\Psi} = \ket{\Psi'} $ si et seulement si la mesure de $ \ket{\Psi'} $ dans l’axe décrit par $ \ket{\Psi} $ retourne toujours `Zero` .
Autrement dit, \begin{align} \ket{\Psi} = \ket{\Psi'} \text{si et seulement si} \braket{\Psi | \Psi'} = 1.
\end{align} à l’aide des opérations primitives définies dans le préambule destiné à, nous pouvons effectuer directement une mesure qui retourne `Zero` si $ \ket{\Psi} $ est un eigenstate de l’un des opérateurs Pauli.


L’opération <xref:microsoft.quantum.diagnostics.assertqubit> fournit un raccourci particulièrement utile pour le faire dans le cas où nous souhaitons tester l’assertion $ \ket{\Psi} = \ket {0} $.
C’est souvent le cas, par exemple, lorsque nous avons non calculé pour retourner Ancilla qubits à $ \ket {0} $ avant de les libérer.
L’assertion de $ \ket {0} $ est également utile lorsque vous souhaitez déclarer que deux opérations de préparation et de préparation d’état `P` `Q` préparent le même État et lorsque `Q` prend en charge `Adjoint` .
En particulier,

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

En général, toutefois, nous ne pouvons pas avoir accès à des assertions sur les États qui ne coïncident pas avec les eigenstates d’opérateurs Pauli.
Par exemple, $ \ket{\Psi} = (\ket {0} + e ^ {i \pi/8} \ket {1} )/\sqrt {2} $ n’est pas une eigenstate d’un opérateur Pauli, de sorte que nous ne pouvons pas utiliser <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> pour déterminer de façon unique qu’un État $ \ket{\Psi'} $ est égal à $ \ket{\Psi} $.
Au lieu de cela, nous devons décomposer l’assertion $ \ket{\Psi'} = \ket{\Psi} $ en hypothèses qui peuvent être testées directement à l’aide des primitives prises en charge par notre simulateur.
Pour ce faire, laissez $ \ket{\Psi} = \alpha \ket {0} + \beta \ket {1} $ pour les nombres complexes $ \alpha = a \_ r + a \_ i et $ \beta $.
Notez que cette expression requiert quatre nombres réels $ \{ a \_ r, a \_ i, b \_ r, b \_ i \} $ pour spécifier, car chaque nombre complexe peut être exprimé comme la somme d’une partie réelle et imaginaire.
En raison de la phase globale, toutefois, nous pouvons choisir $a \_ i = $0, de sorte que nous avons uniquement besoin de trois chiffres réels pour spécifier de manière unique un État à qubit unique.

Par conséquent, nous devons spécifier trois assertions indépendantes les unes des autres afin de déclarer l’État attendu.
Pour ce faire, nous constatons la probabilité d’observer `Zero` pour chaque mesure Pauli en fonction de $ \alpha $ et $ \beta $, et en déclarant chacun séparément.
Autorisez les valeurs $x $, $y $ et $z $ `Result` pour Pauli $X $, $Y $ et $Z $, respectivement.
Puis, à l’aide de la fonction vraisemblance pour les mesures de Quantum, \begin{align} \Pr (x = \texttt{Zero} | \alpha, \beta) & = \frac12 + a \_ r b \_ r + a \_ i b \_ i \\ \\ \Pr (y = \texttt{Zero} | \alpha, \beta) & = \frac12 + a \_ r b \_ i-a \_ i b \_ r \\ \\ \Pr (z = \texttt{Zero} | \alpha, \beta) & = \frac12\left (1 + a \_ r ^ 2 + a \_ i ^ 2 + b \_ r ^ 2 + b \_ i ^ 2 \right).
\end{align}

L' <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> opération implémente ces assertions à des représentations données de $ \alpha $ et $ \beta $ en tant que valeurs de type <xref:microsoft.quantum.math.complex> .
Cela est utile lorsque l’État attendu peut être calculé de façon mathématique.

### <a name="asserting-equality-of-quantum-operations"></a>Assertion de l’égalité des opérations de Quantum ###

Jusqu’ici, nous nous intéressons aux opérations de test qui visent à préparer des États particuliers.
Toutefois, il est souvent intéressant de savoir comment une opération agit pour des entrées arbitraires plutôt que pour une seule entrée fixe.
Supposons, par exemple, que nous ayons implémenté une opération `U : ((Double, Qubit[]) => () : Adjoint)` correspondant à une famille d’opérateurs d’unités $U (t) $ et que vous ayez fourni un `adjoint` bloc explicite au lieu d’utiliser `adjoint auto` .
Il peut être intéressant de déclarer que $U ^ \dagger (t) = U (-t) $, comme prévu si $t $ représente une heure d’évolution.

En général, il existe deux stratégies différentes que nous pouvons suivre pour faire de l’assertion que deux opérations `U` et `V` agissent de la même manière.
Tout d’abord, nous pouvons vérifier que `U(target); (Adjoint V)(target);` l’option conserve chaque État dans une base donnée.
Deuxièmement, nous pouvons vérifier que `U(target); (Adjoint V)(target);` le fait d’agir à la moitié d’un État enchevêtré préserve Cet enchevêtrement.
Ces stratégies sont implémentées par les opérations Canon <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> et <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced> , respectivement.

> [!NOTE]
> L’assertion référencée présentée ci-dessus fonctionne en fonction de l' [Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), une infrastructure mathématique qui lie les opérations sur $n $ qubits aux États enchevêtrés sur $2n $ qubits.
> En particulier, l’opération d’identité sur $n $ qubits est représentée par $n $ copies de l’État enchevêtréd $ \ket{\ beta_ {00} } \mathrel{ : =} (\ket {00} + \ket {11} )/\sqrt {2} $.
> L’opération <xref:microsoft.quantum.preparation.preparechoistate> implémente ce isomorphism, en préparant un État qui représente une opération donnée.

En gros, ces stratégies se distinguent par un compromis d’espace.
L’itération au sein de chaque État d’entrée prend du temps supplémentaire, tandis que l’utilisation de l’enchevêtrement comme référence requiert le stockage de qubits supplémentaires.
Dans les cas où une opération implémente une opération classique réversible, de sorte que nous sommes uniquement intéressés par son comportement sur les États de base de calcul, <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> teste l’égalité sur ce jeu restreint d’entrées.

> [!TIP]
> L’itération sur les États d’entrée est gérée par les opérations d’énumération <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> et <xref:microsoft.quantum.canon.iteratethroughcartesianpower> .
> Ces opérations sont plus généralement utiles pour appliquer une opération à chaque élément du produit cartésien entre deux jeux ou plus.

Plus critique, toutefois, les deux approches testent différentes propriétés des opérations en cours d’examen.
Étant donné que l’assertion sur place appelle chaque opération plusieurs fois, une fois pour chaque État d’entrée, les choix aléatoires et les résultats de mesure peuvent changer d’un appel à l’autre.
En revanche, l’assertion référencée appelle chaque opération une seule fois, de telle sorte qu’elle vérifie que les opérations sont égales *dans une seule capture*.
Ces deux tests sont utiles pour garantir l’exactitude des programmes quantiques.


## <a name="further-reading"></a>En savoir plus ##

- <xref:microsoft.quantum.guide.testingdebugging>
- <xref:microsoft.quantum.diagnostics>
