---
title: Kit de développement quantique Toffoli Simulator | Microsoft Docs
description: Vue d’ensemble du simulateur Toffoli du kit de développement quantique de Microsoft
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 26940d1a8fe31f1035e2d23a68940cd999517c6b
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442356"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Simulateur Toffoli du kit de développement quantique

Le kit de développement quantum fournit un simulateur Toffoli, qui est un simulateur spécialisé qui peut simuler des algorithmes Quantum qui sont limités aux opérations de Quantum x, CNOTIN et multi-contrôlés X (toutes les calculs et logiques classiques sont disponibles).

Alors que le simulateur Toffoli est beaucoup plus limité en fonctionnement que le [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator), il peut simuler beaucoup plus de qubits.
Le simulateur Toffoli peut être utilisé avec des millions de qubits, tandis que le simulateur d’état complet est généralement limité à environ 30.
Il peut exécuter et déboguer un ensemble limité d’algorithmes de Quantum écrits en Q # sur votre ordinateur ; par exemple, les Oracle qui évaluent des fonctions booléennes peuvent être implémentées à l’aide de ces portes et, par conséquent, testées sur la variation d’un grand nombre de qubits utilisant ce simulateur.

Ce simulateur Quantum est exposé via la classe `ToffoliSimulator`.
Pour utiliser le simulateur, il vous suffit de créer une instance de cette classe et de la passer à la méthode `Run` de l’opération Quantum que vous souhaitez exécuter avec le reste des paramètres :

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>Autres opérations

Le `ToffoliSimulator` prend en charge les rotations et élever Paulis, comme `R` et `Exp`, lorsque l’opération obtenue est égale à `X` ou à l’identité.

Les mesures et les Assert sont pris en charge, mais uniquement dans la base Pauli `Z`.
Notez que la probabilité d’une mesure est toujours 0 ou 1 ; Il n’y a pas de caractère aléatoire dans le simulateur Toffoli.

`DumpMachine` et `DumpRegister` sont pris en charge.
Ils génèrent tous deux un état de base `Z`actuel de chaque qubit, un qubit par ligne.

## <a name="qubitcount"></a>QubitCount

Par défaut, le `ToffoliSimulator` alloue de l’espace pour 65 536 qubits.
Si votre algorithme en requiert plus, vous pouvez modifier le nombre de qubit en fournissant une valeur pour le paramètre `qubitCount` au constructeur.
Chaque qubit supplémentaire requiert un octet de mémoire supplémentaire, donc il n’y a pas de coût significatif pour le surestimation du nombre de qubits dont vous avez besoin.

Exemple :

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
