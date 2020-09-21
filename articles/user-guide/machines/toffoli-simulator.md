---
title: Simulateur Quantum Toffoli-Kit de développement quantique
description: Découvrez Microsoft QDK Toffoli Simulator, un simulateur Quantum spécial qui peut être utilisé avec des millions de qubits.
author: alan-geller
ms.author: ageller
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 82882f01d1b5c036faee71f18a18b2595107ddb7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835908"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>QDK (Quantum Development Kit) Toffoli Simulator

Le simulateur QDK Toffoli est un simulateur à usage spécial avec une étendue limitée et prend en charge uniquement les `X` `CNOT` opérations de Quantum, et multiples `X` . Toute la logique et les calculs classiques sont disponibles.

Alors que le simulateur Toffoli est plus limité en termes de fonctionnalités que le [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator), il présente l’avantage de pouvoir simuler beaucoup plus de qubits. Le simulateur Toffoli peut être utilisé avec des millions de qubits, tandis que le simulateur d’état complet est limité à environ 30 qubits. Cela est utile, par exemple, avec Oracle qui évaluent des fonctions booléennes : elles peuvent être implémentées à l’aide de l’ensemble limité d’algorithmes pris en charge et testés sur un grand nombre de qubits.

## <a name="invoking-the-toffoli-simulator"></a>Appel du simulateur Toffoli

Vous exposez le simulateur Toffoli par le biais de la `ToffoliSimulator` classe. Pour plus d’informations, consultez [méthodes d’exécution d’un Q# programme](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-toffoli-simulator-from-c"></a>Appel du simulateur Toffoli à partir de C #

Comme pour les autres ordinateurs cibles, vous devez d’abord créer une instance de la classe `ToffoliSimulator`, puis la passer en tant que premier paramètre de la méthode `Run` d’une opération.

Notez que, contrairement à la classe `QuantumSimulator`, la classe `ToffoliSimulator` n’implémente pas l’interface <xref:System.IDisposable>. Vous n’avez donc pas besoin de la placer dans une instruction `using`.

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>Appel du simulateur Toffoli à partir de Python

Utilisez la méthode [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) à partir de la bibliothèque Python avec l’opération importée Q# :

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>Appel du simulateur Toffoli à partir de la ligne de commande

Quand vous exécutez un Q# programme à partir de la ligne de commande, utilisez le paramètre **--simulateur** (ou **-s** raccourci) pour spécifier l’ordinateur cible du simulateur Toffoli. La commande suivante exécute un programme à l’aide de l’estimateur de ressources : 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>Appel du simulateur Toffoli à partir de blocs-notes Juptyer

Utilisez la Q# commande magique [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) pour exécuter l' Q# opération.

```
%toffoli myOperation
```

## <a name="supported-operations"></a>Opérations prises en charge

Le simulateur Toffoli prend en charge :

* Les rotations et élever Paulis, comme `R` et `Exp` , lorsque l’opération obtenue est égale `X` ou la matrice d’identité.
* Opérations de mesure et d' [assertion](xref:microsoft.quantum.diagnostics.assertmeasurement) , mais uniquement dans la `Z` base Pauli. Notez que la probabilité d’une opération de mesure est toujours **égale à 0** ou **1**; Il n’y a pas de caractère aléatoire dans le simulateur Toffoli.
* `DumpMachine``DumpRegister`fonctions et.
Les deux fonctions génèrent l' `Z` état actuel de chaque qubit, à raison d’un qubit par ligne.

## <a name="specifying-the-number-of-qubits"></a>Spécification du nombre de qubits

Par défaut, une `ToffoliSimulator` instance alloue de l’espace pour 65 536 qubits.
Si votre algorithme requiert plus de qubits, vous pouvez spécifier le nombre de qubit en fournissant une valeur pour le `qubitCount` paramètre au constructeur.
Chaque qubit supplémentaire ne nécessitant qu’un seul octet de mémoire, il n’y a donc pas de coût significatif pour l’estimation du nombre de qubits dont vous avez besoin.

Par exemple :

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a>Voir aussi

- [Estimateur de ressources de Quantum](xref:microsoft.quantum.machines.resources-estimator)
- [Simulateur de traces Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Simulateur d’état complet du quantum](xref:microsoft.quantum.machines.full-state-simulator) 