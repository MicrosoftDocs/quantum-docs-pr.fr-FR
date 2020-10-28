---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: Opération ApplyMultiplyControlledLowDepthAnd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 6900f9b0f014fba28ae73a70f180f3e4696900cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705187"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="14862-102">Opération ApplyMultiplyControlledLowDepthAnd</span><span class="sxs-lookup"><span data-stu-id="14862-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="14862-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="14862-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="14862-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="14862-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="14862-105">Implémente une porte Toffoli à plusieurs contrôleurs, en supposant que la cible qubit est initialisée 0.</span><span class="sxs-lookup"><span data-stu-id="14862-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="14862-106">L’opération joint part du principe que le qubit cible sera réinitialisé à 0.</span><span class="sxs-lookup"><span data-stu-id="14862-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="14862-107">Requiert une profondeur de 1, tandis que le nombre de qubits d’assistance est exponentiel dans le nombre de qubits.</span><span class="sxs-lookup"><span data-stu-id="14862-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="14862-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="14862-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="14862-109">contrôles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="14862-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="14862-110">Qubits de contrôle</span><span class="sxs-lookup"><span data-stu-id="14862-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="14862-111">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="14862-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="14862-112">Qubit cible</span><span class="sxs-lookup"><span data-stu-id="14862-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="14862-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14862-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

