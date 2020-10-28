---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702550"
---
# <a name="bitfliprecoveryfn-function"></a><span data-ttu-id="ee16c-102">BitFlipRecoveryFn fonction)</span><span class="sxs-lookup"><span data-stu-id="ee16c-102">BitFlipRecoveryFn function</span></span>

<span data-ttu-id="ee16c-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ee16c-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ee16c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ee16c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ee16c-105">Fonction pour les opérations de récupération Pauli pour une mesure de syndrome donnée par recherche de table pour le code de retournement ⟦ 3, 1 ⟧ bits.</span><span class="sxs-lookup"><span data-stu-id="ee16c-105">Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.</span></span>

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="ee16c-106">Sortie : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="ee16c-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="ee16c-107">Fonction de type `RecoveryFn` qui prend une mesure de syndrome `Result[]` et retourne les `Pauli[]` opérations qui corrigent l’erreur détectée.</span><span class="sxs-lookup"><span data-stu-id="ee16c-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee16c-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee16c-108">See Also</span></span>

- [<span data-ttu-id="ee16c-109">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="ee16c-109">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)