---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Type défini par l’utilisateur SyndromeMeasOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 1314e16d26c7310bab21caa91cb398d4b6f09b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702388"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="75f22-102">Type défini par l’utilisateur SyndromeMeasOp</span><span class="sxs-lookup"><span data-stu-id="75f22-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="75f22-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="75f22-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="75f22-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="75f22-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="75f22-105">Représente une opération utilisée pour mesurer le syndrome d’un bloc de code de correction des erreurs.</span><span class="sxs-lookup"><span data-stu-id="75f22-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="75f22-106">Notes</span><span class="sxs-lookup"><span data-stu-id="75f22-106">Remarks</span></span>

<span data-ttu-id="75f22-107">La signature `(LogicalRegister => Syndrome)` représente une opération qui agit conjointement avec le qubits dans `LogicalRegister` et certains qubits auxiliaires suivis d’une mesure du qubits auxiliaire pour extraire une `Syndrome` valeur représentant le `Result[]` de ces mesures.</span><span class="sxs-lookup"><span data-stu-id="75f22-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="75f22-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75f22-108">See Also</span></span>

- [<span data-ttu-id="75f22-109">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="75f22-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="75f22-110">Microsoft. Quantum. ErrorCorrection. syndrome</span><span class="sxs-lookup"><span data-stu-id="75f22-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)