---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: Opération ApplyMultiplyControlledLowDepthAnd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 1aeab429bd6304c621e0d5225b43a76eab607c84
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209194"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="5fad4-102">Opération ApplyMultiplyControlledLowDepthAnd</span><span class="sxs-lookup"><span data-stu-id="5fad4-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="5fad4-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5fad4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5fad4-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5fad4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5fad4-105">Implémente une porte Toffoli à plusieurs contrôleurs, en supposant que la cible qubit est initialisée 0.</span><span class="sxs-lookup"><span data-stu-id="5fad4-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="5fad4-106">L’opération joint part du principe que le qubit cible sera réinitialisé à 0.</span><span class="sxs-lookup"><span data-stu-id="5fad4-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="5fad4-107">Requiert une profondeur de 1, tandis que le nombre de qubits d’assistance est exponentiel dans le nombre de qubits.</span><span class="sxs-lookup"><span data-stu-id="5fad4-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="5fad4-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="5fad4-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="5fad4-109">contrôles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5fad4-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5fad4-110">Qubits de contrôle</span><span class="sxs-lookup"><span data-stu-id="5fad4-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="5fad4-111">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5fad4-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5fad4-112">Qubit cible</span><span class="sxs-lookup"><span data-stu-id="5fad4-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="5fad4-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5fad4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

