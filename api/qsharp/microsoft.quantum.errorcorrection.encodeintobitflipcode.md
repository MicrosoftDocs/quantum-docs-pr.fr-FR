---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: Opération EncodeIntoBitFlipCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 44034a864c946a7d3dbb21bad5ee500660709f1a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826673"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="9436a-102">Opération EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="9436a-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="9436a-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="9436a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="9436a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9436a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9436a-105">Encode le code [3, 1, 3]/⟦ 3, 1, 1 ⟧.</span><span class="sxs-lookup"><span data-stu-id="9436a-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="9436a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9436a-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="9436a-107">physRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9436a-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9436a-108">Registre de qubits physique représentant les données à protéger.</span><span class="sxs-lookup"><span data-stu-id="9436a-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="9436a-109">auxQubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9436a-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9436a-110">Un registre des qubits auxiliaires initialement dans l’État $ \ket {00} $ à utiliser pour l’encodage des données à protéger.</span><span class="sxs-lookup"><span data-stu-id="9436a-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="9436a-111">Sortie : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="9436a-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="9436a-112">Qubits physique et auxiliaire utilisés dans l’encodage, représentés sous la forme d’un registre logique.</span><span class="sxs-lookup"><span data-stu-id="9436a-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="9436a-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9436a-113">See Also</span></span>

- [<span data-ttu-id="9436a-114">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="9436a-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)