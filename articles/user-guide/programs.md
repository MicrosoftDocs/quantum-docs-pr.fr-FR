---
title: 'Q # introdution'
description: 'Présentation rapide des programmes Quantum dans Q #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233483"
---
# <a name="q-quantum-programming-language"></a><span data-ttu-id="83f89-103">Q # langage de programmation Quantum</span><span class="sxs-lookup"><span data-stu-id="83f89-103">Q# Quantum Programming Language</span></span>

<span data-ttu-id="83f89-104">Tout ce que vous devez savoir sur le langage de programmation Q # est détaillé dans le [Guide de langage q #](xref:microsoft.quantum.qsharp.index).</span><span class="sxs-lookup"><span data-stu-id="83f89-104">Everything you need to know about the Q# programming language is detailed in the [Q# language guide](xref:microsoft.quantum.qsharp.index).</span></span> <span data-ttu-id="83f89-105">Comme tout autre, notre [processus de conception de langage](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) est open source et les contributions sont les bienvenus.</span><span class="sxs-lookup"><span data-stu-id="83f89-105">Like anything else, our [language design process](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) is open source and we welcome contributions.</span></span>
<span data-ttu-id="83f89-106">Pour plus d’informations sur les fondations et la motivation de Q #, consultez [pourquoi est-ce que q # est nécessaire ?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span><span class="sxs-lookup"><span data-stu-id="83f89-106">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>  
<span data-ttu-id="83f89-107">Q # est fourni dans le cadre du kit de développement quantique (QDK) pour une présentation rapide, consultez [qu’est-ce que le QDK ?](xref:microsoft.quantum.overview.q-sharp).</span><span class="sxs-lookup"><span data-stu-id="83f89-107">Q# is shipped as part of the Quantum Development Kit (QDK) For a quick overview, check out [What is the QDK?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="83f89-108">Qu’est-ce qu’un programme Quantum ?</span><span class="sxs-lookup"><span data-stu-id="83f89-108">What is a quantum program?</span></span>

<span data-ttu-id="83f89-109">Un programme Quantum peut être considéré comme un ensemble particulier de sous-routines classiques qui, lorsqu’il est appelé, effectuent un calcul en interagissant avec un système Quantum ; un programme écrit en Q # ne modélise pas directement l’État Quantum, mais décrit plutôt comment un ordinateur de contrôle classique interagit avec qubits.</span><span class="sxs-lookup"><span data-stu-id="83f89-109">A quantum program can be seen as a particular set of classical subroutines which, when called, perform a computation by interacting with a quantum system; a program written in Q# does not directly model the quantum state, but rather describes how a classical control computer interacts with qubits.</span></span>
<span data-ttu-id="83f89-110">Cela nous permet d’être totalement agnostique quant à ce qu' *est* un État Quantum sur chaque ordinateur cible, qui peut avoir des interprétations différentes en fonction de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="83f89-110">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="83f89-111">Il est important de savoir que Q # n’a pas la possibilité d’inverser l’état d’un qubit ou d’autres propriétés de mécanique de Quantum directement, ce qui garantit qu’un programme Q # peut être exécuté physiquement sur un ordinateur quantique.</span><span class="sxs-lookup"><span data-stu-id="83f89-111">An important consequence of that is that Q# has no ability to introspect into the state of a qubit or other properties of quantum mechanics directly, which guarantees that a Q# program can be physically executed on a quantum computer.</span></span>
<span data-ttu-id="83f89-112">Au lieu de cela, un programme peut appeler des opérations telles que [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) pour extraire des informations classiques d’un qubit.</span><span class="sxs-lookup"><span data-stu-id="83f89-112">Instead, a program can call operations such as [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) to extract classical information from a qubit.</span></span>

<span data-ttu-id="83f89-113">Une fois allouée, un qubit peut être passé à des opérations et des fonctions, également appelées *callables*.</span><span class="sxs-lookup"><span data-stu-id="83f89-113">Once allocated, a qubit can be passed to operations and functions, also referred to as *callables*.</span></span> <span data-ttu-id="83f89-114">Dans certains cas, il s’agit de tout ce qu’un programme Q # peut faire avec un qubit ; Toutes les actions directes sur l’état d’un qubit sont toutes définies par des callables *intrinsèques* , telles que [`X`](xref:Microsoft.Quantum.Intrinsic.X) et, c’est-à-dire des [`H`](xref:Microsoft.Quantum.Intrinsic.H) callables dont les implémentations ne sont pas définies dans Q # mais qui sont plutôt définies par l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="83f89-114">In some sense, this is all that a Q# program can do with a qubit; Any direct actions on state of a qubit are all defined by *intrinsic* callables such as [`X`](xref:Microsoft.Quantum.Intrinsic.X) and [`H`](xref:Microsoft.Quantum.Intrinsic.H) - i.e. callables whose implementations are not defined within Q# but are instead defined by the target machine.</span></span> <span data-ttu-id="83f89-115">Ce que *font* réellement ces opérations n’est rendu concrète que par l’ordinateur cible que nous utilisons pour exécuter le programme Q # en particulier.</span><span class="sxs-lookup"><span data-stu-id="83f89-115">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>

<span data-ttu-id="83f89-116">Par exemple, si vous exécutez le programme sur notre [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator), le simulateur effectue les opérations mathématiques correspondantes sur le système Quantum simulé.</span><span class="sxs-lookup"><span data-stu-id="83f89-116">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="83f89-117">Mais en regardant dans le futur, lorsque l’ordinateur cible est un ordinateur Quantum réel, l’appel de ces opérations dans Q # indiquera à l’ordinateur Quantum d’effectuer les opérations *réelles* correspondantes sur le système Quantum *réel* (par exemple, des impulsions laser avec des minutages précis).</span><span class="sxs-lookup"><span data-stu-id="83f89-117">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="83f89-118">Un programme Q # regroupe ces opérations comme défini par un ordinateur cible pour créer des opérations de niveau supérieur pour exprimer le calcul Quantum.</span><span class="sxs-lookup"><span data-stu-id="83f89-118">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="83f89-119">De cette façon, Q # permet d’exprimer facilement les algorithmes Quantum et Quantum hybrides de logique sous-jacents, tout en étant également général en ce qui concerne la structure d’un ordinateur cible ou d’un simulateur.</span><span class="sxs-lookup"><span data-stu-id="83f89-119">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

<span data-ttu-id="83f89-120">Un exemple simple est le programme suivant, qui alloue un qubit dans l’État $ \ket {0} $, puis lui applique une opération hadarmard `H` et mesure le résultat dans la `PauliZ` base.</span><span class="sxs-lookup"><span data-stu-id="83f89-120">A simple example is the following program, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
@EntryPoint()
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

<span data-ttu-id="83f89-121">Notre [katas Quantum](https://github.com/microsoft/QuantumKatas#introduction) offre une bonne introduction aux [concepts de l’informatique Quantum](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) , tels que les opérations Quantum courantes et la manière de manipuler qubits.</span><span class="sxs-lookup"><span data-stu-id="83f89-121">Our [Quantum Katas](https://github.com/microsoft/QuantumKatas#introduction) give a good introduction on [Quantum Computing Concepts](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) such as common quantum operations and how to manipulate qubits.</span></span> <span data-ttu-id="83f89-122">Vous trouverez d’autres exemples dans [opérations et fonctions intrinsèques](xref:microsoft.quantum.libraries.standard.prelude).</span><span class="sxs-lookup"><span data-stu-id="83f89-122">More examples can also be found in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span>



