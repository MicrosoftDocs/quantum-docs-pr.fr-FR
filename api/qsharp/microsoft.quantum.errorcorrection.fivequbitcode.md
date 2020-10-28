---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702484"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="1e496-102">FiveQubitCode fonction)</span><span class="sxs-lookup"><span data-stu-id="1e496-102">FiveQubitCode function</span></span>

<span data-ttu-id="1e496-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="1e496-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="1e496-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e496-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1e496-105">Retourne une valeur QECC représentant l’encodeur de code ⟦ 5, 1, 3 ⟧ et un décodeur avec mesure de la syndrome sur place.</span><span class="sxs-lookup"><span data-stu-id="1e496-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="1e496-106">Sortie : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="1e496-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="1e496-107">Retourne une implémentation d’un code de correction d’erreur de Quantum en spécifiant un `QECC` type.</span><span class="sxs-lookup"><span data-stu-id="1e496-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="1e496-108">Notes</span><span class="sxs-lookup"><span data-stu-id="1e496-108">Remarks</span></span>

<span data-ttu-id="1e496-109">Ce code a été trouvé indépendamment dans les deux documents suivants :</span><span class="sxs-lookup"><span data-stu-id="1e496-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="1e496-110">C.</span><span class="sxs-lookup"><span data-stu-id="1e496-110">C.</span></span> <span data-ttu-id="1e496-111">H.</span><span class="sxs-lookup"><span data-stu-id="1e496-111">H.</span></span> <span data-ttu-id="1e496-112">Bennett, D. DiVincenzo, J. A.</span><span class="sxs-lookup"><span data-stu-id="1e496-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="1e496-113">Smolin et W. K.</span><span class="sxs-lookup"><span data-stu-id="1e496-113">Smolin and W. K.</span></span> <span data-ttu-id="1e496-114">Wootters, « enchevêtrement d’État mixte et correction d’erreur quantique », «phys. Rev. A, 54 (1996) pp. 3824-3851 ; https://arxiv.org/abs/quant-ph/9604024 et</span><span class="sxs-lookup"><span data-stu-id="1e496-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="1e496-115">R.</span><span class="sxs-lookup"><span data-stu-id="1e496-115">R.</span></span> <span data-ttu-id="1e496-116">Laflamme, C. Miquel, J. P.</span><span class="sxs-lookup"><span data-stu-id="1e496-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="1e496-117">Paz et W. H.</span><span class="sxs-lookup"><span data-stu-id="1e496-117">Paz and W. H.</span></span> <span data-ttu-id="1e496-118">Zurek, « code de correction d’erreur quantique parfait », « phys. Rev. Lett ».</span><span class="sxs-lookup"><span data-stu-id="1e496-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="1e496-119">77 (1996) pp. 198-201 ; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="1e496-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>