---
uid: Microsoft.Quantum.Intrinsic.M
title: Opération M
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: ced3a617a7299e169c7a58a1cd0f83f656b2f0b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212339"
---
# <a name="m-operation"></a><span data-ttu-id="14fad-102">Opération M</span><span class="sxs-lookup"><span data-stu-id="14fad-102">M operation</span></span>

<span data-ttu-id="14fad-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="14fad-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="14fad-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="14fad-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="14fad-105">Effectue une mesure d’un seul qubit dans le Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="14fad-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="14fad-106">Le résultat de la sortie est donné par la \begin{align} de distribution \Pr (\texttt{Zero} | \ket{\Psi}) = \braket{\Psi | 0} \braket{0 | \Psi}.</span><span class="sxs-lookup"><span data-stu-id="14fad-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="14fad-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="14fad-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="14fad-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="14fad-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="14fad-109">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="14fad-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="14fad-110">Qubit à mesurer.</span><span class="sxs-lookup"><span data-stu-id="14fad-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="14fad-111">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="14fad-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="14fad-112">`Zero` Si le eigenvalue $ + $1 est observé et `One` si le eigenvalue $-$1 est observé.</span><span class="sxs-lookup"><span data-stu-id="14fad-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="14fad-113">Notes</span><span class="sxs-lookup"><span data-stu-id="14fad-113">Remarks</span></span>

<span data-ttu-id="14fad-114">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="14fad-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```