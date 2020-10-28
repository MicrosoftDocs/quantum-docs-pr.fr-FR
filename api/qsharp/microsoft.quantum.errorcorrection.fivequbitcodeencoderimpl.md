---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Opération FiveQubitCodeEncoderImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 29b0f47ddffeae3ed4dfda4084304427418e02fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702481"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="9838b-102">Opération FiveQubitCodeEncoderImpl</span><span class="sxs-lookup"><span data-stu-id="9838b-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="9838b-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="9838b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="9838b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9838b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9838b-105">Opération privée utilisée pour implémenter à la fois l’encodeur et le décodeur 5 qubit.</span><span class="sxs-lookup"><span data-stu-id="9838b-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9838b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9838b-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="9838b-107">données : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9838b-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9838b-108">tableau contenant 1 qubit qui est le qubit d’entrée.</span><span class="sxs-lookup"><span data-stu-id="9838b-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="9838b-109">Scratch : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9838b-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9838b-110">tableau contenant 4 qubits qui ajoutent une redondance.</span><span class="sxs-lookup"><span data-stu-id="9838b-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9838b-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9838b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9838b-112">Notes</span><span class="sxs-lookup"><span data-stu-id="9838b-112">Remarks</span></span>

<span data-ttu-id="9838b-113">L’encodeur choisi a été prélevé sur le papier V. Kliuchnikov et D. Maslov, « optimisation des circuits Clifford », «phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) et requiert un total de 11 portes.</span><span class="sxs-lookup"><span data-stu-id="9838b-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>