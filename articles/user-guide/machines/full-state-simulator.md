---
title: Simulateur d’état complet
description: 'Découvrez comment exécuter vos programmes Q # sur le simulateur d’état Microsoft Quantum Development Kit.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274944"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Simulateur d’état complet du kit de développement quantique

Le kit de développement quantum fournit un simulateur Quantum d’état complet similaire à [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) de Microsoft Research.
Ce simulateur peut être utilisé pour exécuter et déboguer des algorithmes de Quantum écrits en Q # sur votre ordinateur.

Ce simulateur Quantum est exposé via la `QuantumSimulator` classe. Pour utiliser le simulateur, il vous suffit de créer une instance de cette classe et de la passer à la `Run` méthode de l’opération Quantum que vous souhaitez exécuter avec le reste des paramètres :

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

La `QuantumSimulator` classe implémente <xref:System.IDisposable> , de sorte `Dispose` que la méthode doit être appelée une fois que l’instance du simulateur n’est plus utilisée. La meilleure façon de procéder consiste à encapsuler le simulateur dans une `using` instruction, comme dans l’exemple ci-dessus.

## <a name="seed"></a>Seed

`QuantumSimulator`Utilise un générateur de nombres aléatoires pour simuler le caractère aléatoire du quantum. À des fins de test, il est parfois utile d’avoir des résultats déterministes. Pour ce faire, vous pouvez fournir une valeur de départ pour le générateur de nombres aléatoires dans le `QuantumSimulator` constructeur de à l’aide du `randomNumberGeneratorSeed` paramètre :

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Threads

`QuantumSimulator`Utilise [OpenMP](http://www.openmp.org/) pour paralléliser l’algèbre linéaire requis. Par défaut, OpenMP utilise tous les threads matériels disponibles, ce qui signifie que les programmes avec un petit nombre de qubits s’exécutent souvent lentement, car la coordination nécessaire va prendre le pas sur le travail réel. Cela peut être résolu en affectant à la variable `OMP_NUM_THREADS` d’environnement un nombre réduit. En règle générale, 1 thread convient pour jusqu’à environ 4 qubits, puis un thread supplémentaire par qubit convient, bien que cela dépende fortement de votre algorithme.

