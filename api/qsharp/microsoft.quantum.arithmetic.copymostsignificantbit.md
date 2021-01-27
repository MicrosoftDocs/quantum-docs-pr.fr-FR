---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Opération CopyMostSignificantBit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 609e937a03bebf45aa9398225bd1b7e2b717807a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843266"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="740c8-102">Opération CopyMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="740c8-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="740c8-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="740c8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="740c8-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="740c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="740c8-105">Copie le bit le plus significatif d’un registre qubit `from` qui représente un entier non signé dans le qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="740c8-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="740c8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="740c8-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="740c8-107">à partir de : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="740c8-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="740c8-108">Entier non signé à partir duquel le bit le plus élevé est copié.</span><span class="sxs-lookup"><span data-stu-id="740c8-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="740c8-109">l’entier est encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="740c8-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="740c8-110">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="740c8-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="740c8-111">Qubit dans lequel le bit le plus élevé est copié.</span><span class="sxs-lookup"><span data-stu-id="740c8-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="740c8-112">L’encodage de bits est basé sur le calcul.</span><span class="sxs-lookup"><span data-stu-id="740c8-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="740c8-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="740c8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="740c8-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="740c8-114">See Also</span></span>

- [<span data-ttu-id="740c8-115">Microsoft. Quantum. Arithmetic. LittleEndian</span><span class="sxs-lookup"><span data-stu-id="740c8-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)