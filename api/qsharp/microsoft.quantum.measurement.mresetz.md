---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Opération MResetZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 494f11c8129175ddd84c6539f5e9df1a758e8a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194132"
---
# <a name="mresetz-operation"></a><span data-ttu-id="8d55d-102">Opération MResetZ</span><span class="sxs-lookup"><span data-stu-id="8d55d-102">MResetZ operation</span></span>

<span data-ttu-id="8d55d-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="8d55d-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="8d55d-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8d55d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8d55d-105">Mesure un qubit unique dans la base Z et le réinitialise à un état initial fixe à la suite de la mesure.</span><span class="sxs-lookup"><span data-stu-id="8d55d-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="8d55d-106">Description</span><span class="sxs-lookup"><span data-stu-id="8d55d-106">Description</span></span>

<span data-ttu-id="8d55d-107">Effectue une mesure de qubit unique dans le $Z $-base, et garantit que le qubit est retourné à $ \ket {0} $ à la suite de la mesure.</span><span class="sxs-lookup"><span data-stu-id="8d55d-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="8d55d-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="8d55d-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="8d55d-109">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8d55d-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8d55d-110">Qubit unique à mesurer.</span><span class="sxs-lookup"><span data-stu-id="8d55d-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="8d55d-111">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="8d55d-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="8d55d-112">Résultat de la mesure `target` dans le Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="8d55d-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>