---
uid: Microsoft.Quantum.Canon.RAll0
title: Opération RAll0
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: bd1f796209a15f290315e55b872ae3b3e508a68b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205658"
---
# <a name="rall0-operation"></a><span data-ttu-id="c42e4-102">Opération RAll0</span><span class="sxs-lookup"><span data-stu-id="c42e4-102">RAll0 operation</span></span>

<span data-ttu-id="c42e4-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c42e4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c42e4-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c42e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c42e4-105">Effectue une opération de décalage de phase.</span><span class="sxs-lookup"><span data-stu-id="c42e4-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="c42e4-106">$R = \boldone-(1-e ^ {i \Phi}) \ket{0\cdots 0} \bra{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="c42e4-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c42e4-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="c42e4-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="c42e4-108">phase : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c42e4-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c42e4-109">La phase $ \Phi $ appliquée à l’État $ \ket{0\cdots 0} \bra{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="c42e4-109">The phase $\phi$ applied to state $\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c42e4-110">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c42e4-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c42e4-111">Registre dont l’État doit être pivoté par $R $.</span><span class="sxs-lookup"><span data-stu-id="c42e4-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c42e4-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c42e4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c42e4-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c42e4-113">See Also</span></span>

- [<span data-ttu-id="c42e4-114">Microsoft. Quantum. Canon. RAll1</span><span class="sxs-lookup"><span data-stu-id="c42e4-114">Microsoft.Quantum.Canon.RAll1</span></span>](xref:Microsoft.Quantum.Canon.RAll1)