---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Opération FiveQubitCodeEncoderImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 0a40d9674c011567b2fa9c838f31a0ee115e4268
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826081"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="582c5-102">Opération FiveQubitCodeEncoderImpl</span><span class="sxs-lookup"><span data-stu-id="582c5-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="582c5-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="582c5-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="582c5-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="582c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="582c5-105">Opération privée utilisée pour implémenter à la fois l’encodeur et le décodeur 5 qubit.</span><span class="sxs-lookup"><span data-stu-id="582c5-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="582c5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="582c5-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="582c5-107">données : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="582c5-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="582c5-108">tableau contenant 1 qubit qui est le qubit d’entrée.</span><span class="sxs-lookup"><span data-stu-id="582c5-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="582c5-109">Scratch : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="582c5-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="582c5-110">tableau contenant 4 qubits qui ajoutent une redondance.</span><span class="sxs-lookup"><span data-stu-id="582c5-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="582c5-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="582c5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="582c5-112">Notes</span><span class="sxs-lookup"><span data-stu-id="582c5-112">Remarks</span></span>

<span data-ttu-id="582c5-113">L’encodeur choisi a été prélevé sur le papier V. Kliuchnikov et D. Maslov, « optimisation des circuits Clifford », «phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) et requiert un total de 11 portes.</span><span class="sxs-lookup"><span data-stu-id="582c5-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>