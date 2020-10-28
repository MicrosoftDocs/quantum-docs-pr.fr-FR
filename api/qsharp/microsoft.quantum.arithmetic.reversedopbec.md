---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: ReversedOpBEC fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5e9aa6e6dfef74bca004170cf2b1cd91aa13f0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706315"
---
# <a name="reversedopbec-function"></a><span data-ttu-id="c4273-102">ReversedOpBEC fonction)</span><span class="sxs-lookup"><span data-stu-id="c4273-102">ReversedOpBEC function</span></span>

<span data-ttu-id="c4273-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c4273-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c4273-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4273-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4273-105">À partir d’une opération qui prend une entrée de poids fort, retourne une nouvelle opération qui prend une entrée de primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="c4273-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="c4273-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c4273-106">Input</span></span>

### <a name="op--bigendian--unit-ctl"></a><span data-ttu-id="c4273-107">OP : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) d' => [unités](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="c4273-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c4273-108">Opération dont l’entrée doit être inversée.</span><span class="sxs-lookup"><span data-stu-id="c4273-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-ctl"></a><span data-ttu-id="c4273-109">Sortie : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => liste CTL d' [unités](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="c4273-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c4273-110">Nouvelle opération qui accepte son entrée comme Registre Little endian.</span><span class="sxs-lookup"><span data-stu-id="c4273-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4273-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c4273-111">See Also</span></span>

- [<span data-ttu-id="c4273-112">Microsoft. Quantum. Arithmetic. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="c4273-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="c4273-113">Microsoft. Quantum. Arithmetic. ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="c4273-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="c4273-114">Microsoft. Quantum. Arithmetic. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="c4273-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="c4273-115">Microsoft. Quantum. Arithmetic. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="c4273-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)