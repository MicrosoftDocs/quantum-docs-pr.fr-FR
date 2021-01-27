---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: Type défini par l’utilisateur StateGenerator
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: b4f6c3ca28e2976b6a0d58f4ef25ea943de9811e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854872"
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
### <a name="prepare--littleendian--unit--is-adj--ctl"></a>Prepare [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) : l' => [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian est Adj + CTL

Opération qui prépare l’entrée encodée sur un registre Little endian de `NQubits` qubits.