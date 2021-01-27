---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Opération AllowAtMostNQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 3aa80767ac0f752e7be0efa2966c580ca3cb8f19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830912"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="40af1-102">Opération AllowAtMostNQubits</span><span class="sxs-lookup"><span data-stu-id="40af1-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="40af1-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="40af1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="40af1-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="40af1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="40af1-105">Entre un appel à cette opération et son voisin, déclare qu’au plus un nombre donné de qubits supplémentaires sont alloués avec des instructions using.</span><span class="sxs-lookup"><span data-stu-id="40af1-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="40af1-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="40af1-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="40af1-107">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="40af1-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="40af1-108">Nombre maximal de qubits qui peuvent être alloués.</span><span class="sxs-lookup"><span data-stu-id="40af1-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="40af1-109">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="40af1-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="40af1-110">Message à afficher en cas d’échec.</span><span class="sxs-lookup"><span data-stu-id="40af1-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="40af1-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="40af1-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="40af1-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="40af1-112">Example</span></span>

<span data-ttu-id="40af1-113">L’extrait de code suivant échoue lorsqu’il est exécuté sur des ordinateurs qui prennent en charge ce diagnostic :</span><span class="sxs-lookup"><span data-stu-id="40af1-113">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
within {
    AllowAtMostNQubits(3, "Too many qubits allocated.");
} apply {
    // Fails since this allocates four qubits.
    using (register = Qubit[4]) {
    }
}
```

## <a name="remarks"></a><span data-ttu-id="40af1-114">Notes</span><span class="sxs-lookup"><span data-stu-id="40af1-114">Remarks</span></span>

<span data-ttu-id="40af1-115">Cette opération peut être remplacée par une absence d’opération sur les cibles qui ne la prennent pas en charge.</span><span class="sxs-lookup"><span data-stu-id="40af1-115">This operation may be replaced by a no-op on targets which do not support it.</span></span>