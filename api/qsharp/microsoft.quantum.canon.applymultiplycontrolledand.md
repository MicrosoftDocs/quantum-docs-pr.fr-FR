---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: Opération ApplyMultiplyControlledAnd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: feca28d394e4af31eb4ffe737111d00ede45e27e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705190"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="f081d-102">Opération ApplyMultiplyControlledAnd</span><span class="sxs-lookup"><span data-stu-id="f081d-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="f081d-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f081d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f081d-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f081d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f081d-105">Implémente une porte Toffoli à plusieurs contrôleurs, en supposant que la cible qubit est initialisée 0.</span><span class="sxs-lookup"><span data-stu-id="f081d-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="f081d-106">L’opération joint part du principe que le qubit cible sera réinitialisé à 0.</span><span class="sxs-lookup"><span data-stu-id="f081d-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="f081d-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="f081d-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="f081d-108">contrôles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f081d-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f081d-109">Qubits de contrôle</span><span class="sxs-lookup"><span data-stu-id="f081d-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f081d-110">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f081d-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f081d-111">Qubit cible</span><span class="sxs-lookup"><span data-stu-id="f081d-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="f081d-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f081d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
