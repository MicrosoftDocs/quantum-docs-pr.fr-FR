---
uid: Microsoft.Quantum.Research.Chemistry.OptimizedTrotterStepOracle
title: OptimizedTrotterStepOracle fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: OptimizedTrotterStepOracle
qsharp.summary: Returns optimized Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: f78d80f7ab71f4fc759d8045c9a134d7178aaa15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701803"
---
# <a name="optimizedtrottersteporacle-function"></a>OptimizedTrotterStepOracle fonction)

Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)

Packages [](https://nuget.org/packages/)


Retourne l’opération de l’étape Trotter optimisée et les paramètres nécessaires pour l’exécuter.

```qsharp
function OptimizedTrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>Entrée

### <a name="qsharpdata--jordanwignerencodingdata"></a>qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Hamilton, décrit par `JordanWignerEncodingData` format.


### <a name="trotterstepsize--double"></a>trotterStepSize : [double](xref:microsoft.quantum.lang-ref.double)

Taille d’étape de l’intégrateur trotter.


### <a name="trotterorder--int"></a>trotterOrder : [entier](xref:microsoft.quantum.lang-ref.int)

Ordre de l’intégrateur trotter.



## <a name="output--intdoublequbit--unit-adj--ctl"></a>Sortie : ([int](xref:microsoft.quantum.lang-ref.int), ([double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL))

Un tuple où : `Int` est le nombre d’qubits alloués, `Double` est `1.0/trotterStepSize` , et l’opération est l’étape trotter.