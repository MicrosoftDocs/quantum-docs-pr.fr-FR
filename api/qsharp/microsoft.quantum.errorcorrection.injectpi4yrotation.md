---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: Opération InjectPi4YRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 249c347c9e9729e719eda69e4e9a21847d9a46eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825942"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="84d18-102">Opération InjectPi4YRotation</span><span class="sxs-lookup"><span data-stu-id="84d18-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="84d18-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="84d18-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="84d18-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84d18-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84d18-105">Fait pivoter un qubit unique par π/4 autour de l’axe Y.</span><span class="sxs-lookup"><span data-stu-id="84d18-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="84d18-106">Description</span><span class="sxs-lookup"><span data-stu-id="84d18-106">Description</span></span>

<span data-ttu-id="84d18-107">Effectue une rotation π/4 autour de `Y` .</span><span class="sxs-lookup"><span data-stu-id="84d18-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="84d18-108">La rotation est effectuée en consommant un État magique ; autrement dit, une copie de l’État $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} .</span><span class="sxs-lookup"><span data-stu-id="84d18-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="84d18-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="84d18-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="84d18-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="84d18-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="84d18-111">données : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="84d18-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="84d18-112">Qubit à faire pivoter sur $Y $ par $ \pi/$4.</span><span class="sxs-lookup"><span data-stu-id="84d18-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="84d18-113">magie : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="84d18-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="84d18-114">Un qubit initialement dans l’État magique.</span><span class="sxs-lookup"><span data-stu-id="84d18-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="84d18-115">L’application suivante de cette opération, `magic` est retournée à l' {0} État $ \ket $.</span><span class="sxs-lookup"><span data-stu-id="84d18-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="84d18-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84d18-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="84d18-117">Notes</span><span class="sxs-lookup"><span data-stu-id="84d18-117">Remarks</span></span>

<span data-ttu-id="84d18-118">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="84d18-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="84d18-119">and</span><span class="sxs-lookup"><span data-stu-id="84d18-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="84d18-120">Cette opération prend en charge `Adjoint` functor, auquel cas le même État magique est consommé, mais l’effet sur le qubit de données est un $-\ pi/4 $ $Y $-rotation.</span><span class="sxs-lookup"><span data-stu-id="84d18-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>