---
title: Utilisation de qubits
description: 'Utilisation des techniques qubits-Q #'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: dc6db93dadc37534aece9624fe516125d919f8cd
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819992"
---
# <a name="working-with-qubits"></a><span data-ttu-id="168ff-103">Utilisation de qubits</span><span class="sxs-lookup"><span data-stu-id="168ff-103">Working with Qubits</span></span>

<span data-ttu-id="168ff-104">Maintenant que vous avez vu une variété de différentes parties du langage Q #, nous allons nous pencher sur l’épaisseur de l’informatique et découvrir comment utiliser qubits eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="168ff-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="168ff-105">Allocation de qubits</span><span class="sxs-lookup"><span data-stu-id="168ff-105">Allocating Qubits</span></span>

<span data-ttu-id="168ff-106">Tout d’abord, pour obtenir un qubit que nous pouvons utiliser dans Q #, nous *allouez* des qubits dans un bloc de `using` :</span><span class="sxs-lookup"><span data-stu-id="168ff-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="168ff-107">Les qubits alloués de cette façon commencent par l’État $ \ket{0}$; dans l’exemple ci-dessus, `register` est donc à l’État $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="168ff-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="168ff-108">À la fin du bloc `using`, toute qubits allouée par ce bloc est immédiatement désallouée et ne peut plus être utilisée.</span><span class="sxs-lookup"><span data-stu-id="168ff-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="168ff-109">Les ordinateurs cibles s’attendent à ce que les qubits se trouvent dans l’État $ \ket{0}$ immédiatement avant la désallocation, afin qu’ils puissent être réutilisés et proposés à d’autres blocs `using` pour l’allocation.</span><span class="sxs-lookup"><span data-stu-id="168ff-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="168ff-110">Dans la mesure du possible, utilisez des opérations unitaires pour renvoyer tous les qubits alloués à $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="168ff-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="168ff-111">Si nécessaire, l’opération @"microsoft.quantum.intrinsic.reset" peut être utilisée pour mesurer un qubit à la place, et pour utiliser ce résultat de mesure pour s’assurer que le qubit mesuré est retourné à $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="168ff-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="168ff-112">Une telle mesure détruit tout enchevêtrement avec le qubits restant et peut donc avoir un impact sur le calcul.</span><span class="sxs-lookup"><span data-stu-id="168ff-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="168ff-113">Opérations intrinsèques</span><span class="sxs-lookup"><span data-stu-id="168ff-113">Intrinsic Operations</span></span>

<span data-ttu-id="168ff-114">Une fois allouée, un qubit peut ensuite être passé aux fonctions et opérations.</span><span class="sxs-lookup"><span data-stu-id="168ff-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="168ff-115">Dans certains cas, il s’agit de tout ce qu’un programme Q # peut faire avec un qubit, car les actions qui peuvent être effectuées sont toutes définies comme des opérations.</span><span class="sxs-lookup"><span data-stu-id="168ff-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="168ff-116">Nous verrons ces opérations plus en détail dans les [opérations et les fonctions intrinsèques](xref:microsoft.quantum.libraries.standard.prelude), mais pour l’instant, nous mentionnons quelques opérations utiles qui peuvent être utilisées pour interagir avec qubits.</span><span class="sxs-lookup"><span data-stu-id="168ff-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="168ff-117">Tout d’abord, les opérateurs Pauli à qubit unique $X $, $Y $ et $Z $ sont représentés dans Q # par les opérations intrinsèques `X`, `Y`et `Z`, chacune ayant une `(Qubit => Unit is Adj + Ctl)`de type.</span><span class="sxs-lookup"><span data-stu-id="168ff-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="168ff-118">Comme décrit dans [opérations et fonctions intrinsèques](xref:microsoft.quantum.libraries.standard.prelude), nous pouvons considérer $X $ et, par conséquent, `X` en tant qu’opération de retournement de bits ou non de porte.</span><span class="sxs-lookup"><span data-stu-id="168ff-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="168ff-119">L’opération de `X` nous permet de préparer les États de la forme $ \ket{s_0 s_1 \dots s_n} $ pour certaines chaînes de bits classiques $s $ :</span><span class="sxs-lookup"><span data-stu-id="168ff-119">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="168ff-120">Plus tard, nous verrons des moyens plus compacts d’écrire cette opération qui ne nécessitent pas de contrôle de Flow manuel.</span><span class="sxs-lookup"><span data-stu-id="168ff-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="168ff-121">Nous pouvons également préparer des États tels que $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ et $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ en utilisant la transformation Hadarmard $H $, qui est représentée dans Q # par l’opération intrinsèque `H : (Qubit => Unit is Adj + Ctl)`:</span><span class="sxs-lookup"><span data-stu-id="168ff-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="168ff-122">Mesures</span><span class="sxs-lookup"><span data-stu-id="168ff-122">Measurements</span></span>

<span data-ttu-id="168ff-123">À l’aide de l’opération `Measure`, qui est une opération intrinsèque non unitaire intégrée, nous pouvons extraire les informations classiques d’un objet de type `Qubit` et assigner une valeur classique comme résultat, qui a un type réservé `Result`, indiquant que le résultat n’est plus un État Quantum.</span><span class="sxs-lookup"><span data-stu-id="168ff-123">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="168ff-124">L’entrée à `Measure` est un axe Pauli sur la sphère Bloch, représenté par une valeur de type `Pauli` (par exemple `PauliX`) et une valeur de type `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="168ff-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="168ff-125">Un exemple simple est l’opération suivante, qui alloue un qubit dans l’État $ \ket{0}$, puis applique une opération Hadarmard `H` et mesure le résultat dans la base de `PauliZ`.</span><span class="sxs-lookup"><span data-stu-id="168ff-125">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

<span data-ttu-id="168ff-126">Un exemple légèrement plus compliqué est donné par l’opération suivante, qui retourne la valeur booléenne `true` si tous les qubits dans un registre de type `Qubit[]` sont dans l’état zéro lorsqu’ils sont mesurés dans une base Pauli spécifiée, et qui retourne `false` dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="168ff-126">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="168ff-127">Le langage Q # permet au workflow de contrôle classique de dépendre des résultats de la mesure des qubits.</span><span class="sxs-lookup"><span data-stu-id="168ff-127">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="168ff-128">Cette fonctionnalité permet à son tour d’implémenter des gadgets probabilistes puissants qui peuvent réduire le coût de calcul de l’implémentation des unités.</span><span class="sxs-lookup"><span data-stu-id="168ff-128">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="168ff-129">Par exemple, il est facile d’implémenter des modèles de *répétition jusqu’à réussite* (RUS) dans Q #.</span><span class="sxs-lookup"><span data-stu-id="168ff-129">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="168ff-130">Ces modèles de RUS sont des programmes probabilistes qui ont un coût faible *attendu* en termes de portes élémentaires, mais pour lesquels le coût réel dépend d’une exécution réelle et d’un entrelacement réel de diverses branches possibles.</span><span class="sxs-lookup"><span data-stu-id="168ff-130">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="168ff-131">Pour faciliter les modèles de répétition jusqu’à réussite (RUS), Q # prend en charge la construction</span><span class="sxs-lookup"><span data-stu-id="168ff-131">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

<span data-ttu-id="168ff-132">où `statementBlock1` et `statementBlock2` sont des instructions Q # ou plus, et `expression` toute expression valide qui correspond à une valeur de type `Bool`.</span><span class="sxs-lookup"><span data-stu-id="168ff-132">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="168ff-133">Dans un cas d’usage courant, l’opération Q # suivante implémente une rotation autour d’un axe irrationnelle de $ (I + 2i Z)/\sqrt{5}$ sur la sphère Bloch.</span><span class="sxs-lookup"><span data-stu-id="168ff-133">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="168ff-134">Pour ce faire, utilisez un modèle de RUS connu :</span><span class="sxs-lookup"><span data-stu-id="168ff-134">This is accomplished by using a known RUS pattern:</span></span>

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

<span data-ttu-id="168ff-135">Cet exemple montre l’utilisation d’une variable mutable `finished` qui se trouve dans la portée de la boucle REPEAT-UNTIL-Fixup entière et qui est initialisée avant la boucle et mise à jour à l’étape de correction.</span><span class="sxs-lookup"><span data-stu-id="168ff-135">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="168ff-136">Enfin, nous présentons un exemple de modèle de RUS pour préparer un État Quantum $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, à partir de l’État $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="168ff-136">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="168ff-137">Consultez également l' [exemple de test unitaire fourni avec la bibliothèque standard](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="168ff-137">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

<span data-ttu-id="168ff-138">Les fonctionnalités de programmation notables présentées dans cette opération sont une `fixup` une partie plus complexe de la boucle, qui implique des opérations Quantum et l’utilisation d’instructions `AssertProb` pour déterminer la probabilité de mesurer l’État Quantum à certains points spécifiés dans le programme.</span><span class="sxs-lookup"><span data-stu-id="168ff-138">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="168ff-139">Pour plus d’informations sur les opérations d' [`Assert`](xref:microsoft.quantum.intrinsic.assert) et de [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) , consultez aussi [test et débogage](xref:microsoft.quantum.techniques.testing-and-debugging) .</span><span class="sxs-lookup"><span data-stu-id="168ff-139">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>
