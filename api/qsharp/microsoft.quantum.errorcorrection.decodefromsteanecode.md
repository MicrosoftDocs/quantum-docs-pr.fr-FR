---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: Opération DecodeFromSteaneCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: e6831a8630c0a80c2abe7c4a720263f0de03edc4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702517"
---
# <a name="decodefromsteanecode-operation"></a><span data-ttu-id="144ae-102">Opération DecodeFromSteaneCode</span><span class="sxs-lookup"><span data-stu-id="144ae-102">DecodeFromSteaneCode operation</span></span>

<span data-ttu-id="144ae-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="144ae-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="144ae-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="144ae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="144ae-105">Opération d’encodage inverse qui mappe un registre quantique non encodé à un registre quantique encodé sous le code Quantum ⟦ 7, 1, 3 ⟧ Steane.</span><span class="sxs-lookup"><span data-stu-id="144ae-105">An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="144ae-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="144ae-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="144ae-107">logicalRegister : [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="144ae-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="144ae-108">Tableau de qubits représentant l’état logique de code 5-qubit encodé.</span><span class="sxs-lookup"><span data-stu-id="144ae-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="144ae-109">Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="144ae-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="144ae-110">Tableau qubit de longueur 1 représentant l’état non encodé dans le premier paramètre, avec qubits auxiliaire dans le deuxième paramètre.</span><span class="sxs-lookup"><span data-stu-id="144ae-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="144ae-111">Notes</span><span class="sxs-lookup"><span data-stu-id="144ae-111">Remarks</span></span>

<span data-ttu-id="144ae-112">Le décodeur choisi utilise la propriété de code CSS du code Steane ⟦ 7, 1, 3 ⟧, c.-à-d., il corrige les erreurs X et Z séparément.</span><span class="sxs-lookup"><span data-stu-id="144ae-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="144ae-113">Une propriété du code est que l’emplacement de la correction Z, respectivement, à appliquer est l’encodage 3 bits du X, respectivement, le syndrome Z lorsqu’il est considéré comme un entier.</span><span class="sxs-lookup"><span data-stu-id="144ae-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="144ae-114">Références</span><span class="sxs-lookup"><span data-stu-id="144ae-114">References</span></span>

- <span data-ttu-id="144ae-115">D.</span><span class="sxs-lookup"><span data-stu-id="144ae-115">D.</span></span> <span data-ttu-id="144ae-116">Gottesman, « codes stabilisants et correction des erreurs Quantum », doctorat. thèse, Caltech, 1997 ; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="144ae-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="144ae-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="144ae-117">See Also</span></span>

- [<span data-ttu-id="144ae-118">Microsoft. Quantum. ErrorCorrection. SteaneCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="144ae-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [<span data-ttu-id="144ae-119">Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="144ae-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [<span data-ttu-id="144ae-120">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="144ae-120">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)