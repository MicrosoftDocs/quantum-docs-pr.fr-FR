---
title: 'Opérations et fonctions dans Q #'
description: Comment définir et appeler des opérations et des fonctions, ainsi que les spécialisations d’opérations contrôlées et voisines.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 6cfc1b14d86e86a1cbf0109d5e81dfe50c3a80bf
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630213"
---
# <a name="operations-and-functions-in-q"></a><span data-ttu-id="edcb3-103">Opérations et fonctions dans Q #</span><span class="sxs-lookup"><span data-stu-id="edcb3-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="edcb3-104">Définition de nouvelles opérations</span><span class="sxs-lookup"><span data-stu-id="edcb3-104">Defining New Operations</span></span>

<span data-ttu-id="edcb3-105">Les opérations sont le cœur de Q #.</span><span class="sxs-lookup"><span data-stu-id="edcb3-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="edcb3-106">Une fois déclarées, elles peuvent être appelées à partir d’applications .NET classiques, par exemple, à l’aide d’un simulateur ou d’autres opérations dans Q #.</span><span class="sxs-lookup"><span data-stu-id="edcb3-106">Once declared, they can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="edcb3-107">Chaque opération définie dans Q # peut alors appeler un nombre quelconque d’autres opérations, y compris les opérations intrinsèques intégrées définies par le langage.</span><span class="sxs-lookup"><span data-stu-id="edcb3-107">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="edcb3-108">La façon dont ces opérations intrinsèques sont définies dépend de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="edcb3-108">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span>
<span data-ttu-id="edcb3-109">Une fois compilée, chaque opération est représentée sous la forme d’un type de classe .NET qui peut être fourni aux ordinateurs cibles.</span><span class="sxs-lookup"><span data-stu-id="edcb3-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="edcb3-110">Chaque fichier source Q # peut définir n’importe quel nombre d’opérations.</span><span class="sxs-lookup"><span data-stu-id="edcb3-110">Each Q# source file may define any number of operations.</span></span>
<span data-ttu-id="edcb3-111">Les noms d’opérations doivent être uniques au sein d’un espace de noms et peuvent ne pas être en conflit avec les noms de type ou de fonction.</span><span class="sxs-lookup"><span data-stu-id="edcb3-111">Operation names must be unique within a namespace and may not conflict with type or function names.</span></span>

<span data-ttu-id="edcb3-112">Une déclaration d’opération se compose du mot clé `operation` , suivi du symbole qui est le nom de l’opération, d’un tuple d’identificateur typé qui définit les arguments de l’opération, d’un signe deux-points `:` , d’une annotation de type qui décrit le type de résultat de l’opération, éventuellement d’une annotation avec les caractéristiques de l' `{` opération `}`</span><span class="sxs-lookup"><span data-stu-id="edcb3-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="edcb3-113">Chaque opération prend une entrée, produit une sortie et spécifie l’implémentation pour une ou plusieurs spécialisations d’opérations.</span><span class="sxs-lookup"><span data-stu-id="edcb3-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="edcb3-114">Les spécialisations possibles et comment les définir/les appeler sont détaillés plus loin ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="edcb3-114">The possible specializations, and how to define/call them, are detailed further below.</span></span>
<span data-ttu-id="edcb3-115">Pour l’instant, considérez l’opération suivante, qui définit uniquement une spécialisation de corps par défaut et qui accepte une seule qubit comme entrée, puis appelle l' <xref:microsoft.quantum.intrinsic.x> opération intégrée sur cette entrée :</span><span class="sxs-lookup"><span data-stu-id="edcb3-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="edcb3-116">Le mot clé `operation` commence la définition de l’opération, suivi du nom ; ici, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-116">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="edcb3-117">Ensuite, le type de l’entrée est défini en tant que `Qubit` , ainsi qu’un nom `target` pour faire référence à l’entrée dans la nouvelle opération.</span><span class="sxs-lookup"><span data-stu-id="edcb3-117">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="edcb3-118">De même, le `Unit` définit que la sortie de l’opération est vide.</span><span class="sxs-lookup"><span data-stu-id="edcb3-118">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="edcb3-119">Elle est utilisée de la même façon que `void` dans C# et d’autres langages impératifs, et est équivalente `unit` en F # et d’autres langages fonctionnels.</span><span class="sxs-lookup"><span data-stu-id="edcb3-119">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="edcb3-120">Les opérations peuvent également retourner des types plus intéressants que `Unit` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="edcb3-121">Par exemple, l' <xref:microsoft.quantum.intrinsic.m> opération retourne une sortie de type `Result` , qui représente l’exécution d’une mesure.</span><span class="sxs-lookup"><span data-stu-id="edcb3-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="edcb3-122">Nous pouvons soit transmettre la sortie d’une opération à une autre opération, soit l’utiliser avec le `let` mot clé pour définir une nouvelle variable.</span><span class="sxs-lookup"><span data-stu-id="edcb3-122">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="edcb3-123">Cela permet de représenter un calcul classique qui interagit avec les opérations de Quantum à un niveau bas, par exemple dans le [codage à haute densité](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span><span class="sxs-lookup"><span data-stu-id="edcb3-123">This allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> <span data-ttu-id="edcb3-124">Chaque opération dans Q # prend exactement une entrée et retourne exactement une sortie.</span><span class="sxs-lookup"><span data-stu-id="edcb3-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="edcb3-125">Plusieurs entrées et sorties sont ensuite représentées à l’aide de *tuples*, qui regroupent plusieurs valeurs en une seule valeur.</span><span class="sxs-lookup"><span data-stu-id="edcb3-125">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="edcb3-126">De manière informelle, nous disons que Q # est un langage de type « Tuple-in-out ».</span><span class="sxs-lookup"><span data-stu-id="edcb3-126">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="edcb3-127">Après ce concept, `()` doit ensuite être lu en tant que Tuple « vide », qui a le type `Unit` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-127">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>


## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="edcb3-128">Opérations contrôlées et apjointes</span><span class="sxs-lookup"><span data-stu-id="edcb3-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="edcb3-129">Si une opération implémente une transformation unitaire, comme c’est le cas pour de nombreuses opérations dans Q #, il est possible de définir la façon dont l’opération agit quand *adjointed* ou *contrôlé*.</span><span class="sxs-lookup"><span data-stu-id="edcb3-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="edcb3-130">Une spécialisation *voisine* d’une opération spécifie la manière dont l’inverse de l’opération agit, tandis qu’une spécialisation *contrôlée* spécifie la manière dont une opération agit quand son application est conditionnée sur l’état d’un registre Quantum particulier.</span><span class="sxs-lookup"><span data-stu-id="edcb3-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="edcb3-131">La adjoints des opérations de Quantum est cruciale pour de nombreux aspects de quantum computing.</span><span class="sxs-lookup"><span data-stu-id="edcb3-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="edcb3-132">Plus loin ci-dessous, dans la section des [conjugaisons](#conjugations) , vous trouverez une telle situation abordée avec une technique de programmation Q # utile.</span><span class="sxs-lookup"><span data-stu-id="edcb3-132">Further below, in the [Conjugations](#conjugations) section, you will find one such situation discussed alongside a useful Q# programming technique.</span></span>

<span data-ttu-id="edcb3-133">La version contrôlée d’une opération est une nouvelle opération qui applique efficacement l’opération de base uniquement si tous les qubits de contrôle sont dans un état spécifié.</span><span class="sxs-lookup"><span data-stu-id="edcb3-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="edcb3-134">Si le contrôle qubits est en superposition, l’opération de base est appliquée de manière cohérente à la partie appropriée de la superposition.</span><span class="sxs-lookup"><span data-stu-id="edcb3-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="edcb3-135">Ainsi, les opérations contrôlées sont souvent utilisées pour générer l’enchevêtrement.</span><span class="sxs-lookup"><span data-stu-id="edcb3-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="edcb3-136">Naturellement, une spécialisation *contrôlée* par l’application est également possible, en spécifiant l’application contrôlée du voisin de l’opération.</span><span class="sxs-lookup"><span data-stu-id="edcb3-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="edcb3-137">Si $U $ est la transformation unitaire implémentée par une opération `U` , `Adjoint U` représente la transformation unitaire $U ^ \dagger $, qui est la transformée conjuguée complexe.</span><span class="sxs-lookup"><span data-stu-id="edcb3-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="edcb3-138">L’application successive d’une opération, puis son voisin à un État laisse l’État inchangé, comme illustré par le fait que $UU ^ \dagger = U ^ \dagger U = \ID $, la matrice d’identité.</span><span class="sxs-lookup"><span data-stu-id="edcb3-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="edcb3-139">La représentation unitaire d’une opération contrôlée est légèrement plus en nuance, mais vous pouvez trouver plus de détails dans [quantum computing concepts : multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="edcb3-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="edcb3-140">La section suivante décrit comment appeler ces différentes spécialisations dans votre code Q #.</span><span class="sxs-lookup"><span data-stu-id="edcb3-140">The following section describes how to call these various specializations in your Q# code.</span></span>
<span data-ttu-id="edcb3-141">Ci-dessous, nous expliquons comment définir des opérations pour les prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="edcb3-141">Below, we detail how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="edcb3-142">Appel des spécialisations d’opérations</span><span class="sxs-lookup"><span data-stu-id="edcb3-142">Calling operation specializations</span></span>

<span data-ttu-id="edcb3-143">Un *functor* dans Q # est une fabrique qui définit une nouvelle opération à partir d’une autre opération.</span><span class="sxs-lookup"><span data-stu-id="edcb3-143">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="edcb3-144">Les deux functors standard dans Q # sont `Adjoint` et `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-144">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="edcb3-145">Les functors ont accès à l’implémentation de l’opération de base lors de la définition de l’implémentation de la nouvelle opération.</span><span class="sxs-lookup"><span data-stu-id="edcb3-145">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="edcb3-146">Ainsi, les functors peuvent exécuter des fonctions plus complexes que les fonctions de niveau supérieur traditionnelles.</span><span class="sxs-lookup"><span data-stu-id="edcb3-146">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="edcb3-147">Les functors n’ont pas de représentation dans le système Q # type.</span><span class="sxs-lookup"><span data-stu-id="edcb3-147">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="edcb3-148">Il n’est donc actuellement pas possible de les lier à une variable ou de les passer comme arguments.</span><span class="sxs-lookup"><span data-stu-id="edcb3-148">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="edcb3-149">Un functor est utilisé en l’appliquant à une opération, en retournant une nouvelle opération.</span><span class="sxs-lookup"><span data-stu-id="edcb3-149">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="edcb3-150">Par exemple, l’opération qui résulte de l’application du `Adjoint` functor à l' `Y` opération est écrite sous la forme `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-150">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="edcb3-151">La nouvelle opération peut ensuite être appelée comme toute autre opération.</span><span class="sxs-lookup"><span data-stu-id="edcb3-151">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="edcb3-152">Pour qu’une opération prenne en charge l’application des `Adjoint` functors et/ou `Controlled` , son type de retour doit obligatoirement être `Unit` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-152">For an operation to support application of the `Adjoint` and/or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="edcb3-153">`Adjoint`functor</span><span class="sxs-lookup"><span data-stu-id="edcb3-153">`Adjoint` functor</span></span>

<span data-ttu-id="edcb3-154">Par conséquent, `Adjoint Y(q1)` applique la functor de l’opération joint à l' `Y` opération pour générer une nouvelle opération et applique cette nouvelle opération à `q1` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-154">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="edcb3-155">La nouvelle opération a la même signature et le même type que l’opération de base `Y` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-155">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="edcb3-156">En particulier, la nouvelle opération autorise également `Adjoint` et autorise `Controlled` si et seulement si l’opération de base a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="edcb3-156">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="edcb3-157">Le functor de l’Contigut est son propre inverse ; autrement dit, `Adjoint Adjoint Op` est toujours identique à `Op` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-157">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="edcb3-158">`Controlled`functor</span><span class="sxs-lookup"><span data-stu-id="edcb3-158">`Controlled` functor</span></span>

<span data-ttu-id="edcb3-159">De même, `Controlled X(controls, target)` applique la functor contrôlée à l' `X` opération pour générer une nouvelle opération et applique cette nouvelle opération à `controls` et `target` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-159">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="edcb3-160">Dans Q #, les versions contrôlées prennent toujours un tableau de qubits de contrôle et l’état spécifié est toujours pour tous les qubits de contrôle à l’État calcul ( `PauliZ` ) `One` , $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="edcb3-160">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="edcb3-161">Le contrôle basé sur d’autres États peut être obtenu en appliquant l’opération unitaire appropriée à l’qubits de contrôle avant l’opération contrôlée, puis en appliquant les inversions de l’opération unitaire après l’opération contrôlée.</span><span class="sxs-lookup"><span data-stu-id="edcb3-161">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="edcb3-162">Par exemple, l’application d’une `X` opération à un contrôle qubit avant et après une opération contrôlée entraîne le contrôle de l’état de l’opération `Zero` ($ \ket {0} $) pour ce qubit ; l’application d’une `H` opération avant et après contrôle l' `PauliX` `One` État, c’est-à-dire-1 eigenvalue de Pauli X, $ \ket {-} \mathrel{ : =} (\ket {0} -\ket {1} )/\sqrt {2} $ plutôt que l' `PauliZ` `One` État.</span><span class="sxs-lookup"><span data-stu-id="edcb3-162">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="edcb3-163">En fonction d’une expression d’opération, une nouvelle expression d’opération peut être formée à l’aide de `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="edcb3-163">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="edcb3-164">La signature de la nouvelle opération est basée sur la signature de l’opération d’origine.</span><span class="sxs-lookup"><span data-stu-id="edcb3-164">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="edcb3-165">Le type de résultat est le même, mais le type d’entrée est un double Tuple avec un tableau qubit qui contient les qubit de contrôle comme premier élément et les arguments de l’opération d’origine comme second élément.</span><span class="sxs-lookup"><span data-stu-id="edcb3-165">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="edcb3-166">La nouvelle opération prend en charge `Controlled` et prendra en charge `Adjoint` si et seulement si l’opération d’origine a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="edcb3-166">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="edcb3-167">Si l’opération d’origine n’a pris qu’un seul argument, l’équivalence du tuple de Singleton sera alors lue ici.</span><span class="sxs-lookup"><span data-stu-id="edcb3-167">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="edcb3-168">Par exemple, `Controlled X` est la version contrôlée de l' `X` opération.</span><span class="sxs-lookup"><span data-stu-id="edcb3-168">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="edcb3-169">`X`a `(Qubit => Unit is Adj + Ctl)` un type, donc `Controlled X` a `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` le type ; en raison de l’équivalence de tuple de Singleton, il est identique à `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-169">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="edcb3-170">Si l’opération de base a pris plusieurs arguments, n’oubliez pas de placer les arguments correspondants de la version contrôlée de l’opération entre parenthèses pour les convertir en Tuple.</span><span class="sxs-lookup"><span data-stu-id="edcb3-170">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="edcb3-171">Par exemple, `Controlled Rz` est la version contrôlée de l' `Rz` opération.</span><span class="sxs-lookup"><span data-stu-id="edcb3-171">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="edcb3-172">`Rz`a le type `((Double, Qubit) => Unit is Adj + Ctl)` , `Controlled Rz` a le type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-172">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="edcb3-173">Par conséquent, `Controlled Rz(controls, (0.1, target))` serait un appel valide de `Controlled Rz` (Notez les parenthèses autour de `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="edcb3-173">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="edcb3-174">Autre exemple, `CNOT(control, target)` peut être implémenté en tant que `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-174">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="edcb3-175">Si une cible doit être contrôlée par deux qubits de contrôle (CCNOT), nous pouvons utiliser l' `Controlled X([control1, control2], target)` instruction.</span><span class="sxs-lookup"><span data-stu-id="edcb3-175">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="edcb3-176">Les `Controlled` `Adjoint` functors et sont Permuted, donc il n’y a aucune différence entre l’application `Controlled Adjoint Op` de ou `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-176">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="edcb3-177">Définition des implémentations contrôlées et apjointes</span><span class="sxs-lookup"><span data-stu-id="edcb3-177">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="edcb3-178">Dans les exemples de déclaration de première opération ci-dessus, les opérations `BitFlip` et `DecodeSuperdense` ont été définies avec des signatures `(Qubit => Unit)` et `((Qubit, Qubit) => (Result, Result))` , respectivement.</span><span class="sxs-lookup"><span data-stu-id="edcb3-178">In the first operation declaration examples above, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="edcb3-179">Comme `DecodeSuperdense` comprend des mesures, il ne s’agit pas d’une opération unitaire et, par conséquent, les spécialisations non contrôlées ne peuvent pas exister (Rappelez-vous que l’exigence correspondante retourne une telle opération `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="edcb3-179">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="edcb3-180">Toutefois, comme il `BitFlip` effectue simplement l' <xref:microsoft.quantum.intrinsic.x> opération unitaire, nous aurions pu le définir avec les deux spécialisations.</span><span class="sxs-lookup"><span data-stu-id="edcb3-180">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, we could have defined it with both specializations.</span></span>

<span data-ttu-id="edcb3-181">Ici, nous expliquons comment inclure l’existence de spécialisations dans vos déclarations de l’opération Q #, ce qui leur donne la possibilité d’appeler conjointement avec les `Adjoint` functors et/ou `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-181">Here, we detail how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` and/or `Controlled` functors.</span></span>
<span data-ttu-id="edcb3-182">Plus [loin](#circumstances-for-validly-defining-specializations), nous décrivons certaines situations dans lesquelles il est valide ou non valide pour déclarer certaines spécialisations.</span><span class="sxs-lookup"><span data-stu-id="edcb3-182">Further [below](#circumstances-for-validly-defining-specializations), we describe some of the situations in which it is either valid or not valid to declare certain specializations.</span></span>

<span data-ttu-id="edcb3-183">Les caractéristiques de l’opération définissent les genres d’functors qui peuvent être appliqués à l’opération déclarée et leur effet.</span><span class="sxs-lookup"><span data-stu-id="edcb3-183">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="edcb3-184">L’existence de ces spécialisations peut être déclarée dans le cadre de la signature de l’opération, en particulier par le biais d’une annotation avec les caractéristiques de l’opération : `is Adj` , `is Ctl` ou `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-184">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="edcb3-185">L’implémentation réelle de chaque spécialisation peut être définie *implicitement* ou *explicitement* .</span><span class="sxs-lookup"><span data-stu-id="edcb3-185">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="edcb3-186">Spécification implicite des implémentations</span><span class="sxs-lookup"><span data-stu-id="edcb3-186">Implicitly specifying implementations</span></span>

<span data-ttu-id="edcb3-187">Dans ce cas, le corps de la déclaration d’opération se compose uniquement de l’implémentation par défaut.</span><span class="sxs-lookup"><span data-stu-id="edcb3-187">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="edcb3-188">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="edcb3-188">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="edcb3-189">Ici, l’implémentation correspondante pour chaque spécialisation déclarée implicitement est générée automatiquement par le compilateur, pour être exécutée si les `Adjoint` `Controlled` functors ou sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="edcb3-189">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="edcb3-190">Ainsi, un appel `Adjoint PrepareEntangledPair` à entraînerait le compilateur qui implémente le voisin de `CNOT` , puis le voisin de `H` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-190">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="edcb3-191">Ces opérations individuelles étant à la fois autonomes, l’opération résultante `Adjoint PrepareEntangledPair` consiste simplement à appliquer, `CNOT(here, there)` puis `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-191">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="edcb3-192">Par conséquent, nous pouvons l’utiliser pour écrire l' `DecodeSuperdense` exemple ci-dessus de façon plus compacte, en utilisant le voisin de `PrepareEntangledPair` pour transformer l’État enchevêtré dans une paire non enchevêtrée de qubits :</span><span class="sxs-lookup"><span data-stu-id="edcb3-192">Hence we can use this to write the `DecodeSuperdense` example above more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="edcb3-193">L’annotation avec les caractéristiques de l’opération dans la déclaration est utile pour s’assurer que le compilateur génère automatiquement d’autres spécialisations en fonction de l’implémentation par défaut.</span><span class="sxs-lookup"><span data-stu-id="edcb3-193">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="edcb3-194">Il existe un certain nombre de limitations importantes à prendre en compte lors de la conception d’opérations à utiliser avec functors.</span><span class="sxs-lookup"><span data-stu-id="edcb3-194">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="edcb3-195">Le plus important, les spécialisations pour une opération qui utilise la valeur de sortie d’une autre opération *ne peuvent pas* être générées automatiquement par le compilateur, car il est ambigu de réorganiser les instructions dans une telle opération pour obtenir le même effet.</span><span class="sxs-lookup"><span data-stu-id="edcb3-195">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="edcb3-196">Par conséquent, il est souvent utile de spécifier explicitement les différentes implémentations.</span><span class="sxs-lookup"><span data-stu-id="edcb3-196">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="edcb3-197">Spécification explicite des implémentations</span><span class="sxs-lookup"><span data-stu-id="edcb3-197">Explicitly specifying implementations</span></span>

<span data-ttu-id="edcb3-198">Dans le cas où l’implémentation ne peut pas être générée par le compilateur, elle peut être spécifiée explicitement.</span><span class="sxs-lookup"><span data-stu-id="edcb3-198">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="edcb3-199">Ces déclarations de spécialisation explicites peuvent se composer d’une *directive de génération* appropriée ou d’une implémentation définie par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="edcb3-199">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="edcb3-200">Nous fournissons ici la gamme complète de possibilités, avec des exemples ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="edcb3-200">Here we provide the full range of possibilities, with examples following below.</span></span>


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="edcb3-201">Déclarations de spécialisation explicites</span><span class="sxs-lookup"><span data-stu-id="edcb3-201">Explicit specialization declarations</span></span>

<span data-ttu-id="edcb3-202">Les opérations Q # peuvent contenir les déclarations de spécialisation explicites suivantes :</span><span class="sxs-lookup"><span data-stu-id="edcb3-202">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="edcb3-203">La `body` spécialisation spécifie l’implémentation de l’opération sans les functors appliqués.</span><span class="sxs-lookup"><span data-stu-id="edcb3-203">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="edcb3-204">La `adjoint` spécialisation spécifie l’implémentation de l’opération avec le `Adjoint` functor appliqué.</span><span class="sxs-lookup"><span data-stu-id="edcb3-204">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="edcb3-205">La `controlled` spécialisation spécifie l’implémentation de l’opération avec le `Controlled` functor appliqué.</span><span class="sxs-lookup"><span data-stu-id="edcb3-205">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="edcb3-206">La `controlled adjoint` spécialisation spécifie l’implémentation de l’opération avec `Adjoint` les `Controlled` functors et appliqués.</span><span class="sxs-lookup"><span data-stu-id="edcb3-206">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="edcb3-207">Cette spécialisation peut également être nommée `adjoint controlled` , dans la mesure où les deux functors se comportent.</span><span class="sxs-lookup"><span data-stu-id="edcb3-207">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="edcb3-208">Une spécialisation d’opération se compose de la balise de spécialisation (par exemple `body` , ou `adjoint` , etc.) suivie de l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="edcb3-208">An operation specialization consists of the specialization tag (e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="edcb3-209">Déclaration explicite comme décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="edcb3-209">An explicit declaration as described below.</span></span>
- <span data-ttu-id="edcb3-210">*Directive* qui indique au compilateur *Comment* générer la spécialisation, l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="edcb3-210">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="edcb3-211">`intrinsic`, qui indique que la spécialisation est fournie par l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="edcb3-211">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="edcb3-212">`distribute`, qui peut être utilisé avec les `controlled` `controlled adjoint` spécialisations et.</span><span class="sxs-lookup"><span data-stu-id="edcb3-212">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="edcb3-213">Lorsqu' `controlled` il est utilisé avec, il indique que le compilateur doit calculer la spécialisation en appliquant `Controlled` à toutes les opérations dans le `body` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-213">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="edcb3-214">Lorsqu' `controlled adjoint` il est utilisé avec, il indique que le compilateur doit calculer la spécialisation en appliquant `Controlled` à toutes les opérations de la `adjoint` spécialisation.</span><span class="sxs-lookup"><span data-stu-id="edcb3-214">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="edcb3-215">`invert`, qui indique que le compilateur doit calculer la `adjoint` spécialisation en inversant le `body` , c’est-à-dire en inversant l’ordre des opérations et en appliquant le voisin à chacun d’entre eux.</span><span class="sxs-lookup"><span data-stu-id="edcb3-215">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="edcb3-216">Lorsqu' `adjoint controlled` il est utilisé avec, cela indique que le compilateur doit calculer la spécialisation en inversant la `controlled` spécialisation.</span><span class="sxs-lookup"><span data-stu-id="edcb3-216">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="edcb3-217">`self`, pour indiquer que la spécialisation voisine est la même que la `body` spécialisation.</span><span class="sxs-lookup"><span data-stu-id="edcb3-217">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="edcb3-218">Cela est légal pour les `adjoint` `adjoint controlled` spécialisations et.</span><span class="sxs-lookup"><span data-stu-id="edcb3-218">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="edcb3-219">Pour `adjoint controlled` , `self` implique que la `adjoint controlled` spécialisation est la même que la `controlled` spécialisation.</span><span class="sxs-lookup"><span data-stu-id="edcb3-219">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="edcb3-220">`auto`, pour indiquer que le compilateur doit sélectionner une directive appropriée à appliquer.</span><span class="sxs-lookup"><span data-stu-id="edcb3-220">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="edcb3-221">`auto`ne peut pas être utilisé pour la `body` spécialisation.</span><span class="sxs-lookup"><span data-stu-id="edcb3-221">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="edcb3-222">Les directives et `auto` toutes requièrent un point-virgule fermant `;` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-222">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="edcb3-223">La `auto` directive se résout en la directive de génération suivante si une déclaration explicite de `body` est fournie :</span><span class="sxs-lookup"><span data-stu-id="edcb3-223">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="edcb3-224">La `adjoint` spécialisation est générée en fonction de la directive `invert` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-224">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="edcb3-225">La `controlled` spécialisation est générée en fonction de la directive `distribute` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-225">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="edcb3-226">La `adjoint controlled` spécialisation est générée selon la directive `invert` si une déclaration explicite pour `controlled` est donnée, mais pas pour `adjoint` , et dans le `distribute` cas contraire.</span><span class="sxs-lookup"><span data-stu-id="edcb3-226">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="edcb3-227">Si une opération est auto-jointe, spécifiez explicitement le voisint ou la spécialisation voisine contrôlée à l’aide de la directive `self` de génération pour permettre au compilateur d’utiliser ces informations à des fins d’optimisation.</span><span class="sxs-lookup"><span data-stu-id="edcb3-227">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="edcb3-228">Une déclaration de spécialisation contenant une implémentation définie par l’utilisateur se compose d’un tuple d’argument suivi d’un bloc d’instructions avec le code Q # qui implémente la spécialisation.</span><span class="sxs-lookup"><span data-stu-id="edcb3-228">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="edcb3-229">Dans la liste d’arguments, `...` est utilisé pour représenter les arguments déclarés pour l’opération dans son ensemble.</span><span class="sxs-lookup"><span data-stu-id="edcb3-229">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="edcb3-230">Pour `body` et `adjoint` , la liste d’arguments doit toujours être `(...)` ; pour `controlled` et `adjoint controlled` , la liste d’arguments doit être un symbole qui représente le tableau de qubits de contrôle, suivi de `...` , placé entre parenthèses ; par exemple, `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-230">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="edcb3-231">Exemples</span><span class="sxs-lookup"><span data-stu-id="edcb3-231">Examples</span></span>

<span data-ttu-id="edcb3-232">Une déclaration d’opération peut être aussi simple que la suivante, qui définit l’opération Pauli X primitive :</span><span class="sxs-lookup"><span data-stu-id="edcb3-232">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="edcb3-233">Notez que la fonction joint de l’opération Pauli X est définie avec la directive `self` , car par définition `X` est sa propre inverse.</span><span class="sxs-lookup"><span data-stu-id="edcb3-233">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="edcb3-234">Le code ci `PrepareEntangledPair` -dessus par exemple est équivalent au code ci-dessous, contenant des déclarations de spécialisation explicites :</span><span class="sxs-lookup"><span data-stu-id="edcb3-234">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="edcb3-235">Le mot clé `auto` indique que le compilateur doit déterminer comment générer l’implémentation de la spécialisation.</span><span class="sxs-lookup"><span data-stu-id="edcb3-235">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="edcb3-236">Implémentation de spécialisation définie par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="edcb3-236">User-defined specialization implementation</span></span>

<span data-ttu-id="edcb3-237">Si le compilateur ne peut pas générer automatiquement l’implémentation pour une certaine spécialisation, ou si une implémentation plus efficace peut être donnée, l’implémentation peut également être définie manuellement.</span><span class="sxs-lookup"><span data-stu-id="edcb3-237">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="edcb3-238">Dans l’exemple ci-dessus, `adjoint invert;` indique que la spécialisation voisine doit être générée en inversant l’implémentation du corps, et `controlled adjoint invert;` indique que la spécialisation de l’entité voisine contrôlée doit être générée en inversant l’implémentation donnée de la spécialisation contrôlée.</span><span class="sxs-lookup"><span data-stu-id="edcb3-238">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="edcb3-239">Si une ou plusieurs spécialisations en plus du corps par défaut doivent être déclarées explicitement, l’implémentation du corps par défaut doit également être incluse dans une déclaration de spécialisation appropriée :</span><span class="sxs-lookup"><span data-stu-id="edcb3-239">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="edcb3-240">Circonstances de la définition correcte de spécialisations</span><span class="sxs-lookup"><span data-stu-id="edcb3-240">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="edcb3-241">Déclarations d’opération avec le voisin/contrôlé</span><span class="sxs-lookup"><span data-stu-id="edcb3-241">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="edcb3-242">Il est légal de spécifier une opération sans les versions voisines ou contrôlées.</span><span class="sxs-lookup"><span data-stu-id="edcb3-242">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="edcb3-243">Par exemple, les opérations de mesure n’ont aucune valeur, car elles ne sont pas réversibles ni contrôlables.</span><span class="sxs-lookup"><span data-stu-id="edcb3-243">For instance, measurement operations have neither, because they are not invertible or controllable.</span></span>

<span data-ttu-id="edcb3-244">Une opération prend en charge les `Adjoint` functors et/ou `Controlled` si sa déclaration contient une déclaration implicite ou explicite des spécialisations respectives.</span><span class="sxs-lookup"><span data-stu-id="edcb3-244">An operation supports the `Adjoint` and/or `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="edcb3-245">Une spécialisation dépendante ou contrôlée de manière explicite implique l’existence d’une spécialisation voisine/contrôlée.</span><span class="sxs-lookup"><span data-stu-id="edcb3-245">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="edcb3-246">Pour une opération dont le corps contient des boucles de répétition jusqu’à réussite, des instructions SET, des mesures, des instructions return ou des appels à d’autres opérations qui ne prennent pas en charge le `Adjoint` functor, la génération automatique d’une spécialisation Join à la suite de la `invert` `auto` directive ou n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="edcb3-246">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="edcb3-247">Pour une opération dont le corps contient des appels à d’autres opérations qui ne prennent pas en charge le `Controlled` functor, la génération automatique d’une spécialisation contrôlée à la suite de la `distribute` `auto` directive ou n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="edcb3-247">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="edcb3-248">Contigut contrôlé</span><span class="sxs-lookup"><span data-stu-id="edcb3-248">Controlled Adjoint</span></span>

<span data-ttu-id="edcb3-249">La version contrôlée par le contrôle contigut d’une opération spécifie la manière dont une version contrôlée par Quantum de l’opération est implémentée.</span><span class="sxs-lookup"><span data-stu-id="edcb3-249">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="edcb3-250">Il est possible de spécifier une opération sans contrôle de version voisine. par exemple, les opérations de mesure n’ont pas de version définie par l’utilisateur, car elles ne sont ni contrôlables ni réversibles.</span><span class="sxs-lookup"><span data-stu-id="edcb3-250">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="edcb3-251">Une spécialisation voisine de l’opération doit exister si et seulement si une spécialisation et une spécialisation contrôlée existent.</span><span class="sxs-lookup"><span data-stu-id="edcb3-251">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="edcb3-252">Dans ce cas, l’existence de la spécialisation voisine contrôlée est déduite et une spécialisation appropriée est générée par le compilateur si aucune implémentation n’a été définie explicitement.</span><span class="sxs-lookup"><span data-stu-id="edcb3-252">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="edcb3-253">Pour une opération dont le corps contient des appels à d’autres opérations qui n’ont pas de version définie par le contrôle, il n’est pas possible de générer automatiquement une spécialisation adjacente à la suite de la `invert` `distribute` `auto` directive ou.</span><span class="sxs-lookup"><span data-stu-id="edcb3-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="edcb3-254">Compatibilité de type</span><span class="sxs-lookup"><span data-stu-id="edcb3-254">Type Compatibility</span></span>

<span data-ttu-id="edcb3-255">Une opération avec des functors supplémentaires pris en charge peut être utilisée partout où une opération avec moins d’functors, mais la même signature est attendue.</span><span class="sxs-lookup"><span data-stu-id="edcb3-255">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="edcb3-256">Par exemple, une opération de type `(Qubit => Unit is Adj)` peut être utilisée partout où une opération de type `(Qubit => Unit)` est attendue.</span><span class="sxs-lookup"><span data-stu-id="edcb3-256">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="edcb3-257">Q # est *covariant* en ce qui concerne les types de retour pouvant être appelés : un pouvant être appelé qui retourne un type `'A` est compatible avec un pouvant être appelé avec le même type d’entrée et un type de résultat `'A` compatible avec.</span><span class="sxs-lookup"><span data-stu-id="edcb3-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="edcb3-258">Q # est *contravariant* en ce qui concerne les types d’entrée : un pouvant être appelé qui prend un type `'A` comme entrée est compatible avec un appelable avec le même type de résultat et un type d’entrée compatible avec `'A` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="edcb3-259">Autrement dit, étant donné les définitions suivantes :</span><span class="sxs-lookup"><span data-stu-id="edcb3-259">That is, given the following definitions:</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="edcb3-260">les conditions suivantes sont vraies :</span><span class="sxs-lookup"><span data-stu-id="edcb3-260">the following are true:</span></span>

- <span data-ttu-id="edcb3-261">La fonction `ConjugateInvertWith` peut être appelée avec un `inner` argument de `Invert` ou `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-261">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="edcb3-262">La fonction `ConjugateUnitaryWith` peut être appelée avec un `inner` argument de `ApplyUnitary` , mais pas `Invert` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-262">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="edcb3-263">Une valeur de type `(Qubit[] => Unit is Adj + Ctl)` peut être retournée à partir de `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-263">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="edcb3-264">Q # 0,3 a introduit une différence significative dans le comportement des types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="edcb3-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="edcb3-265">Les types définis par l’utilisateur sont traités comme une version encapsulée du type sous-jacent, plutôt qu’en tant que sous-type.</span><span class="sxs-lookup"><span data-stu-id="edcb3-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="edcb3-266">Cela signifie qu’une valeur d’un type défini par l’utilisateur n’est pas utilisable quand une valeur du type sous-jacent est attendue.</span><span class="sxs-lookup"><span data-stu-id="edcb3-266">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>


### <a name="conjugations"></a><span data-ttu-id="edcb3-267">Conjugaisons</span><span class="sxs-lookup"><span data-stu-id="edcb3-267">Conjugations</span></span>

<span data-ttu-id="edcb3-268">Contrairement aux bits classiques, la libération de la mémoire Quantum est un peu plus complexe, car la réinitialisation aveugle de qubits peut avoir des effets indésirables sur le calcul restant si les qubits sont toujours pris en compte.</span><span class="sxs-lookup"><span data-stu-id="edcb3-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="edcb3-269">Cela peut être évité en « annulant » les calculs effectués avant la libération de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="edcb3-269">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="edcb3-270">Un modèle courant dans quantum computing est donc le suivant :</span><span class="sxs-lookup"><span data-stu-id="edcb3-270">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="edcb3-271">À partir de notre version 0,9, nous prenons en charge une instruction de conjugaison qui implémente la transformation ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="edcb3-271">Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="edcb3-272">À l’aide de cette instruction, l’opération `ApplyWith` peut être implémentée de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="edcb3-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="edcb3-273">Une telle instruction de conjugaison devient évidemment beaucoup plus utile si les transformations externes et internes ne sont pas facilement disponibles en tant qu’opérations, mais sont plutôt plus pratiques à décrire par un bloc composé de plusieurs instructions.</span><span class="sxs-lookup"><span data-stu-id="edcb3-273">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="edcb3-274">La transformation inverse pour les instructions définies dans le bloc intérieur est générée automatiquement par le compilateur et exécutée après la fin du bloc apply.</span><span class="sxs-lookup"><span data-stu-id="edcb3-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span>
<span data-ttu-id="edcb3-275">Étant donné que toutes les variables mutables utilisées dans le cadre du bloc within ne peuvent pas être reliées dans le bloc Apply, il est garanti que la transformation générée est le voisin du calcul dans le bloc intérieur.</span><span class="sxs-lookup"><span data-stu-id="edcb3-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="edcb3-276">Définition de nouvelles fonctions</span><span class="sxs-lookup"><span data-stu-id="edcb3-276">Defining New Functions</span></span>

<span data-ttu-id="edcb3-277">Les fonctions sont purement déterministes, les routines classiques dans Q #, qui sont distinctes des opérations en ce qu’elles ne sont pas autorisées à avoir des effets autres que le calcul d’une valeur de sortie.</span><span class="sxs-lookup"><span data-stu-id="edcb3-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="edcb3-278">En particulier, les fonctions ne peuvent pas appeler d’opérations ; agir sur, allouer ou emprunter qubits ; exemples de nombres aléatoires Sinon, dépend de l’État au-delà de la valeur d’entrée d’une fonction.</span><span class="sxs-lookup"><span data-stu-id="edcb3-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="edcb3-279">Par conséquent, les fonctions Q # sont *pures*, car elles mappent toujours les mêmes valeurs d’entrée aux mêmes valeurs de sortie.</span><span class="sxs-lookup"><span data-stu-id="edcb3-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="edcb3-280">Cela permet au compilateur Q # de réorganiser en toute sécurité le mode et le moment où les fonctions sont appelées lors de la génération de spécialisations d’opérations.</span><span class="sxs-lookup"><span data-stu-id="edcb3-280">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="edcb3-281">Chaque fichier source Q # peut définir un nombre quelconque de fonctions.</span><span class="sxs-lookup"><span data-stu-id="edcb3-281">Each Q# source file may define any number of functions.</span></span>
<span data-ttu-id="edcb3-282">Les noms de fonctions doivent être uniques dans un espace de noms et peuvent ne pas être en conflit avec des noms d’opération ou de type.</span><span class="sxs-lookup"><span data-stu-id="edcb3-282">Function names must be unique within a namespace and may not conflict with operation or type names.</span></span>

<span data-ttu-id="edcb3-283">La définition d’une fonction fonctionne de la même façon que la définition d’une opération, à la différence qu’il n’est pas possible de définir des spécialisations voisines ou contrôlées pour une fonction.</span><span class="sxs-lookup"><span data-stu-id="edcb3-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="edcb3-284">Exemple :</span><span class="sxs-lookup"><span data-stu-id="edcb3-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="edcb3-285">or</span><span class="sxs-lookup"><span data-stu-id="edcb3-285">or</span></span> 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="edcb3-286">Logique classique dans les fonctions = = bonne</span><span class="sxs-lookup"><span data-stu-id="edcb3-286">Classical logic in functions == good</span></span>

<span data-ttu-id="edcb3-287">Chaque fois que cela est possible, il est utile d’écrire la logique classique en termes de fonctions plutôt que d’opérations, afin qu’elle puisse être utilisée plus facilement à partir des opérations.</span><span class="sxs-lookup"><span data-stu-id="edcb3-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="edcb3-288">Par exemple, si nous avions écrit la `Square` déclaration ci-dessus en tant qu' *opération*, le compilateur n’aurait pas pu garantir que l’appel de la même entrée produirait toujours les mêmes sorties.</span><span class="sxs-lookup"><span data-stu-id="edcb3-288">For example, if we had written the `Square` declaration above as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="edcb3-289">Pour souligner la différence entre les fonctions et les opérations, envisagez le problème d’échantillonnage classique d’un nombre aléatoire à partir d’une opération Q # :</span><span class="sxs-lookup"><span data-stu-id="edcb3-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="edcb3-290">Chaque fois que `U` est appelé, il aura une action différente sur `target` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-290">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="edcb3-291">En particulier, le compilateur ne peut pas garantir que si nous avons ajouté une `adjoint auto` déclaration de spécialisation à `U` , `U(target); Adjoint U(target);` agit en tant qu’identité (autrement dit, en tant que non-op).</span><span class="sxs-lookup"><span data-stu-id="edcb3-291">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="edcb3-292">Cela viole la définition de l’voisine que nous avons vu dans les [vecteurs et les matrices](xref:microsoft.quantum.concepts.vectors), de telle sorte que la génération automatique d’une spécialisation de la version voisine dans une opération où l’opération a été appelée <xref:microsoft.quantum.math.randomreal> entraînerait la rupture des garanties fournies par le compilateur ; <xref:microsoft.quantum.math.randomreal> est une opération pour laquelle il n’existe pas de version voisine ou contrôlée.</span><span class="sxs-lookup"><span data-stu-id="edcb3-292">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="edcb3-293">D’un autre côté, en autorisant les appels de fonction tels que `Square` is safe, dans le sens où le compilateur peut être certain qu’il n’a besoin de conserver l’entrée que pour `Square` maintenir sa sortie stable.</span><span class="sxs-lookup"><span data-stu-id="edcb3-293">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="edcb3-294">Ainsi, l’isolation de la logique classique la plus possible dans les fonctions facilite la réutilisation de cette logique dans d’autres fonctions et opérations.</span><span class="sxs-lookup"><span data-stu-id="edcb3-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="edcb3-295">Générique (paramètre de type) callables</span><span class="sxs-lookup"><span data-stu-id="edcb3-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="edcb3-296">De nombreuses fonctions et opérations que nous pouvons souhaiter définir ne s’appuient pas vraiment sur les types de leurs entrées, mais plutôt implicitement utiliser leurs types via une autre fonction ou opération.</span><span class="sxs-lookup"><span data-stu-id="edcb3-296">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="edcb3-297">Par exemple, considérez le concept de *carte* commun à de nombreux langages fonctionnels ; à partir d’une fonction $f (x) $ et d’une collection de valeurs $ \{ X_1, X_2, \dots, x_n \} $, Map retourne une nouvelle collection $ \{ f (X_1), f (X_2), \dots, f (x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="edcb3-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="edcb3-298">Pour l’implémenter dans Q #, nous pouvons tirer parti de la première classe de ces fonctions.</span><span class="sxs-lookup"><span data-stu-id="edcb3-298">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="edcb3-299">Nous allons écrire un exemple rapide de `Map` , en utilisant ★ en tant qu’espace réservé tout en décrivant les types dont nous avons besoin.</span><span class="sxs-lookup"><span data-stu-id="edcb3-299">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="edcb3-300">Remarque Cette fonction est très similaire, quel que soit le type réel que nous remplaçons.</span><span class="sxs-lookup"><span data-stu-id="edcb3-300">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="edcb3-301">Une carte des entiers à Paulis, par exemple, est similaire à une carte à partir de nombres à virgule flottante en chaînes :</span><span class="sxs-lookup"><span data-stu-id="edcb3-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="edcb3-302">En principe, nous pourrions écrire une version de `Map` pour chaque paire de types que nous rencontrons, mais cela présente un certain nombre de difficultés.</span><span class="sxs-lookup"><span data-stu-id="edcb3-302">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="edcb3-303">Par exemple, si nous trouvons un bogue dans `Map` , nous devons nous assurer que le correctif est appliqué uniformément dans toutes les versions de `Map` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-303">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="edcb3-304">De plus, si nous créons un nouveau tuple ou un type défini par l’utilisateur, nous devons maintenant également construire un nouveau `Map` pour qu’il se présente avec le nouveau type.</span><span class="sxs-lookup"><span data-stu-id="edcb3-304">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="edcb3-305">Bien que cela soit tractable pour un petit nombre de ces fonctions, étant donné que nous recueillons de plus en plus de fonctions de la même forme que `Map` , le coût de l’introduction de nouveaux types devient insuffisant dans un ordre relativement court.</span><span class="sxs-lookup"><span data-stu-id="edcb3-305">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="edcb3-306">Toutefois, une grande partie de cette difficulté est que nous n’avons pas donné au compilateur les informations dont il a besoin pour reconnaître la manière dont les différentes versions de `Map` sont liées.</span><span class="sxs-lookup"><span data-stu-id="edcb3-306">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="edcb3-307">En fait, nous voulons que le compilateur traite `Map` comme une sorte de fonction mathématique des *types* q # en fonctions q #.</span><span class="sxs-lookup"><span data-stu-id="edcb3-307">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="edcb3-308">Cette notion est formalisée en autorisant les fonctions et les opérations à avoir des *paramètres de type*, ainsi que leurs paramètres de tuple ordinaires.</span><span class="sxs-lookup"><span data-stu-id="edcb3-308">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="edcb3-309">Dans les exemples ci-dessus, nous souhaitons considérer `Map` comme ayant des paramètres `Int, Pauli` de type dans le premier cas et `Double, String` dans le deuxième cas.</span><span class="sxs-lookup"><span data-stu-id="edcb3-309">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="edcb3-310">Dans la plupart des cas, ces paramètres de type peuvent ensuite être utilisés comme s’il s’agissait de types ordinaires : nous utilisons des valeurs de paramètres de type pour créer des tableaux et des tuples, appeler des fonctions et des opérations, et les assigner à des variables ordinaires ou mutables.</span><span class="sxs-lookup"><span data-stu-id="edcb3-310">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="edcb3-311">Le cas le plus extrême de dépendance indirecte est celui de qubits, où un programme Q # ne peut pas s’appuyer directement sur la structure du `Qubit` type, mais **doit** passer ces types à d’autres opérations et fonctions.</span><span class="sxs-lookup"><span data-stu-id="edcb3-311">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="edcb3-312">En revenant à l’exemple ci-dessus, nous voyons que nous avons besoin `Map` de paramètres de type, l’un pour représenter l’entrée à `fn` et l’autre pour représenter la sortie de `fn` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-312">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="edcb3-313">Dans Q #, il est écrit en ajoutant des crochets pointus (c’est-à-dire `<>` , pas brakets $ \braket {} $ !) après le nom d’une fonction ou d’une opération dans sa déclaration, et en répertoriant chaque paramètre de type.</span><span class="sxs-lookup"><span data-stu-id="edcb3-313">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="edcb3-314">Le nom de chaque paramètre de type doit commencer par un battement `'` , indiquant qu’il s’agit d’un paramètre de type et non d’un type ordinaire (également connu sous le nom de type *concret* ).</span><span class="sxs-lookup"><span data-stu-id="edcb3-314">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="edcb3-315">Pour `Map` , nous écrivons donc :</span><span class="sxs-lookup"><span data-stu-id="edcb3-315">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="edcb3-316">Notez que la définition de `Map<'Input, 'Output>` semble très similaire aux versions que nous avons écrites auparavant.</span><span class="sxs-lookup"><span data-stu-id="edcb3-316">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="edcb3-317">La seule différence est que nous avons explicitement informé le compilateur qui `Map` ne dépend pas directement de ce qui `'Input` `'Output` est, mais fonctionne pour deux types quelconques en les utilisant indirectement via `fn` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-317">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="edcb3-318">Une fois que nous avons défini `Map<'Input, 'Output>` cette méthode, vous pouvez l’appeler comme s’il s’agissait d’une fonction ordinaire :</span><span class="sxs-lookup"><span data-stu-id="edcb3-318">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="edcb3-319">L’écriture de fonctions et d’opérations génériques est un emplacement où « tuple en sortie de tuple » est un moyen très utile de réfléchir aux fonctions et opérations Q #.</span><span class="sxs-lookup"><span data-stu-id="edcb3-319">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="edcb3-320">Dans la mesure où chaque fonction accepte exactement une entrée et retourne une seule sortie, une entrée de type `'T -> 'U` correspond à *n’importe quelle* fonction Q # de quelque manière que ce soit.</span><span class="sxs-lookup"><span data-stu-id="edcb3-320">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="edcb3-321">De même, toute opération peut être passée à une entrée de type `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-321">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="edcb3-322">En guise de deuxième exemple, considérez le défi que pose l’écriture d’une fonction qui retourne la composition de deux autres fonctions :</span><span class="sxs-lookup"><span data-stu-id="edcb3-322">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="edcb3-323">Ici, nous devons spécifier exactement ce que, `A` `B` et `C` sont, par conséquent, en limitant gravement l’utilitaire de notre nouvelle `Compose` fonction.</span><span class="sxs-lookup"><span data-stu-id="edcb3-323">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="edcb3-324">Après tout, `Compose` dépend uniquement de `A` , et `B` `C` *via* `innerFn` et `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-324">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="edcb3-325">En guise d’alternative, nous pouvons ajouter des paramètres de type à `Compose` qui indiquent qu’il fonctionne pour *n’importe quel* `A` , `B` , et `C` , tant que ces paramètres correspondent à ceux attendus par `innerFn` et `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="edcb3-325">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="edcb3-326">Les bibliothèques standard Q # fournissent une série de ces opérations et fonctions paramétrées de type pour faciliter l’utilisation du workflow de contrôle d’ordre supérieur.</span><span class="sxs-lookup"><span data-stu-id="edcb3-326">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="edcb3-327">Celles-ci sont abordées plus en détail dans le Guide de la [bibliothèque standard Q #](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="edcb3-327">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="edcb3-328">Callables comme valeurs de première classe</span><span class="sxs-lookup"><span data-stu-id="edcb3-328">Callables as First-Class Values</span></span>

<span data-ttu-id="edcb3-329">Une technique critique pour le type de contrôle et la logique classique utilisant des fonctions plutôt que des opérations consiste à utiliser les opérations et les fonctions dans Q # qui sont de *première classe*.</span><span class="sxs-lookup"><span data-stu-id="edcb3-329">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="edcb3-330">En d’autres termes, il s’agit de chaque valeur de la langue, à son propre droit.</span><span class="sxs-lookup"><span data-stu-id="edcb3-330">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="edcb3-331">Par exemple, le code suivant est parfaitement valide Q #, si un peu indirect :</span><span class="sxs-lookup"><span data-stu-id="edcb3-331">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="edcb3-332">La valeur de la variable `ourH` dans l’extrait de code ci-dessus est ensuite l’opération <xref:microsoft.quantum.intrinsic.h> , de sorte que nous pouvons appeler cette valeur comme toute autre opération.</span><span class="sxs-lookup"><span data-stu-id="edcb3-332">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="edcb3-333">Cela nous permet d’écrire des opérations qui prennent des opérations dans le cadre de leur entrée, formant ainsi des concepts de contrôle d’ordre supérieur.</span><span class="sxs-lookup"><span data-stu-id="edcb3-333">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="edcb3-334">Par exemple, nous pourrions penser à « squareiser » une opération en l’appliquant deux fois au même qubit cible.</span><span class="sxs-lookup"><span data-stu-id="edcb3-334">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="edcb3-335">Retour d’opérations à partir d’une fonction</span><span class="sxs-lookup"><span data-stu-id="edcb3-335">Returning operations from a function</span></span>

<span data-ttu-id="edcb3-336">Nous insistons sur le fait que nous pouvons également retourner des opérations dans le cadre des sorties, de telle sorte que nous puissions isoler certains genres de logique conditionnelle classique comme une fonction classique qui retourne une description d’un programme Quantum sous la forme d’une opération.</span><span class="sxs-lookup"><span data-stu-id="edcb3-336">We emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="edcb3-337">En guise d’exemple simple, prenons l’exemple de téléportage, dans lequel le tiers recevant un message classique à deux bits doit utiliser le message pour décoder leur qubit dans l’État téléporté approprié.</span><span class="sxs-lookup"><span data-stu-id="edcb3-337">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="edcb3-338">Nous pourrions écrire cela en termes d’une fonction qui prend ces deux bits classiques et retourne l’opération de décodage appropriée.</span><span class="sxs-lookup"><span data-stu-id="edcb3-338">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

<span data-ttu-id="edcb3-339">Cette nouvelle fonction est effectivement une fonction, car si nous l’appelons avec les mêmes valeurs que `hereBit` et `thereBit` , nous obtenons toujours la même opération.</span><span class="sxs-lookup"><span data-stu-id="edcb3-339">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="edcb3-340">Par conséquent, le décodeur peut être exécuté en toute sécurité au sein d’opérations sans avoir à expliquer comment la logique de décodage interagit avec les définitions des différentes spécialisations d’opérations.</span><span class="sxs-lookup"><span data-stu-id="edcb3-340">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="edcb3-341">Autrement dit, nous avons isolé la logique classique à l’intérieur d’une fonction, garantissant au compilateur que l’appel de fonction peut être réorganisé avec impunity tant que l’entrée est conservée.</span><span class="sxs-lookup"><span data-stu-id="edcb3-341">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="edcb3-342">Application partielle</span><span class="sxs-lookup"><span data-stu-id="edcb3-342">Partial Application</span></span>

<span data-ttu-id="edcb3-343">Nous pouvons en faire beaucoup plus avec les fonctions qui retournent des opérations à l’aide d’une *application partielle*, dans laquelle nous pouvons fournir une ou plusieurs parties de l’entrée à une fonction ou une opération sans réellement l’appeler.</span><span class="sxs-lookup"><span data-stu-id="edcb3-343">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="edcb3-344">Par exemple, en rappelant l' `ApplyTwice` exemple ci-dessus, nous pouvons indiquer que nous ne voulons pas spécifier, immédiatement, à quel qubit l’opération d’entrée doit s’appliquer :</span><span class="sxs-lookup"><span data-stu-id="edcb3-344">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="edcb3-345">Dans ce cas, la variable locale `twiceOp` contient l’opération partiellement appliquée `ApplyTwice(op, _)` , où des parties de l’entrée qui n’ont pas encore été spécifiées sont indiquées par `_` .</span><span class="sxs-lookup"><span data-stu-id="edcb3-345">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="edcb3-346">Lorsque nous appelons `twiceOp` en fait la ligne suivante, nous passons comme entrée à l’opération partiellement appliquée, toutes les autres parties de l’entrée à l’opération d’origine.</span><span class="sxs-lookup"><span data-stu-id="edcb3-346">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="edcb3-347">Ainsi, l’extrait de code ci-dessus est effectivement identique à l’appel `ApplyTwice(op, target)` direct, économisez pour que nous ayons introduit une nouvelle variable locale qui nous permet de retarder l’appel tout en fournissant certaines parties de l’entrée.</span><span class="sxs-lookup"><span data-stu-id="edcb3-347">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="edcb3-348">Étant donné qu’une opération partiellement appliquée n’est pas réellement appelée tant que l’intégralité de son entrée n’a pas été fournie, nous pouvons appliquer des opérations en toute sécurité, même à partir de fonctions.</span><span class="sxs-lookup"><span data-stu-id="edcb3-348">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="edcb3-349">En principe, la logique classique dans `SquareOperation` pourrait avoir été bien plus complexe, mais elle est toujours isolée du reste d’une opération par les garanties que le compilateur peut offrir sur les fonctions.</span><span class="sxs-lookup"><span data-stu-id="edcb3-349">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="edcb3-350">Cette approche sera utilisée dans la bibliothèque standard Q # pour exprimer le workflow de contrôle classique de manière à pouvoir l’utiliser facilement dans des programmes quantiques.</span><span class="sxs-lookup"><span data-stu-id="edcb3-350">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>


## <a name="recursion"></a><span data-ttu-id="edcb3-351">Récursivité</span><span class="sxs-lookup"><span data-stu-id="edcb3-351">Recursion</span></span>

<span data-ttu-id="edcb3-352">Q # callables peuvent être récursives directement ou indirectement.</span><span class="sxs-lookup"><span data-stu-id="edcb3-352">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="edcb3-353">Autrement dit, une opération ou une fonction peut s’appeler elle-même, ou elle peut appeler un autre pouvant être appelé, qui appelle directement ou indirectement l’opération pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="edcb3-353">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="edcb3-354">Il existe toutefois deux commentaires importants sur l’utilisation de la récursivité :</span><span class="sxs-lookup"><span data-stu-id="edcb3-354">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="edcb3-355">L’utilisation de la récursivité dans les opérations est susceptible d’interférer avec certaines optimisations.</span><span class="sxs-lookup"><span data-stu-id="edcb3-355">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="edcb3-356">Cela peut avoir un impact important sur la durée d’exécution de l’algorithme.</span><span class="sxs-lookup"><span data-stu-id="edcb3-356">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="edcb3-357">En cas d’exécution sur un appareil Quantum réel, l’espace de pile peut être limité et, par conséquent, une récurrence profonde peut entraîner une erreur d’exécution.</span><span class="sxs-lookup"><span data-stu-id="edcb3-357">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="edcb3-358">En particulier, le compilateur et le runtime Q # n’identifient pas et n’optimisent pas la récurrence de la fin.</span><span class="sxs-lookup"><span data-stu-id="edcb3-358">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="edcb3-359">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="edcb3-359">Next steps</span></span>

<span data-ttu-id="edcb3-360">En savoir plus sur les [variables](xref:microsoft.quantum.guide.variables) dans Q #.</span><span class="sxs-lookup"><span data-stu-id="edcb3-360">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>