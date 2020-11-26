---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Opération MeasureAllZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227078"
---
# <a name="measureallz-operation"></a><span data-ttu-id="396a2-102">Opération MeasureAllZ</span><span class="sxs-lookup"><span data-stu-id="396a2-102">MeasureAllZ operation</span></span>

<span data-ttu-id="396a2-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="396a2-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="396a2-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="396a2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="396a2-105">Mesure conjointement un registre de qubits dans la base Z Pauli.</span><span class="sxs-lookup"><span data-stu-id="396a2-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="396a2-106">Description</span><span class="sxs-lookup"><span data-stu-id="396a2-106">Description</span></span>

<span data-ttu-id="396a2-107">Mesure un registre de qubits dans la $Z \otimes Z \otimes \cdots \otimes Z $, représentant la parité de l’intégralité du Registre.</span><span class="sxs-lookup"><span data-stu-id="396a2-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="396a2-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="396a2-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="396a2-109">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="396a2-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="396a2-110">Registre à mesurer.</span><span class="sxs-lookup"><span data-stu-id="396a2-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="396a2-111">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="396a2-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="396a2-112">Résultat de la mesure de $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="396a2-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>