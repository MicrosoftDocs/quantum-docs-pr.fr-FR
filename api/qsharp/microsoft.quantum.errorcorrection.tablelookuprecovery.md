---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: e4136add99ab7fb6904d7cac3c7f3e5076cc3176
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213665"
---
# <a name="tablelookuprecovery-function"></a><span data-ttu-id="bde4a-102">TableLookupRecovery fonction)</span><span class="sxs-lookup"><span data-stu-id="bde4a-102">TableLookupRecovery function</span></span>

<span data-ttu-id="bde4a-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="bde4a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="bde4a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bde4a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bde4a-105">Pour une table d’opérations Pauli donnée sur un registre donné de qubits, cette fonction retourne un objet de type `RecoveryFn` qui contient toutes les informations nécessaires pour effectuer un décodage de recherche de table par rapport au tableau d’opérations Pauli donné.</span><span class="sxs-lookup"><span data-stu-id="bde4a-105">For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.</span></span>

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a><span data-ttu-id="bde4a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="bde4a-106">Input</span></span>

### <a name="table--pauli"></a><span data-ttu-id="bde4a-107">table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="bde4a-107">table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="bde4a-108">Table des opérations Pauli qui fonctionnent sur un registre qubit donné</span><span class="sxs-lookup"><span data-stu-id="bde4a-108">Table of Pauli operations that operate on a given qubit register</span></span>



## <a name="output--recoveryfn"></a><span data-ttu-id="bde4a-109">Sortie : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="bde4a-109">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="bde4a-110">Objet de type `RecoveryFn` , c’est-à-dire un mappage `Syndrome -> Pauli[]` qui associe à un tableau de syndrome donné une opération de correction Pauli correspondante.</span><span class="sxs-lookup"><span data-stu-id="bde4a-110">An object of type `RecoveryFn`, i.e., a map `Syndrome -> Pauli[]` that associates with a given syndrome array a corresponding Pauli correction operation.</span></span>