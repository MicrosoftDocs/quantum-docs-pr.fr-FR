---
title: Utilisation des qubits
description: 'En savoir plus sur l’utilisation de qubits dans Q#'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 9a3d7e03016332a04ac9d1610428b6fcd546d1f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691580"
---
# <a name="working-with-qubits"></a><span data-ttu-id="63e86-103">Utilisation des qubits</span><span class="sxs-lookup"><span data-stu-id="63e86-103">Working with qubits</span></span>

<span data-ttu-id="63e86-104">Qubits sont l’objet fondamental des informations dans quantum computing.</span><span class="sxs-lookup"><span data-stu-id="63e86-104">Qubits are the fundamental object of information in quantum computing.</span></span> <span data-ttu-id="63e86-105">Pour obtenir une présentation générale de qubits, consultez Présentation de l' [informatique quantique](xref:microsoft.quantum.overview.understanding)et pour approfondir la représentation mathématique de cette vue, consultez [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="63e86-105">For a general introduction to qubits, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), and to dive deeper into their mathematical representation, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span> 

<span data-ttu-id="63e86-106">Cet article explore l’utilisation de et de l’utilisation de qubits dans un Q# programme.</span><span class="sxs-lookup"><span data-stu-id="63e86-106">This article explores how to use and work with qubits in a Q# program.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="63e86-107">Aucune des instructions décrites dans cet article n’est valide dans le corps d’une fonction.</span><span class="sxs-lookup"><span data-stu-id="63e86-107">None of the statements discussed in this article are valid within the body of a function.</span></span> <span data-ttu-id="63e86-108">Elles ne sont valides que dans les opérations.</span><span class="sxs-lookup"><span data-stu-id="63e86-108">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="63e86-109">Allocation de qubits</span><span class="sxs-lookup"><span data-stu-id="63e86-109">Allocating Qubits</span></span>

<span data-ttu-id="63e86-110">Étant donné que les qubits physiques sont une ressource précieuse dans un ordinateur quantique, une partie du travail du compilateur consiste à s’assurer qu’ils sont utilisés aussi efficacement que possible.</span><span class="sxs-lookup"><span data-stu-id="63e86-110">Because physical qubits are a precious resource in a quantum computer, part of the compiler's job is to make sure they are being used as efficiently as possible.</span></span>
<span data-ttu-id="63e86-111">Par conséquent, vous devez demander Q# à d' *allouer* qubits pour une utilisation dans un bloc d’instructions particulier.</span><span class="sxs-lookup"><span data-stu-id="63e86-111">As such, you need to tell Q# to *allocate* qubits for use within a particular statement block.</span></span>
<span data-ttu-id="63e86-112">Vous pouvez allouer qubits comme un qubit unique, ou comme un tableau de qubits, connu sous le nom de *Registre* .</span><span class="sxs-lookup"><span data-stu-id="63e86-112">You can allocate qubits as a single qubit, or as an array of qubits, known as a *register* .</span></span> 

### <a name="clean-qubits"></a><span data-ttu-id="63e86-113">Nettoyer qubits</span><span class="sxs-lookup"><span data-stu-id="63e86-113">Clean qubits</span></span>

<span data-ttu-id="63e86-114">Utilisez l' `using` instruction pour allouer de nouvelles qubits à utiliser au cours d’un bloc d’instructions.</span><span class="sxs-lookup"><span data-stu-id="63e86-114">Use the `using` statement to allocate new qubits for use during a statement block.</span></span>

<span data-ttu-id="63e86-115">L’instruction se compose du mot clé `using` , suivi d’une liaison placée entre parenthèses `( )` et du bloc d’instructions dans lequel les qubits sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="63e86-115">The statement consists of the keyword `using`, followed by a binding enclosed in parentheses `( )` and the statement block within which the qubits are available.</span></span>
<span data-ttu-id="63e86-116">La liaison suit le même modèle que les `let` instructions : un symbole unique ou un tuple de symboles, suivi d’un signe égal `=` et d’une valeur unique ou d’un tuple correspondant d' *initialiseurs* .</span><span class="sxs-lookup"><span data-stu-id="63e86-116">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers* .</span></span>

<span data-ttu-id="63e86-117">Les initialiseurs sont disponibles pour un qubit unique, indiqué comme `Qubit()` , ou un tableau de qubits, `Qubit[n]` , où `n` est une `Int` expression.</span><span class="sxs-lookup"><span data-stu-id="63e86-117">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="63e86-118">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="63e86-118">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="63e86-119">Les qubits alloués de cette façon commencent par l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="63e86-119">Any qubits allocated in this way start off in the $\ket{0}$ state.</span></span> <span data-ttu-id="63e86-120">Ainsi, dans l’exemple précédent, `auxiliary` est un qubit unique dans l’État $ \ket {0} $ et `register` est dans l’État cinq qubit $ \ket {00000} = \ket {0} \otimes {0} {0} \ket \otimes \cdots \otimes $.</span><span class="sxs-lookup"><span data-stu-id="63e86-120">Thus in the previous example, `auxiliary` is a single qubit in the state $\ket{0}$, and `register` is in the five-qubit state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="63e86-121">À la fin du `using` bloc, toute qubits allouée par ce bloc est immédiatement désallouée et ne peut plus être utilisée.</span><span class="sxs-lookup"><span data-stu-id="63e86-121">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="63e86-122">Les ordinateurs cibles peuvent réutiliser les qubits désalloués et les proposer à d’autres `using` blocs pour l’allocation.</span><span class="sxs-lookup"><span data-stu-id="63e86-122">Target machines can reuse deallocated qubits and offer them to other `using` blocks for allocation.</span></span> <span data-ttu-id="63e86-123">Par conséquent, l’ordinateur cible s’attend à ce que qubits se trouve dans l’État $ \ket {0} $ immédiatement avant la désallocation.</span><span class="sxs-lookup"><span data-stu-id="63e86-123">As such, the target machine expects that qubits are in the $\ket{0}$ state immediately before deallocation.</span></span>
> <span data-ttu-id="63e86-124">Dans la mesure du possible, utilisez des opérations unitaires pour renvoyer tous les qubits alloués à $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="63e86-124">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="63e86-125">Si nécessaire, vous pouvez utiliser l' @"microsoft.quantum.intrinsic.reset" opération, qui retourne qubit à $ \ket {0} $ en le mesurant et en effectuant une opération de manière conditionnelle en fonction du résultat.</span><span class="sxs-lookup"><span data-stu-id="63e86-125">If need be, you can use the @"microsoft.quantum.intrinsic.reset" operation, which returns the qubit to $\ket{0}$ by measuring it and conditionally performing an operation based on the result.</span></span> <span data-ttu-id="63e86-126">Une telle mesure détruit tout enchevêtrement avec le qubits restant et peut donc avoir un impact sur le calcul.</span><span class="sxs-lookup"><span data-stu-id="63e86-126">Such a measurement destroys any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="63e86-127">Qubits empruntés</span><span class="sxs-lookup"><span data-stu-id="63e86-127">Borrowed Qubits</span></span>

<span data-ttu-id="63e86-128">Utilisez l' `borrowing` instruction pour allouer des qubits pour une utilisation temporaire, qui n’ont pas besoin d’être dans un état spécifique.</span><span class="sxs-lookup"><span data-stu-id="63e86-128">Use the `borrowing` statement to allocate qubits for temporary use, which do not need to be in a specific state.</span></span>

<span data-ttu-id="63e86-129">Vous pouvez utiliser des qubits empruntés comme espace de travail pendant un calcul.</span><span class="sxs-lookup"><span data-stu-id="63e86-129">You can use borrowed qubits as scratch space during a computation.</span></span>
<span data-ttu-id="63e86-130">Ces qubits ne sont généralement pas dans un état propre, autrement dit, ils ne sont pas nécessairement initialisés dans un état connu tel que $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="63e86-130">These qubits are generally not in a clean state, that is, they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="63e86-131">Ils sont souvent appelés qubits « modifiés », car leur état est inconnu et peut même être enchevêtré avec d’autres parties de la mémoire de l’ordinateur quantique.</span><span class="sxs-lookup"><span data-stu-id="63e86-131">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="63e86-132">La liaison suit le même modèle et les mêmes règles que l' `using` instruction.</span><span class="sxs-lookup"><span data-stu-id="63e86-132">The binding follows the same pattern and rules as the `using` statement.</span></span>
<span data-ttu-id="63e86-133">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="63e86-133">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="63e86-134">Le qubits emprunté est dans un état inconnu et est hors de portée à la fin du bloc d’instructions.</span><span class="sxs-lookup"><span data-stu-id="63e86-134">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="63e86-135">L’emprunteur s’engage à laisser le qubits dans le même État que celui dans lequel il se trouvait lorsqu’il les a empruntés ; autrement dit, leur état au début et à la fin du bloc d’instructions doit être le même.</span><span class="sxs-lookup"><span data-stu-id="63e86-135">The borrower commits to leaving the qubits in the same state they were in when they borrowed them; that is, their state at the beginning and the end of the statement block should be the same.</span></span>
<span data-ttu-id="63e86-136">Étant donné que cet État n’est pas nécessairement un État classique, dans la plupart des cas, les étendues de emprunt ne doivent pas contenir de mesures.</span><span class="sxs-lookup"><span data-stu-id="63e86-136">Because this state is not necessarily a classical state, in most cases borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="63e86-137">Lorsque vous empruntez des qubits, le système tente d’abord de remplir la demande à partir de qubits qui sont en cours d’utilisation, mais qui ne sont pas accessibles pendant le corps de l' `borrowing` instruction.</span><span class="sxs-lookup"><span data-stu-id="63e86-137">When borrowing qubits, the system first tries to fill the request from qubits that are in use but not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="63e86-138">S’il n’y a pas suffisamment de qubits, il alloue de nouveaux qubits pour terminer la demande.</span><span class="sxs-lookup"><span data-stu-id="63e86-138">If there aren't enough such qubits, then it allocates new qubits to complete the request.</span></span>

<span data-ttu-id="63e86-139">Parmi les cas d’utilisation connus des qubits modifiés, citons les implémentations de portes CNOTIN multicontrôlées qui requièrent uniquement très peu de qubits et l’implémentation d’incrémenteurs.</span><span class="sxs-lookup"><span data-stu-id="63e86-139">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="63e86-140">Pour obtenir un exemple de leur utilisation dans Q# , consultez l' [exemple emprunting qubits](#borrowing-qubits-example) dans cet article, ou la [*factorisation papier à l’aide de 2n + 2 qubits avec la multiplication modulaire basée sur Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler et Svore 2017) pour un algorithme qui utilise des qubits empruntés.</span><span class="sxs-lookup"><span data-stu-id="63e86-140">For an example of their use in Q#, see [Borrowing Qubits Example](#borrowing-qubits-example) in this article, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="63e86-141">Opérations intrinsèques</span><span class="sxs-lookup"><span data-stu-id="63e86-141">Intrinsic Operations</span></span>

<span data-ttu-id="63e86-142">Une fois allouée, vous pouvez passer un qubit à des fonctions et des opérations.</span><span class="sxs-lookup"><span data-stu-id="63e86-142">Once allocated, you can pass a qubit to functions and operations.</span></span>
<span data-ttu-id="63e86-143">Dans certains cas, il s’agit de tout ce qu’un Q# programme peut faire avec un qubit, car les actions qui peuvent être effectuées sont toutes définies comme des opérations.</span><span class="sxs-lookup"><span data-stu-id="63e86-143">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>

<span data-ttu-id="63e86-144">Cet article présente quelques Q# opérations utiles que vous pouvez utiliser pour interagir avec qubits.</span><span class="sxs-lookup"><span data-stu-id="63e86-144">This article discusses a few useful Q# operations that you can use to interact with qubits.</span></span>
<span data-ttu-id="63e86-145">Pour plus d’informations sur ces éléments et d’autres, consultez [fonctions et opérations intrinsèques](xref:microsoft.quantum.libraries.standard.prelude).</span><span class="sxs-lookup"><span data-stu-id="63e86-145">For more detail about these and others, see [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span> 

<span data-ttu-id="63e86-146">Tout d’abord, les opérateurs Pauli à qubit unique $X $, $Y $ et $Z $ sont représentés Q# par les opérations intrinsèques [`X`](xref:Microsoft.Quantum.Intrinsic.X) , [`Y`](xref:Microsoft.Quantum.Intrinsic.Y) et [`Z`](xref:Microsoft.Quantum.Intrinsic.Z) , chacune d’elles ayant le type `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="63e86-146">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations [`X`](xref:Microsoft.Quantum.Intrinsic.X), [`Y`](xref:Microsoft.Quantum.Intrinsic.Y), and [`Z`](xref:Microsoft.Quantum.Intrinsic.Z), each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="63e86-147">Comme décrit dans [opérations et fonctions intrinsèques](xref:microsoft.quantum.libraries.standard.prelude), imaginez $X $ et, par conséquent, `X` une opération de retournement de bits ou pas de porte.</span><span class="sxs-lookup"><span data-stu-id="63e86-147">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="63e86-148">Vous pouvez utiliser l' `X` opération pour préparer les États de la forme $ \ket{s_0 s_1 \dots S_N} $ pour certaines chaînes de bits classiques $s $ :</span><span class="sxs-lookup"><span data-stu-id="63e86-148">You can use the `X` operation to prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit
is Adj + Ctl {
    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> <span data-ttu-id="63e86-149">Plus tard, vous verrez des méthodes plus compactes pour l’écriture de cette opération qui ne nécessitent pas de contrôle manuel.</span><span class="sxs-lookup"><span data-stu-id="63e86-149">Later, you will see more compact ways of writing this operation that do not require manual control flow.</span></span>

<span data-ttu-id="63e86-150">Vous pouvez également préparer des États tels que $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ et $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\Sqrt {2} $ en utilisant la transformation hadarmard $H $, qui est représentée Q# par l’opération intrinsèque [`H`](xref:Microsoft.Quantum.Intrinsic.H) (également de type (qubit => unité est Adj + CTL) ') :</span><span class="sxs-lookup"><span data-stu-id="63e86-150">You can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation [`H`](xref:Microsoft.Quantum.Intrinsic.H) (also of type (Qubit => Unit is Adj + Ctl)\`):</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="63e86-151">Mesures</span><span class="sxs-lookup"><span data-stu-id="63e86-151">Measurements</span></span>

<span data-ttu-id="63e86-152">Les mesures des qubits individuelles peuvent être effectuées dans différentes bases, chacune représentée par un axe Pauli sur la [sphère Bloch](xref:microsoft.quantum.glossary#bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="63e86-152">Measurements of individual qubits can be performed in different bases, each represented by a Pauli axis on the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere).</span></span>
<span data-ttu-id="63e86-153">La base de *calcul* fait référence à la base `PauliZ` et est la base la plus courante utilisée pour la mesure.</span><span class="sxs-lookup"><span data-stu-id="63e86-153">The *computational basis* refers to the `PauliZ` basis, and is the most common basis used for measurement.</span></span>

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a><span data-ttu-id="63e86-154">Mesure d’un qubit unique dans la `PauliZ` base</span><span class="sxs-lookup"><span data-stu-id="63e86-154">Measure a single qubit in the `PauliZ` basis</span></span>

<span data-ttu-id="63e86-155">Utilisez l' [`M`](xref:Microsoft.Quantum.Intrinsic.M) opération, qui est une opération intrinsèque non unitaire intégrée, pour mesurer un qubit unique dans la `PauliZ` base et assigner une valeur classique au résultat.</span><span class="sxs-lookup"><span data-stu-id="63e86-155">Use the [`M`](xref:Microsoft.Quantum.Intrinsic.M) operation, which is a built-in intrinsic non-unitary operation, to measure a single qubit in the `PauliZ` basis and assign a classical value to the result.</span></span>
<span data-ttu-id="63e86-156">`M` a un type de retour réservé, `Result` , qui peut uniquement prendre des valeurs `Zero` ou `One` correspond aux États mesurés $ \ket {0} $ ou $ \ket {1} $-indiquant que le résultat n’est plus un État Quantum.</span><span class="sxs-lookup"><span data-stu-id="63e86-156">`M` has a reserved return type, `Result`, which can only take values `Zero` or `One` corresponding to the measured states $\ket{0}$ or $\ket{1}$ - indicating that the result is no longer a quantum state.</span></span>

<span data-ttu-id="63e86-157">Un exemple simple est l’opération suivante, qui alloue un qubit dans l’État $ \ket {0} $, puis lui applique une opération hadarmard `H` et mesure le résultat dans la `PauliZ` base.</span><span class="sxs-lookup"><span data-stu-id="63e86-157">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a><span data-ttu-id="63e86-158">Mesure d’un ou plusieurs qubits dans des bases spécifiques</span><span class="sxs-lookup"><span data-stu-id="63e86-158">Measure one or more qubits in specific bases</span></span>

<span data-ttu-id="63e86-159">Pour mesurer un tableau d’un ou plusieurs qubits dans des bases spécifiques, vous pouvez utiliser l' [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) opération.</span><span class="sxs-lookup"><span data-stu-id="63e86-159">To measure an array of one or more qubits in specific bases, you can use the [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) operation.</span></span>

<span data-ttu-id="63e86-160">Les entrées de `Measure` sont un tableau de `Pauli` types (par exemple, `[PauliX, PauliZ, PauliZ]` ) et un tableau de qubits.</span><span class="sxs-lookup"><span data-stu-id="63e86-160">The inputs to `Measure` are an array of `Pauli` types (for example, `[PauliX, PauliZ, PauliZ]`) and an array of qubits.</span></span>

<span data-ttu-id="63e86-161">Un exemple légèrement plus compliqué est donné par l’opération suivante, qui retourne la valeur booléenne `true` si tous les qubits dans un registre de type `Qubit[]` sont dans l’état zéro lorsqu’ils sont mesurés dans une base de Pauli spécifiée, et qui retourne `false` sinon.</span><span class="sxs-lookup"><span data-stu-id="63e86-161">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

<span data-ttu-id="63e86-162">Notez que cet exemple s’exécute toujours uniquement `Measure` sur des qubits individuels, mais l’opération peut être étendue à des mesures communes sur plusieurs qubits.</span><span class="sxs-lookup"><span data-stu-id="63e86-162">Note that this example still only performs `Measure` on individual qubits one at a time, but the operation can be extended to joint measurements on multiple qubits.</span></span>

## <a name="borrowing-qubits-example"></a><span data-ttu-id="63e86-163">Exemple d’emprunt d’qubits</span><span class="sxs-lookup"><span data-stu-id="63e86-163">Borrowing Qubits Example</span></span>

<span data-ttu-id="63e86-164">L’Canon contient des exemples qui utilisent le `borrowing` mot clé, comme la fonction suivante `MultiControlledXBorrow` .</span><span class="sxs-lookup"><span data-stu-id="63e86-164">There are examples in the canon that use the `borrowing` keyword, such as the following function `MultiControlledXBorrow`.</span></span> <span data-ttu-id="63e86-165">Si `controls` indique que le contrôle qubits à ajouter à une `X` opération, le nombre de [ancillas](xref:microsoft.quantum.glossary#ancilla) de modifications ajoutés par cette implémentation est `Length(controls)-2` .</span><span class="sxs-lookup"><span data-stu-id="63e86-165">If `controls` denotes the control qubits to add to an `X` operation, then the number of dirty [ancillas](xref:microsoft.quantum.glossary#ancilla) added by this implementation is `Length(controls)-2`.</span></span>

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

<span data-ttu-id="63e86-166">Notez que cet exemple utilise une utilisation intensive du `With` combinateur, sous sa forme applicable pour les opérations qui prennent en charge joint, par exemple, `WithA` .</span><span class="sxs-lookup"><span data-stu-id="63e86-166">Note that this example used extensive use of the `With` combinator, in its form that is applicable for operations that support adjoint, for example, `WithA`.</span></span>
<span data-ttu-id="63e86-167">Il s’agit d’un bon style de programmation, car l’ajout d’un contrôle à des structures impliquant `With` des propagations contrôle uniquement à l’opération interne.</span><span class="sxs-lookup"><span data-stu-id="63e86-167">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="63e86-168">Notez également que, en plus de l' `body` opération, une implémentation du `controlled` corps de l’opération a été fournie explicitement, plutôt que de recourir à une `controlled auto` instruction.</span><span class="sxs-lookup"><span data-stu-id="63e86-168">Also note that, in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="63e86-169">Cela est dû au fait que, en raison de la structure du circuit, il est facile d’ajouter des contrôles supplémentaires, ce qui est avantageux par rapport à l’ajout du contrôle à chaque porte dans le `body` .</span><span class="sxs-lookup"><span data-stu-id="63e86-169">The reason for this is that, because of the structure of the circuit, it is easy to add further controls, which is beneficial compared to adding control to each gate in the `body`.</span></span> 

<span data-ttu-id="63e86-170">Il est intéressant de comparer ce code avec une autre fonction Canon `MultiControlledXClean` qui atteint le même objectif de l’implémentation d’une opération à contrôle multiple `X` , mais qui utilise plusieurs qubits propres à l’aide du `using` mécanisme.</span><span class="sxs-lookup"><span data-stu-id="63e86-170">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="63e86-171">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="63e86-171">Next steps</span></span>

<span data-ttu-id="63e86-172">En savoir plus sur [le workflow de contrôle](xref:microsoft.quantum.guide.controlflow) dans Q# .</span><span class="sxs-lookup"><span data-stu-id="63e86-172">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>