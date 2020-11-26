---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: Type défini par l’utilisateur StateGenerator
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: 5c9643f5c917ff3cb25fa8c046856b03cc287edd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211557"
---
# <a name="stategenerator-user-defined-type"></a>Type défini par l’utilisateur StateGenerator

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Décrit une opération qui prépare une entrée donnée à un classifieur séquentiel.

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Éléments nommés

### <a name="nqubits--int"></a>NQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits sur lesquels l’entrée encodée est définie.
### <a name="prepare--littleendian--unit--is-adj--ctl"></a>Prepare [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) : l' => [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian est Adj + CTL

Opération qui prépare l’entrée encodée sur un registre Little endian de `NQubits` qubits.