---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: Opération InjectPi4YRotation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702475"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="30fe3-102">Opération InjectPi4YRotation</span><span class="sxs-lookup"><span data-stu-id="30fe3-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="30fe3-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="30fe3-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="30fe3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="30fe3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="30fe3-105">Fait pivoter un qubit unique par π/4 autour de l’axe Y.</span><span class="sxs-lookup"><span data-stu-id="30fe3-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="30fe3-106">Description</span><span class="sxs-lookup"><span data-stu-id="30fe3-106">Description</span></span>

<span data-ttu-id="30fe3-107">Effectue une rotation π/4 autour de `Y` .</span><span class="sxs-lookup"><span data-stu-id="30fe3-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="30fe3-108">La rotation est effectuée en consommant un État magique ; autrement dit, une copie de l’État $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} .</span><span class="sxs-lookup"><span data-stu-id="30fe3-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="30fe3-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="30fe3-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="30fe3-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="30fe3-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="30fe3-111">données : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="30fe3-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="30fe3-112">Qubit à faire pivoter sur $Y $ par $ \pi/$4.</span><span class="sxs-lookup"><span data-stu-id="30fe3-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="30fe3-113">magie : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="30fe3-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="30fe3-114">Un qubit initialement dans l’État magique.</span><span class="sxs-lookup"><span data-stu-id="30fe3-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="30fe3-115">L’application suivante de cette opération, `magic` est retournée à l' {0} État $ \ket $.</span><span class="sxs-lookup"><span data-stu-id="30fe3-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="30fe3-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="30fe3-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="30fe3-117">Notes</span><span class="sxs-lookup"><span data-stu-id="30fe3-117">Remarks</span></span>

<span data-ttu-id="30fe3-118">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="30fe3-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="30fe3-119">et</span><span class="sxs-lookup"><span data-stu-id="30fe3-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="30fe3-120">Cette opération prend en charge `Adjoint` functor, auquel cas le même État magique est consommé, mais l’effet sur le qubit de données est un $-\ pi/4 $ $Y $-rotation.</span><span class="sxs-lookup"><span data-stu-id="30fe3-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>