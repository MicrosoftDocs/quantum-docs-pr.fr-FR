---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: Opération DecodeFromBitFlipCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: be6ad5fce9eeb3eea031ff301b78dbb3680b66f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702544"
---
# <a name="decodefrombitflipcode-operation"></a><span data-ttu-id="9326a-102">Opération DecodeFromBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="9326a-102">DecodeFromBitFlipCode operation</span></span>

<span data-ttu-id="9326a-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="9326a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="9326a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9326a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9326a-105">Décode à partir du code [3, 1, 3]/⟦ 3, 1, 1 ⟧.</span><span class="sxs-lookup"><span data-stu-id="9326a-105">Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="9326a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9326a-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="9326a-107">logicalRegister : [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="9326a-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="9326a-108">Bloc de code du code d’inversion de bits.</span><span class="sxs-lookup"><span data-stu-id="9326a-108">A code block of the bit-flip code.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="9326a-109">Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="9326a-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="9326a-110">Tuple des données encodées dans le registre logique, et qubits auxiliaire utilisé pour représenter le syndrome.</span><span class="sxs-lookup"><span data-stu-id="9326a-110">A tuple of the data encoded into the logical register, and the auxiliary qubits used to represent the syndrome.</span></span>

## <a name="see-also"></a><span data-ttu-id="9326a-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9326a-111">See Also</span></span>

- [<span data-ttu-id="9326a-112">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="9326a-112">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="9326a-113">Microsoft. Quantum. ErrorCorrection. EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="9326a-113">Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode</span></span>](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)