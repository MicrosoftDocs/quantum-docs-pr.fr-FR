---
uid: Microsoft.Quantum.Measurement.MResetY
title: Opération MResetY
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709083"
---
# <a name="mresety-operation"></a><span data-ttu-id="2070f-102">Opération MResetY</span><span class="sxs-lookup"><span data-stu-id="2070f-102">MResetY operation</span></span>

<span data-ttu-id="2070f-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="2070f-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="2070f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2070f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2070f-105">Mesure un qubit unique dans la base Y et le réinitialise à un état initial fixe à la suite de la mesure.</span><span class="sxs-lookup"><span data-stu-id="2070f-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="2070f-106">Description</span><span class="sxs-lookup"><span data-stu-id="2070f-106">Description</span></span>

<span data-ttu-id="2070f-107">Effectue une mesure de qubit unique dans le $Y $-base, et garantit que le qubit est retourné à $ \ket {0} $ à la suite de la mesure.</span><span class="sxs-lookup"><span data-stu-id="2070f-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="2070f-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="2070f-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="2070f-109">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2070f-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2070f-110">Qubit unique à mesurer.</span><span class="sxs-lookup"><span data-stu-id="2070f-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="2070f-111">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="2070f-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="2070f-112">Résultat de la mesure `target` dans le Pauli $Y $.</span><span class="sxs-lookup"><span data-stu-id="2070f-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>