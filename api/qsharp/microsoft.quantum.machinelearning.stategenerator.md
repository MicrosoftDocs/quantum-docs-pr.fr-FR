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
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="2ecba-102">Type défini par l’utilisateur StateGenerator</span><span class="sxs-lookup"><span data-stu-id="2ecba-102">StateGenerator user defined type</span></span>

<span data-ttu-id="2ecba-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2ecba-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2ecba-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2ecba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2ecba-105">Décrit une opération qui prépare une entrée donnée à un classifieur séquentiel.</span><span class="sxs-lookup"><span data-stu-id="2ecba-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="2ecba-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="2ecba-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="2ecba-107">NQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2ecba-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2ecba-108">Nombre de qubits sur lesquels l’entrée encodée est définie.</span><span class="sxs-lookup"><span data-stu-id="2ecba-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit-adj--ctl"></a><span data-ttu-id="2ecba-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="2ecba-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2ecba-110">Opération qui prépare l’entrée encodée sur un registre Little endian de `NQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="2ecba-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>