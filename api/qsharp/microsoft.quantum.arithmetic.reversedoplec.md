---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: ReversedOpLEC fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 3a4872be6b81498c26ab9a14134940c5ef8628b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706286"
---
# <a name="reversedoplec-function"></a><span data-ttu-id="4c18d-102">ReversedOpLEC fonction)</span><span class="sxs-lookup"><span data-stu-id="4c18d-102">ReversedOpLEC function</span></span>

<span data-ttu-id="4c18d-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4c18d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4c18d-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4c18d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4c18d-105">À partir d’une opération qui prend une entrée de primauté des octets de poids faible, retourne une nouvelle opération qui prend une entrée de poids fort (Big-endian).</span><span class="sxs-lookup"><span data-stu-id="4c18d-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="4c18d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="4c18d-106">Input</span></span>

### <a name="op--littleendian--unit-ctl"></a><span data-ttu-id="4c18d-107">OP : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) d' => [unités](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="4c18d-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="4c18d-108">Opération dont l’entrée doit être inversée.</span><span class="sxs-lookup"><span data-stu-id="4c18d-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-ctl"></a><span data-ttu-id="4c18d-109">Sortie : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => liste CTL d' [unités](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="4c18d-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="4c18d-110">Nouvelle opération qui accepte son entrée sous la forme d’un registre Big-endian.</span><span class="sxs-lookup"><span data-stu-id="4c18d-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c18d-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c18d-111">See Also</span></span>

- [<span data-ttu-id="4c18d-112">Microsoft. Quantum. Arithmetic. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="4c18d-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="4c18d-113">Microsoft. Quantum. Arithmetic. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="4c18d-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="4c18d-114">Microsoft. Quantum. Arithmetic. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="4c18d-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="4c18d-115">Microsoft. Quantum. Arithmetic. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="4c18d-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)