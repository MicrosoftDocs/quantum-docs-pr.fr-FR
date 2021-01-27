---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Opération DumpOperation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829279"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="c72a7-102">Opération DumpOperation</span><span class="sxs-lookup"><span data-stu-id="c72a7-102">DumpOperation operation</span></span>

<span data-ttu-id="c72a7-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c72a7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c72a7-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c72a7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c72a7-105">Pour une opération donnée, affiche des diagnostics sur l’opération qui sont rendues disponibles par la cible d’exécution actuelle.</span><span class="sxs-lookup"><span data-stu-id="c72a7-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="c72a7-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c72a7-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="c72a7-107">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c72a7-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c72a7-108">Nombre de qubits sur lequel l’opération donnée agit.</span><span class="sxs-lookup"><span data-stu-id="c72a7-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="c72a7-109">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="c72a7-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c72a7-110">Opération à diagnostiquer.</span><span class="sxs-lookup"><span data-stu-id="c72a7-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c72a7-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c72a7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="c72a7-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="c72a7-112">Example</span></span>

<span data-ttu-id="c72a7-113">Lorsqu’il est exécuté sur la cible du simulateur Quantum, l’extrait de code suivant génère la sortie de la matrice $ $ \begin{Aligned} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \end{Matrix}\right) \end{Aligned}.</span><span class="sxs-lookup"><span data-stu-id="c72a7-113">When run on the quantum simulator target, the following snippet will output the matrix $$ \begin{aligned} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \end{matrix}\right) \end{aligned}.</span></span>
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a><span data-ttu-id="c72a7-114">Notes</span><span class="sxs-lookup"><span data-stu-id="c72a7-114">Remarks</span></span>

<span data-ttu-id="c72a7-115">L’appel de cette opération n’a aucun effet observable à partir de Q #.</span><span class="sxs-lookup"><span data-stu-id="c72a7-115">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="c72a7-116">Les diagnostics précis qui s’affichent, le cas échéant, dépendent de la cible d’exécution actuelle et de l’environnement de l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="c72a7-116">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="c72a7-117">Par exemple, lorsqu’il est utilisé sur le simulateur Quantum à état complet, une matrice d’unités utilisée pour représenter `op` est affichée.</span><span class="sxs-lookup"><span data-stu-id="c72a7-117">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="c72a7-118">Notez que, lorsqu’il est exécuté sur des simulateurs qui reconnaissent une ambiguïté de phase globale (par exemple, le simulateur d’état complet), les représentations retournées peuvent varier jusqu’à une phase globale.</span><span class="sxs-lookup"><span data-stu-id="c72a7-118">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="c72a7-119">De même, le classement des représentations de matrices de lignes et de colonnes peut varier selon les conventions utilisées par chaque simulateur qui prend en charge cette opération.</span><span class="sxs-lookup"><span data-stu-id="c72a7-119">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>