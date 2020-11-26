---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: Opération SteaneCodeEncoderImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: 3a9a1b11ed9255f18135e3717de7e9e1ec891298
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200423"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="e0558-102">Opération SteaneCodeEncoderImpl</span><span class="sxs-lookup"><span data-stu-id="e0558-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="e0558-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e0558-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e0558-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0558-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0558-105">Opération privée utilisée pour implémenter à la fois l’encodeur et le décodeur du code Steane.</span><span class="sxs-lookup"><span data-stu-id="e0558-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="e0558-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e0558-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="e0558-107">données : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e0558-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e0558-108">tableau contenant 1 qubit qui est le qubit d’entrée.</span><span class="sxs-lookup"><span data-stu-id="e0558-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="e0558-109">Scratch : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e0558-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e0558-110">tableau contenant 6 qubits qui ajoutent une redondance.</span><span class="sxs-lookup"><span data-stu-id="e0558-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e0558-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e0558-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

