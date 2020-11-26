---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Type défini par l’utilisateur ReflectionOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226653"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="0ffc1-102">Type défini par l’utilisateur ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="0ffc1-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="0ffc1-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="0ffc1-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="0ffc1-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0ffc1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0ffc1-105">Représente une réflexion Oracle.</span><span class="sxs-lookup"><span data-stu-id="0ffc1-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="0ffc1-106">Une réflexion Oracle, $O $, a des entrées :</span><span class="sxs-lookup"><span data-stu-id="0ffc1-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="0ffc1-107">Phase $ \Phi $ par laquelle faire pivoter le sous-espace réfléchi.</span><span class="sxs-lookup"><span data-stu-id="0ffc1-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="0ffc1-108">Registre qubit sur lequel effectuer la réflexion donnée.</span><span class="sxs-lookup"><span data-stu-id="0ffc1-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="0ffc1-109">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="0ffc1-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a><span data-ttu-id="0ffc1-110">ApplyReflection : ([double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="0ffc1-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="0ffc1-111">Notes</span><span class="sxs-lookup"><span data-stu-id="0ffc1-111">Remarks</span></span>

<span data-ttu-id="0ffc1-112">Ce $O Oracle = \boldone-(1-e ^ {i \Phi}) \ket{\Psi}\bra{\Psi} $ effectue une réflexion partielle par une phase $ \Phi $ à propos d’un seul état pur $ \ket{\Psi} $.</span><span class="sxs-lookup"><span data-stu-id="0ffc1-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>