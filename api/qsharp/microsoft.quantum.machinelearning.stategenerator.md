---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: Type défini par l’utilisateur StateGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707964"
---
# <a name="stategenerator-user-defined-type"></a>Type défini par l’utilisateur StateGenerator

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


Décrit une opération qui prépare une entrée donnée à un classifieur séquentiel.

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Éléments nommés

### <a name="nqubits--int"></a>NQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits sur lesquels l’entrée encodée est définie.
### <a name="prepare--littleendian--unit-adj--ctl"></a>Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + CTL

Opération qui prépare l’entrée encodée sur un registre Little endian de `NQubits` qubits.