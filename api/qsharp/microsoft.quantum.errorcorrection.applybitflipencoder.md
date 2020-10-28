---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: Opération ApplyBitFlipEncoder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: 4d78cbb5892aabc600321185641bbf217bd4d745
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702559"
---
# <a name="applybitflipencoder-operation"></a><span data-ttu-id="e7cc7-102">Opération ApplyBitFlipEncoder</span><span class="sxs-lookup"><span data-stu-id="e7cc7-102">ApplyBitFlipEncoder operation</span></span>

<span data-ttu-id="e7cc7-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e7cc7-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e7cc7-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e7cc7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e7cc7-105">Opération privée utilisée pour implémenter à la fois le codeur et le décodeur de retournement de bits.</span><span class="sxs-lookup"><span data-stu-id="e7cc7-105">Private operation used to implement both the bit flip encoder and decoder.</span></span>

<span data-ttu-id="e7cc7-106">Notez que cet encodeur peut utiliser la récupération cohérente sur place, auquel cas il « provoquera » l’erreur décrite par l’état initial de `auxQubits` .</span><span class="sxs-lookup"><span data-stu-id="e7cc7-106">Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`.</span></span>
<span data-ttu-id="e7cc7-107">En particulier, si `auxQubits` est initialement dans l’État $ \ket {10} $, cela provoque une erreur $X _ 1 $ sur le qubit encodé.</span><span class="sxs-lookup"><span data-stu-id="e7cc7-107">In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.</span></span>

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e7cc7-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="e7cc7-108">Input</span></span>

### <a name="coherentrecovery--bool"></a><span data-ttu-id="e7cc7-109">coherentRecovery : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e7cc7-109">coherentRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="data--qubit"></a><span data-ttu-id="e7cc7-110">données : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e7cc7-110">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="scratch--qubit"></a><span data-ttu-id="e7cc7-111">Scratch : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e7cc7-111">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="e7cc7-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e7cc7-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="e7cc7-113">Références</span><span class="sxs-lookup"><span data-stu-id="e7cc7-113">References</span></span>

- <span data-ttu-id="e7cc7-114">doi : 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="e7cc7-114">doi:10.1103/PhysRevA.85.044302</span></span>