---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: Opération SteaneCodeEncoderImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702418"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="3e8d8-102">Opération SteaneCodeEncoderImpl</span><span class="sxs-lookup"><span data-stu-id="3e8d8-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="3e8d8-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="3e8d8-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="3e8d8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e8d8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e8d8-105">Opération privée utilisée pour implémenter à la fois l’encodeur et le décodeur du code Steane.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3e8d8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3e8d8-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="3e8d8-107">données : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3e8d8-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3e8d8-108">tableau contenant 1 qubit qui est le qubit d’entrée.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="3e8d8-109">Scratch : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3e8d8-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3e8d8-110">tableau contenant 6 qubits qui ajoutent une redondance.</span><span class="sxs-lookup"><span data-stu-id="3e8d8-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e8d8-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e8d8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
