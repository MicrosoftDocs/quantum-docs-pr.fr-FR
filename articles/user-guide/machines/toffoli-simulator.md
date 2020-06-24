---
title: Simulateur Toffoli du kit de développement quantique
description: Découvrez Microsoft QDK Toffoli Simulator, un simulateur Quantum spécial qui peut être utilisé avec des millions de qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275147"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Simulateur Toffoli du kit de développement quantique

Le kit de développement quantum fournit un simulateur Toffoli, qui est un simulateur spécialisé qui peut simuler des algorithmes Quantum qui sont limités aux opérations de Quantum x, CNOTIN et multi-contrôlés X (toutes les calculs et logiques classiques sont disponibles).

Alors que le simulateur Toffoli est beaucoup plus limité en fonctionnement que le [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator), il peut simuler beaucoup plus de qubits.
Le simulateur Toffoli peut être utilisé avec des millions de qubits, tandis que le simulateur d’état complet est généralement limité à environ 30.
Il peut exécuter et déboguer un ensemble limité d’algorithmes de Quantum écrits en Q # sur votre ordinateur ; par exemple, les Oracle qui évaluent des fonctions booléennes peuvent être implémentées à l’aide de ces portes et, par conséquent, testées sur la variation d’un grand nombre de qubits utilisant ce simulateur.

Ce simulateur Quantum est exposé via la `ToffoliSimulator` classe.
Pour utiliser le simulateur, il vous suffit de créer une instance de cette classe et de la passer à la `Run` méthode de l’opération Quantum que vous souhaitez exécuter avec le reste des paramètres :

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>Autres opérations

`ToffoliSimulator`Prend en charge les rotations et les élever Paulis, tels que `R` et `Exp` , lorsque l’opération obtenue est égale à `X` ou à l’identité.

Les mesures et les Assert sont pris en charge, mais uniquement dans la `Z` base Pauli.
Notez que la probabilité d’une mesure est toujours 0 ou 1 ; Il n’y a pas de caractère aléatoire dans le simulateur Toffoli.

`DumpMachine`et `DumpRegister` sont pris en charge.
Ils génèrent tous deux l' `Z` état actuel de chaque qubit, à raison d’un qubit par ligne.

## <a name="qubitcount"></a>QubitCount

Par défaut, le `ToffoliSimulator` alloue de l’espace pour 65 536 qubits.
Si votre algorithme en requiert plus, vous pouvez modifier le nombre de qubit en fournissant une valeur pour le `qubitCount` paramètre au constructeur.
Chaque qubit supplémentaire requiert un octet de mémoire supplémentaire, donc il n’y a pas de coût significatif pour le surestimation du nombre de qubits dont vous avez besoin.

Par exemple :

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
