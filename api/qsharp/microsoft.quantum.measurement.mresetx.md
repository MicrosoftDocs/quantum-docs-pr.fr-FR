---
uid: Microsoft.Quantum.Measurement.MResetX
title: Opération MResetX
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 44459e681daf1d28ce7d45f91ad59059babe5716
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853758"
---
# <a name="mresetx-operation"></a><span data-ttu-id="2fab5-102">Opération MResetX</span><span class="sxs-lookup"><span data-stu-id="2fab5-102">MResetX operation</span></span>

<span data-ttu-id="2fab5-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="2fab5-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="2fab5-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2fab5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2fab5-105">Mesure un qubit unique dans la base X et le réinitialise à un état initial fixe à la suite de la mesure.</span><span class="sxs-lookup"><span data-stu-id="2fab5-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="2fab5-106">Description</span><span class="sxs-lookup"><span data-stu-id="2fab5-106">Description</span></span>

<span data-ttu-id="2fab5-107">Effectue une mesure de qubit unique dans le $X $-base, et garantit que le qubit est retourné à $ \ket {0} $ à la suite de la mesure.</span><span class="sxs-lookup"><span data-stu-id="2fab5-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="2fab5-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="2fab5-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="2fab5-109">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2fab5-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2fab5-110">Qubit unique à mesurer.</span><span class="sxs-lookup"><span data-stu-id="2fab5-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="2fab5-111">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="2fab5-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="2fab5-112">Résultat de la mesure `target` dans le Pauli $X $.</span><span class="sxs-lookup"><span data-stu-id="2fab5-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>