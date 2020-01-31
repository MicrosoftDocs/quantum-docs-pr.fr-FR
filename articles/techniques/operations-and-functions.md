---
title: 'Opérations et fonctions-Q # techniques | Microsoft Docs'
description: 'Opérations et fonctions-Q # techniques'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fca20bb44cc42008f7d25d2fc71a39b962525c2
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820774"
---
# <a name="q-operations-and-functions"></a><span data-ttu-id="15b2e-103">Opérations et fonctions Q #</span><span class="sxs-lookup"><span data-stu-id="15b2e-103">Q# Operations and Functions</span></span>

<span data-ttu-id="15b2e-104">Q # les programmes se composent d’une ou plusieurs *opérations* qui décrivent les effets secondaires que les opérations de Quantum peuvent avoir sur les données Quantum et une ou plusieurs *fonctions* qui permettent de modifier les données classiques.</span><span class="sxs-lookup"><span data-stu-id="15b2e-104">Q# programs consist of one or more *operations* that describe side effects quantum operations can have on quantum data, and one or more *functions* that allow modifications to classical data.</span></span> <span data-ttu-id="15b2e-105">Contrairement aux opérations, les fonctions sont utilisées pour décrire le comportement purement classique et n’ont aucun effet en plus des valeurs de sortie classiques.</span><span class="sxs-lookup"><span data-stu-id="15b2e-105">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span>

<span data-ttu-id="15b2e-106">Chaque opération définie dans Q # peut alors appeler un nombre quelconque d’autres opérations, y compris les opérations intrinsèques intégrées définies par le langage.</span><span class="sxs-lookup"><span data-stu-id="15b2e-106">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="15b2e-107">La façon dont ces opérations intrinsèques sont définies dépend de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="15b2e-107">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span> <span data-ttu-id="15b2e-108">Une fois compilée, chaque opération est représentée sous la forme d’un type de classe .NET qui peut être fourni aux ordinateurs cibles.</span><span class="sxs-lookup"><span data-stu-id="15b2e-108">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="15b2e-109">Définition de nouvelles opérations</span><span class="sxs-lookup"><span data-stu-id="15b2e-109">Defining New Operations</span></span>

<span data-ttu-id="15b2e-110">Comme décrit ci-dessus, le bloc de construction le plus basique d’un programme Quantum écrit en Q # est une *opération*qui peut être appelée à partir d’applications .net classiques, par exemple, à l’aide d’un simulateur ou d’autres opérations dans Q #.</span><span class="sxs-lookup"><span data-stu-id="15b2e-110">As described above, the most basic building block of a quantum program written in Q# is an *operation*, which can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="15b2e-111">Chaque opération prend une entrée, produit une sortie et spécifie l’implémentation pour une ou plusieurs spécialisations d’opérations.</span><span class="sxs-lookup"><span data-stu-id="15b2e-111">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="15b2e-112">Par exemple, l’opération suivante définit uniquement une spécialisation de corps par défaut et prend un qubit unique comme entrée, puis appelle l’opération de `X` intégrée sur cette entrée :</span><span class="sxs-lookup"><span data-stu-id="15b2e-112">For instance, the following operation defines only a default body specialization and takes a single qubit as its input, then calls the built-in `X` operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="15b2e-113">Le mot clé `operation` commence la définition de l’opération, suivi du nom ; ici, `BitFlip`.</span><span class="sxs-lookup"><span data-stu-id="15b2e-113">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="15b2e-114">Ensuite, le type de l’entrée est défini en tant que `Qubit`, ainsi qu’un nom `target` pour faire référence à l’entrée dans la nouvelle opération.</span><span class="sxs-lookup"><span data-stu-id="15b2e-114">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="15b2e-115">De même, le `Unit` définit que la sortie de l’opération est vide.</span><span class="sxs-lookup"><span data-stu-id="15b2e-115">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="15b2e-116">Cela est utilisé de la même façon que C# `void` dans et d’autres langages impératifs, et F# équivaut à `unit` dans et dans d’autres langages fonctionnels.</span><span class="sxs-lookup"><span data-stu-id="15b2e-116">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

> [!NOTE]
> <span data-ttu-id="15b2e-117">Nous allons l’explorer plus en détail ci-dessous, mais chaque opération dans Q # prend exactement une entrée et retourne exactement une sortie.</span><span class="sxs-lookup"><span data-stu-id="15b2e-117">We will explore this in more detail below, but each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="15b2e-118">Plusieurs entrées et sorties sont ensuite représentées à l’aide de *tuples*, qui regroupent plusieurs valeurs en une seule valeur.</span><span class="sxs-lookup"><span data-stu-id="15b2e-118">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="15b2e-119">De manière informelle, nous disons que Q # est un langage de type « Tuple-in-out ».</span><span class="sxs-lookup"><span data-stu-id="15b2e-119">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="15b2e-120">À la suite de ce concept, `()` doit ensuite être lu en tant que Tuple « vide », qui a le type `Unit`.</span><span class="sxs-lookup"><span data-stu-id="15b2e-120">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

<span data-ttu-id="15b2e-121">Dans la nouvelle opération, l’implémentation peut être spécifiée directement dans la déclaration si seule l’implémentation de la spécialisation du corps par défaut doit être spécifiée explicitement.</span><span class="sxs-lookup"><span data-stu-id="15b2e-121">Within the new operation, the implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to be specified explicitly.</span></span> <span data-ttu-id="15b2e-122">En outre, il est possible de définir les implémentations de, par exemple, une ou plusieurs opérations de `functor`, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="15b2e-122">Additionally, it is possible to define the implementations of, for example, one or more `functor` operations, as elaborated below.</span></span> <span data-ttu-id="15b2e-123">Dans l’exemple ci-dessus, la seule instruction consiste à appeler l’opération Q # intégrée <xref:microsoft.quantum.intrinsic.x>.</span><span class="sxs-lookup"><span data-stu-id="15b2e-123">In the example above, the only statement is to call the built-in Q# operation <xref:microsoft.quantum.intrinsic.x>.</span></span>

<span data-ttu-id="15b2e-124">Les opérations peuvent également retourner des types plus intéressants que `Unit`.</span><span class="sxs-lookup"><span data-stu-id="15b2e-124">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="15b2e-125">Par exemple, l’opération <xref:microsoft.quantum.intrinsic.m> retourne une sortie de type `Result`, qui représente l’exécution d’une mesure.</span><span class="sxs-lookup"><span data-stu-id="15b2e-125">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="15b2e-126">Nous pouvons soit transmettre la sortie d’une opération à une autre opération, soit l’utiliser avec le mot clé `let` pour définir une nouvelle variable.</span><span class="sxs-lookup"><span data-stu-id="15b2e-126">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>
<!-- Link to UID for superdense conceptual and example documentation. -->
<span data-ttu-id="15b2e-127">Cela permet de représenter un calcul classique qui interagit avec les opérations de Quantum à un niveau bas, par exemple dans le codage à haute densité :</span><span class="sxs-lookup"><span data-stu-id="15b2e-127">This allows for representing classical computation that interacts with quantum operations at a low level, such as in superdense coding:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a><span data-ttu-id="15b2e-128">Functors, contigut et contrôlé</span><span class="sxs-lookup"><span data-stu-id="15b2e-128">Functors, adjoint and controlled</span></span>
<span data-ttu-id="15b2e-129">Si une opération implémente une transformation unitaire, il est possible de définir la façon dont l’opération agit quand *adjointed* ou *contrôlé*.</span><span class="sxs-lookup"><span data-stu-id="15b2e-129">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="15b2e-130">Une spécialisation voisine d’une opération spécifie la manière dont elle agit lorsqu’elle est exécutée en sens inverse, tandis qu’une spécialisation contrôlée spécifie la manière dont une opération agit lorsqu’elle est appliquée en fonction de l’état d’un registre Quantum.</span><span class="sxs-lookup"><span data-stu-id="15b2e-130">An adjoint specialization of an operation specifies how it acts when run in reverse, while a controlled specialization specifies how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="15b2e-131">L’existence de ces spécialisations peut être déclarée dans le cadre de la signature de l’opération : `is Adj + Ctl` dans l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="15b2e-131">The existence of these specializations can be declared as part of the operation signature: `is Adj + Ctl` in the following example.</span></span> <span data-ttu-id="15b2e-132">L’implémentation correspondante pour chaque spécialisation déclarée implicitement est ensuite générée par le compilateur.</span><span class="sxs-lookup"><span data-stu-id="15b2e-132">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> <span data-ttu-id="15b2e-133">De nombreuses opérations dans Q # représentent des portes unitaires.</span><span class="sxs-lookup"><span data-stu-id="15b2e-133">Many operations in Q# represent unitary gates.</span></span>
> <span data-ttu-id="15b2e-134">Si $U $ est la porte unitaire représentée par une `U`d’opération, `Adjoint U` représente la porte d’unité $U ^ \dagger $.</span><span class="sxs-lookup"><span data-stu-id="15b2e-134">If $U$ is the unitary gate represented by an operation `U`, then `Adjoint U` represents the unitary gate $U^\dagger$.</span></span>

<span data-ttu-id="15b2e-135">Dans le cas où l’implémentation ne peut pas être générée par le compilateur, elle peut être spécifiée explicitement.</span><span class="sxs-lookup"><span data-stu-id="15b2e-135">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="15b2e-136">Ces déclarations de spécialisation explicites peuvent se composer d’une directive de génération appropriée ou d’une implémentation définie par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="15b2e-136">Such explicit specialization declarations can consist of a suitable generation directive or a user defined implementation.</span></span> <span data-ttu-id="15b2e-137">Le code de `PrepareEntangledPair` ci-dessus, par exemple, est équivalent au code ci-dessous, contenant des déclarations de spécialisation explicites :</span><span class="sxs-lookup"><span data-stu-id="15b2e-137">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="15b2e-138">Le mot clé `auto` indique que le compilateur doit déterminer comment générer l’implémentation de la spécialisation.</span><span class="sxs-lookup"><span data-stu-id="15b2e-138">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="15b2e-139">Si le compilateur ne peut pas générer automatiquement l’implémentation pour une certaine spécialisation, ou si une implémentation plus efficace peut être donnée, l’implémentation peut également être définie manuellement.</span><span class="sxs-lookup"><span data-stu-id="15b2e-139">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="15b2e-140">Dans l’exemple ci-dessus, `adjoint invert;` indique que la spécialisation voisine doit être générée en inversant l’implémentation du corps, et `controlled adjoint invert;` indique que la spécialisation de la spécialisation voisine doit être générée en inversant l’implémentation donnée de la spécialisation contrôlée.</span><span class="sxs-lookup"><span data-stu-id="15b2e-140">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="15b2e-141">Nous verrons plus d’exemples dans le [processus de contrôle d’ordre supérieur](xref:microsoft.quantum.concepts.control-flow).</span><span class="sxs-lookup"><span data-stu-id="15b2e-141">We will see more examples of this in [Higher-Order Control Flow](xref:microsoft.quantum.concepts.control-flow).</span></span>

<span data-ttu-id="15b2e-142">Pour appeler une spécialisation d’une opération, utilisez les mots clés `Adjoint` ou `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="15b2e-142">To call a specialization of an operation, use the `Adjoint` or `Controlled` keywords.</span></span>
<span data-ttu-id="15b2e-143">Par exemple, l’exemple de codage superdense ci-dessus peut être écrit plus compact en utilisant le voisin de `PrepareEntangledPair` pour transformer l’État enchevêtré dans une paire non enchevêtrée de qubits :</span><span class="sxs-lookup"><span data-stu-id="15b2e-143">For example, the superdense coding example above can be written more compactly by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="15b2e-144">Il existe un certain nombre de limitations importantes à prendre en compte lors de la conception d’opérations à utiliser avec functors.</span><span class="sxs-lookup"><span data-stu-id="15b2e-144">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="15b2e-145">Le plus important, les spécialisations pour une opération qui utilise la valeur de sortie d’une autre opération ne peuvent pas être générées automatiquement par le compilateur, car il est ambigu de réorganiser les instructions dans une telle opération pour obtenir le même effet.</span><span class="sxs-lookup"><span data-stu-id="15b2e-145">Most critically, specializations for an operation that uses the output value of any other operation cannot be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="15b2e-146">Définition de nouvelles fonctions</span><span class="sxs-lookup"><span data-stu-id="15b2e-146">Defining New Functions</span></span>

<span data-ttu-id="15b2e-147">Q # permet également de définir des *fonctions*, qui sont distinctes des opérations en ce qu’elles ne sont pas autorisées à avoir des effets autres que le calcul d’une valeur de sortie.</span><span class="sxs-lookup"><span data-stu-id="15b2e-147">Q# also allows for defining *functions*, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="15b2e-148">En particulier, les fonctions ne peuvent pas appeler d’opérations, agir sur qubits, échantillonner des nombres aléatoires ou dépendre de l’État au-delà de la valeur d’entrée d’une fonction.</span><span class="sxs-lookup"><span data-stu-id="15b2e-148">In particular, functions cannot call operations, act on qubits, sample random numbers, or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="15b2e-149">Par conséquent, les fonctions Q # sont *pures*, car elles mappent toujours les mêmes valeurs d’entrée aux mêmes valeurs de sortie.</span><span class="sxs-lookup"><span data-stu-id="15b2e-149">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="15b2e-150">Cela permet au compilateur Q # de réorganiser en toute sécurité le mode et le moment où les fonctions sont appelées lors de la génération de spécialisations d’opérations.</span><span class="sxs-lookup"><span data-stu-id="15b2e-150">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="15b2e-151">La définition d’une fonction fonctionne de la même façon que la définition d’une opération, à la différence qu’il n’est pas possible de définir des spécialisations voisines ou contrôlées pour une fonction.</span><span class="sxs-lookup"><span data-stu-id="15b2e-151">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="15b2e-152">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="15b2e-152">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
<span data-ttu-id="15b2e-153">Chaque fois que cela est possible, il est utile d’écrire la logique classique en termes de fonctions plutôt que d’opérations, afin qu’elle puisse être utilisée plus facilement à partir des opérations.</span><span class="sxs-lookup"><span data-stu-id="15b2e-153">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="15b2e-154">Si nous avions écrit `Square` en tant qu’opération, par exemple, le compilateur n’aurait pas pu garantir que l’appel de cette même entrée produirait toujours les mêmes sorties.</span><span class="sxs-lookup"><span data-stu-id="15b2e-154">If we had written `Square` as an operation, for example, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="15b2e-155">Pour souligner la différence entre les fonctions et les opérations, envisagez le problème d’échantillonnage classique d’un nombre aléatoire à partir d’une opération Q # :</span><span class="sxs-lookup"><span data-stu-id="15b2e-155">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="15b2e-156">Chaque fois que `U` est appelé, il aura une action différente sur `target`.</span><span class="sxs-lookup"><span data-stu-id="15b2e-156">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="15b2e-157">En particulier, le compilateur ne peut pas garantir que si nous avons ajouté une déclaration de spécialisation `adjoint auto` à `U`, `U(target); Adjoint U(target);` agit comme une identité (autrement dit, une absence d’opération).</span><span class="sxs-lookup"><span data-stu-id="15b2e-157">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="15b2e-158">Cela viole la définition de l’voisine que nous avons vu dans les [vecteurs et les matrices](xref:microsoft.quantum.concepts.vectors), ce qui permet de générer automatiquement une spécialisation joint dans une opération où nous avons appelé l’opération <xref:microsoft.quantum.math.randomreal> annulerait les garanties fournies par le compilateur. <xref:microsoft.quantum.math.randomreal> est une opération pour laquelle il n’existe aucune version voisine ou contrôlée.</span><span class="sxs-lookup"><span data-stu-id="15b2e-158">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="15b2e-159">D’un autre côté, il est possible d’autoriser les appels de fonction tels que `Square`, dans la mesure où le compilateur peut être certain qu’il n’a besoin de conserver l’entrée que pour `Square` afin de maintenir la stabilité de la sortie.</span><span class="sxs-lookup"><span data-stu-id="15b2e-159">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="15b2e-160">Ainsi, l’isolation de la logique classique la plus possible dans les fonctions facilite la réutilisation de cette logique dans d’autres fonctions et opérations.</span><span class="sxs-lookup"><span data-stu-id="15b2e-160">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>

## <a name="control-flow"></a><span data-ttu-id="15b2e-161">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="15b2e-161">Control Flow</span></span>

<span data-ttu-id="15b2e-162">Au sein d’une opération ou d’une fonction, chaque instruction s’exécute dans l’ordre, de la même façon que la plupart des langages classiques impératifs.</span><span class="sxs-lookup"><span data-stu-id="15b2e-162">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="15b2e-163">Ce déroulement de contrôle peut toutefois être modifié de trois façons différentes :</span><span class="sxs-lookup"><span data-stu-id="15b2e-163">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="15b2e-164">Instructions `if`</span><span class="sxs-lookup"><span data-stu-id="15b2e-164">`if` Statements</span></span>
- <span data-ttu-id="15b2e-165">`for` boucles</span><span class="sxs-lookup"><span data-stu-id="15b2e-165">`for` Loops</span></span>
- <span data-ttu-id="15b2e-166">`repeat`-boucles `until`</span><span class="sxs-lookup"><span data-stu-id="15b2e-166">`repeat`-`until` Loops</span></span>

<span data-ttu-id="15b2e-167">Nous différerons la discussion de ce dernier jusqu’à ce que nous ayons abordé les circuits de [répétition jusqu’à la réussite (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) .</span><span class="sxs-lookup"><span data-stu-id="15b2e-167">We defer discussion of the latter until we discuss [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) circuits.</span></span>
<span data-ttu-id="15b2e-168">Toutefois, les constructions de workflow de contrôle `if` et `for` se déroulent dans une certaine mesure pour la plupart des langages de programmation classiques.</span><span class="sxs-lookup"><span data-stu-id="15b2e-168">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>
<span data-ttu-id="15b2e-169">En particulier, une instruction `if` peut prendre une condition, peut être suivie d’une ou de plusieurs instructions `elif` et peut se terminer par une `else`:</span><span class="sxs-lookup"><span data-stu-id="15b2e-169">In particular, an `if` statement can take a condition, may be followed by one or more `elif` statements, and may end with an `else`:</span></span>

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

<span data-ttu-id="15b2e-170">De même, `for` boucles indiquent une itération sur une plage d’entiers ou sur les éléments d’un tableau :</span><span class="sxs-lookup"><span data-stu-id="15b2e-170">Similarly, `for` loops indicate iteration over a range of integers or over the elements of an array:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

<span data-ttu-id="15b2e-171">Important, `for` boucles et les instructions `if` peuvent même être utilisées dans des opérations pour lesquelles des spécialisations sont générées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="15b2e-171">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="15b2e-172">Dans ce cas, le voisin d’une boucle de `for` inverse la direction et prend la voisine de chaque itération.</span><span class="sxs-lookup"><span data-stu-id="15b2e-172">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="15b2e-173">Cela suit le principe des chaussures et des Socks : Si vous souhaitez annuler la pose sur SOCKS, puis sur des chaussures, vous devez annuler la pose des chaussures, puis annuler l’ajout de Socks.</span><span class="sxs-lookup"><span data-stu-id="15b2e-173">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="15b2e-174">Il est préférable de ne pas essayer de mettre votre Socks en marche tout en continuant à porter vos chaussures.</span><span class="sxs-lookup"><span data-stu-id="15b2e-174">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="operations-and-functions-as-first-class-values"></a><span data-ttu-id="15b2e-175">Opérations et fonctions comme valeurs de première classe</span><span class="sxs-lookup"><span data-stu-id="15b2e-175">Operations and Functions as First-Class Values</span></span>

<span data-ttu-id="15b2e-176">Une technique critique pour le type de contrôle et la logique classique utilisant des fonctions plutôt que des opérations consiste à utiliser les opérations et les fonctions dans Q # qui sont de *première classe*.</span><span class="sxs-lookup"><span data-stu-id="15b2e-176">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="15b2e-177">En d’autres termes, il s’agit de chaque valeur de la langue, à son propre droit.</span><span class="sxs-lookup"><span data-stu-id="15b2e-177">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="15b2e-178">Par exemple, le code suivant est parfaitement valide Q #, si un peu indirect :</span><span class="sxs-lookup"><span data-stu-id="15b2e-178">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="15b2e-179">La valeur de la variable `ourH` dans l’extrait de code ci-dessus est l’opération <xref:microsoft.quantum.intrinsic.h>, de sorte que nous pouvons appeler cette valeur comme n’importe quelle autre opération.</span><span class="sxs-lookup"><span data-stu-id="15b2e-179">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="15b2e-180">Cela nous permet d’écrire des opérations qui prennent des opérations dans le cadre de leur entrée, formant ainsi des concepts de contrôle d’ordre supérieur.</span><span class="sxs-lookup"><span data-stu-id="15b2e-180">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="15b2e-181">Par exemple, nous pourrions penser à « squareiser » une opération en l’appliquant deux fois au même qubit cible.</span><span class="sxs-lookup"><span data-stu-id="15b2e-181">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="15b2e-182">Dans cet exemple, la `=>` flèche qui apparaît dans le type `(Qubit => Unit)` indique que le champ d’entrée `op` est une opération qui prend comme entrée le type `Qubit` et produit un tuple vide comme sortie.</span><span class="sxs-lookup"><span data-stu-id="15b2e-182">In this example, the `=>` arrow that appears in the type `(Qubit => Unit)` denotes that the input field `op` is an operation which takes as its input the type `Qubit` and produces an empty tuple as its output.</span></span>
<span data-ttu-id="15b2e-183">En outre, nous spécifions les caractéristiques de ce type d’opération, qui contiennent les informations sur les functors pris en charge.</span><span class="sxs-lookup"><span data-stu-id="15b2e-183">Additionally we specify the characteristics of that operation type, which contain the information about which functors are supported.</span></span>
<span data-ttu-id="15b2e-184">Une opération de type `(Qubit => Unit)` ne prend en charge ni l' `Adjoint` ni le `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="15b2e-184">An operation of type `(Qubit => Unit)` supports neither the `Adjoint` nor the `Controlled` functor.</span></span> <span data-ttu-id="15b2e-185">Si vous souhaitez indiquer qu’une opération de ce type doit prendre en charge, par exemple, le `Adjoint` functor, nous devons le déclarer comme étant adjointable.</span><span class="sxs-lookup"><span data-stu-id="15b2e-185">If we want to indicate that an operation of that type has to support e.g. the `Adjoint` functor, we have to declare it as being adjointable.</span></span> <span data-ttu-id="15b2e-186">Pour ce faire, utilisez l’annotation `is Adj` au type.</span><span class="sxs-lookup"><span data-stu-id="15b2e-186">This is done by using the annotation `is Adj` to the type.</span></span> <span data-ttu-id="15b2e-187">De même, `(Qubit => Unit is Ctl)` indique qu’une opération de ce type prend en charge l' `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="15b2e-187">Similarly, `(Qubit => Unit is Ctl)` denotes that an operation of that type supports the `Controlled` functor.</span></span> <span data-ttu-id="15b2e-188">Nous étudierons ce point plus en détail lorsque nous aborderons les [types dans Q #] (XREF : Microsoft. Quantum. Language. type-Model) plus généralement.</span><span class="sxs-lookup"><span data-stu-id="15b2e-188">We will explore this further when we discuss [types in Q#] (xref:microsoft.quantum.language.type-model) more generally.</span></span>

<span data-ttu-id="15b2e-189">Pour le moment, nous insistons sur le fait que nous pouvons également retourner des opérations dans le cadre des sorties, de telle sorte que nous puissions isoler certains genres de logique conditionnelle classique comme une fonction classique qui retourne une description d’un programme Quantum sous la forme d’une opération.</span><span class="sxs-lookup"><span data-stu-id="15b2e-189">For now, we emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="15b2e-190">En guise d’exemple simple, prenons l’exemple de téléportage, dans lequel le tiers recevant un message classique à deux bits doit utiliser le message pour décoder leur qubit dans l’État téléporté approprié.</span><span class="sxs-lookup"><span data-stu-id="15b2e-190">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="15b2e-191">Nous pourrions écrire cela en termes d’une fonction qui prend ces deux bits classiques et retourne l’opération de décodage appropriée.</span><span class="sxs-lookup"><span data-stu-id="15b2e-191">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="15b2e-192">Cette nouvelle fonction est effectivement une fonction, car si nous l’appelons avec les mêmes valeurs de `hereBit` et `thereBit`, nous obtenons toujours la même opération.</span><span class="sxs-lookup"><span data-stu-id="15b2e-192">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="15b2e-193">Par conséquent, le décodeur peut être exécuté en toute sécurité au sein d’opérations sans avoir à expliquer comment la logique de décodage interagit avec les définitions des différentes spécialisations d’opérations.</span><span class="sxs-lookup"><span data-stu-id="15b2e-193">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="15b2e-194">Autrement dit, nous avons isolé la logique classique à l’intérieur d’une fonction, garantissant au compilateur que l’appel de fonction peut être réorganisé avec impunity tant que l’entrée est conservée.</span><span class="sxs-lookup"><span data-stu-id="15b2e-194">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>

<span data-ttu-id="15b2e-195">Nous pouvons également traiter les fonctions comme des valeurs de première classe, comme nous le verrons plus en détail lorsque nous aborderons [les types d’opérations et de fonctions](#operations-and-functions-as-first-class-values).</span><span class="sxs-lookup"><span data-stu-id="15b2e-195">We can also treat functions as first-class values, as we will see in more detail when we discuss [operations and function types](#operations-and-functions-as-first-class-values).</span></span>

## <a name="partially-applying-operations-and-functions"></a><span data-ttu-id="15b2e-196">Application partielle des opérations et des fonctions</span><span class="sxs-lookup"><span data-stu-id="15b2e-196">Partially Applying Operations and Functions</span></span>

<span data-ttu-id="15b2e-197">Nous pouvons en faire beaucoup plus avec les fonctions qui retournent des opérations à l’aide d’une *application partielle*, dans laquelle nous pouvons fournir une ou plusieurs parties de l’entrée à une fonction ou une opération sans réellement l’appeler.</span><span class="sxs-lookup"><span data-stu-id="15b2e-197">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="15b2e-198">Par exemple, si vous rappelez l’exemple de `ApplyTwice` ci-dessus, nous pouvons indiquer que nous ne voulons pas spécifier, immédiatement, à quel qubit l’opération d’entrée doit s’appliquer :</span><span class="sxs-lookup"><span data-stu-id="15b2e-198">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="15b2e-199">Dans ce cas, la variable locale `twiceOp` contient l’opération partiellement appliquée `ApplyTwice(op, _)`, où des parties de l’entrée qui n’ont pas encore été spécifiées sont indiquées par `_`.</span><span class="sxs-lookup"><span data-stu-id="15b2e-199">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="15b2e-200">Lorsque nous appelons `twiceOp` dans la ligne suivante, nous passons comme entrée à l’opération partiellement appliquée, toutes les autres parties de l’entrée à l’opération d’origine.</span><span class="sxs-lookup"><span data-stu-id="15b2e-200">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="15b2e-201">Par conséquent, l’extrait de code ci-dessus est effectivement identique à l’appel de `ApplyTwice(op, target)` directement, économisez pour que nous ayons introduit une nouvelle variable locale qui nous permet de retarder l’appel tout en fournissant certaines parties de l’entrée.</span><span class="sxs-lookup"><span data-stu-id="15b2e-201">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="15b2e-202">Étant donné qu’une opération partiellement appliquée n’est pas réellement appelée tant que l’intégralité de son entrée n’a pas été fournie, nous pouvons appliquer des opérations en toute sécurité, même à partir de fonctions.</span><span class="sxs-lookup"><span data-stu-id="15b2e-202">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="15b2e-203">En principe, la logique classique dans `SquareOperation` peut avoir été bien plus complexe, mais elle est toujours isolée du reste d’une opération par les garanties que le compilateur peut offrir sur les fonctions.</span><span class="sxs-lookup"><span data-stu-id="15b2e-203">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="15b2e-204">Cette approche sera utilisée dans la bibliothèque standard Q # pour exprimer le workflow de contrôle classique de manière à pouvoir l’utiliser facilement dans des programmes quantiques.</span><span class="sxs-lookup"><span data-stu-id="15b2e-204">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>
