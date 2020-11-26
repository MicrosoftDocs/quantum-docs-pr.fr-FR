---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: ReversedOpLEC fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 8c91391691b23786df02ae2a35264b578dccad41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222080"
---
# <a name="reversedoplec-function"></a><span data-ttu-id="405ad-102">ReversedOpLEC fonction)</span><span class="sxs-lookup"><span data-stu-id="405ad-102">ReversedOpLEC function</span></span>

<span data-ttu-id="405ad-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="405ad-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="405ad-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="405ad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="405ad-105">À partir d’une opération qui prend une entrée de primauté des octets de poids faible, retourne une nouvelle opération qui prend une entrée de poids fort (Big-endian).</span><span class="sxs-lookup"><span data-stu-id="405ad-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="405ad-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="405ad-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="405ad-107">OP : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian est CTL</span><span class="sxs-lookup"><span data-stu-id="405ad-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="405ad-108">Opération dont l’entrée doit être inversée.</span><span class="sxs-lookup"><span data-stu-id="405ad-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-ctl"></a><span data-ttu-id="405ad-109">Sortie : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) l' => [unité](xref:microsoft.quantum.lang-ref.unit) bigEndian est CTL</span><span class="sxs-lookup"><span data-stu-id="405ad-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="405ad-110">Nouvelle opération qui accepte son entrée sous la forme d’un registre Big-endian.</span><span class="sxs-lookup"><span data-stu-id="405ad-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="405ad-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="405ad-111">See Also</span></span>

- [<span data-ttu-id="405ad-112">Microsoft. Quantum. Arithmetic. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="405ad-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="405ad-113">Microsoft. Quantum. Arithmetic. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="405ad-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="405ad-114">Microsoft. Quantum. Arithmetic. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="405ad-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="405ad-115">Microsoft. Quantum. Arithmetic. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="405ad-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)