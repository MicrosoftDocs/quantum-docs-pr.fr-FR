---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853055"
---
# <a name="steanecode-function"></a><span data-ttu-id="f0e79-102">SteaneCode fonction)</span><span class="sxs-lookup"><span data-stu-id="f0e79-102">SteaneCode function</span></span>

<span data-ttu-id="f0e79-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f0e79-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f0e79-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0e79-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0e79-105">Retourne une valeur CSS représentant l’encodeur de code ⟦ 7, 1, 3 ⟧ Steane et le décodeur avec mesure de syndrome sur place.</span><span class="sxs-lookup"><span data-stu-id="f0e79-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="f0e79-106">Sortie : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="f0e79-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="f0e79-107">Objet de type CSS qui collecte toutes les données pertinentes pour effectuer l’encodage et la correction d’erreur pour le code Steane 7, 1, 3 ⟧ ⟦.</span><span class="sxs-lookup"><span data-stu-id="f0e79-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0e79-108">Notes</span><span class="sxs-lookup"><span data-stu-id="f0e79-108">Remarks</span></span>

<span data-ttu-id="f0e79-109">Ce code a été trouvé dans le document suivant :</span><span class="sxs-lookup"><span data-stu-id="f0e79-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="f0e79-110">R.</span><span class="sxs-lookup"><span data-stu-id="f0e79-110">A.</span></span> <span data-ttu-id="f0e79-111">Steane, « plusieurs interférences de particule et correction d’erreur quantique », proc.</span><span class="sxs-lookup"><span data-stu-id="f0e79-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="f0e79-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="f0e79-112">Roy.</span></span> <span data-ttu-id="f0e79-113">SOC. lond.</span><span class="sxs-lookup"><span data-stu-id="f0e79-113">Soc. Lond.</span></span> <span data-ttu-id="f0e79-114">A452 (1996) pp. 2551 ; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="f0e79-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>