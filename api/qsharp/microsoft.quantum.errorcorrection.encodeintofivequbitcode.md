---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Opération EncodeIntoFiveQubitCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 1bccf46453ad34199dcebc5bcff693359fe2254c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826321"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="46961-102">Opération EncodeIntoFiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="46961-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="46961-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="46961-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="46961-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="46961-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="46961-105">Encode le code Quantum ⟦ 5, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="46961-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="46961-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="46961-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="46961-107">physRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="46961-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="46961-108">Qubit représentant un État non encodé.</span><span class="sxs-lookup"><span data-stu-id="46961-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="46961-109">Ce tableau `Qubit[]` a une longueur de 1.</span><span class="sxs-lookup"><span data-stu-id="46961-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="46961-110">auxQubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="46961-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="46961-111">Registre de qubits auxiliaires qui sera utilisé pour représenter l’État encodé.</span><span class="sxs-lookup"><span data-stu-id="46961-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="46961-112">Sortie : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="46961-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="46961-113">Tableau de qubits physiques de type `LogicalRegister` qui stocke l’État encodé.</span><span class="sxs-lookup"><span data-stu-id="46961-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="46961-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46961-114">See Also</span></span>

- [<span data-ttu-id="46961-115">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="46961-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)