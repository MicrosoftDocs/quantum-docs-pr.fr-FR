---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 0f6b987ca23bd9ff2076080d60f1ca756b36848e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702394"
---
# <a name="steanecoderecoveryx-function"></a><span data-ttu-id="65faf-102">SteaneCodeRecoveryX fonction)</span><span class="sxs-lookup"><span data-stu-id="65faf-102">SteaneCodeRecoveryX function</span></span>

<span data-ttu-id="65faf-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="65faf-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="65faf-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="65faf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="65faf-105">Décodeur de la partie X du groupe stabilisant du code Quantum ⟦ 7, 1, 3 ⟧ Steane.</span><span class="sxs-lookup"><span data-stu-id="65faf-105">Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="65faf-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="65faf-106">Input</span></span>

### <a name="syndrome--syndrome"></a><span data-ttu-id="65faf-107">syndrome : [syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="65faf-107">syndrome : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="65faf-108">Tableau de syndromes obtenu à partir de la mesure de la partie X du stabilisateur.</span><span class="sxs-lookup"><span data-stu-id="65faf-108">A syndrome array obtained from measuring the X-part of the stabilizer.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="65faf-109">Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="65faf-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="65faf-110">Tableau d’opérations Pauli qui, lorsqu’il est appliqué au système Quantum encodé, corrige l’erreur correspondant à `syndrome` .</span><span class="sxs-lookup"><span data-stu-id="65faf-110">An array of Pauli operations which, when applied to the encoded quantum system corrects the error corresponding to `syndrome`.</span></span>

## <a name="remarks"></a><span data-ttu-id="65faf-111">Notes</span><span class="sxs-lookup"><span data-stu-id="65faf-111">Remarks</span></span>

<span data-ttu-id="65faf-112">Le décodeur choisi utilise la propriété de code CSS du code Steane ⟦ 7, 1, 3 ⟧, c.-à-d., il corrige les erreurs X et Z séparément.</span><span class="sxs-lookup"><span data-stu-id="65faf-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="65faf-113">Une propriété du code est que l’emplacement de la correction Z, respectivement, à appliquer est l’encodage 3 bits du X, respectivement, le syndrome Z lorsqu’il est considéré comme un entier.</span><span class="sxs-lookup"><span data-stu-id="65faf-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="65faf-114">Références</span><span class="sxs-lookup"><span data-stu-id="65faf-114">References</span></span>

- <span data-ttu-id="65faf-115">D.</span><span class="sxs-lookup"><span data-stu-id="65faf-115">D.</span></span> <span data-ttu-id="65faf-116">Gottesman, « codes stabilisants et correction des erreurs Quantum », doctorat. thèse, Caltech, 1997 ; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="65faf-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="65faf-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65faf-117">See Also</span></span>

- [<span data-ttu-id="65faf-118">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="65faf-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="65faf-119">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="65faf-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)