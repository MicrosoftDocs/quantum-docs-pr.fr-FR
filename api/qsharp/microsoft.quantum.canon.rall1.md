---
uid: Microsoft.Quantum.Canon.RAll1
title: Opération RAll1
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: 36e460f93b4349bc2e3da9bfb22cb0aa82ef1795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205528"
---
# <a name="rall1-operation"></a><span data-ttu-id="813a1-102">Opération RAll1</span><span class="sxs-lookup"><span data-stu-id="813a1-102">RAll1 operation</span></span>

<span data-ttu-id="813a1-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="813a1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="813a1-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="813a1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="813a1-105">Effectue une opération de décalage de phase.</span><span class="sxs-lookup"><span data-stu-id="813a1-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="813a1-106">$R = \boldone-(1-e ^ {i \Phi}) \ket{1\cdots 1} \bra{1\cdots 1} $.</span><span class="sxs-lookup"><span data-stu-id="813a1-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="813a1-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="813a1-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="813a1-108">phase : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="813a1-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="813a1-109">La phase $ \Phi $ appliquée à l’État $ \ket{1\cdots 1} \bra{1\cdots 1} $.</span><span class="sxs-lookup"><span data-stu-id="813a1-109">The phase $\phi$ applied to state $\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="813a1-110">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="813a1-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="813a1-111">Registre dont l’État doit être pivoté par $R $.</span><span class="sxs-lookup"><span data-stu-id="813a1-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="813a1-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="813a1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

