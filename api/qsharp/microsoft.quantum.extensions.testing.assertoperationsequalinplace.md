---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualInPlace
title: Opération AssertOperationsEqualInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualInPlace has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 6d2ead95a60ed3cc8ee95fb7f91e1aa49d366a48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702199"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="2c233-102">Opération AssertOperationsEqualInPlace</span><span class="sxs-lookup"><span data-stu-id="2c233-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="2c233-103">Espace de noms : [Microsoft. Quantum. extensions. testing](xref:Microsoft.Quantum.Extensions.Testing)</span><span class="sxs-lookup"><span data-stu-id="2c233-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="2c233-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c233-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="2c233-105">AssertOperationsEqualInPlace est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="2c233-105">AssertOperationsEqualInPlace has been deprecated.</span></span> <span data-ttu-id="2c233-106">Utilisez plutôt <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace>.</span><span class="sxs-lookup"><span data-stu-id="2c233-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.</span></span>
>
> <span data-ttu-id="2c233-107">Utilisez @"microsoft.quantum.diagnostics.assertoperationsequalinplace".</span><span class="sxs-lookup"><span data-stu-id="2c233-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".</span></span>
> <span data-ttu-id="2c233-108">Notez que l’ordre des arguments pour cette opération a changé.</span><span class="sxs-lookup"><span data-stu-id="2c233-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualInPlace (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="2c233-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="2c233-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="2c233-110">réel : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c233-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit-adj"></a><span data-ttu-id="2c233-111">ATTENDU : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c233-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="2c233-112">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2c233-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="2c233-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c233-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

