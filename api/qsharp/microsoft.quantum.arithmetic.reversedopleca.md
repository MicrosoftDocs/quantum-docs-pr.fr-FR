---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: ReversedOpLECA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: b5413e43ad50ba7252705ef53b21e63650dbb2a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706275"
---
# <a name="reversedopleca-function"></a><span data-ttu-id="1b179-102">ReversedOpLECA fonction)</span><span class="sxs-lookup"><span data-stu-id="1b179-102">ReversedOpLECA function</span></span>

<span data-ttu-id="1b179-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1b179-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1b179-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b179-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b179-105">À partir d’une opération qui prend une entrée de primauté des octets de poids faible, retourne une nouvelle opération qui prend une entrée de poids fort (Big-endian).</span><span class="sxs-lookup"><span data-stu-id="1b179-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="1b179-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1b179-106">Input</span></span>

### <a name="op--littleendian--unit-adj--ctl"></a><span data-ttu-id="1b179-107">OP : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) d' => [unité](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="1b179-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="1b179-108">Opération dont l’entrée doit être inversée.</span><span class="sxs-lookup"><span data-stu-id="1b179-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-adj--ctl"></a><span data-ttu-id="1b179-109">Sortie : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unité](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="1b179-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="1b179-110">Nouvelle opération qui accepte son entrée sous la forme d’un registre Big-endian.</span><span class="sxs-lookup"><span data-stu-id="1b179-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b179-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b179-111">See Also</span></span>

- [<span data-ttu-id="1b179-112">Microsoft. Quantum. Arithmetic. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="1b179-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [<span data-ttu-id="1b179-113">Microsoft. Quantum. Arithmetic. ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="1b179-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="1b179-114">Microsoft. Quantum. Arithmetic. ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="1b179-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="1b179-115">Microsoft. Quantum. Arithmetic. ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="1b179-115">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)