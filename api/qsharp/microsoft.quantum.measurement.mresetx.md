---
uid: Microsoft.Quantum.Measurement.MResetX
title: Opération MResetX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: a16d7405388b560edcdb6c36b6668791f7ba1398
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709080"
---
# <a name="mresetx-operation"></a><span data-ttu-id="5f8e6-102">Opération MResetX</span><span class="sxs-lookup"><span data-stu-id="5f8e6-102">MResetX operation</span></span>

<span data-ttu-id="5f8e6-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="5f8e6-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="5f8e6-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5f8e6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5f8e6-105">Mesure un qubit unique dans la base X et le réinitialise à un état initial fixe à la suite de la mesure.</span><span class="sxs-lookup"><span data-stu-id="5f8e6-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="5f8e6-106">Description</span><span class="sxs-lookup"><span data-stu-id="5f8e6-106">Description</span></span>

<span data-ttu-id="5f8e6-107">Effectue une mesure de qubit unique dans le $X $-base, et garantit que le qubit est retourné à $ \ket {0} $ à la suite de la mesure.</span><span class="sxs-lookup"><span data-stu-id="5f8e6-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="5f8e6-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="5f8e6-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="5f8e6-109">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5f8e6-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5f8e6-110">Qubit unique à mesurer.</span><span class="sxs-lookup"><span data-stu-id="5f8e6-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="5f8e6-111">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="5f8e6-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="5f8e6-112">Résultat de la mesure `target` dans le Pauli $X $.</span><span class="sxs-lookup"><span data-stu-id="5f8e6-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>