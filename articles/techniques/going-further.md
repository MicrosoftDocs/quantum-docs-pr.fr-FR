---
title: 'Q # techniques-aller plus loin | Microsoft Docs'
description: 'Q # techniques-aller plus loin'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4677b0f9c4f64a9c1bc46d34e8a883dc006ba8f0
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183299"
---
# <a name="going-further"></a><span data-ttu-id="9b54c-103">Aller plus loin</span><span class="sxs-lookup"><span data-stu-id="9b54c-103">Going Further</span></span> #

<span data-ttu-id="9b54c-104">Maintenant que vous avez vu comment écrire des programmes quantiques intéressants dans Q #, cette section va plus loin en introduisant des rubriques plus avancées qui doivent se révéler utiles.</span><span class="sxs-lookup"><span data-stu-id="9b54c-104">Now that you've seen how to write interesting quantum programs in Q#, this section goes further by introducing a few more advanced topics that should prove useful going forward.</span></span>

<!-- Moved Debugging and Testing Quantum Programs section to a separate article -->

## <a name="generic-operations-and-functions"></a><span data-ttu-id="9b54c-105">Opérations et fonctions génériques</span><span class="sxs-lookup"><span data-stu-id="9b54c-105">Generic Operations and Functions</span></span> ##

> [!TIP]
> <span data-ttu-id="9b54c-106">Cette section suppose une connaissance de base des [génériques dans C# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), des [génériques dans F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [ C++ des modèles](https://docs.microsoft.com/cpp/cpp/templates-cpp)ou des approches similaires à la surprogrammation dans d’autres langages.</span><span class="sxs-lookup"><span data-stu-id="9b54c-106">This section assumes some basic familiarity with [generics in C#](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generics in F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [C++ templates](https://docs.microsoft.com/cpp/cpp/templates-cpp), or similar approaches to metaprogramming in other languages.</span></span>

<span data-ttu-id="9b54c-107">De nombreuses fonctions et opérations que nous pouvons souhaiter définir ne s’appuient pas vraiment sur les types de leurs entrées, mais plutôt implicitement utiliser leurs types via une autre fonction ou opération.</span><span class="sxs-lookup"><span data-stu-id="9b54c-107">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="9b54c-108">Par exemple, considérez le concept de *carte* commun à de nombreux langages fonctionnels ; à partir d’une fonction $f (x) $ et d’une collection de valeurs $\{X_1, X_2, \dots, x_n\}$, Map retourne une nouvelle collection $\{f (X_1), f (X_2), \dots, f (x_n)\}$.</span><span class="sxs-lookup"><span data-stu-id="9b54c-108">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="9b54c-109">Pour l’implémenter dans Q #, nous pouvons tirer parti de la première classe de ces fonctions.</span><span class="sxs-lookup"><span data-stu-id="9b54c-109">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="9b54c-110">Nous allons écrire un exemple rapide de `Map`, en utilisant ★ en tant qu’espace réservé tout en décrivant les types dont nous avons besoin.</span><span class="sxs-lookup"><span data-stu-id="9b54c-110">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="9b54c-111">Remarque Cette fonction est très similaire, quel que soit le type réel que nous remplaçons.</span><span class="sxs-lookup"><span data-stu-id="9b54c-111">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="9b54c-112">Une carte des entiers à Paulis, par exemple, est similaire à une carte à partir de nombres à virgule flottante en chaînes :</span><span class="sxs-lookup"><span data-stu-id="9b54c-112">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="9b54c-113">En principe, nous pourrions écrire une version de `Map` pour chaque paire de types que nous rencontrons, mais cela introduit un certain nombre de difficultés.</span><span class="sxs-lookup"><span data-stu-id="9b54c-113">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="9b54c-114">Par exemple, si nous trouvons un bogue dans `Map`, nous devons nous assurer que le correctif est appliqué uniformément dans toutes les versions de `Map`.</span><span class="sxs-lookup"><span data-stu-id="9b54c-114">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="9b54c-115">De plus, si nous construisons un nouveau tuple ou UDT, nous devons maintenant créer également un nouveau `Map` pour aller avec le nouveau type.</span><span class="sxs-lookup"><span data-stu-id="9b54c-115">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="9b54c-116">Bien que cela soit tractable pour un petit nombre de ces fonctions, étant donné que nous recueillons de plus en plus de fonctions de la même forme que `Map`, le coût de l’introduction de nouveaux types devient insuffisant dans un ordre relativement court.</span><span class="sxs-lookup"><span data-stu-id="9b54c-116">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="9b54c-117">Toutefois, une grande partie de cette difficulté est que nous n’avons pas donné au compilateur les informations dont il a besoin pour reconnaître comment les différentes versions de `Map` sont associées.</span><span class="sxs-lookup"><span data-stu-id="9b54c-117">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="9b54c-118">En fait, nous voulons que le compilateur traite `Map` comme un type de fonction mathématique des *types* q # aux fonctions q #.</span><span class="sxs-lookup"><span data-stu-id="9b54c-118">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>
<span data-ttu-id="9b54c-119">Cette notion est formalisée en autorisant les fonctions et les opérations à avoir des *paramètres de type*, ainsi que leurs paramètres de tuple ordinaires.</span><span class="sxs-lookup"><span data-stu-id="9b54c-119">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="9b54c-120">Dans les exemples ci-dessus, nous souhaitons considérer `Map` comme ayant des paramètres de type `Int, Pauli` dans le premier cas et `Double, String` dans le second cas.</span><span class="sxs-lookup"><span data-stu-id="9b54c-120">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="9b54c-121">Dans la plupart des cas, ces paramètres de type peuvent ensuite être utilisés comme s’il s’agissait de types ordinaires : nous utilisons des valeurs de paramètres de type pour créer des tableaux et des tuples, appeler des fonctions et des opérations, et les assigner à des variables ordinaires ou mutables.</span><span class="sxs-lookup"><span data-stu-id="9b54c-121">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="9b54c-122">Le cas le plus extrême de dépendance indirecte est le cas de qubits, où un programme Q # ne peut pas s’appuyer directement sur la structure du type de `Qubit`, mais **doit** passer ces types à d’autres opérations et fonctions.</span><span class="sxs-lookup"><span data-stu-id="9b54c-122">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="9b54c-123">En revenant à l’exemple ci-dessus, nous pouvons voir que nous avons besoin de `Map` pour avoir des paramètres de type, l’un pour représenter l’entrée à `fn` et l’autre pour représenter la sortie de `fn`.</span><span class="sxs-lookup"><span data-stu-id="9b54c-123">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="9b54c-124">Dans Q #, il est écrit en ajoutant des crochets pointus (`<>`, et non brakets $ \braket{}$ !) après le nom d’une fonction ou d’une opération dans sa déclaration, et en répertoriant chaque paramètre de type.</span><span class="sxs-lookup"><span data-stu-id="9b54c-124">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="9b54c-125">Le nom de chaque paramètre de type doit commencer par un cycle `'`, indiquant qu’il s’agit d’un paramètre de type et non d’un type ordinaire (également appelé type *concret* ).</span><span class="sxs-lookup"><span data-stu-id="9b54c-125">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="9b54c-126">Par `Map`, nous écrivons donc :</span><span class="sxs-lookup"><span data-stu-id="9b54c-126">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="9b54c-127">Notez que la définition de `Map<'Input, 'Output>` semble très similaire aux versions que nous avons écrites auparavant.</span><span class="sxs-lookup"><span data-stu-id="9b54c-127">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="9b54c-128">La seule différence est que nous avons explicitement informé le compilateur que `Map` ne dépend pas directement des `'Input` et des `'Output`, mais fonctionne pour deux types quelconques en les utilisant indirectement par le biais de `fn`.</span><span class="sxs-lookup"><span data-stu-id="9b54c-128">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="9b54c-129">Une fois que nous avons défini `Map<'Input, 'Output>` de cette manière, nous pouvons l’appeler comme s’il s’agissait d’une fonction ordinaire :</span><span class="sxs-lookup"><span data-stu-id="9b54c-129">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="9b54c-130">L’écriture de fonctions et d’opérations génériques est un emplacement où « tuple en sortie de tuple » est un moyen très utile de réfléchir aux fonctions et opérations Q #.</span><span class="sxs-lookup"><span data-stu-id="9b54c-130">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="9b54c-131">Étant donné que chaque fonction accepte exactement une entrée et retourne exactement une sortie, une entrée de type `'T -> 'U` correspond à *n’importe quelle* fonction Q # de quelque manière que ce soit.</span><span class="sxs-lookup"><span data-stu-id="9b54c-131">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="9b54c-132">De même, toute opération peut être passée à une entrée de type `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="9b54c-132">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="9b54c-133">En guise de deuxième exemple, considérez le défi que pose l’écriture d’une fonction qui retourne la composition de deux autres fonctions :</span><span class="sxs-lookup"><span data-stu-id="9b54c-133">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="9b54c-134">Ici, nous devons spécifier exactement ce que `A`, `B`et `C` sont, par conséquent, il est donc nécessaire de limiter gravement l’utilitaire de notre nouvelle fonction `Compose`.</span><span class="sxs-lookup"><span data-stu-id="9b54c-134">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="9b54c-135">Après tout, `Compose` dépend de `A`, `B`et `C` *via* `innerFn` et `outerFn`.</span><span class="sxs-lookup"><span data-stu-id="9b54c-135">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="9b54c-136">En guise d’alternative, nous pouvons ajouter des paramètres de type à `Compose` indiquant qu’elle fonctionne pour *n’importe quel* `A`, `B`et `C`, tant que ces paramètres correspondent à ceux attendus par `innerFn` et `outerFn`:</span><span class="sxs-lookup"><span data-stu-id="9b54c-136">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="9b54c-137">Les bibliothèques standard Q # fournissent une série de ces opérations et fonctions paramétrées de type pour faciliter l’utilisation du workflow de contrôle d’ordre supérieur.</span><span class="sxs-lookup"><span data-stu-id="9b54c-137">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="9b54c-138">Celles-ci sont abordées plus en détail dans le Guide de la [bibliothèque standard Q #](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="9b54c-138">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="borrowing-qubits"></a><span data-ttu-id="9b54c-139">Emprunt d’qubits</span><span class="sxs-lookup"><span data-stu-id="9b54c-139">Borrowing Qubits</span></span> ##

<span data-ttu-id="9b54c-140">Le mécanisme d’emprunt autorise l’allocation de qubits qui peut être utilisé comme espace de travail pendant un calcul.</span><span class="sxs-lookup"><span data-stu-id="9b54c-140">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span> <span data-ttu-id="9b54c-141">Ces qubits ne sont généralement pas dans un état propre, c’est-à-dire qu’ils ne sont pas nécessairement initialisés dans un état connu tel que $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="9b54c-141">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span> <span data-ttu-id="9b54c-142">L’un d’eux parle également de « qubits », car leur état est inconnu et peut même être enchevêtré avec d’autres parties de la mémoire de l’ordinateur quantique.</span><span class="sxs-lookup"><span data-stu-id="9b54c-142">One also speaks of "dirty" qubits as their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span> <span data-ttu-id="9b54c-143">Parmi les cas d’utilisation connus des qubits modifiés, citons les implémentations de portes CNOTIN multicontrôlées qui requièrent uniquement très peu de qubits et l’implémentation d’incrémenteurs.</span><span class="sxs-lookup"><span data-stu-id="9b54c-143">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>

<span data-ttu-id="9b54c-144">Dans l’Canon, il existe des exemples qui utilisent le mot clé `borrowing`, par exemple la fonction `MultiControlledXBorrow` définie ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9b54c-144">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="9b54c-145">Si `controls` dénote le contrôle qubits qui doit être ajouté à une opération de `X`, alors l’ensemble de `Length(controls)-2` de ancillas modifiés sera ajouté par cette implémentation.</span><span class="sxs-lookup"><span data-stu-id="9b54c-145">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="9b54c-146">Notez que l’utilisation intensive du combineur `With`---dans sa forme applicable pour les opérations qui prennent en charge la valeur de voisint, c’est-à-dire `WithA`---a été effectuée dans cet exemple, ce qui est un bon style de programmation, car l’ajout d’un contrôle à des structures impliquant `With` uniquement propage le contrôle à l’opération interne.</span><span class="sxs-lookup"><span data-stu-id="9b54c-146">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example which is good programming style as adding control to structures involving `With` only propagates control to the inner operation.</span></span> <span data-ttu-id="9b54c-147">Notez également que, en plus de la `body` de l’opération, une implémentation du corps `controlled` de l’opération a été explicitement fournie, plutôt que de recourir à une instruction `controlled auto`.</span><span class="sxs-lookup"><span data-stu-id="9b54c-147">Further note that here in addition to the `body` of the operation an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span> <span data-ttu-id="9b54c-148">Cela est dû au fait que nous savons à partir de la structure du circuit comment ajouter facilement des contrôles supplémentaires, ce qui est avantageux par rapport à l’ajout de contrôle à chaque porte de la `body`.</span><span class="sxs-lookup"><span data-stu-id="9b54c-148">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="9b54c-149">Il est intéressant de comparer ce code avec une autre fonction Canon `MultiControlledXClean` qui atteint le même objectif de l’implémentation d’une opération `X` à contrôle multiple, mais qui utilise plusieurs qubits propres à l’aide du mécanisme de `using`.</span><span class="sxs-lookup"><span data-stu-id="9b54c-149">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 
