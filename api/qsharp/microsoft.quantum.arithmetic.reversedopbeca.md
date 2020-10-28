---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBECA
title: ReversedOpBECA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBECA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5617e191260903ac25effc8b922810932b7dc505
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706307"
---
# <a name="reversedopbeca-function"></a><span data-ttu-id="4af19-102">ReversedOpBECA fonction)</span><span class="sxs-lookup"><span data-stu-id="4af19-102">ReversedOpBECA function</span></span>

<span data-ttu-id="4af19-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4af19-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4af19-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4af19-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4af19-105">À partir d’une opération qui prend une entrée de poids fort, retourne une nouvelle opération qui prend une entrée de primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="4af19-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="4af19-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="4af19-106">Input</span></span>

### <a name="op--bigendian--unit-adj--ctl"></a><span data-ttu-id="4af19-107">OP : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) d' => [unité](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="4af19-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="4af19-108">Opération dont l’entrée doit être inversée.</span><span class="sxs-lookup"><span data-stu-id="4af19-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="4af19-109">Sortie : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unité](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="4af19-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="4af19-110">Nouvelle opération qui accepte son entrée comme Registre Little endian.</span><span class="sxs-lookup"><span data-stu-id="4af19-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="4af19-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4af19-111">See Also</span></span>

- [<span data-ttu-id="4af19-112">Microsoft. Quantum. Arithmetic. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="4af19-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
- [<span data-ttu-id="4af19-113">Microsoft. Quantum. Arithmetic. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="4af19-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="4af19-114">Microsoft. Quantum. Arithmetic. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="4af19-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="4af19-115">Microsoft. Quantum. Arithmetic. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="4af19-115">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)