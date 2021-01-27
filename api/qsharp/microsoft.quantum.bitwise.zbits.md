---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: d1ddc2a4cdbdfd3945885de856456b3108592594
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842056"
---
# <a name="zbits-function"></a><span data-ttu-id="d60c4-102">ZBits fonction)</span><span class="sxs-lookup"><span data-stu-id="d60c4-102">ZBits function</span></span>

<span data-ttu-id="d60c4-103">Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="d60c4-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="d60c4-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d60c4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d60c4-105">Retourne un entier représentant les bits Z d’un tableau d’opérateurs Pauli.</span><span class="sxs-lookup"><span data-stu-id="d60c4-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="d60c4-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d60c4-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="d60c4-107">Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="d60c4-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="d60c4-108">Tableau d’opérateurs Pauli à représenter sous la forme d’un entier.</span><span class="sxs-lookup"><span data-stu-id="d60c4-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="d60c4-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d60c4-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d60c4-110">Entier $x $ avec la représentation binaire $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, où $p _i = $0 si `paulis[i]` est `PauliI` ou `PauliX` et où $p _i = $1 si `paulis[i]` est `PauliY` ou `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="d60c4-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d60c4-111">Notes</span><span class="sxs-lookup"><span data-stu-id="d60c4-111">Remarks</span></span>

<span data-ttu-id="d60c4-112">La fonction lèvera une exception si la longueur du `paulis` tableau est supérieure à 63.</span><span class="sxs-lookup"><span data-stu-id="d60c4-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="d60c4-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d60c4-113">See Also</span></span>

- [<span data-ttu-id="d60c4-114">Microsoft. Quantum. bit. XBits</span><span class="sxs-lookup"><span data-stu-id="d60c4-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)