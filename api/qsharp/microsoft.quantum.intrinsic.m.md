---
uid: Microsoft.Quantum.Intrinsic.M
title: Opération M
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 0037d7f5ad060857c6ca2c863b1d24aca3e338cf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818870"
---
# <a name="m-operation"></a><span data-ttu-id="bda69-102">Opération M</span><span class="sxs-lookup"><span data-stu-id="bda69-102">M operation</span></span>

<span data-ttu-id="bda69-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="bda69-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="bda69-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bda69-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bda69-105">Effectue une mesure d’un seul qubit dans le Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="bda69-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="bda69-106">Le résultat de la sortie est donné par la \begin{align} de distribution \Pr (\texttt{Zero} | \ket{\Psi}) = \braket{\Psi | 0} \braket{0 | \Psi}.</span><span class="sxs-lookup"><span data-stu-id="bda69-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="bda69-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="bda69-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="bda69-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="bda69-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="bda69-109">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bda69-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bda69-110">Qubit à mesurer.</span><span class="sxs-lookup"><span data-stu-id="bda69-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="bda69-111">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="bda69-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="bda69-112">`Zero` Si le eigenvalue $ + $1 est observé et `One` si le eigenvalue $-$1 est observé.</span><span class="sxs-lookup"><span data-stu-id="bda69-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="bda69-113">Notes</span><span class="sxs-lookup"><span data-stu-id="bda69-113">Remarks</span></span>

<span data-ttu-id="bda69-114">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="bda69-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```