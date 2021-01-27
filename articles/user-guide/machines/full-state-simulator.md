---
title: Simulateur Quantum à état complet-Kit de développement quantique
description: Découvrez comment exécuter vos Q# programmes sur le simulateur d’état Microsoft Quantum Development Kit.
author: anpaz
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 950e61c812cc6df739ddaa1de855f753557d6d1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858169"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>Simulateur d’état complet du kit de développement quantique (QDK)

QDK fournit un simulateur d’état complet qui simule un ordinateur quantique sur votre ordinateur local. Vous pouvez utiliser le simulateur d’état complet pour exécuter et déboguer des algorithmes de Quantum écrits dans Q# , en utilisant jusqu’à 30 qubits. Le simulateur d’état complet est semblable au simulateur Quantum utilisé dans la plateforme  [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) de Microsoft Research.

## <a name="invoking-and-running-the-full-state-simulator"></a>Appel et exécution du simulateur d’état complet

Vous exposez le simulateur d’état complet par le biais de la `QuantumSimulator` classe. Pour plus d’informations, consultez [méthodes d’exécution d’un Q# programme](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-simulator-from-c"></a>Appel du simulateur à partir de C #

Créez une instance de la `QuantumSimulator` classe, puis transmettez-la à la `Run` méthode d’une opération de Quantum, ainsi que tous les paramètres supplémentaires.
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

Étant donné que la `QuantumSimulator` classe implémente l' <xref:System.IDisposable> interface, vous devez appeler la `Dispose` méthode une fois que vous n’avez plus besoin de l’instance du simulateur. La meilleure façon de procéder consiste à encapsuler la déclaration et les opérations du simulateur dans une instruction [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) , qui appelle automatiquement la `Dispose` méthode.

### <a name="invoking-the-simulator-from-python"></a>Appel du simulateur à partir de Python

Utilisez la méthode [simulation ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) de la Q# bibliothèque Python avec l’opération importée Q# :

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>Appel du simulateur à partir de la ligne de commande

Lors de l’exécution Q# d’un programme à partir de la ligne de commande, le simulateur d’état complet est l’ordinateur cible par défaut. Si vous le souhaitez, vous pouvez utiliser le paramètre **--simulateur** (ou **-s** shortcut) pour spécifier l’ordinateur cible souhaité. Les deux commandes suivantes exécutent un programme à l’aide du simulateur d’état complet. 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>Appel du simulateur à partir d’un bloc-notes Juptyer

Utilisez la Q# commande magique [% simuler](xref:microsoft.quantum.iqsharp.magic-ref.simulate) pour exécuter l' Q# opération.

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a>Amorçage du simulateur

Par défaut, le simulateur d’état complet utilise un générateur de nombres aléatoires pour simuler le caractère aléatoire du quantum. À des fins de test, il est parfois utile d’avoir des résultats déterministes. Dans un programme C#, vous pouvez le faire en fournissant une valeur de départ pour le générateur de nombres aléatoires dans le `QuantumSimulator` constructeur via le `randomNumberGeneratorSeed` paramètre.

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a>Configuration des threads

Le simulateur d’état complet utilise [OpenMP](http://www.openmp.org/) pour paralléliser l’algèbre linéaire requis. Par défaut, OpenMP utilise tous les threads matériels disponibles, ce qui signifie que les programmes avec un petit nombre de qubits s’exécutent souvent lentement, car la coordination requise expose le travail réel. Vous pouvez résoudre ce problème en définissant la variable `OMP_NUM_THREADS` d’environnement sur un petit nombre. En règle générale, configurez un thread pour un maximum de quatre qubits, puis un thread supplémentaire par qubit. Vous devrez peut-être ajuster la variable en fonction de votre algorithme.

## <a name="see-also"></a>Voir aussi

- [Estimateur de ressources quantiques](xref:microsoft.quantum.machines.resources-estimator)
- [Simulateur Toffoli quantique](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulateur de traces Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)