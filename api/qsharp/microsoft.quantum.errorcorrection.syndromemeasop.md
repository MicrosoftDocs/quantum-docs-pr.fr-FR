---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Type défini par l’utilisateur SyndromeMeasOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850051"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="fbc39-102">Type défini par l’utilisateur SyndromeMeasOp</span><span class="sxs-lookup"><span data-stu-id="fbc39-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="fbc39-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="fbc39-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="fbc39-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fbc39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fbc39-105">Représente une opération utilisée pour mesurer le syndrome d’un bloc de code de correction des erreurs.</span><span class="sxs-lookup"><span data-stu-id="fbc39-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a><span data-ttu-id="fbc39-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="fbc39-106">Example</span></span>

<span data-ttu-id="fbc39-107">Mesurez les syndromes du code de retournement binaire $S = \langle ZZI, IZZ \rangle $ à l’aide de Scratch qubits en mode non tolérant aux pannes :</span><span class="sxs-lookup"><span data-stu-id="fbc39-107">Measure syndromes for the bit-flip code $S = \langle ZZI, IZZ \rangle$ using scratch qubits in a non–fault tolerant manner:</span></span>

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a><span data-ttu-id="fbc39-108">Notes</span><span class="sxs-lookup"><span data-stu-id="fbc39-108">Remarks</span></span>

<span data-ttu-id="fbc39-109">La signature `(LogicalRegister => Syndrome)` représente une opération qui agit conjointement avec le qubits dans `LogicalRegister` et certains qubits auxiliaires suivis d’une mesure du qubits auxiliaire pour extraire une `Syndrome` valeur représentant le `Result[]` de ces mesures.</span><span class="sxs-lookup"><span data-stu-id="fbc39-109">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbc39-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fbc39-110">See Also</span></span>

- [<span data-ttu-id="fbc39-111">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="fbc39-111">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="fbc39-112">Microsoft. Quantum. ErrorCorrection. syndrome</span><span class="sxs-lookup"><span data-stu-id="fbc39-112">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)