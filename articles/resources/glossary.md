---
title: Glossaire quantum computing
description: Glossaire des termes, actions et objets les plus courants utilisés dans quantum computing.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: ba4d171d84d808f082b919dcc6156d9c65df7c05
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274791"
---
# <a name="quantum-computing-glossary"></a><span data-ttu-id="39b19-103">Glossaire quantum computing</span><span class="sxs-lookup"><span data-stu-id="39b19-103">Quantum computing glossary</span></span>

## <a name="adjoint"></a><span data-ttu-id="39b19-104">Voisin</span><span class="sxs-lookup"><span data-stu-id="39b19-104">Adjoint</span></span>

<span data-ttu-id="39b19-105">Transpose complexe conjugué d’une [opération](xref:microsoft.quantum.glossary#operation).</span><span class="sxs-lookup"><span data-stu-id="39b19-105">The complex conjugate transpose of an [operation](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="39b19-106">Pour les opérations qui implémentent un opérateur unitaire, l' [entité](xref:microsoft.quantum.glossary#unitary-operator) voisine est l’inverse de l’opération et est indiquée par un symbole poignard.</span><span class="sxs-lookup"><span data-stu-id="39b19-106">For operations that implement a [unitary](xref:microsoft.quantum.glossary#unitary-operator) operator, the adjoint is the inverse of the operation and is indicated by a dagger symbol.</span></span> <span data-ttu-id="39b19-107">Par exemple, si l’opération `U` représente l’opérateur d’unité $U $ , `Adjoint U` représente $U ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="39b19-107">For example, if the operation `U` represents the unitary operator $U$, then `Adjoint U` represents $U^\dagger$.</span></span> <span data-ttu-id="39b19-108">Pour plus d’informations, consultez [joint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span><span class="sxs-lookup"><span data-stu-id="39b19-108">For more information, see [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="ancilla"></a><span data-ttu-id="39b19-109">Ancilla</span><span class="sxs-lookup"><span data-stu-id="39b19-109">Ancilla</span></span>

<span data-ttu-id="39b19-110">Un [qubit](xref:microsoft.quantum.glossary#qubit) qui sert de mémoire temporaire pour un ordinateur quantique et qui est alloué et désalloué en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="39b19-110">A [qubit](xref:microsoft.quantum.glossary#qubit) that serves as temporary memory for a quantum computer and is allocated and de-allocated as needed.</span></span>  <span data-ttu-id="39b19-111">Pour plus d’informations, consultez [plusieurs qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="39b19-111">For more information, see [Multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

## <a name="bell-state"></a><span data-ttu-id="39b19-112">État de la cloche</span><span class="sxs-lookup"><span data-stu-id="39b19-112">Bell state</span></span>

<span data-ttu-id="39b19-113">L’un des quatre [entangled](xref:microsoft.quantum.glossary#entanglement) [États quantiques](xref:microsoft.quantum.glossary#quantum-state) des deux qubits.</span><span class="sxs-lookup"><span data-stu-id="39b19-113">One of four specific maximally [entangled](xref:microsoft.quantum.glossary#entanglement) [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two qubits.</span></span> <span data-ttu-id="39b19-114">Les quatre États sont définis : $ \ket { \ beta_ {IJ } } = (\Mathbb{I } \Otimes X ^ iz ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $.</span><span class="sxs-lookup"><span data-stu-id="39b19-114">The four states are defined $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="39b19-115">Un état de cloche est également appelé [paire de EPR](xref:microsoft.quantum.glossary#epr-pair).</span><span class="sxs-lookup"><span data-stu-id="39b19-115">A Bell state is also known as an [EPR pair](xref:microsoft.quantum.glossary#epr-pair).</span></span>

## <a name="bloch-sphere"></a><span data-ttu-id="39b19-116">Sphère Bloch</span><span class="sxs-lookup"><span data-stu-id="39b19-116">Bloch sphere</span></span>

<span data-ttu-id="39b19-117">Représentation graphique d’un [État Quantum](xref:microsoft.quantum.glossary#quantum-state) à[qubit](xref:microsoft.quantum.glossary#qubit) unique comme point dans une sphère d’unité en trois dimensions.</span><span class="sxs-lookup"><span data-stu-id="39b19-117">A graphical representation of a single-[qubit](xref:microsoft.quantum.glossary#qubit) [quantum state](xref:microsoft.quantum.glossary#quantum-state) as a point in a three-dimensional unit sphere.</span></span> <span data-ttu-id="39b19-118">Pour plus d’informations, consultez [visualisation des qubits et des transformations à l’aide de la sphère Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="39b19-118">For more information, see  [Visualizing Qubits and Transformations using the Bloch Sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

## <a name="callable"></a><span data-ttu-id="39b19-119">Pouvant être appelé</span><span class="sxs-lookup"><span data-stu-id="39b19-119">Callable</span></span>

<span data-ttu-id="39b19-120">Une [opération](xref:microsoft.quantum.glossary#operation) ou une [fonction](xref:microsoft.quantum.glossary#function) dans le langage Q #.</span><span class="sxs-lookup"><span data-stu-id="39b19-120">An [operation](xref:microsoft.quantum.glossary#operation) or [function](xref:microsoft.quantum.glossary#function) in the Q# language.</span></span> <span data-ttu-id="39b19-121">Pour plus d’informations, consultez [opérations et fonctions](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="39b19-121">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="clifford-group"></a><span data-ttu-id="39b19-122">Groupe Clifford</span><span class="sxs-lookup"><span data-stu-id="39b19-122">Clifford group</span></span>

<span data-ttu-id="39b19-123">L’ensemble des opérations qui occupent le octants de la [sphère Bloch](xref:microsoft.quantum.glossary#bloch-sphere) et les permutations d’effet des [opérateurs Pauli](xref:microsoft.quantum.glossary#pauli-operators).</span><span class="sxs-lookup"><span data-stu-id="39b19-123">The set of operations that occupy the octants of the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere) and effect permutations of the [Pauli operators](xref:microsoft.quantum.glossary#pauli-operators).</span></span> <span data-ttu-id="39b19-124">Celles-ci incluent les opérations [$X $ ](xref:microsoft.quantum.intrinsic.x), [$Y $ ](xref:microsoft.quantum.intrinsic.y), [$Z $ ](xref:microsoft.quantum.intrinsic.z), [$H $ ](xref:microsoft.quantum.intrinsic.h) et [$S $ ](xref:microsoft.quantum.intrinsic.s).</span><span class="sxs-lookup"><span data-stu-id="39b19-124">These include the operations [$X$](xref:microsoft.quantum.intrinsic.x), [$Y$](xref:microsoft.quantum.intrinsic.y), [$Z$](xref:microsoft.quantum.intrinsic.z), [$H$](xref:microsoft.quantum.intrinsic.h) and [$S$](xref:microsoft.quantum.intrinsic.s).</span></span>

## <a name="controlled"></a><span data-ttu-id="39b19-125">Contrôl</span><span class="sxs-lookup"><span data-stu-id="39b19-125">Controlled</span></span>

<span data-ttu-id="39b19-126">[Opération](xref:microsoft.quantum.glossary#operation) de Quantum qui prend un ou plusieurs [qubits](xref:microsoft.quantum.glossary#qubit) comme activateurs pour l’opération cible.</span><span class="sxs-lookup"><span data-stu-id="39b19-126">A quantum [operation](xref:microsoft.quantum.glossary#operation) that takes one or more [qubits](xref:microsoft.quantum.glossary#qubit) as enablers for the target operation.</span></span> <span data-ttu-id="39b19-127">Pour plus d’informations, consultez [opérations contrôlées et apjointes](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span><span class="sxs-lookup"><span data-stu-id="39b19-127">For more information, see [Controlled and adjoint operations](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="dirac-notation"></a><span data-ttu-id="39b19-128">Notation Dirac</span><span class="sxs-lookup"><span data-stu-id="39b19-128">Dirac Notation</span></span>

<span data-ttu-id="39b19-129">Raccourci symbolique qui simplifie la représentation des [États quantiques](xref:microsoft.quantum.glossary#quantum-state), également appelée notation *Bra-Ket* .</span><span class="sxs-lookup"><span data-stu-id="39b19-129">A symbolic shorthand that simplifies the representation of [quantum states](xref:microsoft.quantum.glossary#quantum-state), also called *bra-ket* notation.</span></span>  <span data-ttu-id="39b19-130">La partie *Bra* représente un vecteur de ligne, par exemple $ \bra{A } = \begin{ bmatrix } a {_ 1 } & a {_2 } \end{ bmatrix } $ et la partie *Ket* représente un vecteur de colonne, $ \ket{B } = \begin{ bmatrix } B {_ 1 } \\ \\ b {_2 } \end{ bmatrix } $.</span><span class="sxs-lookup"><span data-stu-id="39b19-130">The *bra* portion represents a row vector, for example  $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ and the *ket* portion represents a column vector, $\ket{B} = \begin{bmatrix} B{_1} \\\\ B{_2} \end{bmatrix}$.</span></span> <span data-ttu-id="39b19-131">Pour plus d’informations, consultez [notation Dirac](xref:microsoft.quantum.concepts.dirac).</span><span class="sxs-lookup"><span data-stu-id="39b19-131">For more information, see [Dirac Notation](xref:microsoft.quantum.concepts.dirac).</span></span>

## <a name="eigenvalue"></a><span data-ttu-id="39b19-132">Eigenvalue</span><span class="sxs-lookup"><span data-stu-id="39b19-132">Eigenvalue</span></span>

<span data-ttu-id="39b19-133">Facteur par lequel la grandeur d’un [extraction](xref:microsoft.quantum.glossary#eigenvector) d’une transformation donnée est modifiée par l’application de la transformation.</span><span class="sxs-lookup"><span data-stu-id="39b19-133">The factor by which the magnitude of an [eigenvector](xref:microsoft.quantum.glossary#eigenvector) of a given transformation is changed by the application of the transformation.</span></span>  <span data-ttu-id="39b19-134">À partir d’une matrice carrée $M $ et d’un $v extraction $ , $mV = CV $ , où $c $ est le eigenvalue et peut être un nombre complexe d’un argument.</span><span class="sxs-lookup"><span data-stu-id="39b19-134">Given a square matrix $M$ and an eigenvector $v$, then $Mv = cv$, where $c$ is the eigenvalue and can be a complex number of any argument.</span></span> <span data-ttu-id="39b19-135">Pour plus d’informations, consultez [concepts avancés](xref:microsoft.quantum.concepts.matrix-advanced)de la matrice.</span><span class="sxs-lookup"><span data-stu-id="39b19-135">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="eigenvector"></a><span data-ttu-id="39b19-136">Extraction</span><span class="sxs-lookup"><span data-stu-id="39b19-136">Eigenvector</span></span>

<span data-ttu-id="39b19-137">Vecteur dont la direction est inchangée par une transformation donnée et dont l’amplitude est modifiée par un facteur correspondant au [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)de ce vecteur.</span><span class="sxs-lookup"><span data-stu-id="39b19-137">A vector whose direction is unchanged by a given transformation and whose magnitude is changed by a factor corresponding to that vector's [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue).</span></span> <span data-ttu-id="39b19-138">À partir d’une matrice carrée $M $ et d’un $c eigenvalue $ , $mV = CV $ , où $v $ est un extraction de la matrice et peut être un nombre complexe d’un argument.</span><span class="sxs-lookup"><span data-stu-id="39b19-138">Given a square matrix $M$ and an eigenvalue $c$, then $Mv = cv$, where $v$ is an eigenvector of the matrix and can be a complex number of any argument.</span></span> <span data-ttu-id="39b19-139">Pour plus d’informations, consultez [concepts avancés](xref:microsoft.quantum.concepts.matrix-advanced)de la matrice.</span><span class="sxs-lookup"><span data-stu-id="39b19-139">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="entanglement"></a><span data-ttu-id="39b19-140">Intrication</span><span class="sxs-lookup"><span data-stu-id="39b19-140">Entanglement</span></span>

<span data-ttu-id="39b19-141">Les particules quantiques, telles que [qubits](xref:microsoft.quantum.glossary#qubit), peuvent être connectées ou *enchevêtrées* de sorte qu’elles ne puissent pas être décrites indépendamment les unes des autres.</span><span class="sxs-lookup"><span data-stu-id="39b19-141">Quantum particles, such as [qubits](xref:microsoft.quantum.glossary#qubit), can be connected or *entangled* such that they cannot be described independently from each other.</span></span> <span data-ttu-id="39b19-142">Leurs résultats de mesure sont corrélés même lorsqu’ils sont séparés à l’infini.</span><span class="sxs-lookup"><span data-stu-id="39b19-142">Their measurement results are correlated even when they are separated infinitely far away.</span></span> <span data-ttu-id="39b19-143">L’enchevêtrement est essentiel à la [mesure](xref:microsoft.quantum.glossary#measurement) de l' [État](xref:microsoft.quantum.glossary#quantum-state) d’un qubit.</span><span class="sxs-lookup"><span data-stu-id="39b19-143">Entanglement is essential to [measuring](xref:microsoft.quantum.glossary#measurement) the [state](xref:microsoft.quantum.glossary#quantum-state) of a qubit.</span></span>  <span data-ttu-id="39b19-144">Pour plus d’informations, consultez [concepts avancés](xref:microsoft.quantum.concepts.matrix-advanced)de la matrice.</span><span class="sxs-lookup"><span data-stu-id="39b19-144">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="epr-pair"></a><span data-ttu-id="39b19-145">Paire EPR</span><span class="sxs-lookup"><span data-stu-id="39b19-145">EPR pair</span></span>

<span data-ttu-id="39b19-146">L’un des quatre [États quantiques](xref:microsoft.quantum.glossary#quantum-state) des deux [qubits](xref:microsoft.quantum.glossary#qubit).</span><span class="sxs-lookup"><span data-stu-id="39b19-146">One of four specific maximally entangled [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two [qubits](xref:microsoft.quantum.glossary#qubit).</span></span> <span data-ttu-id="39b19-147">Les quatre États sont définis : $ \ket { \ beta_ {IJ } } = (\Mathbb{1 } \Otimes X ^ iz ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $.</span><span class="sxs-lookup"><span data-stu-id="39b19-147">The four states are defined $\ket{\beta_{ij}} = (\mathbb{1} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="39b19-148">Une paire EPR est également appelée « [État Bell](xref:microsoft.quantum.glossary#bell-state) ».</span><span class="sxs-lookup"><span data-stu-id="39b19-148">An EPR pair is also known as a [Bell state](xref:microsoft.quantum.glossary#bell-state)</span></span>

## <a name="evolution"></a><span data-ttu-id="39b19-149">Révolution</span><span class="sxs-lookup"><span data-stu-id="39b19-149">Evolution</span></span>

<span data-ttu-id="39b19-150">Comment un [État Quantum](xref:microsoft.quantum.glossary#quantum-state) change dans le temps.</span><span class="sxs-lookup"><span data-stu-id="39b19-150">How a [quantum state](xref:microsoft.quantum.glossary#quantum-state) changes over time.</span></span> <span data-ttu-id="39b19-151">Pour plus d’informations, consultez [exponentielles](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)de la matrice.</span><span class="sxs-lookup"><span data-stu-id="39b19-151">For more information, see [Matrix exponentials](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).</span></span>

## <a name="function"></a><span data-ttu-id="39b19-152">Fonction</span><span class="sxs-lookup"><span data-stu-id="39b19-152">Function</span></span>
<span data-ttu-id="39b19-153">Type de sous-routine dans le langage Q # qui est purement classique (non Quantum).</span><span class="sxs-lookup"><span data-stu-id="39b19-153">A type of subroutine in the Q# language that is purely classical (non-quantum).</span></span> <span data-ttu-id="39b19-154">Tandis que les fonctions sont utilisées dans les algorithmes Quantum, elles ne peuvent pas agir sur les [opérations](xref:microsoft.quantum.glossary#operation)de [qubits](xref:microsoft.quantum.glossary#qubit) ou d’appel.</span><span class="sxs-lookup"><span data-stu-id="39b19-154">While functions are used within quantum algorithms, they cannot act on [qubits](xref:microsoft.quantum.glossary#qubit) or call [operations](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="39b19-155">Pour plus d’informations, consultez [opérations et fonctions](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="39b19-155">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="gate"></a><span data-ttu-id="39b19-156">Transistor</span><span class="sxs-lookup"><span data-stu-id="39b19-156">Gate</span></span>

<span data-ttu-id="39b19-157">Terme hérité pour une [opération](xref:microsoft.quantum.glossary#operation)de Quantum, basé sur le concept de portes logiques classiques.</span><span class="sxs-lookup"><span data-stu-id="39b19-157">A legacy term for a quantum [operation](xref:microsoft.quantum.glossary#operation), based on the concept of classical logic gates.</span></span> <span data-ttu-id="39b19-158">Un [circuit Quantum](xref:microsoft.quantum.glossary#quantum-circuit-diagram) est un réseau de portes (ou d’opérations), basé sur le concept similaire des circuits logiques classiques.</span><span class="sxs-lookup"><span data-stu-id="39b19-158">A [quantum circuit](xref:microsoft.quantum.glossary#quantum-circuit-diagram) is a network of gates (or operations), based on the similar concept of classical logic circuits.</span></span>

## <a name="global-phase"></a><span data-ttu-id="39b19-159">Phase globale</span><span class="sxs-lookup"><span data-stu-id="39b19-159">Global phase</span></span>

<span data-ttu-id="39b19-160">Lorsque deux [États](xref:microsoft.quantum.glossary#quantum-state) sont identiques à un multiple d’un nombre complexe $e ^ {i \phi } $, il est dit qu’ils diffèrent d’une phase globale.</span><span class="sxs-lookup"><span data-stu-id="39b19-160">When two [states](xref:microsoft.quantum.glossary#quantum-state) are identical up to a multiple of a complex number $e^{i\phi}$, they are said to differ up to a global phase.</span></span> <span data-ttu-id="39b19-161">Contrairement aux phases locales, les phases globales ne peuvent pas être observées par des [mesurages](xref:microsoft.quantum.glossary#measurement).</span><span class="sxs-lookup"><span data-stu-id="39b19-161">Unlike local phases, global phases cannot be observed through any [measurment](xref:microsoft.quantum.glossary#measurement).</span></span> <span data-ttu-id="39b19-162">Pour plus d’informations, consultez [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="39b19-162">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="hadamard"></a><span data-ttu-id="39b19-163">Hadamard</span><span class="sxs-lookup"><span data-stu-id="39b19-163">Hadamard</span></span>

<span data-ttu-id="39b19-164">L’opération Hadarmard (également appelée porte ou transformation Hadarmard) agit sur un seul [qubit](xref:microsoft.quantum.glossary#qubit) et la place dans une [superposition](xref:microsoft.quantum.glossary#superposition) de $ \ket{0 } $ ou de $ \ket{1 } $ si le qubit est initialement dans l’État $ \ket{0 } $.</span><span class="sxs-lookup"><span data-stu-id="39b19-164">The Hadamard operation (also referred to as the Hadamard gate or transform) acts on a single [qubit](xref:microsoft.quantum.glossary#qubit) and puts it in an even [superposition](xref:microsoft.quantum.glossary#superposition) of $\ket{0}$ or $\ket{1}$ if the qubit is initially in the $\ket{0}$ state.</span></span> <span data-ttu-id="39b19-165">Dans Q #, cette opération est appliquée par l’opération prédéfinie [`H`](xref:microsoft.quantum.intrinsic.h) .</span><span class="sxs-lookup"><span data-stu-id="39b19-165">In Q#, this operation is applied by the pre-defined [`H`](xref:microsoft.quantum.intrinsic.h) operation.</span></span>

## <a name="immutable"></a><span data-ttu-id="39b19-166">Non modifiable</span><span class="sxs-lookup"><span data-stu-id="39b19-166">Immutable</span></span>

<span data-ttu-id="39b19-167">Variable dont la valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="39b19-167">A variable whose value cannot be changed.</span></span> <span data-ttu-id="39b19-168">Une variable immuable dans Q # est créée à l’aide du `let` mot clé.</span><span class="sxs-lookup"><span data-stu-id="39b19-168">An immutable variable in Q# is created using the `let` keyword.</span></span> <span data-ttu-id="39b19-169">Pour déclarer des variables qui *peuvent* être modifiées, utilisez le mot clé [mutable](xref:microsoft.quantum.glossary#immutable) pour déclarer et le `set` mot clé pour modifier la valeur.</span><span class="sxs-lookup"><span data-stu-id="39b19-169">To declare variables that *can* be changed, use the [mutable](xref:microsoft.quantum.glossary#immutable) keyword to declare and the `set` keyword to modify the value.</span></span> 

## <a name="measurement"></a><span data-ttu-id="39b19-170">Mesure</span><span class="sxs-lookup"><span data-stu-id="39b19-170">Measurement</span></span>

<span data-ttu-id="39b19-171">Manipulation d’un [qubit](xref:microsoft.quantum.glossary#qubit) (ou d’un ensemble de qubits) qui produit le résultat d’une observation, en obtenant un bit classique.</span><span class="sxs-lookup"><span data-stu-id="39b19-171">A manipulation of a [qubit](xref:microsoft.quantum.glossary#qubit) (or set of qubits) that yields the result of an observation, in effect obtaining a classical bit.</span></span> <span data-ttu-id="39b19-172">Pour plus d’informations, consultez [qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span><span class="sxs-lookup"><span data-stu-id="39b19-172">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span></span>

## <a name="mutable"></a><span data-ttu-id="39b19-173">Mutable</span><span class="sxs-lookup"><span data-stu-id="39b19-173">Mutable</span></span>

<span data-ttu-id="39b19-174">Variable dont la valeur peut être modifiée après sa création.</span><span class="sxs-lookup"><span data-stu-id="39b19-174">A variable whose value may be changed after it is created.</span></span> <span data-ttu-id="39b19-175">Une variable mutable dans Q # est déclarée à l’aide du `mutable` mot clé et modifiée à l’aide du `set` mot clé.</span><span class="sxs-lookup"><span data-stu-id="39b19-175">A mutable variable in Q# is declared using the `mutable` keyword and modified using the `set` keyword.</span></span> <span data-ttu-id="39b19-176">Les variables créées avec le `let` mot clé sont [immuables](xref:microsoft.quantum.glossary#immutable) et leur valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="39b19-176">Variables created with the `let` keyword are [immutable](xref:microsoft.quantum.glossary#immutable) and their value cannot be changed.</span></span>

## <a name="namespace"></a><span data-ttu-id="39b19-177">Espace de noms</span><span class="sxs-lookup"><span data-stu-id="39b19-177">Namespace</span></span>

<span data-ttu-id="39b19-178">Étiquette pour une collection de noms associés (c’est-à-dire des [opérations](xref:microsoft.quantum.glossary#operation), des [fonctions](xref:microsoft.quantum.glossary#function)et des [types définis par l’utilisateur](xref:microsoft.quantum.glossary#user-defined-type)).</span><span class="sxs-lookup"><span data-stu-id="39b19-178">A label for a collection of related names (i.e., [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function), and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type)).</span></span> <span data-ttu-id="39b19-179">Par exemple, l’espace de noms [Microsoft. Quantum. PREPARATION](xref:microsoft.quantum.preparation) étiquette tous les symboles définis dans la bibliothèque standard qui facilitent la préparation des États initiaux.</span><span class="sxs-lookup"><span data-stu-id="39b19-179">For instance the namespace [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) labels all of the symbols defined in the standard library that help with preparing initial states.</span></span>

## <a name="operation"></a><span data-ttu-id="39b19-180">Opération</span><span class="sxs-lookup"><span data-stu-id="39b19-180">Operation</span></span>

<span data-ttu-id="39b19-181">Unité de base de l’exécution du quantum dans Q #.</span><span class="sxs-lookup"><span data-stu-id="39b19-181">The basic unit of quantum execution in Q#.</span></span> <span data-ttu-id="39b19-182">Elle est à peu près équivalente à une fonction en C, C++ ou python, ou une méthode statique en C# ou en Java.</span><span class="sxs-lookup"><span data-stu-id="39b19-182">It is roughly equivalent to a function in C, C++ or Python, or a static method in C# or Java.</span></span> <span data-ttu-id="39b19-183">Pour plus d’informations, consultez [opérations et fonctions](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="39b19-183">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="operator-application"></a><span data-ttu-id="39b19-184">Application opérateur</span><span class="sxs-lookup"><span data-stu-id="39b19-184">Operator application</span></span>

<span data-ttu-id="39b19-185">Exécution d’une opération de Quantum.</span><span class="sxs-lookup"><span data-stu-id="39b19-185">Performing a quantum operation.</span></span> <span data-ttu-id="39b19-186">Cela applique généralement une matrice d’unités au vecteur d’État Quantum actuel.</span><span class="sxs-lookup"><span data-stu-id="39b19-186">This typically applies a unitary matrix to the current quantum state vector.</span></span>

## <a name="oracle"></a><span data-ttu-id="39b19-187">Oracle</span><span class="sxs-lookup"><span data-stu-id="39b19-187">Oracle</span></span>

<span data-ttu-id="39b19-188">Sous-routine qui fournit des informations dépendantes aux données à un algorithme Quantum au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="39b19-188">A subroutine that provides data-dependent information to a quantum algorithm at runtime.</span></span> <span data-ttu-id="39b19-189">En règle générale, l’objectif est de fournir une [superposition](xref:microsoft.quantum.glossary#superposition) des sorties correspondant aux entrées en superposition.</span><span class="sxs-lookup"><span data-stu-id="39b19-189">Typically, the goal is to provide a [superposition](xref:microsoft.quantum.glossary#superposition) of outputs corresponding to inputs that are in superposition.</span></span> <span data-ttu-id="39b19-190">Pour plus d’informations, consultez [Oracle](xref:microsoft.quantum.libraries.data-structures#oracles).</span><span class="sxs-lookup"><span data-stu-id="39b19-190">For more information, see [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).</span></span>

## <a name="partial-application"></a><span data-ttu-id="39b19-191">Application partielle</span><span class="sxs-lookup"><span data-stu-id="39b19-191">Partial application</span></span>

<span data-ttu-id="39b19-192">Appel d’une [fonction](xref:microsoft.quantum.glossary#function) ou d’une [opération](xref:microsoft.quantum.glossary#operation) sans toutes les entrées requises.</span><span class="sxs-lookup"><span data-stu-id="39b19-192">Calling a [function](xref:microsoft.quantum.glossary#function) or [operation](xref:microsoft.quantum.glossary#operation) without all the required inputs.</span></span> <span data-ttu-id="39b19-193">Cela retourne un nouvel [appelable](xref:microsoft.quantum.glossary#callable) qui n’a besoin que des paramètres manquants (indiqués par un trait de soulignement) à fournir au cours d’une prochaine application.</span><span class="sxs-lookup"><span data-stu-id="39b19-193">This returns a new [callable](xref:microsoft.quantum.glossary#callable) that only needs the missing parameters (indicated by an underscore) to be supplied during a future application.</span></span> <span data-ttu-id="39b19-194">Par exemple, étant donné la fonction, `MyFunc(x : int, y : int) : int {return x + y;}` vous pouvez l’appliquer partiellement à une nouvelle fonction `let NewFunc = MyFunc(_, 3)` .</span><span class="sxs-lookup"><span data-stu-id="39b19-194">For example, given the function `MyFunc(x : int, y : int) : int {return x + y;}` you can partially apply it to a new function `let NewFunc = MyFunc(_, 3)`.</span></span> <span data-ttu-id="39b19-195">Vous pouvez ensuite appeler la nouvelle fonction ultérieurement avec le paramètre manquant `NewFunc(2)` qui retourne la valeur *5*.</span><span class="sxs-lookup"><span data-stu-id="39b19-195">You can then call the new function at a later time with the missing parameter `NewFunc(2)` which returns the value *5*.</span></span>  <span data-ttu-id="39b19-196">Pour plus d’informations, consultez [application partielle](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span><span class="sxs-lookup"><span data-stu-id="39b19-196">For more information, see [Partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span></span>

## <a name="pauli-operators"></a><span data-ttu-id="39b19-197">Pauli, opérateurs</span><span class="sxs-lookup"><span data-stu-id="39b19-197">Pauli operators</span></span>

<span data-ttu-id="39b19-198">Ensemble de trois matrices d’unités de 2 x 2, appelées `X` `Y` opérations de `Z` Quantum et.</span><span class="sxs-lookup"><span data-stu-id="39b19-198">A set of three 2 x 2 unitary matrices known as the `X`, `Y` and `Z` quantum operations.</span></span> <span data-ttu-id="39b19-199">La matrice d’identité, $I $ , est souvent incluse dans le jeu également.</span><span class="sxs-lookup"><span data-stu-id="39b19-199">The identity matrix, $I$, is often included in the set as well.</span></span>  <span data-ttu-id="39b19-200">$I = \begin{ bmatrix } 1 & 0 \\ \\ 0 & 1 \end{ bmatrix } $, $X = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } $, $Y = \begin{ bmatrix } 0 &-i & \\ \\ 0 \end{ bmatrix } $, $Z = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } $.</span><span class="sxs-lookup"><span data-stu-id="39b19-200">$I = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix}$, $X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}$, $Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix}$, $Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}$.</span></span>   <span data-ttu-id="39b19-201">Pour plus d’informations, consultez [opérations à qubit unique](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span><span class="sxs-lookup"><span data-stu-id="39b19-201">For more information, see [Single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>

## <a name="quantum-circuit-diagram"></a><span data-ttu-id="39b19-202">Diagramme de circuit quantique</span><span class="sxs-lookup"><span data-stu-id="39b19-202">Quantum circuit diagram</span></span>

<span data-ttu-id="39b19-203">Méthode pour représenter graphiquement la séquence d' [opérations](xref:microsoft.quantum.glossary#operation) (ou de [portes](xref:microsoft.quantum.glossary#gate)) pour les programmes quantiques simples, par exemple</span><span class="sxs-lookup"><span data-stu-id="39b19-203">A method to graphically represent the sequence of [operations](xref:microsoft.quantum.glossary#operation) (or [gates](xref:microsoft.quantum.glossary#gate)) for simple quantum programs, for example</span></span> 

![Exemple de diagramme de circuit](~/media/qpe.png)<span data-ttu-id="39b19-205">.</span><span class="sxs-lookup"><span data-stu-id="39b19-205">.</span></span> 

<span data-ttu-id="39b19-206">Pour plus d’informations, consultez la page [circuits quantiques](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="39b19-206">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits).</span></span>

## <a name="quantum-libraries"></a><span data-ttu-id="39b19-207">Bibliothèques Quantum</span><span class="sxs-lookup"><span data-stu-id="39b19-207">Quantum libraries</span></span>

<span data-ttu-id="39b19-208">Collections d' [opérations](xref:microsoft.quantum.glossary#operation), de [fonctions](xref:microsoft.quantum.glossary#function) et de [types définis](xref:microsoft.quantum.glossary#user-defined-type) par l’utilisateur pour la création de programmes Q #.</span><span class="sxs-lookup"><span data-stu-id="39b19-208">Collections of [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) for creating Q# programs.</span></span> <span data-ttu-id="39b19-209">La [bibliothèque standard](xref:microsoft.quantum.libraries.standard.intro) est installée par défaut.</span><span class="sxs-lookup"><span data-stu-id="39b19-209">The [Standard library](xref:microsoft.quantum.libraries.standard.intro) is installed by default.</span></span> <span data-ttu-id="39b19-210">Les autres bibliothèques disponibles sont la [bibliothèque chimie](xref:microsoft.quantum.chemistry.concepts.intro), la [bibliothèque de valeurs numériques](xref:microsoft.quantum.numerics.intro) et la [bibliothèque machine learning](xref:microsoft.quantum.machine-learning.concepts.intro).</span><span class="sxs-lookup"><span data-stu-id="39b19-210">Other libraries available are the [Chemistry library](xref:microsoft.quantum.chemistry.concepts.intro), the [Numerics library](xref:microsoft.quantum.numerics.intro) and the [Machine learning library](xref:microsoft.quantum.machine-learning.concepts.intro).</span></span>

## <a name="quantum-state"></a><span data-ttu-id="39b19-211">État Quantum</span><span class="sxs-lookup"><span data-stu-id="39b19-211">Quantum state</span></span>

<span data-ttu-id="39b19-212">État précis d’un système quantique isolé, à partir duquel les probabilités de [mesure](xref:microsoft.quantum.glossary#measurement) peuvent être extraites.</span><span class="sxs-lookup"><span data-stu-id="39b19-212">The precise state of an isolated quantum system, from which [measurement](xref:microsoft.quantum.glossary#measurement) probabilities can be extracted.</span></span> <span data-ttu-id="39b19-213">Dans Quantum Computing, le simulateur quantum utilise ces informations pour simuler la manière dont qubits répond aux opérations.</span><span class="sxs-lookup"><span data-stu-id="39b19-213">In quantum computing, the quantum simulator uses this information to simulate how qubits respond to operations.</span></span> <span data-ttu-id="39b19-214">Pour plus d’informations, consultez [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="39b19-214">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="qubit"></a><span data-ttu-id="39b19-215">Qubit</span><span class="sxs-lookup"><span data-stu-id="39b19-215">Qubit</span></span>

<span data-ttu-id="39b19-216">Unité de base d’informations de Quantum, analogue à un *peu* dans l’informatique classique.</span><span class="sxs-lookup"><span data-stu-id="39b19-216">A basic unit of quantum information, analogous to a *bit* in classical computing.</span></span> <span data-ttu-id="39b19-217">Pour plus d’informations, consultez [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="39b19-217">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="repeat-until-success"></a><span data-ttu-id="39b19-218">Répéter jusqu’à réussite</span><span class="sxs-lookup"><span data-stu-id="39b19-218">Repeat-until-success</span></span>

<span data-ttu-id="39b19-219">Un algorithme Quantum qui fonctionne de façon probabiliste.</span><span class="sxs-lookup"><span data-stu-id="39b19-219">A quantum algorithm that probabilistically succeeds.</span></span> <span data-ttu-id="39b19-220">En cas d’échec, la routine réessaie jusqu’à ce qu’elle réussisse (ou qu’une limite a été atteinte).</span><span class="sxs-lookup"><span data-stu-id="39b19-220">Upon failure, the routine will retry until successful (or a limit has been reached).</span></span> <span data-ttu-id="39b19-221">Pour plus d’informations, consultez [répéter jusqu’à la réussite (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span><span class="sxs-lookup"><span data-stu-id="39b19-221">For more information, see [Repeat Until Success (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span></span>

## <a name="standard-libraries"></a><span data-ttu-id="39b19-222">Bibliothèques standard</span><span class="sxs-lookup"><span data-stu-id="39b19-222">Standard libraries</span></span>

<span data-ttu-id="39b19-223">[Opérations](xref:microsoft.quantum.glossary#operation), [fonctions](xref:microsoft.quantum.glossary#function) et [types définis](xref:microsoft.quantum.glossary#user-defined-type) par l’utilisateur installés avec le compilateur Q # pendant l’installation.</span><span class="sxs-lookup"><span data-stu-id="39b19-223">[Operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) that are installed along with the Q# compiler during installation.</span></span> <span data-ttu-id="39b19-224">L’implémentation de la bibliothèque standard est indépendante en ce qui concerne les ordinateurs cibles.</span><span class="sxs-lookup"><span data-stu-id="39b19-224">The standard library implementation is agnostic with respect to target machines.</span></span> <span data-ttu-id="39b19-225">Pour plus d’informations, consultez [bibliothèques standard](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="39b19-225">For more information, see [Standard libraries](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="superposition"></a><span data-ttu-id="39b19-226">Superposition</span><span class="sxs-lookup"><span data-stu-id="39b19-226">Superposition</span></span>

<span data-ttu-id="39b19-227">Le concept dans quantum computing qu’un [qubit](xref:microsoft.quantum.glossary#qubit) est une combinaison linéaire de deux États, $ \ket{0 } $ et $ \ket{1 } $, jusqu’à ce qu’il soit [mesuré](xref:microsoft.quantum.glossary#measurement).</span><span class="sxs-lookup"><span data-stu-id="39b19-227">The concept in quantum computing that a [qubit](xref:microsoft.quantum.glossary#qubit) is a linear combination of two states, $\ket{0}$ and $\ket{1}$, until it is [measured](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="39b19-228">Pour plus d’informations, consultez [Understanding quantum computing](xref:microsoft.quantum.overview.understanding).</span><span class="sxs-lookup"><span data-stu-id="39b19-228">For more information, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding).</span></span>

## <a name="target-machine"></a><span data-ttu-id="39b19-229">Ordinateur cible</span><span class="sxs-lookup"><span data-stu-id="39b19-229">Target machine</span></span>

<span data-ttu-id="39b19-230">Cible de compilation qui réduit un programme Quantum abstrait en vue d’un matériel ou d’une simulation.</span><span class="sxs-lookup"><span data-stu-id="39b19-230">A compilation target that lowers an abstract quantum program towards hardware or simulation.</span></span> <span data-ttu-id="39b19-231">Cela inclut généralement les réécritions pour de nombreuses raisons, notamment le remplacement de la porte, l’encodage pour la correction des erreurs, la disposition géométrique et autres.</span><span class="sxs-lookup"><span data-stu-id="39b19-231">This typically include re-writes for many purposes including gate replacement, encoding for error correction, geometric layout and others.</span></span> <span data-ttu-id="39b19-232">Pour plus d’informations, consultez [simulations de Quantum et applications hôtes](xref:microsoft.quantum.machines).</span><span class="sxs-lookup"><span data-stu-id="39b19-232">For more information, see [Quantum simulators and host applications](xref:microsoft.quantum.machines).</span></span>

## <a name="teleportation"></a><span data-ttu-id="39b19-233">Téléportation</span><span class="sxs-lookup"><span data-stu-id="39b19-233">Teleportation</span></span>

<span data-ttu-id="39b19-234">Méthode pour régénérer des données, ou l' [État Quantum](xref:microsoft.quantum.glossary#quantum-state), d’un [qubit](xref:microsoft.quantum.glossary#qubit) d’un emplacement à un autre sans déplacer physiquement le qubit, à l’aide d’un [enchevêtrement](xref:microsoft.quantum.glossary#entanglement) et d’une [mesure](xref:microsoft.quantum.glossary#measurement).</span><span class="sxs-lookup"><span data-stu-id="39b19-234">A method for regenerating data, or the [quantum state](xref:microsoft.quantum.glossary#quantum-state), of one [qubit](xref:microsoft.quantum.glossary#qubit) from one place to another without physically moving the qubit, using [entanglement](xref:microsoft.quantum.glossary#entanglement) and [measurement](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="39b19-235">Pour plus d’informations, consultez les [circuits quantiques](xref:microsoft.quantum.concepts.circuits) et les Kata respectifs dans [Quantum katas](xref:microsoft.quantum.overview.katas).</span><span class="sxs-lookup"><span data-stu-id="39b19-235">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits) and the respective kata at [Quantum Katas](xref:microsoft.quantum.overview.katas).</span></span>

## <a name="tuple"></a><span data-ttu-id="39b19-236">Tuple</span><span class="sxs-lookup"><span data-stu-id="39b19-236">Tuple</span></span>

<span data-ttu-id="39b19-237">Collection de valeurs séparées par des virgules qui agit comme une valeur unique.</span><span class="sxs-lookup"><span data-stu-id="39b19-237">A collection of comma-separated values that acts as a single value.</span></span> <span data-ttu-id="39b19-238">Le *type* d’un tuple est défini par les types de valeurs qu’il contient.</span><span class="sxs-lookup"><span data-stu-id="39b19-238">The *type* of a tuple is defined by the types of values it contains.</span></span> <span data-ttu-id="39b19-239">Dans Q #, les tuples sont [immuables](xref:microsoft.quantum.glossary#immutable) et peuvent être imbriqués, contenir des tableaux ou utilisés dans un tableau.</span><span class="sxs-lookup"><span data-stu-id="39b19-239">In Q#, tuples are [immutable](xref:microsoft.quantum.glossary#immutable) and can be nested, contain arrays, or used in an array.</span></span> <span data-ttu-id="39b19-240">Pour plus d’informations, consultez [types de tuples](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="39b19-240">For more information, see [Tuple types](xref:microsoft.quantum.guide.types#tuple-types).</span></span>

## <a name="unitary-operator"></a><span data-ttu-id="39b19-241">Opérateur unitaire</span><span class="sxs-lookup"><span data-stu-id="39b19-241">Unitary operator</span></span>

<span data-ttu-id="39b19-242">Opérateur dont l’inverse est égal à son [voisin](xref:microsoft.quantum.glossary#adjoint), c.-à-d. $uu ^ {\dagger } = \ID $ .</span><span class="sxs-lookup"><span data-stu-id="39b19-242">An operator whose inverse is equal to its [adjoint](xref:microsoft.quantum.glossary#adjoint), i.e., $UU^{\dagger} = \id$.</span></span>

## <a name="user-defined-type"></a><span data-ttu-id="39b19-243">Type défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="39b19-243">User-defined type</span></span>

<span data-ttu-id="39b19-244">Collection de types intégrés ou définis précédemment qui peuvent être référencés comme une seule unité.</span><span class="sxs-lookup"><span data-stu-id="39b19-244">A collection of built-in or previously defined types that may be referred to as a single unit.</span></span> <span data-ttu-id="39b19-245">Pour plus d’informations, consultez [types définis par l’utilisateur](xref:microsoft.quantum.guide.types#user-defined-types).</span><span class="sxs-lookup"><span data-stu-id="39b19-245">For more information, see [User-defined types](xref:microsoft.quantum.guide.types#user-defined-types).</span></span>