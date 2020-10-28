---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: eabeb8e068ef32cf6717efd6e818271a667b39b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706291"
---
# <a name="reversedoplea-function"></a><span data-ttu-id="51cb3-102">ReversedOpLEA fonction)</span><span class="sxs-lookup"><span data-stu-id="51cb3-102">ReversedOpLEA function</span></span>

<span data-ttu-id="51cb3-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="51cb3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="51cb3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="51cb3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="51cb3-105">À partir d’une opération qui prend une entrée de primauté des octets de poids faible, retourne une nouvelle opération qui prend une entrée de poids fort (Big-endian).</span><span class="sxs-lookup"><span data-stu-id="51cb3-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="51cb3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="51cb3-106">Input</span></span>

### <a name="op--littleendian--unit-adj"></a><span data-ttu-id="51cb3-107">opération : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="51cb3-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="51cb3-108">Opération dont l’entrée doit être inversée.</span><span class="sxs-lookup"><span data-stu-id="51cb3-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-adj"></a><span data-ttu-id="51cb3-109">Sortie : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="51cb3-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="51cb3-110">Nouvelle opération qui accepte son entrée sous la forme d’un registre Big-endian.</span><span class="sxs-lookup"><span data-stu-id="51cb3-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="51cb3-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="51cb3-111">See Also</span></span>

- [<span data-ttu-id="51cb3-112">Microsoft. Quantum. Arithmetic. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="51cb3-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="51cb3-113">Microsoft. Quantum. Arithmetic. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="51cb3-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="51cb3-114">Microsoft. Quantum. Arithmetic. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="51cb3-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="51cb3-115">Microsoft. Quantum. Arithmetic. ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="51cb3-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)