---
uid: Microsoft.Quantum.Canon.RAll0
title: Opération RAll0
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: 660e6633df6750747963d41a6ff28a4fd4b02d4e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840248"
---
# <a name="rall0-operation"></a><span data-ttu-id="5c938-102">Opération RAll0</span><span class="sxs-lookup"><span data-stu-id="5c938-102">RAll0 operation</span></span>

<span data-ttu-id="5c938-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5c938-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5c938-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c938-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5c938-105">Effectue une opération de décalage de phase.</span><span class="sxs-lookup"><span data-stu-id="5c938-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="5c938-106">$R = \boldone-(1-e ^ {i \Phi}) \ket{0\cdots 0} \bra{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="5c938-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5c938-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="5c938-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="5c938-108">phase : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5c938-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5c938-109">La phase $ \Phi $ appliquée à l’État $ \ket{0\cdots 0} \bra{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="5c938-109">The phase $\phi$ applied to state $\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5c938-110">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5c938-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5c938-111">Registre dont l’État doit être pivoté par $R $.</span><span class="sxs-lookup"><span data-stu-id="5c938-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5c938-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5c938-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="5c938-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5c938-113">See Also</span></span>

- [<span data-ttu-id="5c938-114">Microsoft. Quantum. Canon. RAll1</span><span class="sxs-lookup"><span data-stu-id="5c938-114">Microsoft.Quantum.Canon.RAll1</span></span>](xref:Microsoft.Quantum.Canon.RAll1)