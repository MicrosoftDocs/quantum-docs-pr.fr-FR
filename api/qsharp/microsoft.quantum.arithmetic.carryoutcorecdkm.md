---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: Opération CarryOutCoreCDKM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707398"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="d9a43-102">Opération CarryOutCoreCDKM</span><span class="sxs-lookup"><span data-stu-id="d9a43-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="d9a43-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d9a43-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d9a43-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9a43-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9a43-105">L’opération de base dans le RippleCarryAdderCDKM, utilisée avec l’opération ApplyOuterCDKMAdder ci-dessus, c’est-à-dire conjuguée avec cette opération pour obtenir le fonctionnement interne du RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="d9a43-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="d9a43-106">Cette opération calcule le qubit d’exécution et applique une séquence de non-portes sur une partie de l’entrée `ys` .</span><span class="sxs-lookup"><span data-stu-id="d9a43-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d9a43-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="d9a43-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d9a43-108">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d9a43-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d9a43-109">Premier registre qubit.</span><span class="sxs-lookup"><span data-stu-id="d9a43-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="d9a43-110">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d9a43-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d9a43-111">Deuxième Registre qubit.</span><span class="sxs-lookup"><span data-stu-id="d9a43-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="d9a43-112">Ancilla : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d9a43-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d9a43-113">Ancilla qubit utilisé dans RippleCarryAdderCDKM passé à cette opération.</span><span class="sxs-lookup"><span data-stu-id="d9a43-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="d9a43-114">transporter : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d9a43-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d9a43-115">Exécutez qubit dans l’opération RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="d9a43-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d9a43-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9a43-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="d9a43-117">Références</span><span class="sxs-lookup"><span data-stu-id="d9a43-117">References</span></span>

- <span data-ttu-id="d9a43-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton : « A New Quantum ondulation-Carry apporting circuit », 2004.</span><span class="sxs-lookup"><span data-stu-id="d9a43-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1