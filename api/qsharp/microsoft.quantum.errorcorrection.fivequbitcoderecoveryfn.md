---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 5b8afe222d197eb7d342ac45f027f2de9130b61a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702478"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="e0a64-102">FiveQubitCodeRecoveryFn fonction)</span><span class="sxs-lookup"><span data-stu-id="e0a64-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="e0a64-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e0a64-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e0a64-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e0a64-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e0a64-105">Retourne une fonction qui mappe les mesures de syndrome d’erreur aux opérateurs Pauli de correction des erreurs appropriés par recherche de table pour le code Quantum ⟦ 5, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="e0a64-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="e0a64-106">Sortie : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="e0a64-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="e0a64-107">Fonction de type `RecoveryFn` qui prend une mesure de syndrome `Result[]` et retourne les `Pauli[]` opérateurs qui corrigent l’erreur détectée.</span><span class="sxs-lookup"><span data-stu-id="e0a64-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="e0a64-108">Notes</span><span class="sxs-lookup"><span data-stu-id="e0a64-108">Remarks</span></span>

<span data-ttu-id="e0a64-109">En effectuant une itération sur toutes les erreurs de poids $1 $, nous obtenons un total de $3 \ Times 5 = 15 $ de syndromes non triviales possibles.</span><span class="sxs-lookup"><span data-stu-id="e0a64-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="e0a64-110">Avec l’identité, un tableau d’erreurs et le syndrome correspondant sont générés.</span><span class="sxs-lookup"><span data-stu-id="e0a64-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="e0a64-111">Pour le code 5 qubit, cette table est donnée par : $X \_ 1 : (0, 0, 0, 1); X \_ 2 : (1,0, 0, 0); X \_ 3 : (1, 1, 0, 0); X \_ 4 : (0, 1, 1, 0); X \_ 5 : (0, 0, 1, 1) $, $Z \_ 1 : (1, 0, 1, 0); Z \_ 2 : (0, 1, 0, 1); Z \_ 3 : (0, 0, 1, 0); Z \_ 4 : (1, 0, 0, 1); Z \_ 5 : (0, 1, 0, 0) $ avec $Y _i $ obtenue en ajoutant le $X _i $ et $Z _i $ syndromes.</span><span class="sxs-lookup"><span data-stu-id="e0a64-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="e0a64-112">Notez que le classement de la récupération de la table de recherche est donné en convertissant le bitvectors en entiers (à l’aide de Little endian).</span><span class="sxs-lookup"><span data-stu-id="e0a64-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="e0a64-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e0a64-113">See Also</span></span>

- [<span data-ttu-id="e0a64-114">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="e0a64-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)