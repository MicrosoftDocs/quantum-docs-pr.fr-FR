---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: ba30a7e87bd970961dc87f048aa586ff5c512e2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701764"
---
# <a name="_pauliblockencoding-function"></a><span data-ttu-id="8d1e8-102">_PauliBlockEncoding fonction)</span><span class="sxs-lookup"><span data-stu-id="8d1e8-102">_PauliBlockEncoding function</span></span>

<span data-ttu-id="8d1e8-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8d1e8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8d1e8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8d1e8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8d1e8-105">Crée un Unity d’encodage de bloc pour un produit Hamilton.</span><span class="sxs-lookup"><span data-stu-id="8d1e8-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="8d1e8-106">Le $H de Hamilton, = \ sum_ {j} \ alpha_j P_j $ est décrit par une somme de termes Pauli $P _j $, chacun avec un coefficient réel $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="8d1e8-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="8d1e8-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="8d1e8-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="8d1e8-108">generatorSystem : [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="8d1e8-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="8d1e8-109">`GeneratorSystem`Qui décrit $H $ en tant que somme de termes Pauli</span><span class="sxs-lookup"><span data-stu-id="8d1e8-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>


### <a name="stateprepunitary--double---littleendian--unit-adj--ctl"></a><span data-ttu-id="8d1e8-110">statePrepUnitary : [double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="8d1e8-110">statePrepUnitary : [Double](xref:microsoft.quantum.lang-ref.double)[] -> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="8d1e8-111">Une opération unitaire $V $ qui applique le $V unitaire _j $ contrôlé sur l’index $ \ket{j} $, étant donné une fonction $f : j\rightarrow V_j $.</span><span class="sxs-lookup"><span data-stu-id="8d1e8-111">A unitary operation $V$ that applies the unitary $V_j$ controlled on index $\ket{j}$, given a function $f: j\rightarrow V_j$.</span></span>


### <a name="multiplexer--intint---qubit--unit-adj--ctl---littleendianqubit--unit-adj--ctl"></a><span data-ttu-id="8d1e8-112">multiplexeur : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit) Adj + CTL)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) ajuster + CTL</span><span class="sxs-lookup"><span data-stu-id="8d1e8-112">multiplexer : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>





## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="8d1e8-113">Sortie : ([double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="8d1e8-113">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="8d1e8-114">Premier paramètre</span><span class="sxs-lookup"><span data-stu-id="8d1e8-114">First parameter</span></span>

<span data-ttu-id="8d1e8-115">La norme « One-normal » est $ \alpha = \ sum_ {j} | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="8d1e8-115">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="8d1e8-116">Deuxième paramètre</span><span class="sxs-lookup"><span data-stu-id="8d1e8-116">Second parameter</span></span>

<span data-ttu-id="8d1e8-117">Un `BlockEncodingReflection` $U unitaire $ du $U Hamilton</span><span class="sxs-lookup"><span data-stu-id="8d1e8-117">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $U$.</span></span> <span data-ttu-id="8d1e8-118">Étant donné que cette unité répond à $U ^ 2 = I $, il s’agit également d’une réflexion.</span><span class="sxs-lookup"><span data-stu-id="8d1e8-118">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="8d1e8-119">Notes</span><span class="sxs-lookup"><span data-stu-id="8d1e8-119">Remarks</span></span>

<span data-ttu-id="8d1e8-120">Exemples d’opérations la préparation et la dépréparation de l’État $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $, et la construction d’un Unity contrôlé par multiplication sont <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> et <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="8d1e8-120">Example operations the prepare and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and construct a multiply-controlled unitary are <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>