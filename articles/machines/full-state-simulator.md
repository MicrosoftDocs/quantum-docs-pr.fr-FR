---
title: Simulateur d’état complet
description: 'Découvrez comment exécuter vos programmes Q # sur le simulateur d’état Microsoft Quantum Development Kit.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906115"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Simulateur d’état complet du kit de développement quantique

Le kit de développement quantum fournit un simulateur Quantum d’état complet similaire à [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) de Microsoft Research.
Ce simulateur peut être utilisé pour exécuter et déboguer des algorithmes de Quantum écrits en Q # sur votre ordinateur.

Ce simulateur Quantum est exposé via la classe `QuantumSimulator`. Pour utiliser le simulateur, il vous suffit de créer une instance de cette classe et de la passer à la méthode `Run` de l’opération Quantum que vous souhaitez exécuter avec le reste des paramètres :

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

La classe `QuantumSimulator` implémente <xref:System.IDisposable>. par conséquent, la méthode `Dispose` doit être appelée une fois que l’instance du simulateur n’est plus utilisée. La meilleure façon de procéder consiste à encapsuler le simulateur dans une instruction `using`, comme dans l’exemple ci-dessus.

## <a name="seed"></a>Seed

L' `QuantumSimulator` utilise un générateur de nombres aléatoires pour simuler le caractère aléatoire du quantum. À des fins de test, il est parfois utile d’avoir des résultats déterministes. Pour ce faire, vous pouvez fournir une valeur de départ pour le générateur de nombres aléatoires dans le constructeur de `QuantumSimulator`via le paramètre `randomNumberGeneratorSeed` :

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Threads

L' `QuantumSimulator` utilise [OpenMP](http://www.openmp.org/) pour paralléliser l’algèbre linéaire requis. Par défaut, OpenMP utilise tous les threads matériels disponibles, ce qui signifie que les programmes avec un petit nombre de qubits s’exécutent souvent lentement, car la coordination nécessaire va prendre le pas sur le travail réel. Vous pouvez résoudre ce problème en définissant la variable d’environnement `OMP_NUM_THREADS` sur un petit nombre. En règle générale, 1 thread convient pour jusqu’à environ 4 qubits, puis un thread supplémentaire par qubit convient, bien que cela dépende fortement de votre algorithme.

