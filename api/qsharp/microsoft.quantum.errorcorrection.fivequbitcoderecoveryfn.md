---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 94b6c12f31b0e6367151d0ebb225cff5f82915e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853124"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="b29cf-102">FiveQubitCodeRecoveryFn fonction)</span><span class="sxs-lookup"><span data-stu-id="b29cf-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="b29cf-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="b29cf-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="b29cf-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b29cf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b29cf-105">Retourne une fonction qui mappe les mesures de syndrome d’erreur aux opérateurs Pauli de correction des erreurs appropriés par recherche de table pour le code Quantum ⟦ 5, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="b29cf-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="b29cf-106">Sortie : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="b29cf-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="b29cf-107">Fonction de type `RecoveryFn` qui prend une mesure de syndrome `Result[]` et retourne les `Pauli[]` opérateurs qui corrigent l’erreur détectée.</span><span class="sxs-lookup"><span data-stu-id="b29cf-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="b29cf-108">Notes</span><span class="sxs-lookup"><span data-stu-id="b29cf-108">Remarks</span></span>

<span data-ttu-id="b29cf-109">En effectuant une itération sur toutes les erreurs de poids $1 $, nous obtenons un total de $3 \ Times 5 = 15 $ de syndromes non triviales possibles.</span><span class="sxs-lookup"><span data-stu-id="b29cf-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="b29cf-110">Avec l’identité, un tableau d’erreurs et le syndrome correspondant sont générés.</span><span class="sxs-lookup"><span data-stu-id="b29cf-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="b29cf-111">Pour le code 5 qubit, cette table est donnée par : $X \_ 1 : (0, 0, 0, 1); X \_ 2 : (1,0, 0, 0); X \_ 3 : (1, 1, 0, 0); X \_ 4 : (0, 1, 1, 0); X \_ 5 : (0, 0, 1, 1) $, $Z \_ 1 : (1, 0, 1, 0); Z \_ 2 : (0, 1, 0, 1); Z \_ 3 : (0, 0, 1, 0); Z \_ 4 : (1, 0, 0, 1); Z \_ 5 : (0, 1, 0, 0) $ avec $Y _i $ obtenue en ajoutant le $X _i $ et $Z _i $ syndromes.</span><span class="sxs-lookup"><span data-stu-id="b29cf-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="b29cf-112">Notez que le classement de la récupération de la table de recherche est donné en convertissant le bitvectors en entiers (à l’aide de Little endian).</span><span class="sxs-lookup"><span data-stu-id="b29cf-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="b29cf-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b29cf-113">See Also</span></span>

- [<span data-ttu-id="b29cf-114">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="b29cf-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)