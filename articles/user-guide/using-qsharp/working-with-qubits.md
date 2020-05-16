---
title: Utilisation des qubits
description: Description de remplissage
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: e89b9ccfe2a0796e01eedfc99f7ce71038d85f38
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430932"
---
# <a name="working-with-qubits"></a><span data-ttu-id="2baa6-103">Utilisation des qubits</span><span class="sxs-lookup"><span data-stu-id="2baa6-103">Working with qubits</span></span>

<span data-ttu-id="2baa6-104">Maintenant que vous avez vu une variété de différentes parties du langage Q #, nous allons nous pencher sur l’épaisseur de l’informatique et découvrir comment utiliser qubits eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="2baa6-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

<span data-ttu-id="2baa6-105">Notez qu’aucune de ces instructions n’est autorisée dans le corps d’une fonction.</span><span class="sxs-lookup"><span data-stu-id="2baa6-105">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="2baa6-106">Elles ne sont valides que dans les opérations.</span><span class="sxs-lookup"><span data-stu-id="2baa6-106">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="2baa6-107">Allocation de qubits</span><span class="sxs-lookup"><span data-stu-id="2baa6-107">Allocating Qubits</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="2baa6-108">Nettoyer qubits</span><span class="sxs-lookup"><span data-stu-id="2baa6-108">Clean qubits</span></span>

<span data-ttu-id="2baa6-109">L' `using` instruction est utilisée pour *allouer* de nouvelles qubits à utiliser au cours d’un bloc d’instructions.</span><span class="sxs-lookup"><span data-stu-id="2baa6-109">The `using` statement is used to *allocate* new qubits for use during a statement block.</span></span>

<span data-ttu-id="2baa6-110">L’instruction se compose du mot clé `using` , suivi d’une parenthèse ouverte `(` , d’une liaison, d’une parenthèse fermante `)` et du bloc d’instructions dans lequel le qubits est disponible.</span><span class="sxs-lookup"><span data-stu-id="2baa6-110">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="2baa6-111">La liaison suit le même modèle que les `let` instructions : un symbole unique ou un tuple de symboles, suivi d’un signe égal `=` et d’une valeur unique ou d’un tuple correspondant d' *initialiseurs*.</span><span class="sxs-lookup"><span data-stu-id="2baa6-111">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="2baa6-112">Les initialiseurs sont disponibles pour un qubit unique, indiqué comme `Qubit()` , ou un tableau de qubits, `Qubit[n]` , où `n` est une `Int` expression.</span><span class="sxs-lookup"><span data-stu-id="2baa6-112">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="2baa6-113">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="2baa6-113">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="2baa6-114">Les qubits alloués de cette façon commencent par l’État $ \ket {0} $. dans l’exemple ci-dessus, `register` est donc à l’État $ \ket {00000} = \ket {0} \otimes \ket \otimes \cdots \otimes {0} \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="2baa6-114">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="2baa6-115">À la fin du `using` bloc, toute qubits allouée par ce bloc est immédiatement désallouée et ne peut plus être utilisée.</span><span class="sxs-lookup"><span data-stu-id="2baa6-115">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="2baa6-116">Les ordinateurs cibles s’attendent à ce que les qubits se trouvent dans l’État $ \ket {0} $ immédiatement avant la désallocation, afin qu’ils puissent être réutilisés et proposés à d’autres `using` blocs pour l’allocation.</span><span class="sxs-lookup"><span data-stu-id="2baa6-116">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="2baa6-117">Dans la mesure du possible, utilisez des opérations unitaires pour renvoyer tous les qubits alloués à $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="2baa6-117">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="2baa6-118">Si nécessaire, l' @"microsoft.quantum.intrinsic.reset" opération peut être utilisée pour mesurer un qubit à la place, et pour utiliser ce résultat de mesure pour garantir que le qubit mesuré est retourné à $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="2baa6-118">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="2baa6-119">Une telle mesure détruit tout enchevêtrement avec le qubits restant et peut donc avoir un impact sur le calcul.</span><span class="sxs-lookup"><span data-stu-id="2baa6-119">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="2baa6-120">Qubits empruntés</span><span class="sxs-lookup"><span data-stu-id="2baa6-120">Borrowed Qubits</span></span>

<span data-ttu-id="2baa6-121">L' `borrowing` instruction est utilisée pour rendre les qubits disponibles pour une utilisation temporaire, qui n’ont pas besoin d’être dans un état spécifique.</span><span class="sxs-lookup"><span data-stu-id="2baa6-121">The `borrowing` statement is used to make qubits available for temporary use, which do not need be in a specific state.</span></span>

<span data-ttu-id="2baa6-122">Le mécanisme d’emprunt autorise l’allocation de qubits qui peut être utilisé comme espace de travail pendant un calcul.</span><span class="sxs-lookup"><span data-stu-id="2baa6-122">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span>
<span data-ttu-id="2baa6-123">Ces qubits ne sont généralement pas dans un état propre, c’est-à-dire qu’ils ne sont pas nécessairement initialisés dans un état connu tel que $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="2baa6-123">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="2baa6-124">Ils sont souvent appelés qubits « modifiés », car leur état est inconnu et peut même être enchevêtré avec d’autres parties de la mémoire de l’ordinateur quantique.</span><span class="sxs-lookup"><span data-stu-id="2baa6-124">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="2baa6-125">La liaison suit le même modèle et les mêmes règles que celle d’une `using` instruction.</span><span class="sxs-lookup"><span data-stu-id="2baa6-125">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>
<span data-ttu-id="2baa6-126">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="2baa6-126">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="2baa6-127">Le qubits emprunté est dans un état inconnu et est hors de portée à la fin du bloc d’instructions.</span><span class="sxs-lookup"><span data-stu-id="2baa6-127">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="2baa6-128">L’emprunteur s’engage à laisser le qubits dans le même État que celui dans lequel il se trouvait lorsqu’il a été emprunté, c’est-à-dire que son état au début et à la fin du bloc d’instructions est supposé être le même.</span><span class="sxs-lookup"><span data-stu-id="2baa6-128">The borrower commits to leaving the qubits in the same state they were in when they were borrowed,  i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="2baa6-129">En particulier, cet État n’est pas nécessairement un État classique, ce qui signifie que dans la plupart des cas, les étendues d’emprunt ne doivent pas contenir de mesures.</span><span class="sxs-lookup"><span data-stu-id="2baa6-129">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="2baa6-130">Lorsque vous empruntez des qubits, le système tente d’abord de remplir la demande à partir de qubits qui sont en cours d’utilisation, mais qui ne sont pas accessibles pendant le corps de l' `borrowing` instruction.</span><span class="sxs-lookup"><span data-stu-id="2baa6-130">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="2baa6-131">S’il n’y a pas suffisamment de qubits, il allouera de nouvelles qubits pour terminer la demande.</span><span class="sxs-lookup"><span data-stu-id="2baa6-131">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>


<span data-ttu-id="2baa6-132">Parmi les cas d’utilisation connus des qubits modifiés, citons les implémentations de portes CNOTIN multicontrôlées qui requièrent uniquement très peu de qubits et l’implémentation d’incrémenteurs.</span><span class="sxs-lookup"><span data-stu-id="2baa6-132">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="2baa6-133">Pour voir un exemple de leur utilisation dans Q #, ou la factorisation du papier [*à l’aide de 2n + 2 qubits avec multiplication modulaire basée sur Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler et Svore 2017) pour un algorithme utilisant des qubits empruntés, consultez l' [exemple qubits emprunté](#borrowing-qubits-example) ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="2baa6-133">See the [Borrowing Qubits Example](#borrowing-qubits-example) below to see an example of their use in Q#, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>


## <a name="intrinsic-operations"></a><span data-ttu-id="2baa6-134">Opérations intrinsèques</span><span class="sxs-lookup"><span data-stu-id="2baa6-134">Intrinsic Operations</span></span>

<span data-ttu-id="2baa6-135">Une fois allouée, un qubit peut ensuite être passé aux fonctions et opérations.</span><span class="sxs-lookup"><span data-stu-id="2baa6-135">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="2baa6-136">Dans certains cas, il s’agit de tout ce qu’un programme Q # peut faire avec un qubit, car les actions qui peuvent être effectuées sont toutes définies comme des opérations.</span><span class="sxs-lookup"><span data-stu-id="2baa6-136">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="2baa6-137">Nous verrons ces opérations plus en détail dans les [opérations et les fonctions intrinsèques](xref:microsoft.quantum.libraries.standard.prelude), mais pour l’instant, nous mentionnons quelques opérations utiles qui peuvent être utilisées pour interagir avec qubits.</span><span class="sxs-lookup"><span data-stu-id="2baa6-137">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="2baa6-138">Tout d’abord, les opérateurs Pauli à qubit unique $X $, $Y $ et $Z $ sont représentés dans Q # par les opérations intrinsèques `X` , `Y` et `Z` , chacune ayant le type `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="2baa6-138">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="2baa6-139">Comme décrit dans [opérations et fonctions intrinsèques](xref:microsoft.quantum.libraries.standard.prelude), nous pouvons considérer $X $ et donc `X` comme une opération de retournement de bits ou non de porte.</span><span class="sxs-lookup"><span data-stu-id="2baa6-139">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="2baa6-140">L' `X` opération nous permet de préparer les États de la forme $ \ket{s_0 s_1 \dots S_N} $ pour certaines chaînes de bits classiques $s $ :</span><span class="sxs-lookup"><span data-stu-id="2baa6-140">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> <span data-ttu-id="2baa6-141">Plus tard, nous verrons des moyens plus compacts d’écrire cette opération qui ne nécessitent pas de contrôle de Flow manuel.</span><span class="sxs-lookup"><span data-stu-id="2baa6-141">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="2baa6-142">Nous pouvons également préparer des États tels que $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ et $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\Sqrt {2} $ en utilisant la transformation hadarmard $H $, qui est représentée dans Q # par l’opération intrinsèque `H : (Qubit => Unit is Adj + Ctl)` :</span><span class="sxs-lookup"><span data-stu-id="2baa6-142">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="2baa6-143">Mesures</span><span class="sxs-lookup"><span data-stu-id="2baa6-143">Measurements</span></span>

<span data-ttu-id="2baa6-144">À l’aide de l' `Measure` opération, qui est une opération intrinsèque non unitaire intégrée, nous pouvons extraire les informations classiques d’un objet de type `Qubit` et assigner une valeur classique comme résultat, qui a un type réservé `Result` , indiquant que le résultat n’est plus un État Quantum.</span><span class="sxs-lookup"><span data-stu-id="2baa6-144">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="2baa6-145">L’entrée de `Measure` est un axe Pauli sur la sphère Bloch, représenté par une valeur de type `Pauli` (par exemple `PauliX` ) et une valeur de type `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="2baa6-145">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="2baa6-146">Un exemple simple est l’opération suivante, qui alloue un qubit dans l’État $ \ket {0} $, puis lui applique une opération hadarmard `H` et mesure le résultat dans la `PauliZ` base.</span><span class="sxs-lookup"><span data-stu-id="2baa6-146">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

<span data-ttu-id="2baa6-147">Un exemple légèrement plus compliqué est donné par l’opération suivante, qui retourne la valeur booléenne `true` si tous les qubits dans un registre de type `Qubit[]` sont dans l’état zéro lorsqu’ils sont mesurés dans une base de Pauli spécifiée, et qui retourne `false` sinon.</span><span class="sxs-lookup"><span data-stu-id="2baa6-147">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

## <a name="borrowing-qubits-example"></a><span data-ttu-id="2baa6-148">Exemple d’emprunt d’qubits</span><span class="sxs-lookup"><span data-stu-id="2baa6-148">Borrowing Qubits Example</span></span>

<span data-ttu-id="2baa6-149">Dans l’Canon, il existe des exemples qui utilisent le `borrowing` mot clé, par exemple la fonction `MultiControlledXBorrow` définie ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="2baa6-149">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="2baa6-150">Si `controls` dénote le contrôle qubits qui doit être ajouté à une `X` opération, un `Length(controls)-2` grand nombre de ancillas d’intégrité incorrects seront ajoutés par cette implémentation.</span><span class="sxs-lookup"><span data-stu-id="2baa6-150">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="2baa6-151">Notez que l’utilisation intensive de l' `With` ---combinable dans sa forme applicable pour les opérations qui prennent en charge joint, c’est-à-dire, `WithA` ---a été effectuée dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="2baa6-151">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example.</span></span>
<span data-ttu-id="2baa6-152">Il s’agit d’un bon style de programmation, car l’ajout d’un contrôle à des structures impliquant `With` des propagations contrôle uniquement à l’opération interne.</span><span class="sxs-lookup"><span data-stu-id="2baa6-152">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="2baa6-153">Notez également que, en plus du `body` de l’opération, une implémentation du `controlled` corps de l’opération a été explicitement fournie, plutôt que de recourir à une `controlled auto` instruction.</span><span class="sxs-lookup"><span data-stu-id="2baa6-153">Further, note that here in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="2baa6-154">Cela est dû au fait que nous savons à partir de la structure du circuit comment ajouter facilement des contrôles supplémentaires, ce qui est avantageux par rapport à l’ajout de contrôle à chaque porte individuelle dans le `body` .</span><span class="sxs-lookup"><span data-stu-id="2baa6-154">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="2baa6-155">Il est intéressant de comparer ce code avec une autre fonction Canon `MultiControlledXClean` qui atteint le même objectif de l’implémentation d’une opération à contrôle multiple `X` , mais qui utilise plusieurs qubits propres à l’aide du `using` mécanisme.</span><span class="sxs-lookup"><span data-stu-id="2baa6-155">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="whats-next"></a><span data-ttu-id="2baa6-156">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="2baa6-156">What's Next?</span></span>
<span data-ttu-id="2baa6-157">En savoir plus sur [le workflow de contrôle](xref:microsoft.quantum.guide.controlflow) dans Q #.</span><span class="sxs-lookup"><span data-stu-id="2baa6-157">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>