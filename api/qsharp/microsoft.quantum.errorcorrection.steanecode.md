---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702415"
---
# <a name="steanecode-function"></a><span data-ttu-id="05ca5-102">SteaneCode fonction)</span><span class="sxs-lookup"><span data-stu-id="05ca5-102">SteaneCode function</span></span>

<span data-ttu-id="05ca5-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="05ca5-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="05ca5-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05ca5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05ca5-105">Retourne une valeur CSS représentant l’encodeur de code ⟦ 7, 1, 3 ⟧ Steane et le décodeur avec mesure de syndrome sur place.</span><span class="sxs-lookup"><span data-stu-id="05ca5-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="05ca5-106">Sortie : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="05ca5-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="05ca5-107">Objet de type CSS qui collecte toutes les données pertinentes pour effectuer l’encodage et la correction d’erreur pour le code Steane 7, 1, 3 ⟧ ⟦.</span><span class="sxs-lookup"><span data-stu-id="05ca5-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="05ca5-108">Notes</span><span class="sxs-lookup"><span data-stu-id="05ca5-108">Remarks</span></span>

<span data-ttu-id="05ca5-109">Ce code a été trouvé dans le document suivant :</span><span class="sxs-lookup"><span data-stu-id="05ca5-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="05ca5-110">R.</span><span class="sxs-lookup"><span data-stu-id="05ca5-110">A.</span></span> <span data-ttu-id="05ca5-111">Steane, « plusieurs interférences de particule et correction d’erreur quantique », proc.</span><span class="sxs-lookup"><span data-stu-id="05ca5-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="05ca5-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="05ca5-112">Roy.</span></span> <span data-ttu-id="05ca5-113">SOC. lond.</span><span class="sxs-lookup"><span data-stu-id="05ca5-113">Soc. Lond.</span></span> <span data-ttu-id="05ca5-114">A452 (1996) pp. 2551 ; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="05ca5-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>