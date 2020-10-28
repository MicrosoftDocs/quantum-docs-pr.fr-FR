---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Opération EncodeIntoFiveQubitCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: c9df4c5c98a78cae8b3af4597020d35469454153
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702508"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="0e4d3-102">Opération EncodeIntoFiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="0e4d3-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="0e4d3-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="0e4d3-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="0e4d3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0e4d3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0e4d3-105">Encode le code Quantum ⟦ 5, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="0e4d3-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="0e4d3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="0e4d3-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="0e4d3-107">physRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0e4d3-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0e4d3-108">Qubit représentant un État non encodé.</span><span class="sxs-lookup"><span data-stu-id="0e4d3-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="0e4d3-109">Ce tableau `Qubit[]` a une longueur de 1.</span><span class="sxs-lookup"><span data-stu-id="0e4d3-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="0e4d3-110">auxQubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0e4d3-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0e4d3-111">Registre de qubits auxiliaires qui sera utilisé pour représenter l’État encodé.</span><span class="sxs-lookup"><span data-stu-id="0e4d3-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="0e4d3-112">Sortie : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="0e4d3-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="0e4d3-113">Tableau de qubits physiques de type `LogicalRegister` qui stocke l’État encodé.</span><span class="sxs-lookup"><span data-stu-id="0e4d3-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e4d3-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0e4d3-114">See Also</span></span>

- [<span data-ttu-id="0e4d3-115">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="0e4d3-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)