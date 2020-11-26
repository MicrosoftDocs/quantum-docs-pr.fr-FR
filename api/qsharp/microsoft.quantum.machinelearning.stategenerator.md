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
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="63cc2-102">Type défini par l’utilisateur StateGenerator</span><span class="sxs-lookup"><span data-stu-id="63cc2-102">StateGenerator user defined type</span></span>

<span data-ttu-id="63cc2-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="63cc2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="63cc2-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="63cc2-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="63cc2-105">Décrit une opération qui prépare une entrée donnée à un classifieur séquentiel.</span><span class="sxs-lookup"><span data-stu-id="63cc2-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="63cc2-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="63cc2-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="63cc2-107">NQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="63cc2-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="63cc2-108">Nombre de qubits sur lesquels l’entrée encodée est définie.</span><span class="sxs-lookup"><span data-stu-id="63cc2-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="63cc2-109">Prepare [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) : l' => [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="63cc2-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="63cc2-110">Opération qui prépare l’entrée encodée sur un registre Little endian de `NQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="63cc2-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>