---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Opération MeasureAllZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854669"
---
# <a name="measureallz-operation"></a><span data-ttu-id="18cde-102">Opération MeasureAllZ</span><span class="sxs-lookup"><span data-stu-id="18cde-102">MeasureAllZ operation</span></span>

<span data-ttu-id="18cde-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="18cde-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="18cde-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="18cde-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="18cde-105">Mesure conjointement un registre de qubits dans la base Z Pauli.</span><span class="sxs-lookup"><span data-stu-id="18cde-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="18cde-106">Description</span><span class="sxs-lookup"><span data-stu-id="18cde-106">Description</span></span>

<span data-ttu-id="18cde-107">Mesure un registre de qubits dans la $Z \otimes Z \otimes \cdots \otimes Z $, représentant la parité de l’intégralité du Registre.</span><span class="sxs-lookup"><span data-stu-id="18cde-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="18cde-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="18cde-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="18cde-109">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="18cde-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="18cde-110">Registre à mesurer.</span><span class="sxs-lookup"><span data-stu-id="18cde-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="18cde-111">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="18cde-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="18cde-112">Résultat de la mesure de $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="18cde-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>