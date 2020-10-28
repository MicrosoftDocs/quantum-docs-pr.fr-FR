---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: ReversedOpBE fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 170f63e60e6c26dbdd33af02c6a3387a1b3dbc44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706331"
---
# <a name="reversedopbe-function"></a><span data-ttu-id="86d50-102">ReversedOpBE fonction)</span><span class="sxs-lookup"><span data-stu-id="86d50-102">ReversedOpBE function</span></span>

<span data-ttu-id="86d50-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="86d50-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="86d50-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="86d50-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="86d50-105">À partir d’une opération qui prend une entrée de poids fort, retourne une nouvelle opération qui prend une entrée de primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="86d50-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="86d50-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="86d50-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="86d50-107">OP : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unité](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="86d50-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="86d50-108">Opération dont l’entrée doit être inversée.</span><span class="sxs-lookup"><span data-stu-id="86d50-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit"></a><span data-ttu-id="86d50-109">Sortie : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="86d50-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="86d50-110">Nouvelle opération qui accepte son entrée comme Registre Little endian.</span><span class="sxs-lookup"><span data-stu-id="86d50-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="86d50-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="86d50-111">See Also</span></span>

- [<span data-ttu-id="86d50-112">Microsoft. Quantum. Arithmetic. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="86d50-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="86d50-113">Microsoft. Quantum. Arithmetic. ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="86d50-113">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="86d50-114">Microsoft. Quantum. Arithmetic. ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="86d50-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="86d50-115">Microsoft. Quantum. Arithmetic. ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="86d50-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)