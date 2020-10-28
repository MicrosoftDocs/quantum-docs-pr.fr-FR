---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: b2418911e71c0b98e1a78247b2ae066887d89cd8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706326"
---
# <a name="reversedopbea-function"></a><span data-ttu-id="1f497-102">ReversedOpBEA fonction)</span><span class="sxs-lookup"><span data-stu-id="1f497-102">ReversedOpBEA function</span></span>

<span data-ttu-id="1f497-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1f497-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1f497-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f497-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f497-105">À partir d’une opération qui prend une entrée de poids fort, retourne une nouvelle opération qui prend une entrée de primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="1f497-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="1f497-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1f497-106">Input</span></span>

### <a name="op--bigendian--unit-adj"></a><span data-ttu-id="1f497-107">opération : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="1f497-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1f497-108">Opération dont l’entrée doit être inversée.</span><span class="sxs-lookup"><span data-stu-id="1f497-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-adj"></a><span data-ttu-id="1f497-109">Sortie : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="1f497-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1f497-110">Nouvelle opération qui accepte son entrée comme Registre Little endian.</span><span class="sxs-lookup"><span data-stu-id="1f497-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f497-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1f497-111">See Also</span></span>

- [<span data-ttu-id="1f497-112">Microsoft. Quantum. Arithmetic. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="1f497-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="1f497-113">Microsoft. Quantum. Arithmetic. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="1f497-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="1f497-114">Microsoft. Quantum. Arithmetic. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="1f497-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="1f497-115">Microsoft. Quantum. Arithmetic. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="1f497-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)