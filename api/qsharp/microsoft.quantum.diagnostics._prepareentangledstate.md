---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: opération de _prepareEntangledState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 5a74978a536a92dafae0b532805bd8e8ae1c888e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830986"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="a7dea-102">opération de _prepareEntangledState</span><span class="sxs-lookup"><span data-stu-id="a7dea-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="a7dea-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a7dea-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a7dea-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a7dea-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a7dea-105">À partir de deux registres, prépare l’état de l’enchevêtrement maximal entre chaque paire de qubits sur les registres respectifs.</span><span class="sxs-lookup"><span data-stu-id="a7dea-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="a7dea-106">Toutes les qubits doivent démarrer dans l’État | 0 ⟩.</span><span class="sxs-lookup"><span data-stu-id="a7dea-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="a7dea-107">Le résultat est que les paires correspondantes de qubits de chaque registre se trouvent dans la variable $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $.</span><span class="sxs-lookup"><span data-stu-id="a7dea-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a7dea-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="a7dea-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="a7dea-109">gauche : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a7dea-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a7dea-110">Un tableau qubit dans l’État $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="a7dea-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="a7dea-111">Right : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a7dea-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a7dea-112">Un tableau qubit dans l’État $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="a7dea-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="a7dea-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7dea-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

