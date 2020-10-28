---
title: 'Opérations et fonctions dans :::no-loc(Q#):::'
description: Comment définir et appeler des opérations et des fonctions, ainsi que les spécialisations d’opérations contrôlées et voisines.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 55e6d3e1a242386c46213083692377520df83a80
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692128"
---
# <a name="operations-and-functions-in-no-locq"></a><span data-ttu-id="a6b71-103">Opérations et fonctions dans :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="a6b71-103">Operations and Functions in :::no-loc(Q#):::</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="a6b71-104">Définition de nouvelles opérations</span><span class="sxs-lookup"><span data-stu-id="a6b71-104">Defining New Operations</span></span>

<span data-ttu-id="a6b71-105">Les opérations sont le cœur de :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="a6b71-105">Operations are the core of :::no-loc(Q#):::.</span></span>
<span data-ttu-id="a6b71-106">Une fois déclarées, elles peuvent être appelées à partir d’applications .NET classiques, par exemple, à l’aide d’un simulateur ou d’autres opérations dans :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="a6b71-106">Once declared, they can either be called from classical .NET applications, for example, using a simulator or by other operations within :::no-loc(Q#):::.</span></span>
<span data-ttu-id="a6b71-107">Chaque opération définie dans :::no-loc(Q#)::: peut appeler un nombre quelconque d’autres opérations, y compris les opérations intrinsèques intégrées définies par le langage.</span><span class="sxs-lookup"><span data-stu-id="a6b71-107">Each operation defined in :::no-loc(Q#)::: can call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="a6b71-108">La façon dont :::no-loc(Q#)::: définit ces opérations intrinsèques dépend de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="a6b71-108">The particular way in which :::no-loc(Q#)::: defines these intrinsic operations depends on the target machine.</span></span>
<span data-ttu-id="a6b71-109">Une fois compilée, chaque opération est représentée sous la forme d’un type de classe .NET qui peut être fourni aux ordinateurs cibles.</span><span class="sxs-lookup"><span data-stu-id="a6b71-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="a6b71-110">Chaque :::no-loc(Q#)::: fichier source peut définir un nombre quelconque d’opérations.</span><span class="sxs-lookup"><span data-stu-id="a6b71-110">Each :::no-loc(Q#)::: source file can define any number of operations.</span></span>
<span data-ttu-id="a6b71-111">Les noms d’opérations doivent être uniques dans un espace de noms et ne peuvent pas être en conflit avec des noms de type ou de fonction.</span><span class="sxs-lookup"><span data-stu-id="a6b71-111">Operation names must be unique within a namespace and can not conflict with type or function names.</span></span>

<span data-ttu-id="a6b71-112">Une déclaration d’opération se compose du mot clé `operation` , suivi du symbole qui est le nom de l’opération, d’un tuple d’identificateur typé qui définit les arguments de l’opération, d’un signe deux-points `:` , d’une annotation de type qui décrit le type de résultat de l’opération, éventuellement d’une annotation avec les caractéristiques de l’opération `{ }`</span><span class="sxs-lookup"><span data-stu-id="a6b71-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace, and then the body of the operation declaration, enclosed in braces `{ }`.</span></span>

<span data-ttu-id="a6b71-113">Chaque opération prend une entrée, produit une sortie et spécifie l’implémentation pour une ou plusieurs spécialisations d’opérations.</span><span class="sxs-lookup"><span data-stu-id="a6b71-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="a6b71-114">Les spécialisations possibles, ainsi que la façon de les définir et de les appeler, sont détaillées dans les différentes sections de cet article.</span><span class="sxs-lookup"><span data-stu-id="a6b71-114">The possible specializations, and how to define and call them, are detailed in the different sections of this article.</span></span>
<span data-ttu-id="a6b71-115">Pour l’instant, considérez l’opération suivante, qui définit uniquement une spécialisation de corps par défaut et qui accepte une seule qubit comme entrée, puis appelle l' <xref:Microsoft.Quantum.Intrinsic.X> opération intégrée sur cette entrée :</span><span class="sxs-lookup"><span data-stu-id="a6b71-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:Microsoft.Quantum.Intrinsic.X> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="a6b71-116">Le mot clé `operation` commence la définition de l’opération, suivie du nom ; ici, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-116">The keyword `operation` begins the operation definition, followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="a6b71-117">Ensuite, le type d’entrée est défini ( `Qubit` ), ainsi qu’un nom, `target` , pour faire référence à l’entrée dans la nouvelle opération.</span><span class="sxs-lookup"><span data-stu-id="a6b71-117">Next, the type of input is defined (`Qubit`), along with a name, `target`, for referring to the input within the new operation.</span></span>
<span data-ttu-id="a6b71-118">Enfin, `Unit` définit que la sortie de l’opération est vide.</span><span class="sxs-lookup"><span data-stu-id="a6b71-118">Lastly, `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="a6b71-119">`Unit` est utilisé de la même façon `void` que dans C# et d’autres langages impératifs, et est équivalent à `unit` en F # et à d’autres langages fonctionnels.</span><span class="sxs-lookup"><span data-stu-id="a6b71-119">`Unit` is used similarly to `void` in C# and other imperative languages and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="a6b71-120">Les opérations peuvent également retourner des types plus intéressants que `Unit` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="a6b71-121">Par exemple, l' <xref:Microsoft.Quantum.Intrinsic.m> opération retourne une sortie de type `Result` , qui représente l’exécution d’une mesure.</span><span class="sxs-lookup"><span data-stu-id="a6b71-121">For instance, the <xref:Microsoft.Quantum.Intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span>  <span data-ttu-id="a6b71-122">Vous pouvez la passer d’une opération à une autre opération ou l’utiliser avec le `let` mot clé pour définir une nouvelle variable.</span><span class="sxs-lookup"><span data-stu-id="a6b71-122">You can pass it from an operation to another operation or use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="a6b71-123">Cette approche permet de représenter un calcul classique qui interagit avec les opérations de Quantum à un niveau bas, par exemple dans le [code superdense](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding):</span><span class="sxs-lookup"><span data-stu-id="a6b71-123">This approach allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding):</span></span>

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
> <span data-ttu-id="a6b71-124">Chaque opération dans :::no-loc(Q#)::: prend exactement une entrée et retourne exactement une sortie.</span><span class="sxs-lookup"><span data-stu-id="a6b71-124">Each operation in :::no-loc(Q#)::: takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="a6b71-125">Plusieurs entrées et sorties sont représentées à l’aide de *tuples* , qui regroupent plusieurs valeurs en une seule valeur.</span><span class="sxs-lookup"><span data-stu-id="a6b71-125">Multiple inputs and outputs are represented using *tuples* , which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="a6b71-126">À cet égard, :::no-loc(Q#)::: est un langage de « tuple en sortie de tuples ».</span><span class="sxs-lookup"><span data-stu-id="a6b71-126">In this regard, :::no-loc(Q#)::: is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="a6b71-127">À la suite de ce concept, un jeu de parenthèses vides, `()` , doit ensuite être lu en tant que Tuple « vide », qui a le type `Unit` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-127">Following this concept, a set of empty parentheses, `()`, should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="a6b71-128">Opérations contrôlées et apjointes</span><span class="sxs-lookup"><span data-stu-id="a6b71-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="a6b71-129">Si une opération implémente une transformation unitaire, comme c’est le cas pour de nombreuses opérations dans :::no-loc(Q#)::: , il est possible de définir la façon dont l’opération agit quand *adjointed* ou *contrôlé* .</span><span class="sxs-lookup"><span data-stu-id="a6b71-129">If an operation implements a unitary transformation, as is the case for many operations in :::no-loc(Q#):::, then it is possible to define how the operation acts when *adjointed* or *controlled* .</span></span> <span data-ttu-id="a6b71-130">Une spécialisation *voisine* d’une opération spécifie la manière dont l’inverse de l’opération agit, tandis qu’une spécialisation *contrôlée* spécifie la manière dont une opération agit quand son application est conditionnée sur l’état d’un registre Quantum particulier.</span><span class="sxs-lookup"><span data-stu-id="a6b71-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="a6b71-131">La adjoints des opérations de Quantum est cruciale pour de nombreux aspects de quantum computing.</span><span class="sxs-lookup"><span data-stu-id="a6b71-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="a6b71-132">Pour obtenir un exemple d’une telle situation présentée avec une :::no-loc(Q#)::: technique de programmation utile, consultez [Flow Control : conjugaisons](xref:microsoft.quantum.guide.controlflow#conjugations).</span><span class="sxs-lookup"><span data-stu-id="a6b71-132">For an example of one such situation discussed alongside a useful :::no-loc(Q#)::: programming technique, see [Control Flow: Conjugations](xref:microsoft.quantum.guide.controlflow#conjugations).</span></span> <span data-ttu-id="a6b71-133">La version contrôlée d’une opération est une nouvelle opération qui applique efficacement l’opération de base uniquement si tous les qubits de contrôle sont dans un état spécifié.</span><span class="sxs-lookup"><span data-stu-id="a6b71-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="a6b71-134">Si le contrôle qubits est en superposition, l’opération de base est appliquée de manière cohérente à la partie appropriée de la superposition.</span><span class="sxs-lookup"><span data-stu-id="a6b71-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="a6b71-135">Ainsi, les opérations contrôlées sont souvent utilisées pour générer l’enchevêtrement.</span><span class="sxs-lookup"><span data-stu-id="a6b71-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="a6b71-136">Naturellement, une spécialisation *contrôlée* par l’application est également possible, en spécifiant l’application contrôlée du voisin de l’opération.</span><span class="sxs-lookup"><span data-stu-id="a6b71-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="a6b71-137">Si $U $ est la transformation unitaire implémentée par une opération `U` , `Adjoint U` représente la transformation unitaire $U ^ \dagger $, qui est la transformée conjuguée complexe.</span><span class="sxs-lookup"><span data-stu-id="a6b71-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="a6b71-138">L’application successive d’une opération, puis son voisin à un État laisse l’État inchangé, comme illustré par le fait que $UU ^ \dagger = U ^ \dagger U = \ID $, la matrice d’identité.</span><span class="sxs-lookup"><span data-stu-id="a6b71-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="a6b71-139">La représentation unitaire d’une opération contrôlée est légèrement plus en nuance, mais vous pouvez trouver plus de détails dans [quantum computing concepts : multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="a6b71-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="a6b71-140">La section suivante décrit comment appeler ces diverses spécialisations dans votre :::no-loc(Q#)::: code et comment définir des opérations pour les prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="a6b71-140">The following section describes how to call these various specializations in your :::no-loc(Q#)::: code, and how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="a6b71-141">Appel des spécialisations d’opérations</span><span class="sxs-lookup"><span data-stu-id="a6b71-141">Calling operation specializations</span></span>

<span data-ttu-id="a6b71-142">Un *functor* dans :::no-loc(Q#)::: est une fabrique qui définit une nouvelle opération à partir d’une autre opération.</span><span class="sxs-lookup"><span data-stu-id="a6b71-142">A *functor* in :::no-loc(Q#)::: is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="a6b71-143">Les deux functors standard dans :::no-loc(Q#)::: sont `Adjoint` et `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-143">The two standard functors in :::no-loc(Q#)::: are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="a6b71-144">Les functors ont accès à l’implémentation de l’opération de base lors de la définition de l’implémentation de la nouvelle opération.</span><span class="sxs-lookup"><span data-stu-id="a6b71-144">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="a6b71-145">Ainsi, les functors peuvent exécuter des fonctions plus complexes que les fonctions de niveau supérieur traditionnelles.</span><span class="sxs-lookup"><span data-stu-id="a6b71-145">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="a6b71-146">Les functors n’ont pas de représentation dans le :::no-loc(Q#)::: système de type.</span><span class="sxs-lookup"><span data-stu-id="a6b71-146">Functors do not have a representation in the :::no-loc(Q#)::: type system.</span></span> <span data-ttu-id="a6b71-147">Il n’est donc actuellement pas possible de les lier à une variable ou de les passer comme arguments.</span><span class="sxs-lookup"><span data-stu-id="a6b71-147">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="a6b71-148">Utilisez un functor en l’appliquant à une opération, qui retourne une nouvelle opération.</span><span class="sxs-lookup"><span data-stu-id="a6b71-148">Use a functor by applying it to an operation, which returns a new operation.</span></span>
<span data-ttu-id="a6b71-149">Par exemple, l’application `Adjoint` de functor à l' `Y` opération retourne la nouvelle opération `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-149">For example, applying the `Adjoint` functor to the `Y` operation returns the new operation `Adjoint Y`.</span></span> <span data-ttu-id="a6b71-150">Vous pouvez appeler la nouvelle opération comme n’importe quelle autre opération.</span><span class="sxs-lookup"><span data-stu-id="a6b71-150">You can invoke the new operation like any other operation.</span></span>
<span data-ttu-id="a6b71-151">Pour qu’une opération prenne en charge l’application des `Adjoint` `Controlled` functors ou, son type de retour doit obligatoirement être `Unit` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-151">For an operation to support the application of the `Adjoint` or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="a6b71-152">`Adjoint` functor</span><span class="sxs-lookup"><span data-stu-id="a6b71-152">`Adjoint` functor</span></span>

<span data-ttu-id="a6b71-153">Par conséquent, `Adjoint Y(q1)` applique le `Adjoint` functor à l' `Y` opération pour générer une nouvelle opération et applique cette nouvelle opération à `q1` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-153">Thus, `Adjoint Y(q1)` applies the `Adjoint` functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="a6b71-154">La nouvelle opération a la même signature et le même type que l’opération de base `Y` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-154">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="a6b71-155">En particulier, la nouvelle opération prend également en charge `Adjoint` et prend en charge `Controlled` si et uniquement si l’opération de base a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="a6b71-155">In particular, the new operation also supports `Adjoint`, and supports `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="a6b71-156">Le `Adjoint` functor est son propre inverse ; autrement dit, `Adjoint Adjoint Op` est toujours le même que `Op` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-156">The `Adjoint` functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="a6b71-157">`Controlled` functor</span><span class="sxs-lookup"><span data-stu-id="a6b71-157">`Controlled` functor</span></span>

<span data-ttu-id="a6b71-158">De même, `Controlled X(controls, target)` applique le `Controlled` functor à l' `X` opération pour générer une nouvelle opération et applique cette nouvelle opération à `controls` et `target` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-158">Similarly, `Controlled X(controls, target)` applies the `Controlled` functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="a6b71-159">Dans :::no-loc(Q#)::: , les versions contrôlées prennent toujours un tableau de qubits de contrôle et le contrôle est toujours basé sur tous les qubits de contrôle qui sont dans l’état de calcul ( `PauliZ` ) `One` , $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="a6b71-159">In :::no-loc(Q#):::, controlled versions always take an array of control qubits, and the controlling is always based on all of the control qubits being in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="a6b71-160">Le contrôle basé sur d’autres États est obtenu en appliquant l’opération unitaire appropriée au contrôle qubits avant l’opération contrôlée, puis en appliquant les inversions de l’opération unitaire après l’opération contrôlée.</span><span class="sxs-lookup"><span data-stu-id="a6b71-160">Controlling based on other states is achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="a6b71-161">Par exemple, l’application d’une `X` opération à un contrôle qubit avant et après une opération contrôlée fait que l’opération contrôle l' `Zero` État ($ \ket {0} $) pour ce qubit ; en appliquant une `H` opération avant et après les contrôles sur l' `PauliX` `One` État, c’est-à-dire-1 eigenvalue de Pauli X, $ \ket {-} \mathrel{ : =} (\ket {0} -\ket {1} )/\sqrt {2} $ plutôt que l' `PauliZ` `One` État.</span><span class="sxs-lookup"><span data-stu-id="a6b71-161">For example, applying an `X` operation to a control qubit before and after a controlled operation causes the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after controls on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="a6b71-162">En fonction d’une expression d’opération, vous pouvez former une nouvelle expression d’opération à l’aide de `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="a6b71-162">Given an operation expression, you can form a new operation expression by using the `Controlled` functor.</span></span>
<span data-ttu-id="a6b71-163">La signature de la nouvelle opération est basée sur la signature de l’opération d’origine.</span><span class="sxs-lookup"><span data-stu-id="a6b71-163">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="a6b71-164">Le type de résultat est le même, mais le type d’entrée est un double Tuple avec un tableau qubit qui contient les qubit de contrôle comme premier élément et les arguments de l’opération d’origine comme second élément.</span><span class="sxs-lookup"><span data-stu-id="a6b71-164">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="a6b71-165">La nouvelle opération prend en charge `Controlled` et prendra en charge `Adjoint` si et seulement si l’opération d’origine a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="a6b71-165">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="a6b71-166">Si l’opération d’origine n’a pris qu’un seul argument, l' [équivalence de tuple de Singleton](xref:microsoft.quantum.guide.types) entre dans la lecture ici.</span><span class="sxs-lookup"><span data-stu-id="a6b71-166">If the original operation took only a single argument, then [singleton tuple equivalence](xref:microsoft.quantum.guide.types) comes into play here.</span></span>
<span data-ttu-id="a6b71-167">Par exemple, `Controlled X` est la version contrôlée de l' `X` opération.</span><span class="sxs-lookup"><span data-stu-id="a6b71-167">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="a6b71-168">`X` a `(Qubit => Unit is Adj + Ctl)` un type, donc `Controlled X` a `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` le type ; en raison de l’équivalence de tuple de Singleton, il est identique à `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-168">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="a6b71-169">Si l’opération de base a pris plusieurs arguments, n’oubliez pas de placer les arguments correspondants de la version contrôlée de l’opération entre parenthèses pour les convertir en Tuple.</span><span class="sxs-lookup"><span data-stu-id="a6b71-169">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="a6b71-170">Par exemple, `Controlled Rz` est la version contrôlée de l' `Rz` opération.</span><span class="sxs-lookup"><span data-stu-id="a6b71-170">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="a6b71-171">`Rz` a le type `((Double, Qubit) => Unit is Adj + Ctl)` , `Controlled Rz` a le type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-171">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="a6b71-172">Par conséquent, `Controlled Rz(controls, (0.1, target))` serait un appel valide de `Controlled Rz` (Notez les parenthèses autour de `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="a6b71-172">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="a6b71-173">Autre exemple, `CNOT(control, target)` peut être implémenté en tant que `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-173">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="a6b71-174">Si une cible doit être contrôlée par deux qubits de contrôle (CCNOT), utilisez une `Controlled X([control1, control2], target)` instruction.</span><span class="sxs-lookup"><span data-stu-id="a6b71-174">If a target should be controlled by two control qubits (CCNOT), use a `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="a6b71-175">Les `Controlled` `Adjoint` functors et sont Permuted, donc il n’y a aucune différence entre l’application `Controlled Adjoint Op` de ou `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-175">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="a6b71-176">Définition des implémentations contrôlées et apjointes</span><span class="sxs-lookup"><span data-stu-id="a6b71-176">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="a6b71-177">Dans la première déclaration d’opération dans les exemples précédents, les opérations `BitFlip` et `DecodeSuperdense` ont été définies avec les signatures `(Qubit => Unit)` et `((Qubit, Qubit) => (Result, Result))` , respectivement.</span><span class="sxs-lookup"><span data-stu-id="a6b71-177">In the first operation declaration in the previous examples, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="a6b71-178">Comme `DecodeSuperdense` comprend des mesures, il ne s’agit pas d’une opération unitaire et, par conséquent, les spécialisations non contrôlées ne peuvent pas exister (Rappelez-vous que l’exigence correspondante retourne une telle opération `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="a6b71-178">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="a6b71-179">Toutefois, comme il `BitFlip` effectue simplement l' <xref:Microsoft.Quantum.Intrinsic.X> opération unitaire, vous pouvez l’avoir défini avec les deux spécialisations.</span><span class="sxs-lookup"><span data-stu-id="a6b71-179">However, as `BitFlip` simply performs the unitary <xref:Microsoft.Quantum.Intrinsic.X> operation, you could have defined it with both specializations.</span></span>

<span data-ttu-id="a6b71-180">Cette section explique en détail comment inclure l’existence de spécialisations dans vos :::no-loc(Q#)::: déclarations d’opération, donnant ainsi la possibilité d’appeler conjointement avec les `Adjoint` `Controlled` functors ou.</span><span class="sxs-lookup"><span data-stu-id="a6b71-180">This section details how to include the existence of specializations in your :::no-loc(Q#)::: operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` or `Controlled` functors.</span></span>
<span data-ttu-id="a6b71-181">Pour plus d’informations sur certaines situations dans lesquelles il est valide ou non valide pour déclarer certaines spécialisations, consultez [circonstances de la définition correcte de spécialisations](#circumstances-for-validly-defining-specializations) dans cet article.</span><span class="sxs-lookup"><span data-stu-id="a6b71-181">For more information about some of the situations in which it is either valid or not valid to declare certain specializations, see [Circumstances for validly defining specializations](#circumstances-for-validly-defining-specializations) in this article.</span></span>

<span data-ttu-id="a6b71-182">Les caractéristiques de l’opération définissent les genres d’functors que vous pouvez appliquer à l’opération déclarée et leur effet.</span><span class="sxs-lookup"><span data-stu-id="a6b71-182">Operation characteristics define what kinds of functors you can apply to the declared operation, and what effect they have.</span></span> <span data-ttu-id="a6b71-183">L’existence de ces spécialisations peut être déclarée dans le cadre de la signature de l’opération, en particulier par le biais d’une annotation avec les caractéristiques de l’opération : `is Adj` , `is Ctl` ou `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-183">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="a6b71-184">L’implémentation réelle de chaque spécialisation peut être définie *implicitement* ou *explicitement* .</span><span class="sxs-lookup"><span data-stu-id="a6b71-184">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="a6b71-185">Spécification implicite des implémentations</span><span class="sxs-lookup"><span data-stu-id="a6b71-185">Implicitly specifying implementations</span></span>

<span data-ttu-id="a6b71-186">Dans ce cas, le corps de la déclaration d’opération se compose uniquement de l’implémentation par défaut.</span><span class="sxs-lookup"><span data-stu-id="a6b71-186">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="a6b71-187">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a6b71-187">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="a6b71-188">Ici, l’implémentation correspondante pour chaque spécialisation déclarée implicitement est générée automatiquement par le compilateur, pour être exécutée si les `Adjoint` `Controlled` functors ou sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="a6b71-188">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="a6b71-189">Ainsi, un appel `Adjoint PrepareEntangledPair` à entraînerait le compilateur qui implémente le voisin de `CNOT` , puis le voisin de `H` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-189">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="a6b71-190">Ces opérations individuelles étant à la fois autonomes, l’opération résultante `Adjoint PrepareEntangledPair` consiste simplement à appliquer, `CNOT(here, there)` puis `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-190">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="a6b71-191">Par conséquent, vous pouvez l’utiliser pour écrire le `DecodeSuperdense` dans l’exemple précédent de façon plus compacte, en utilisant le voisint de `PrepareEntangledPair` pour transformer l’État enchevêtré dans une paire non enchevêtrée de qubits :</span><span class="sxs-lookup"><span data-stu-id="a6b71-191">Hence you can use this to write the `DecodeSuperdense` in the previous example more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="a6b71-192">L’annotation avec les caractéristiques de l’opération dans la déclaration est utile pour s’assurer que le compilateur génère automatiquement d’autres spécialisations en fonction de l’implémentation par défaut.</span><span class="sxs-lookup"><span data-stu-id="a6b71-192">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="a6b71-193">Il existe plusieurs limitations importantes à prendre en compte lors de la conception d’opérations à utiliser avec functors.</span><span class="sxs-lookup"><span data-stu-id="a6b71-193">There are several important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="a6b71-194">Le plus important, les spécialisations pour une opération qui utilise la valeur de sortie d’une autre opération *ne peuvent pas* être générées automatiquement par le compilateur, car il est ambigu de réorganiser les instructions dans une telle opération pour obtenir le même effet.</span><span class="sxs-lookup"><span data-stu-id="a6b71-194">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="a6b71-195">Par conséquent, il est souvent utile de spécifier explicitement les différentes implémentations.</span><span class="sxs-lookup"><span data-stu-id="a6b71-195">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="a6b71-196">Spécification explicite des implémentations</span><span class="sxs-lookup"><span data-stu-id="a6b71-196">Explicitly specifying implementations</span></span>

<span data-ttu-id="a6b71-197">Dans le cas où le compilateur ne peut pas générer l’implémentation, vous pouvez le spécifier explicitement.</span><span class="sxs-lookup"><span data-stu-id="a6b71-197">In the case where the compiler cannot generate the implementation, you can specify it explicitly.</span></span> <span data-ttu-id="a6b71-198">Ces déclarations de spécialisation explicites peuvent se composer d’une *directive de génération* appropriée ou d’une implémentation définie par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a6b71-198">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="a6b71-199">Voici la gamme complète de possibilités, avec quelques exemples de spécialisation explicite.</span><span class="sxs-lookup"><span data-stu-id="a6b71-199">Following are the full range of possibilities, with some examples of explicit specialization.</span></span> 


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="a6b71-200">Déclarations de spécialisation explicites</span><span class="sxs-lookup"><span data-stu-id="a6b71-200">Explicit specialization declarations</span></span>

<span data-ttu-id="a6b71-201">:::no-loc(Q#)::: les opérations peuvent contenir les déclarations de spécialisation explicite suivantes :</span><span class="sxs-lookup"><span data-stu-id="a6b71-201">:::no-loc(Q#)::: operations can contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="a6b71-202">La `body` spécialisation spécifie l’implémentation de l’opération sans les functors appliqués.</span><span class="sxs-lookup"><span data-stu-id="a6b71-202">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="a6b71-203">La `adjoint` spécialisation spécifie l’implémentation de l’opération avec le `Adjoint` functor appliqué.</span><span class="sxs-lookup"><span data-stu-id="a6b71-203">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="a6b71-204">La `controlled` spécialisation spécifie l’implémentation de l’opération avec le `Controlled` functor appliqué.</span><span class="sxs-lookup"><span data-stu-id="a6b71-204">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="a6b71-205">La `controlled adjoint` spécialisation spécifie l’implémentation de l’opération avec `Adjoint` les `Controlled` functors et appliqués.</span><span class="sxs-lookup"><span data-stu-id="a6b71-205">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="a6b71-206">Cette spécialisation peut également être nommée `adjoint controlled` , dans la mesure où les deux functors se comportent.</span><span class="sxs-lookup"><span data-stu-id="a6b71-206">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="a6b71-207">Une spécialisation d’opération se compose de la balise de spécialisation (par exemple, `body` ou `adjoint` ) suivie de l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a6b71-207">An operation specialization consists of the specialization tag (for example, `body` or `adjoint`) followed by one of:</span></span>

- <span data-ttu-id="a6b71-208">Une déclaration explicite, comme décrit dans le code suivant.</span><span class="sxs-lookup"><span data-stu-id="a6b71-208">An explicit declaration as described in the following.</span></span>
- <span data-ttu-id="a6b71-209">*Directive* qui indique au compilateur *Comment* générer la spécialisation, l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a6b71-209">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="a6b71-210">`intrinsic`, qui indique que l’ordinateur cible fournit la spécialisation.</span><span class="sxs-lookup"><span data-stu-id="a6b71-210">`intrinsic`, which indicates that the target machine provides the specialization.</span></span>
  - <span data-ttu-id="a6b71-211">`distribute`, utilisé avec les `controlled` `controlled adjoint` spécialisations et.</span><span class="sxs-lookup"><span data-stu-id="a6b71-211">`distribute`, used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="a6b71-212">Lorsqu' `controlled` il est utilisé avec, il indique que le compilateur doit calculer la spécialisation en appliquant `Controlled` à toutes les opérations dans le `body` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-212">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="a6b71-213">Lorsqu' `controlled adjoint` il est utilisé avec, il indique que le compilateur doit calculer la spécialisation en appliquant `Controlled` à toutes les opérations de la `adjoint` spécialisation.</span><span class="sxs-lookup"><span data-stu-id="a6b71-213">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="a6b71-214">`invert`, qui indique que le compilateur doit calculer la `adjoint` spécialisation en inversant `body` , par exemple, en inversant l’ordre des opérations et en appliquant le voisin à chacun d’entre eux.</span><span class="sxs-lookup"><span data-stu-id="a6b71-214">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, for example, reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="a6b71-215">Lorsqu' `adjoint controlled` il est utilisé avec, cela indique que le compilateur doit calculer la spécialisation en inversant la `controlled` spécialisation.</span><span class="sxs-lookup"><span data-stu-id="a6b71-215">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="a6b71-216">`self`, pour indiquer que la spécialisation voisine est identique à la `body` spécialisation.</span><span class="sxs-lookup"><span data-stu-id="a6b71-216">`self`, to indicate that the adjoint specialization is the same as the `body` specialization.</span></span>
    <span data-ttu-id="a6b71-217">L’utilisation `self` de est légale pour les `adjoint` `adjoint controlled` spécialisations et.</span><span class="sxs-lookup"><span data-stu-id="a6b71-217">Using `self` is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="a6b71-218">Pour `adjoint controlled` , `self` implique que la `adjoint controlled` spécialisation est la même que la `controlled` spécialisation.</span><span class="sxs-lookup"><span data-stu-id="a6b71-218">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="a6b71-219">`auto`, pour indiquer que le compilateur doit sélectionner une directive appropriée à appliquer.</span><span class="sxs-lookup"><span data-stu-id="a6b71-219">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="a6b71-220">Vous ne pouvez pas utiliser `auto` pour la `body` spécialisation.</span><span class="sxs-lookup"><span data-stu-id="a6b71-220">You cannot use`auto` for the `body` specialization.</span></span>

<span data-ttu-id="a6b71-221">Les directives et `auto` toutes requièrent un point-virgule fermant `;` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-221">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="a6b71-222">La `auto` directive se résout en la directive générée suivante si une déclaration explicite de `body` est fournie :</span><span class="sxs-lookup"><span data-stu-id="a6b71-222">The `auto` directive resolves to the following generated directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="a6b71-223">La `adjoint` spécialisation est générée en fonction de la directive `invert` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-223">The `adjoint` specialization generates according to the directive `invert`.</span></span>
- <span data-ttu-id="a6b71-224">La `controlled` spécialisation est générée en fonction de la directive `distribute` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-224">The `controlled` specialization generates according to the directive `distribute`.</span></span>
- <span data-ttu-id="a6b71-225">La `adjoint controlled` spécialisation génère en fonction de la directive `invert` si une déclaration explicite pour `controlled` est donnée, mais pas pour `adjoint` , et dans le `distribute` cas contraire.</span><span class="sxs-lookup"><span data-stu-id="a6b71-225">The `adjoint controlled` specialization  generates according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="a6b71-226">Si une opération est auto-jointe, spécifiez explicitement le voisint ou la spécialisation voisine contrôlée à l’aide de la directive `self` de génération pour permettre au compilateur d’utiliser ces informations à des fins d’optimisation.</span><span class="sxs-lookup"><span data-stu-id="a6b71-226">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="a6b71-227">Une déclaration de spécialisation contenant une implémentation définie par l’utilisateur se compose d’un tuple d’argument suivi d’un bloc d’instructions et du :::no-loc(Q#)::: code qui implémente la spécialisation.</span><span class="sxs-lookup"><span data-stu-id="a6b71-227">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the :::no-loc(Q#)::: code that implements the specialization.</span></span>
<span data-ttu-id="a6b71-228">Dans la liste d’arguments, `...` est utilisé pour représenter les arguments déclarés pour l’opération dans son ensemble.</span><span class="sxs-lookup"><span data-stu-id="a6b71-228">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="a6b71-229">Pour `body` et `adjoint` , la liste d’arguments doit toujours être `(...)` ; pour `controlled` et `adjoint controlled` , la liste d’arguments doit être un symbole qui représente le tableau de qubits de contrôle, suivi de `...` , placé entre parenthèses ; par exemple, `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-229">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="a6b71-230">Exemples</span><span class="sxs-lookup"><span data-stu-id="a6b71-230">Examples</span></span>

<span data-ttu-id="a6b71-231">Une déclaration d’opération peut être aussi simple que la suivante, qui définit l’opération Pauli X primitive :</span><span class="sxs-lookup"><span data-stu-id="a6b71-231">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="a6b71-232">Notez que la fonction joint de l’opération Pauli X est définie avec la directive `self` , car par définition `X` est sa propre inverse.</span><span class="sxs-lookup"><span data-stu-id="a6b71-232">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="a6b71-233">Dans l' `PrepareEntangledPair` exemple précédent, le code est équivalent au code suivant contenant des déclarations de spécialisation explicites :</span><span class="sxs-lookup"><span data-stu-id="a6b71-233">In the earlier `PrepareEntangledPair` example, the code is equivalent to the following code containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="a6b71-234">Le mot clé `auto` indique que le compilateur doit déterminer comment générer l’implémentation de la spécialisation.</span><span class="sxs-lookup"><span data-stu-id="a6b71-234">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="a6b71-235">Implémentation de spécialisation définie par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="a6b71-235">User-defined specialization implementation</span></span>

<span data-ttu-id="a6b71-236">Si le compilateur ne peut pas générer automatiquement l’implémentation pour une certaine spécialisation, ou si une implémentation plus efficace peut être donnée, vous pouvez définir manuellement l’implémentation.</span><span class="sxs-lookup"><span data-stu-id="a6b71-236">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then you can manually define the implementation.</span></span>

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
<span data-ttu-id="a6b71-237">Dans l’exemple précédent, `adjoint invert;` indique que la spécialisation voisine doit être générée en inversant l’implémentation du corps, et `controlled adjoint invert;` indique que la spécialisation de l’entité voisine contrôlée doit être générée en inversant l’implémentation donnée de la spécialisation contrôlée.</span><span class="sxs-lookup"><span data-stu-id="a6b71-237">In the previous example, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="a6b71-238">Si une ou plusieurs spécialisations en plus du corps par défaut doivent être déclarées explicitement, l’implémentation du corps par défaut doit également être incluse dans une déclaration de spécialisation appropriée :</span><span class="sxs-lookup"><span data-stu-id="a6b71-238">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="a6b71-239">Circonstances de la définition correcte de spécialisations</span><span class="sxs-lookup"><span data-stu-id="a6b71-239">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="a6b71-240">Déclarations d’opération avec le voisin/contrôlé</span><span class="sxs-lookup"><span data-stu-id="a6b71-240">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="a6b71-241">Il est légal de spécifier une opération sans les versions voisines ou contrôlées.</span><span class="sxs-lookup"><span data-stu-id="a6b71-241">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="a6b71-242">Par exemple, les opérations de mesure n’ont aucun effet, car elles ne sont pas réversibles ni contrôlable.</span><span class="sxs-lookup"><span data-stu-id="a6b71-242">For instance, measurement operations have neither because they are not invertible or controllable.</span></span>

<span data-ttu-id="a6b71-243">Une opération prend en charge les `Adjoint` `Controlled` functors et si sa déclaration contient une déclaration implicite ou explicite des spécialisations respectives.</span><span class="sxs-lookup"><span data-stu-id="a6b71-243">An operation supports the `Adjoint` and `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="a6b71-244">Une spécialisation dépendante ou contrôlée de manière explicite implique l’existence d’une spécialisation voisine/contrôlée.</span><span class="sxs-lookup"><span data-stu-id="a6b71-244">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="a6b71-245">Pour une opération dont le corps contient des boucles de répétition jusqu’à réussite, des instructions SET, des mesures, des instructions return ou des appels à d’autres opérations qui ne prennent pas en charge le `Adjoint` functor, la génération automatique d’une spécialisation Join à la suite de la `invert` `auto` directive ou n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="a6b71-245">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="a6b71-246">Pour une opération dont le corps contient des appels à d’autres opérations qui ne prennent pas en charge le `Controlled` functor, la génération automatique d’une spécialisation contrôlée à la suite de la `distribute` `auto` directive ou n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="a6b71-246">For an operation whose body contains calls to other operations that do not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="a6b71-247">Contigut contrôlé</span><span class="sxs-lookup"><span data-stu-id="a6b71-247">Controlled Adjoint</span></span>

<span data-ttu-id="a6b71-248">La version contrôlée par le contrôle joint d’une opération spécifie comment implémenter une version contrôlée par Quantum de l’opération.</span><span class="sxs-lookup"><span data-stu-id="a6b71-248">The controlled adjoint version of an operation specifies how to implement a quantum-controlled version of the adjoint of the operation.</span></span>
<span data-ttu-id="a6b71-249">Il est possible de spécifier une opération sans contrôle de version voisine. par exemple, les opérations de mesure n’ont pas de version définie par l’utilisateur, car elles ne sont ni contrôlables ni réversibles.</span><span class="sxs-lookup"><span data-stu-id="a6b71-249">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="a6b71-250">Une spécialisation voisine de l’opération doit exister si et seulement si une spécialisation et une spécialisation contrôlée existent.</span><span class="sxs-lookup"><span data-stu-id="a6b71-250">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="a6b71-251">Dans ce cas, l’existence de la spécialisation voisine contrôlée est déduite.</span><span class="sxs-lookup"><span data-stu-id="a6b71-251">In that case, the existence of the controlled adjoint specialization is inferred.</span></span> <span data-ttu-id="a6b71-252">Si aucune implémentation n’est définie explicitement, la compilation génère une spécialisation appropriée.</span><span class="sxs-lookup"><span data-stu-id="a6b71-252">If no implementation is explicitly defined, the compile generates an appropriate specialization.</span></span>

<span data-ttu-id="a6b71-253">Pour une opération dont le corps contient des appels à d’autres opérations qui n’ont pas de version définie par le contrôle, il n’est pas possible de générer automatiquement une spécialisation adjacente à la suite de la `invert` `distribute` directive, ou `auto` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute`, or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="a6b71-254">Compatibilité de type</span><span class="sxs-lookup"><span data-stu-id="a6b71-254">Type Compatibility</span></span>

<span data-ttu-id="a6b71-255">Utilisez une opération dont les functors supplémentaires sont pris en charge partout où vous utilisez une opération avec moins de functors, mais la même signature.</span><span class="sxs-lookup"><span data-stu-id="a6b71-255">Use an operation with additional functors supported anywhere you use an operation with fewer functors but the same signature.</span></span> <span data-ttu-id="a6b71-256">Par exemple, utilisez une opération de type `(Qubit => Unit is Adj)` partout où vous utilisez une opération de type `(Qubit => Unit)` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-256">For instance, use an operation of type `(Qubit => Unit is Adj)` anywhere you use an operation of type `(Qubit => Unit)`.</span></span>

<span data-ttu-id="a6b71-257">:::no-loc(Q#)::: est *covariant* en ce qui concerne les types de retour pouvant être appelés : un pouvant être appelé qui retourne un type `'A` est compatible avec un pouvant être appelé avec le même type d’entrée et un type de résultat compatible avec `'A` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-257">:::no-loc(Q#)::: is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that is compatible with `'A` .</span></span>

<span data-ttu-id="a6b71-258">:::no-loc(Q#)::: est *contravariant* en ce qui concerne les types d’entrée : un pouvant être appelé qui prend un type `'A` comme entrée est compatible avec un pouvant être appelé avec le même type de résultat et un type d’entrée compatible avec `'A` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-258">:::no-loc(Q#)::: is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="a6b71-259">Autrement dit, étant donné les définitions suivantes,</span><span class="sxs-lookup"><span data-stu-id="a6b71-259">That is, given the following definitions,</span></span>

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

<span data-ttu-id="a6b71-260">Vous pouvez</span><span class="sxs-lookup"><span data-stu-id="a6b71-260">you can</span></span>

- <span data-ttu-id="a6b71-261">Appelez la fonction `ConjugateInvertWith` avec un `inner` argument de `Invert` ou `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-261">Invoke the function `ConjugateInvertWith` with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="a6b71-262">Appelez la fonction `ConjugateUnitaryWith` avec un `inner` argument de `ApplyUnitary` , mais pas `Invert` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-262">Invoke the function `ConjugateUnitaryWith` with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="a6b71-263">Retourne une valeur de type `(Qubit[] => Unit is Adj + Ctl)` à partir de `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-263">Return a value of type `(Qubit[] => Unit is Adj + Ctl)` from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6b71-264">:::no-loc(Q#)::: 0,3 a introduit une différence significative dans le comportement des types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a6b71-264">:::no-loc(Q#)::: 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="a6b71-265">Les types définis par l’utilisateur sont traités comme une version encapsulée du type sous-jacent, plutôt qu’en tant que sous-type.</span><span class="sxs-lookup"><span data-stu-id="a6b71-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="a6b71-266">Cela signifie qu’une valeur d’un type défini par l’utilisateur n’est pas utilisable lorsque vous vous attendez à ce que la valeur du type sous-jacent soit.</span><span class="sxs-lookup"><span data-stu-id="a6b71-266">This means that a value of a user-defined type is not usable where you expect a value of the underlying type is.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="a6b71-267">Définition de nouvelles fonctions</span><span class="sxs-lookup"><span data-stu-id="a6b71-267">Defining New Functions</span></span>

<span data-ttu-id="a6b71-268">Les fonctions sont purement déterministes, les routines classiques dans :::no-loc(Q#)::: , qui sont distinctes des opérations en ce qu’elles ne sont pas autorisées à avoir des effets autres que le calcul d’une valeur de sortie.</span><span class="sxs-lookup"><span data-stu-id="a6b71-268">Functions are purely deterministic, classical routines in :::no-loc(Q#):::, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="a6b71-269">En particulier, les fonctions ne peuvent pas appeler d’opérations ; agir sur, allouer ou emprunter qubits ; exemples de nombres aléatoires Sinon, dépend de l’État au-delà de la valeur d’entrée d’une fonction.</span><span class="sxs-lookup"><span data-stu-id="a6b71-269">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="a6b71-270">Par conséquent, :::no-loc(Q#)::: les fonctions sont *pures* , car elles mappent toujours les mêmes valeurs d’entrée aux mêmes valeurs de sortie.</span><span class="sxs-lookup"><span data-stu-id="a6b71-270">As a consequence, :::no-loc(Q#)::: functions are *pure* , in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="a6b71-271">Ce comportement permet au :::no-loc(Q#)::: compilateur de réorganiser en toute sécurité Comment et quand appeler des fonctions lors de la génération de spécialisations d’opérations.</span><span class="sxs-lookup"><span data-stu-id="a6b71-271">This behavior allows the :::no-loc(Q#)::: compiler to safely reorder how and when to call functions when generating operation specializations.</span></span>

<span data-ttu-id="a6b71-272">Chaque :::no-loc(Q#)::: fichier source peut définir un nombre quelconque de fonctions.</span><span class="sxs-lookup"><span data-stu-id="a6b71-272">Each :::no-loc(Q#)::: source file can define any number of functions.</span></span>
<span data-ttu-id="a6b71-273">Les noms de fonctions doivent être uniques au sein d’un espace de noms et ne peuvent pas entrer en conflit avec des noms d’opération ou de type.</span><span class="sxs-lookup"><span data-stu-id="a6b71-273">Function names must be unique within a namespace and cannot conflict with operation or type names.</span></span>

<span data-ttu-id="a6b71-274">La définition d’une fonction fonctionne de la même façon que la définition d’une opération, à la différence qu’il n’est pas possible de définir des spécialisations voisines ou contrôlées pour une fonction.</span><span class="sxs-lookup"><span data-stu-id="a6b71-274">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="a6b71-275">Exemple :</span><span class="sxs-lookup"><span data-stu-id="a6b71-275">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="a6b71-276">or</span><span class="sxs-lookup"><span data-stu-id="a6b71-276">or</span></span> 

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

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="a6b71-277">Logique classique dans les fonctions = = bonne</span><span class="sxs-lookup"><span data-stu-id="a6b71-277">Classical logic in functions == good</span></span>

<span data-ttu-id="a6b71-278">À chaque fois que cela est possible, il est utile d’écrire la logique classique en termes de fonctions plutôt que d’opérations, afin que les opérations puissent l’utiliser plus facilement.</span><span class="sxs-lookup"><span data-stu-id="a6b71-278">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations so that operations can more readily use it.</span></span> <span data-ttu-id="a6b71-279">Par exemple, si vous avez écrit la `Square` déclaration antérieure en tant qu' *opération* , le compilateur n’aurait pas pu garantir que l’appel de la même entrée produirait toujours les mêmes sorties.</span><span class="sxs-lookup"><span data-stu-id="a6b71-279">For example, if you had written the earlier `Square` declaration as an *operation* , then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="a6b71-280">Pour souligner la différence entre les fonctions et les opérations, envisagez le problème d’échantillonnage classique d’un nombre aléatoire à partir d’une :::no-loc(Q#)::: opération :</span><span class="sxs-lookup"><span data-stu-id="a6b71-280">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a :::no-loc(Q#)::: operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="a6b71-281">Chaque fois que `U` la méthode est appelée, elle a une action différente sur `target` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-281">Each time that `U` is called, it has a different action on `target`.</span></span>
<span data-ttu-id="a6b71-282">En particulier, le compilateur ne peut pas garantir que si vous ajoutez une `adjoint auto` déclaration de spécialisation à `U` , `U(target); Adjoint U(target);` agit en tant qu’identité (autrement dit, en tant que non-op).</span><span class="sxs-lookup"><span data-stu-id="a6b71-282">In particular, the compiler cannot guarantee that if you add an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="a6b71-283">Cela viole la définition de l’emplacement de l’emplacement défini dans les [vecteurs et les matrices](xref:microsoft.quantum.concepts.vectors), ce qui permet au compilateur de générer automatiquement une spécialisation joint dans une opération où vous appelez l’opération <xref:Microsoft.Quantum.Math.RandomReal> pour rompre les garanties fournies par le compilateur ; <xref:Microsoft.Quantum.Math.RandomReal> est une opération pour laquelle il n’existe aucune version voisine ou contrôlée.</span><span class="sxs-lookup"><span data-stu-id="a6b71-283">This violates the definition of the adjoint defined in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing the compiler to auto-generate an adjoint specialization in an operation where you call the operation <xref:Microsoft.Quantum.Math.RandomReal> would break the guarantees provided by the compiler; <xref:Microsoft.Quantum.Math.RandomReal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="a6b71-284">D’un autre côté, en autorisant les appels de fonction tels que `Square` est sécurisé, et garantit au compilateur qu’il n’a besoin de conserver l’entrée que pour `Square` maintenir sa sortie stable.</span><span class="sxs-lookup"><span data-stu-id="a6b71-284">On the other hand, allowing function calls such as `Square` is safe, and assures the compiler that it only needs to preserve the input to `Square` to keep its output stable.</span></span>
<span data-ttu-id="a6b71-285">Ainsi, l’isolation de la logique classique la plus possible dans les fonctions facilite la réutilisation de cette logique dans d’autres fonctions et opérations.</span><span class="sxs-lookup"><span data-stu-id="a6b71-285">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="a6b71-286">Générique (paramètre de type) callables</span><span class="sxs-lookup"><span data-stu-id="a6b71-286">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="a6b71-287">De nombreuses fonctions et opérations que vous pouvez souhaiter définir ne s’appuient pas vraiment sur les types de leurs entrées, mais plutôt implicitement utiliser leurs types via une autre fonction ou opération.</span><span class="sxs-lookup"><span data-stu-id="a6b71-287">Many functions and operations that you might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="a6b71-288">Par exemple, considérez le concept de *carte* commun à de nombreux langages fonctionnels ; à partir d’une fonction $f (x) $ et d’une collection de valeurs $ \{ X_1, X_2, \dots, x_n \} $, Map retourne une nouvelle collection $ \{ f (X_1), f (X_2), \dots, f (x_n) \} $.</span><span class="sxs-lookup"><span data-stu-id="a6b71-288">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="a6b71-289">Pour implémenter cela dans :::no-loc(Q#)::: , tirez parti du fait que les fonctions sont de première classe.</span><span class="sxs-lookup"><span data-stu-id="a6b71-289">To implement this in :::no-loc(Q#):::, take advantage of the fact that functions are first class.</span></span>
<span data-ttu-id="a6b71-290">Voici un exemple rapide d' `Map` utilisation de `T` en tant qu’espace réservé lorsque vous déterminez les types dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="a6b71-290">Here is a quick example of `Map`, using `T` as a placeholder while you figure out what types you need.</span></span>

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="a6b71-291">Notez que cette fonction est très similaire, quel que soit le type réel que vous remplacez.</span><span class="sxs-lookup"><span data-stu-id="a6b71-291">Note that this function looks very much the same no matter what actual types you substitute in.</span></span>
<span data-ttu-id="a6b71-292">Une carte des entiers à Paulis, par exemple, est similaire à une carte à partir de nombres à virgule flottante en chaînes :</span><span class="sxs-lookup"><span data-stu-id="a6b71-292">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="a6b71-293">En principe, vous pouvez écrire une version de `Map` pour chaque paire de types que vous rencontrez, mais cela présente plusieurs difficultés.</span><span class="sxs-lookup"><span data-stu-id="a6b71-293">In principle, you could write a version of `Map` for every pair of types that you encounter, but this introduces several difficulties.</span></span>
<span data-ttu-id="a6b71-294">Par exemple, si vous trouvez un bogue dans `Map` , vous devez vous assurer que le correctif est appliqué uniformément dans toutes les versions de `Map` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-294">For instance, if you find a bug in `Map`, then you must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="a6b71-295">De plus, si vous construisez un nouveau tuple ou un type défini par l’utilisateur, vous devez maintenant également construire un nouveau `Map` pour l’utiliser avec le nouveau type.</span><span class="sxs-lookup"><span data-stu-id="a6b71-295">Moreover, if you construct a new tuple or UDT, then you must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="a6b71-296">Bien que cela soit tractable pour un petit nombre de ces fonctions, à mesure que vous recueillez de plus en plus de fonctions de la même forme que `Map` , le coût de l’introduction de nouveaux types devient trop raisonnable dans un ordre relativement court.</span><span class="sxs-lookup"><span data-stu-id="a6b71-296">While this is tractable for a small number of such functions, as you collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="a6b71-297">Toutefois, une grande partie de cette difficulté résulte du fait que vous n’avez pas donné au compilateur les informations dont il a besoin pour reconnaître la manière dont les différentes versions de `Map` sont liées.</span><span class="sxs-lookup"><span data-stu-id="a6b71-297">However, much of this difficulty results from the fact that you have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="a6b71-298">En fait, vous souhaitez que le compilateur traite `Map` comme un genre de fonction mathématique des :::no-loc(Q#)::: *types* aux :::no-loc(Q#)::: fonctions.</span><span class="sxs-lookup"><span data-stu-id="a6b71-298">Effectively, you want the compiler to treat `Map` as some kind of mathematical function from :::no-loc(Q#)::: *types* to :::no-loc(Q#)::: functions.</span></span>

<span data-ttu-id="a6b71-299">:::no-loc(Q#)::: formalise cette notion en autorisant les fonctions et les opérations à avoir des *paramètres de type* , ainsi que leurs paramètres de tuple ordinaires.</span><span class="sxs-lookup"><span data-stu-id="a6b71-299">:::no-loc(Q#)::: formalizes this notion by allowing functions and operations to have *type parameters* , as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="a6b71-300">Dans les exemples précédents, vous souhaitez considérer `Map` comme ayant des paramètres de type `Int, Pauli` dans le premier cas et `Double, String` dans le deuxième cas.</span><span class="sxs-lookup"><span data-stu-id="a6b71-300">In the previous examples, you wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="a6b71-301">Pour l’essentiel, utilisez ces paramètres de type comme s’il s’agissait de types ordinaires.</span><span class="sxs-lookup"><span data-stu-id="a6b71-301">For the most part, use these type parameters as though they were ordinary types.</span></span> <span data-ttu-id="a6b71-302">Utilisez des valeurs de paramètres de type pour créer des tableaux et des tuples, appeler des fonctions et des opérations et les assigner à des variables ordinaires ou mutables.</span><span class="sxs-lookup"><span data-stu-id="a6b71-302">Use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="a6b71-303">Le cas le plus extrême de dépendance indirecte est celui de qubits, où un :::no-loc(Q#)::: programme ne peut pas s’appuyer directement sur la structure du `Qubit` type, mais qui **doit** passer ces types à d’autres opérations et fonctions.</span><span class="sxs-lookup"><span data-stu-id="a6b71-303">The most extreme case of indirect dependence is that of qubits, where a :::no-loc(Q#)::: program cannot directly rely on the structure of the `Qubit` type but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="a6b71-304">En revenant à l’exemple précédent, vous voyez que `Map` doit avoir des paramètres de type, un pour représenter l’entrée à `fn` et un pour représenter la sortie de `fn` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-304">Returning to the earlier example, then, you see that `Map` needs to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="a6b71-305">Dans :::no-loc(Q#)::: , il est écrit en ajoutant des crochets pointus (qui `<>` ne sont pas brakets $ \braket {} $ !) après le nom d’une fonction ou d’une opération dans sa déclaration, et en répertoriant chaque paramètre de type.</span><span class="sxs-lookup"><span data-stu-id="a6b71-305">In :::no-loc(Q#):::, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="a6b71-306">Le nom de chaque paramètre de type doit commencer par un battement `'` , indiquant qu’il s’agit d’un paramètre de type et non d’un type ordinaire (également connu sous le nom de type *concret* ).</span><span class="sxs-lookup"><span data-stu-id="a6b71-306">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="a6b71-307">Par conséquent, `Map` est écrit :</span><span class="sxs-lookup"><span data-stu-id="a6b71-307">Thus, `Map`, is written:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="a6b71-308">Notez que la définition de `Map<'Input, 'Output>` semble très similaire aux versions previoius.</span><span class="sxs-lookup"><span data-stu-id="a6b71-308">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the previoius versions.</span></span>
<span data-ttu-id="a6b71-309">La seule différence est que vous avez explicitement informé le compilateur qui `Map` ne dépend pas directement de ce qui `'Input` `'Output` est, mais fonctionne pour deux types quelconques en les utilisant indirectement via `fn` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-309">The only difference is that you have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="a6b71-310">Une fois que vous l’avez définie `Map<'Input, 'Output>` de cette façon, vous pouvez l’appeler comme s’il s’agissait d’une fonction ordinaire :</span><span class="sxs-lookup"><span data-stu-id="a6b71-310">Once you have defined `Map<'Input, 'Output>` in this way, you can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="a6b71-311">L’écriture de fonctions et d’opérations génériques est un emplacement où « tuple en sortie de tuple » est un moyen très utile de réfléchir aux :::no-loc(Q#)::: fonctions et aux opérations.</span><span class="sxs-lookup"><span data-stu-id="a6b71-311">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about :::no-loc(Q#)::: functions and operations.</span></span>
> <span data-ttu-id="a6b71-312">Étant donné que chaque fonction accepte exactement une entrée et retourne une seule sortie, une entrée de type `'T -> 'U` correspond à *n’importe quelle* :::no-loc(Q#)::: fonction.</span><span class="sxs-lookup"><span data-stu-id="a6b71-312">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* :::no-loc(Q#)::: function whatsoever.</span></span>
> <span data-ttu-id="a6b71-313">De même, vous pouvez passer n’importe quelle opération à une entrée de type `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-313">Similarly, you can pass any operation to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="a6b71-314">En guise de deuxième exemple, considérez le défi que pose l’écriture d’une fonction qui retourne la composition de deux autres fonctions :</span><span class="sxs-lookup"><span data-stu-id="a6b71-314">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="a6b71-315">Ici, vous devez spécifier exactement ce que, `A` `B` et `C` sont, par conséquent, en limitant gravement l’utilitaire de notre nouvelle `Compose` fonction.</span><span class="sxs-lookup"><span data-stu-id="a6b71-315">Here, you must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="a6b71-316">Après tout, `Compose` dépend uniquement de `A` , et `B` `C` *via* `innerFn` et `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="a6b71-316">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="a6b71-317">En guise d’alternative, vous pouvez ajouter des paramètres de type à `Compose` qui indiquent qu’il fonctionne pour *n’importe quel* `A` , `B` , et `C` , tant que ces paramètres correspondent à ceux attendus par `innerFn` et `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="a6b71-317">As an alternative, then, you can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="a6b71-318">Les :::no-loc(Q#)::: bibliothèques standard fournissent une plage de ces opérations et fonctions paramétrées de type pour faciliter l’utilisation du workflow de contrôle d’ordre supérieur.</span><span class="sxs-lookup"><span data-stu-id="a6b71-318">The :::no-loc(Q#)::: standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="a6b71-319">Celles-ci sont décrites plus en détail dans le Guide de la [ :::no-loc(Q#)::: bibliothèque standard](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="a6b71-319">These are discussed further in the [:::no-loc(Q#)::: standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="a6b71-320">Callables comme valeurs First-Class</span><span class="sxs-lookup"><span data-stu-id="a6b71-320">Callables as First-Class Values</span></span>

<span data-ttu-id="a6b71-321">Une technique critique pour le raisonnement sur le workflow de contrôle et la logique classique utilisant des fonctions plutôt que des opérations consiste à utiliser les opérations et les fonctions dans qui :::no-loc(Q#)::: sont de *première classe* .</span><span class="sxs-lookup"><span data-stu-id="a6b71-321">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in :::no-loc(Q#)::: are *first-class* .</span></span>
<span data-ttu-id="a6b71-322">En d’autres termes, il s’agit de chaque valeur de la langue, à son propre droit.</span><span class="sxs-lookup"><span data-stu-id="a6b71-322">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="a6b71-323">Par exemple, le code suivant est parfaitement valide :::no-loc(Q#)::: , si un peu indirect :</span><span class="sxs-lookup"><span data-stu-id="a6b71-323">For instance, the following is perfectly valid :::no-loc(Q#)::: code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="a6b71-324">La valeur de la variable `ourH` dans l’extrait de code précédent est l’opération <xref:Microsoft.Quantum.Intrinsic.H> , de telle sorte que vous pouvez appeler cette valeur comme toute autre opération.</span><span class="sxs-lookup"><span data-stu-id="a6b71-324">The value of the variable `ourH` in the previous snippet is then the operation <xref:Microsoft.Quantum.Intrinsic.H>, such that you can call that value like any other operation.</span></span>
<span data-ttu-id="a6b71-325">Avec cette fonctionnalité, vous pouvez écrire des opérations qui prennent des opérations dans le cadre de leur entrée, formant ainsi des concepts de contrôle d’ordre supérieur.</span><span class="sxs-lookup"><span data-stu-id="a6b71-325">With this ability, you can write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="a6b71-326">Par exemple, imaginez que vous souhaitiez « carrér » une opération en l’appliquant deux fois au même qubit cible.</span><span class="sxs-lookup"><span data-stu-id="a6b71-326">For instance, you could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="a6b71-327">Retour d’opérations à partir d’une fonction</span><span class="sxs-lookup"><span data-stu-id="a6b71-327">Returning operations from a function</span></span>

<span data-ttu-id="a6b71-328">Il est important de souligner que vous pouvez également retourner des opérations dans le cadre des sorties, de telle sorte que vous puissiez isoler certains genres de logique conditionnelle classique comme une fonction classique, qui retourne une description d’un programme Quantum sous la forme d’une opération.</span><span class="sxs-lookup"><span data-stu-id="a6b71-328">It's important to emphasize that you can also return operations as a part of outputs, such that you can isolate some kinds of classical conditional logic as a classical function, which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="a6b71-329">En guise d’exemple simple, prenons l’exemple de téléportage, dans lequel le tiers recevant un message classique à deux bits doit utiliser le message pour décoder leur qubit dans l’État téléporté approprié.</span><span class="sxs-lookup"><span data-stu-id="a6b71-329">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="a6b71-330">Vous pouvez écrire ce code en tant que fonction qui prend ces deux bits classiques et retourne l’opération de décodage appropriée.</span><span class="sxs-lookup"><span data-stu-id="a6b71-330">You could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="a6b71-331">Cette nouvelle fonction est effectivement une fonction, car si vous l’appelez avec les mêmes valeurs que `hereBit` et `thereBit` , vous récupérez toujours la même opération.</span><span class="sxs-lookup"><span data-stu-id="a6b71-331">This new function is indeed a function, in that if you call it with the same values of `hereBit` and `thereBit`, you always get back the same operation.</span></span>
<span data-ttu-id="a6b71-332">Ainsi, le décodeur peut s’exécuter en toute sécurité dans des opérations sans avoir à expliquer comment la logique de décodage interagit avec les définitions des différentes spécialisations d’opérations.</span><span class="sxs-lookup"><span data-stu-id="a6b71-332">Thus, the decoder can safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="a6b71-333">Autrement dit, la logique classique à l’intérieur d’une fonction est isolée, garantissant au compilateur que l’appel de fonction peut être réorganisé avec impunity tant que l’entrée est conservée.</span><span class="sxs-lookup"><span data-stu-id="a6b71-333">That is, the classical logic inside a function is isolated, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="a6b71-334">Application partielle</span><span class="sxs-lookup"><span data-stu-id="a6b71-334">Partial Application</span></span>

<span data-ttu-id="a6b71-335">Vous pouvez en faire beaucoup plus avec les fonctions qui retournent des opérations à l’aide d’une *application partielle* , dans laquelle vous fournissez une ou plusieurs parties de l’entrée à une fonction ou une opération sans réellement l’appeler.</span><span class="sxs-lookup"><span data-stu-id="a6b71-335">You can do significantly more with functions that return operations by using *partial application* , in which you provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="a6b71-336">Dans l' `ApplyTwice` exemple précédent, vous pouvez indiquer que vous ne souhaitez pas spécifier, immédiatement, à quelle qubit l’opération d’entrée doit s’appliquer :</span><span class="sxs-lookup"><span data-stu-id="a6b71-336">In the earlier `ApplyTwice` example, you can indicate that you don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="a6b71-337">Dans ce cas, la variable locale `twiceOp` contient l’opération partiellement appliquée `ApplyTwice(op, _)` , où `_` indique les parties de l’entrée qui n’ont pas encore été spécifiées.</span><span class="sxs-lookup"><span data-stu-id="a6b71-337">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where `_` indicates parts of the input that have not yet been specified.</span></span>
<span data-ttu-id="a6b71-338">Lorsque vous appelez `twiceOp` dans la ligne suivante, vous transmettez comme entrée à l’opération partiellement appliquée toutes les autres parties de l’entrée à l’opération d’origine.</span><span class="sxs-lookup"><span data-stu-id="a6b71-338">When you call `twiceOp` in the next line, you pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="a6b71-339">Par conséquent, l’extrait de code précédent est effectivement identique à l’appel `ApplyTwice(op, target)` direct, économisez pour que vous ayez introduit une nouvelle variable locale afin de pouvoir retarder l’appel tout en fournissant certaines parties de l’entrée.</span><span class="sxs-lookup"><span data-stu-id="a6b71-339">Thus, the previous snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that you have introduced a new local variable so you can delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="a6b71-340">Étant donné qu’une opération partiellement appliquée n’est pas réellement appelée tant que l’intégralité de son entrée n’a pas été fournie, vous pouvez appliquer des opérations en toute sécurité, même à partir de fonctions.</span><span class="sxs-lookup"><span data-stu-id="a6b71-340">Since an operation that has been partially applied is not actually called until its entire input has been provided, you can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="a6b71-341">En principe, la logique classique dans `SquareOperation` pourrait avoir été bien plus complexe, mais elle est toujours isolée du reste d’une opération par les garanties que le compilateur peut offrir sur les fonctions.</span><span class="sxs-lookup"><span data-stu-id="a6b71-341">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span> <span data-ttu-id="a6b71-342">La :::no-loc(Q#)::: bibliothèque standard utilise cette approche tout à fait pour exprimer le workflow de contrôle classique de manière à ce que les programmes quantiques puissent facilement les utiliser.</span><span class="sxs-lookup"><span data-stu-id="a6b71-342">The :::no-loc(Q#)::: standard library uses this approach throughout for expressing classical control flow in a way that quantum programs can readily use.</span></span>


## <a name="recursion"></a><span data-ttu-id="a6b71-343">Récursivité</span><span class="sxs-lookup"><span data-stu-id="a6b71-343">Recursion</span></span>

<span data-ttu-id="a6b71-344">:::no-loc(Q#)::: les callables sont autorisés à être récursifs directement ou indirectement.</span><span class="sxs-lookup"><span data-stu-id="a6b71-344">:::no-loc(Q#)::: callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="a6b71-345">Autrement dit, une opération ou une fonction peut s’appeler elle-même, ou elle peut appeler un autre pouvant être appelé, qui appelle directement ou indirectement l’opération pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="a6b71-345">That is, an operation or function can call itself, or it can call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="a6b71-346">Il existe toutefois deux commentaires importants sur l’utilisation de la récursivité :</span><span class="sxs-lookup"><span data-stu-id="a6b71-346">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="a6b71-347">L’utilisation de la récursivité dans les opérations est susceptible d’interférer avec certaines optimisations.</span><span class="sxs-lookup"><span data-stu-id="a6b71-347">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="a6b71-348">Cette interférence peut avoir un impact important sur la durée d’exécution de l’algorithme.</span><span class="sxs-lookup"><span data-stu-id="a6b71-348">This interference can have a substantial impact on the run time of the algorithm.</span></span>
- <span data-ttu-id="a6b71-349">En cas d’exécution sur un appareil Quantum réel, l’espace de pile peut être limité et, par conséquent, une récurrence profonde peut entraîner une erreur d’exécution.</span><span class="sxs-lookup"><span data-stu-id="a6b71-349">When running on an actual quantum device, stack space might be limited, and so deep recursion can lead to a runtime error.</span></span>
  <span data-ttu-id="a6b71-350">En particulier, le :::no-loc(Q#)::: compilateur et le runtime n’identifient pas et n’optimisent pas la récurrence de la fin.</span><span class="sxs-lookup"><span data-stu-id="a6b71-350">In particular, the :::no-loc(Q#)::: compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a6b71-351">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="a6b71-351">Next steps</span></span>

<span data-ttu-id="a6b71-352">En savoir plus sur les [variables](xref:microsoft.quantum.guide.variables) dans :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="a6b71-352">Learn about [Variables](xref:microsoft.quantum.guide.variables) in :::no-loc(Q#):::.</span></span>