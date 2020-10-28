---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 91619803c7efe56e617b16637f5302aa0b7978ec
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705571"
---
# <a name="xbits-function"></a><span data-ttu-id="76122-102">XBits fonction)</span><span class="sxs-lookup"><span data-stu-id="76122-102">XBits function</span></span>

<span data-ttu-id="76122-103">Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="76122-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="76122-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76122-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="76122-105">Retourne un entier représentant les X bits d’un tableau d’opérateurs Pauli.</span><span class="sxs-lookup"><span data-stu-id="76122-105">Returns an integer representing the X bits of an array of Pauli operators.</span></span>

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="76122-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="76122-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="76122-107">Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="76122-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="76122-108">Tableau d’opérateurs Pauli à représenter sous la forme d’un entier.</span><span class="sxs-lookup"><span data-stu-id="76122-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="76122-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="76122-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="76122-110">Entier $x $ avec la représentation binaire $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, où $p _i = $0 si `paulis[i]` est `PauliI` ou `PauliZ` et où $p _i = $1 si `paulis[i]` est `PauliX` ou `PauliY` .</span><span class="sxs-lookup"><span data-stu-id="76122-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliZ` and where $p_i = 1$ if `paulis[i]` is `PauliX` or `PauliY`.</span></span>

## <a name="remarks"></a><span data-ttu-id="76122-111">Notes</span><span class="sxs-lookup"><span data-stu-id="76122-111">Remarks</span></span>

<span data-ttu-id="76122-112">La fonction lèvera une exception si la longueur du `paulis` tableau est supérieure à 63.</span><span class="sxs-lookup"><span data-stu-id="76122-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="76122-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="76122-113">See Also</span></span>

- [<span data-ttu-id="76122-114">Microsoft. Quantum. bit. ZBits</span><span class="sxs-lookup"><span data-stu-id="76122-114">Microsoft.Quantum.Bitwise.ZBits</span></span>](xref:Microsoft.Quantum.Bitwise.ZBits)