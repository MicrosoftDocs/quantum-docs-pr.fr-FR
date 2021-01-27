---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Opération ApproximateQFT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 31fd87c0f61292142c7493cc29cad1082a9a2d67
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850320"
---
# <a name="approximateqft-operation"></a><span data-ttu-id="9ef05-102">Opération ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="9ef05-102">ApproximateQFT operation</span></span>

<span data-ttu-id="9ef05-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9ef05-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9ef05-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9ef05-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9ef05-105">Appliquez la transformation de Fourier quantique approximative (AQFT) à un registre Quantum.</span><span class="sxs-lookup"><span data-stu-id="9ef05-105">Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.</span></span>

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9ef05-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9ef05-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="9ef05-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9ef05-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9ef05-108">paramètre de approximation qui détermine à quel niveau les rotations Z contrôlées qui se produisent dans le circuit QFT sont nettoyées.</span><span class="sxs-lookup"><span data-stu-id="9ef05-108">approximation parameter which determines at which level the controlled Z-rotations that occur in the QFT circuit are pruned.</span></span>

<span data-ttu-id="9ef05-109">Le paramètre approximatif a détermine le niveau de nettoyage des rotations Z, c’est-à-dire un ∈ {0.. n} et toutes les rotations de Z 2π/2k où k>a sont supprimés du circuit QFT.</span><span class="sxs-lookup"><span data-stu-id="9ef05-109">The approximation parameter a determines the pruning level of the Z-rotations, i.e., a ∈ {0..n} and all Z-rotations 2π/2ᵏ where k>a are removed from the QFT circuit.</span></span> <span data-ttu-id="9ef05-110">Il est connu que, pour k >= log ₂ (n) + Journal ₂ (1/ε) + 3, une liaison peut être liée | | QFT-AQFT | |<ε.</span><span class="sxs-lookup"><span data-stu-id="9ef05-110">It is known that for k >= log₂(n)+log₂(1/ε)+3 one can bound ||QFT-AQFT||<ε.</span></span>


### <a name="qs--bigendian"></a><span data-ttu-id="9ef05-111">QS : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="9ef05-111">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="9ef05-112">Registre quantique de n qubits auquel la transformation de Fourier quantique approximative est appliquée.</span><span class="sxs-lookup"><span data-stu-id="9ef05-112">quantum register of n qubits to which the Approximate Quantum Fourier Transform is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9ef05-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ef05-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9ef05-114">Notes</span><span class="sxs-lookup"><span data-stu-id="9ef05-114">Remarks</span></span>

<span data-ttu-id="9ef05-115">AQFT requiert des portes de rotation Z de la forme 2π/2k et des portes Hadarmard.</span><span class="sxs-lookup"><span data-stu-id="9ef05-115">AQFT requires Z-rotation gates of the form 2π/2ᵏ and Hadamard gates.</span></span>

<span data-ttu-id="9ef05-116">L’entrée et la sortie sont supposées être encodées en encodage Big endian.</span><span class="sxs-lookup"><span data-stu-id="9ef05-116">The input and output are assumed to be encoded in big endian encoding.</span></span>

## <a name="references"></a><span data-ttu-id="9ef05-117">Références</span><span class="sxs-lookup"><span data-stu-id="9ef05-117">References</span></span>

- [<span data-ttu-id="9ef05-118">*M. Roetteler, Th. Beth*, Appl. algèbre eng. commun. Terminé. 19 (3) : 177-193 (2008)</span><span class="sxs-lookup"><span data-stu-id="9ef05-118"> *M. Roetteler, Th. Beth*, Appl. Algebra Eng. Commun. Comput. 19(3): 177-193 (2008) </span></span>](http://doi.org/10.1007/s00200-008-0072-2)
- [<span data-ttu-id="9ef05-119">*D. Coppersmith* arXiv : quant-pH/0201067v1</span><span class="sxs-lookup"><span data-stu-id="9ef05-119"> *D. Coppersmith* arXiv:quant-ph/0201067v1 </span></span>](https://arxiv.org/abs/quant-ph/0201067)