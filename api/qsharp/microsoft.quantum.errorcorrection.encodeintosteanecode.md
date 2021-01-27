---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: Opération EncodeIntoSteaneCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 2f65423a17dafadd1f9f10a07335150dfc8bf886
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826207"
---
# <a name="encodeintosteanecode-operation"></a><span data-ttu-id="2c4d3-102">Opération EncodeIntoSteaneCode</span><span class="sxs-lookup"><span data-stu-id="2c4d3-102">EncodeIntoSteaneCode operation</span></span>

<span data-ttu-id="2c4d3-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="2c4d3-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="2c4d3-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2c4d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2c4d3-105">Opération d’encodage qui mappe un registre quantique non encodé à un registre quantique encodé sous le code Quantum ⟦ 7, 1, 3 ⟧ Steane.</span><span class="sxs-lookup"><span data-stu-id="2c4d3-105">An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="2c4d3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2c4d3-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="2c4d3-107">physRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2c4d3-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2c4d3-108">Un registre qubit qui contient l’État Quantum non encodé</span><span class="sxs-lookup"><span data-stu-id="2c4d3-108">A qubit register which holds the an unencoded quantum state</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="2c4d3-109">auxQubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2c4d3-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2c4d3-110">Un registre qubit qui est initialement zéro et qui est ajouté au système Quantum pour permettre l’exécution d’une opération d’encodage</span><span class="sxs-lookup"><span data-stu-id="2c4d3-110">A qubit register which is initially zero and which gets added to the quantum system so that an encoding operation can be performed</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="2c4d3-111">Sortie : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="2c4d3-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="2c4d3-112">Registre quantique contenant l’état après l’application de l’encodeur Steane</span><span class="sxs-lookup"><span data-stu-id="2c4d3-112">A quantum register holding the state after the Steane encoder has been applied</span></span>

## <a name="see-also"></a><span data-ttu-id="2c4d3-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c4d3-113">See Also</span></span>

- [<span data-ttu-id="2c4d3-114">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="2c4d3-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="2c4d3-115">Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="2c4d3-115">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)