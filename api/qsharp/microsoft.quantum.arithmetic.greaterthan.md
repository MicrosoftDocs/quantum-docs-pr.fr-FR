---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan, opération
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 553efb0fc83f24235cb4a77933bd1d547bbd1fed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846628"
---
# <a name="greaterthan-operation"></a><span data-ttu-id="d6aee-102">GreaterThan, opération</span><span class="sxs-lookup"><span data-stu-id="d6aee-102">GreaterThan operation</span></span>

<span data-ttu-id="d6aee-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d6aee-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d6aee-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d6aee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d6aee-105">Applique une comparaison « supérieur à » entre deux entiers encodés dans des registres qubit, en retournant un qubit cible en fonction du résultat de la comparaison.</span><span class="sxs-lookup"><span data-stu-id="d6aee-105">Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.</span></span>

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d6aee-106">Description</span><span class="sxs-lookup"><span data-stu-id="d6aee-106">Description</span></span>

<span data-ttu-id="d6aee-107">Effectue une comparaison strictement supérieure à deux entiers $x $ et $y $, encodés dans qubit inscrit XS et distinctes.</span><span class="sxs-lookup"><span data-stu-id="d6aee-107">Carries out a strictly greater than comparison of two integers $x$ and $y$, encoded in qubit registers xs and ys.</span></span> <span data-ttu-id="d6aee-108">Si $x > y $, le résultat qubit sera retourné, sinon le qubit de résultat conservera son état.</span><span class="sxs-lookup"><span data-stu-id="d6aee-108">If $x > y$, then the result qubit will be flipped, otherwise the result qubit will retain its state.</span></span>

## <a name="input"></a><span data-ttu-id="d6aee-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="d6aee-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d6aee-110">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d6aee-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d6aee-111">LittleEndian qubit Register Encoding le premier entier $x $.</span><span class="sxs-lookup"><span data-stu-id="d6aee-111">LittleEndian qubit register encoding the first integer $x$.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="d6aee-112">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d6aee-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d6aee-113">LittleEndian qubit Register Encoding le deuxième entier $y $.</span><span class="sxs-lookup"><span data-stu-id="d6aee-113">LittleEndian qubit register encoding the second integer $y$.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="d6aee-114">résultat : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d6aee-114">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d6aee-115">Qubit unique qui sera retournée si $x > y.</span><span class="sxs-lookup"><span data-stu-id="d6aee-115">Single qubit that will be flipped if $x > y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d6aee-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6aee-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d6aee-117">Notes</span><span class="sxs-lookup"><span data-stu-id="d6aee-117">Remarks</span></span>

<span data-ttu-id="d6aee-118">Utilise l’astuce qui $x-y = (x' + y) ' $, où’désigne le complément à 1.</span><span class="sxs-lookup"><span data-stu-id="d6aee-118">Uses the trick that $x - y = (x'+y)'$, where ' denotes the one's complement.</span></span>

## <a name="references"></a><span data-ttu-id="d6aee-119">Références</span><span class="sxs-lookup"><span data-stu-id="d6aee-119">References</span></span>

- <span data-ttu-id="d6aee-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton : « A New Quantum ondulation-Carry apporting circuit », 2004.</span><span class="sxs-lookup"><span data-stu-id="d6aee-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1

- <span data-ttu-id="d6aee-121">Thomas Haener, Martin Roetteler, Krysta M. Svore : « factorisation à l’aide de 2n + 2 qubits avec multiplication modulaire basée sur Toffoli », 2016 https://arxiv.org/abs/1611.07995</span><span class="sxs-lookup"><span data-stu-id="d6aee-121">Thomas Haener, Martin Roetteler, Krysta M. Svore: "Factoring using 2n+2 qubits with Toffoli based modular multiplication", 2016 https://arxiv.org/abs/1611.07995</span></span>