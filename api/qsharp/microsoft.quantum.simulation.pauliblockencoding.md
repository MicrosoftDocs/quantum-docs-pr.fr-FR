---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 1426c7cbc257f9263ff45a96738fe798c3679ba1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706675"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="68972-102">PauliBlockEncoding fonction)</span><span class="sxs-lookup"><span data-stu-id="68972-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="68972-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="68972-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="68972-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="68972-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="68972-105">Crée un Unity d’encodage de bloc pour un produit Hamilton.</span><span class="sxs-lookup"><span data-stu-id="68972-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="68972-106">Le $H de Hamilton, = \ sum_ {j} \ alpha_j P_j $ est décrit par une somme de termes Pauli $P _j $, chacun avec un coefficient réel $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="68972-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="68972-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="68972-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="68972-108">generatorSystem : [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="68972-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="68972-109">`GeneratorSystem`Qui décrit $H $ en tant que somme de termes Pauli</span><span class="sxs-lookup"><span data-stu-id="68972-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="68972-110">Sortie : ([double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="68972-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="68972-111">Premier paramètre</span><span class="sxs-lookup"><span data-stu-id="68972-111">First parameter</span></span>

<span data-ttu-id="68972-112">La norme « One-normal » est $ \alpha = \ sum_ {j} | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="68972-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="68972-113">Deuxième paramètre</span><span class="sxs-lookup"><span data-stu-id="68972-113">Second parameter</span></span>

<span data-ttu-id="68972-114">Un `BlockEncodingReflection` $U unitaire $ du $H Hamilton</span><span class="sxs-lookup"><span data-stu-id="68972-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="68972-115">Étant donné que cette unité répond à $U ^ 2 = I $, il s’agit également d’une réflexion.</span><span class="sxs-lookup"><span data-stu-id="68972-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="68972-116">Notes</span><span class="sxs-lookup"><span data-stu-id="68972-116">Remarks</span></span>

<span data-ttu-id="68972-117">Cela est obtenu en préparant et en dépréparant l’État $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $, et en construisant un ensemble unitaire contrôlé par multiplication <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> et <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="68972-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>