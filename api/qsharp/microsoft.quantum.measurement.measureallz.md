---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Opération MeasureAllZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701941"
---
# <a name="measureallz-operation"></a><span data-ttu-id="0dce2-102">Opération MeasureAllZ</span><span class="sxs-lookup"><span data-stu-id="0dce2-102">MeasureAllZ operation</span></span>

<span data-ttu-id="0dce2-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="0dce2-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="0dce2-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0dce2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0dce2-105">Mesure conjointement un registre de qubits dans la base Z Pauli.</span><span class="sxs-lookup"><span data-stu-id="0dce2-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="0dce2-106">Description</span><span class="sxs-lookup"><span data-stu-id="0dce2-106">Description</span></span>

<span data-ttu-id="0dce2-107">Mesure un registre de qubits dans la $Z \otimes Z \otimes \cdots \otimes Z $, représentant la parité de l’intégralité du Registre.</span><span class="sxs-lookup"><span data-stu-id="0dce2-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="0dce2-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="0dce2-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="0dce2-109">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0dce2-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0dce2-110">Registre à mesurer.</span><span class="sxs-lookup"><span data-stu-id="0dce2-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="0dce2-111">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="0dce2-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="0dce2-112">Résultat de la mesure de $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="0dce2-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>