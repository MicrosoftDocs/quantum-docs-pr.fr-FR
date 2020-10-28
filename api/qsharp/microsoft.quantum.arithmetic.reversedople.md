---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 6ebc4e97cb6d515e99e85922d03ca246b56084ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706294"
---
# <a name="reversedople-function"></a><span data-ttu-id="94d27-102">ReversedOpLE fonction)</span><span class="sxs-lookup"><span data-stu-id="94d27-102">ReversedOpLE function</span></span>

<span data-ttu-id="94d27-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="94d27-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="94d27-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="94d27-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="94d27-105">À partir d’une opération qui prend une entrée de primauté des octets de poids faible, retourne une nouvelle opération qui prend une entrée de poids fort (Big-endian).</span><span class="sxs-lookup"><span data-stu-id="94d27-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="94d27-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="94d27-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="94d27-107">OP : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="94d27-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="94d27-108">Opération dont l’entrée doit être inversée.</span><span class="sxs-lookup"><span data-stu-id="94d27-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="94d27-109">Sortie : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unité](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="94d27-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="94d27-110">Nouvelle opération qui accepte son entrée sous la forme d’un registre Big-endian.</span><span class="sxs-lookup"><span data-stu-id="94d27-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="94d27-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94d27-111">See Also</span></span>

- [<span data-ttu-id="94d27-112">Microsoft. Quantum. Arithmetic. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="94d27-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="94d27-113">Microsoft. Quantum. Arithmetic. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="94d27-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="94d27-114">Microsoft. Quantum. Arithmetic. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="94d27-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="94d27-115">Microsoft. Quantum. Arithmetic. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="94d27-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)