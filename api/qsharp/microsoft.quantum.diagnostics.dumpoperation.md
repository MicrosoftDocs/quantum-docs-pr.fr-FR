---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Opération DumpOperation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: 444d42e2440b30b3bdf50d55a399568bed063222
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702706"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="82124-102">Opération DumpOperation</span><span class="sxs-lookup"><span data-stu-id="82124-102">DumpOperation operation</span></span>

<span data-ttu-id="82124-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="82124-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="82124-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82124-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82124-105">Pour une opération donnée, affiche des diagnostics sur l’opération qui sont rendues disponibles par la cible d’exécution actuelle.</span><span class="sxs-lookup"><span data-stu-id="82124-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="82124-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="82124-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="82124-107">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82124-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="82124-108">Nombre de qubits sur lequel l’opération donnée agit.</span><span class="sxs-lookup"><span data-stu-id="82124-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit-adj"></a><span data-ttu-id="82124-109">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="82124-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="82124-110">Opération à diagnostiquer.</span><span class="sxs-lookup"><span data-stu-id="82124-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="82124-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="82124-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="82124-112">Notes</span><span class="sxs-lookup"><span data-stu-id="82124-112">Remarks</span></span>

<span data-ttu-id="82124-113">L’appel de cette opération n’a aucun effet observable à partir de Q #.</span><span class="sxs-lookup"><span data-stu-id="82124-113">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="82124-114">Les diagnostics précis qui s’affichent, le cas échéant, dépendent de la cible d’exécution actuelle et de l’environnement de l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="82124-114">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="82124-115">Par exemple, lorsqu’il est utilisé sur le simulateur Quantum à état complet, une matrice d’unités utilisée pour représenter `op` est affichée.</span><span class="sxs-lookup"><span data-stu-id="82124-115">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="82124-116">Notez que, lorsqu’il est exécuté sur des simulateurs qui reconnaissent une ambiguïté de phase globale (par exemple, le simulateur d’état complet), les représentations retournées peuvent varier jusqu’à une phase globale.</span><span class="sxs-lookup"><span data-stu-id="82124-116">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="82124-117">De même, le classement des représentations de matrices de lignes et de colonnes peut varier selon les conventions utilisées par chaque simulateur qui prend en charge cette opération.</span><span class="sxs-lookup"><span data-stu-id="82124-117">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>