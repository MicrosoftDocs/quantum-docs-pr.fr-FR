---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Type défini par l’utilisateur ReflectionOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708741"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="a430e-102">Type défini par l’utilisateur ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="a430e-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="a430e-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="a430e-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="a430e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a430e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a430e-105">Représente une réflexion Oracle.</span><span class="sxs-lookup"><span data-stu-id="a430e-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="a430e-106">Une réflexion Oracle, $O $, a des entrées :</span><span class="sxs-lookup"><span data-stu-id="a430e-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="a430e-107">Phase $ \Phi $ par laquelle faire pivoter le sous-espace réfléchi.</span><span class="sxs-lookup"><span data-stu-id="a430e-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="a430e-108">Registre qubit sur lequel effectuer la réflexion donnée.</span><span class="sxs-lookup"><span data-stu-id="a430e-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="a430e-109">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="a430e-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a><span data-ttu-id="a430e-110">ApplyReflection : ([double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => la touche d' [unité](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="a430e-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="a430e-111">Notes</span><span class="sxs-lookup"><span data-stu-id="a430e-111">Remarks</span></span>

<span data-ttu-id="a430e-112">Ce $O Oracle = \boldone-(1-e ^ {i \Phi}) \ket{\Psi}\bra{\Psi} $ effectue une réflexion partielle par une phase $ \Phi $ à propos d’un seul état pur $ \ket{\Psi} $.</span><span class="sxs-lookup"><span data-stu-id="a430e-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>