---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: Opération ApplyMultiplyControlledAnd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: 17a757278500833bc5a5d0635af020cfe1fd569f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218391"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="d034f-102">Opération ApplyMultiplyControlledAnd</span><span class="sxs-lookup"><span data-stu-id="d034f-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="d034f-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d034f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d034f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d034f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d034f-105">Implémente une porte Toffoli à plusieurs contrôleurs, en supposant que la cible qubit est initialisée 0.</span><span class="sxs-lookup"><span data-stu-id="d034f-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="d034f-106">L’opération joint part du principe que le qubit cible sera réinitialisé à 0.</span><span class="sxs-lookup"><span data-stu-id="d034f-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="d034f-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="d034f-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="d034f-108">contrôles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d034f-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d034f-109">Qubits de contrôle</span><span class="sxs-lookup"><span data-stu-id="d034f-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d034f-110">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d034f-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d034f-111">Qubit cible</span><span class="sxs-lookup"><span data-stu-id="d034f-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="d034f-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d034f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

