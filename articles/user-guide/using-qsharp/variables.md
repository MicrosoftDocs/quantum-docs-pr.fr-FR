---
title: 'Variables dans Q #'
description: Description de remplissage
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 08301f408dcb2211ba25c582a5e5aa43310b714a
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885283"
---
# <a name="variables-in-q"></a><span data-ttu-id="05e19-103">Variables dans Q #</span><span class="sxs-lookup"><span data-stu-id="05e19-103">Variables in Q#</span></span>

<span data-ttu-id="05e19-104">Q # permet de faire la distinction entre les symboles mutables et immuables, ou les *variables*, qui sont liés/assignés à des expressions.</span><span class="sxs-lookup"><span data-stu-id="05e19-104">Q# distinguishes between mutable and immutable symbols, or *variables*, which are bound/assigned to expressions.</span></span>
<span data-ttu-id="05e19-105">En général, l’utilisation de symboles immuables est encouragée, car elle permet au compilateur d’effectuer des optimisations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="05e19-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="05e19-106">La partie gauche d’une liaison se compose d’un tuple de symboles et de la partie droite d’une expression.</span><span class="sxs-lookup"><span data-stu-id="05e19-106">The left-hand-side of a binding consists of a symbol tuple and the right-hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="05e19-107">Variables immuables</span><span class="sxs-lookup"><span data-stu-id="05e19-107">Immutable Variables</span></span>

<span data-ttu-id="05e19-108">Vous pouvez assigner une valeur de n’importe quel type dans Q # à une variable pour la réutiliser au sein d’une opération ou d’une fonction à l’aide du `let` mot clé.</span><span class="sxs-lookup"><span data-stu-id="05e19-108">You can assign a value of any type in Q# to a variable for reuse within an operation or function by using the `let` keyword.</span></span> 

<span data-ttu-id="05e19-109">Une liaison immuable se compose du mot clé `let` , suivi d’un symbole ou d’un tuple de symbole, d’un signe égal `=` , d’une expression pour lier le ou des symboles à et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="05e19-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="05e19-110">Exemple :</span><span class="sxs-lookup"><span data-stu-id="05e19-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="05e19-111">Cela affecte un tableau particulier d’opérateurs Pauli au nom de la variable (ou « Symbol »), `measurementOperator` .</span><span class="sxs-lookup"><span data-stu-id="05e19-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="05e19-112">Dans l’exemple précédent, il n’est pas nécessaire de spécifier explicitement le type de la nouvelle variable, car l’expression sur le côté droit de l' `let` instruction n’est pas ambiguë et le compilateur déduit le type correct.</span><span class="sxs-lookup"><span data-stu-id="05e19-112">In the previous example, there is no need to explicitly specify the type of the new variable, as the expression on the right-hand side of the `let` statement is unambiguous, and the compiler infers the correct type.</span></span> 

<span data-ttu-id="05e19-113">Les variables définies à l’aide de `let` sont *immuables*, ce qui signifie qu’une fois que vous l’avez définie, vous ne pouvez plus la modifier.</span><span class="sxs-lookup"><span data-stu-id="05e19-113">Variables defined using `let` are *immutable*, meaning that once you define it, you can no longer change it in any way.</span></span>
<span data-ttu-id="05e19-114">Cela permet d’effectuer plusieurs optimisations bénéfiques, notamment l’optimisation de la logique classique qui agit sur les variables à réorganiser pour l’application `Adjoint` de la variante d’une opération.</span><span class="sxs-lookup"><span data-stu-id="05e19-114">This allows for several beneficial optimizations, including optimization of the classical logic that acts on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="05e19-115">Variables mutables</span><span class="sxs-lookup"><span data-stu-id="05e19-115">Mutable Variables</span></span>

<span data-ttu-id="05e19-116">En guise d’alternative à la création d’une variable avec `let` , le `mutable` mot clé crée une variable mutable qui *peut* être reliée après sa création initiale à l’aide du `set` mot clé.</span><span class="sxs-lookup"><span data-stu-id="05e19-116">As an alternative to creating a variable with `let`, the `mutable` keyword creates a mutable variable that *can* be rebound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="05e19-117">Vous pouvez relier les symboles déclarés et liés dans le cadre d’une `mutable` instruction à une valeur différente ultérieurement dans le code.</span><span class="sxs-lookup"><span data-stu-id="05e19-117">You can rebind symbols declared and bound as part of a `mutable` statement to a different value later in the code.</span></span> <span data-ttu-id="05e19-118">Si un symbole est relié ultérieurement dans le code, son type ne change pas et la valeur qui vient d’être liée doit être compatible avec ce type.</span><span class="sxs-lookup"><span data-stu-id="05e19-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value must be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="05e19-119">Reliaison de symboles mutables</span><span class="sxs-lookup"><span data-stu-id="05e19-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="05e19-120">Vous pouvez relier une variable mutable à l’aide d’une `set` instruction.</span><span class="sxs-lookup"><span data-stu-id="05e19-120">You can rebind a mutable variable using a `set` statement.</span></span>
<span data-ttu-id="05e19-121">Une telle reliaison se compose du mot clé `set` , suivi d’un symbole ou d’un tuple de symbole, d’un signe égal `=` , d’une expression pour relier le ou des symboles à, et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="05e19-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="05e19-122">Voici quelques exemples de techniques d’instruction de reliaison.</span><span class="sxs-lookup"><span data-stu-id="05e19-122">The following are some examples of rebinding statement techniques.</span></span>

#### <a name="apply-and-reassign-statements"></a><span data-ttu-id="05e19-123">Instructions Apply-and-réassign</span><span class="sxs-lookup"><span data-stu-id="05e19-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="05e19-124">Un genre particulier d' `set` instruction, l’instruction *apply-and-réassign* , offre un moyen pratique de concaténer si le côté droit est constitué de l’application d’un opérateur binaire, et le résultat doit être relié à l’argument Left à l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="05e19-124">A particular kind of `set`-statement, the *apply-and-reassign* statement, provides a convenient way of concatenation if the right-hand side consists of the application of a binary operator, and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="05e19-125">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="05e19-125">For example,</span></span>

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="05e19-126">incrémente la valeur du compteur `counter` dans chaque itération de la `for` boucle.</span><span class="sxs-lookup"><span data-stu-id="05e19-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="05e19-127">Le code précédent est équivalent à</span><span class="sxs-lookup"><span data-stu-id="05e19-127">The previous code is equivalent to</span></span> 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="05e19-128">Des instructions similaires sont disponibles pour tous les opérateurs binaires dans lesquels le type du côté gauche correspond au type d’expression.</span><span class="sxs-lookup"><span data-stu-id="05e19-128">Similar statements are available for all binary operators in which the type of the left-hand side matches the expression type.</span></span> <span data-ttu-id="05e19-129">Ces instructions offrent un moyen pratique d’accumuler des valeurs.</span><span class="sxs-lookup"><span data-stu-id="05e19-129">These statements provide a convenient way to accumulate values.</span></span>

<span data-ttu-id="05e19-130">Par exemple, supposons qu' `qubits` il s’agit d’un registre de qubits :</span><span class="sxs-lookup"><span data-stu-id="05e19-130">For example, supposing `qubits` is a register of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a><span data-ttu-id="05e19-131">Instructions Update-and-Assign</span><span class="sxs-lookup"><span data-stu-id="05e19-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="05e19-132">Une concaténation similaire existe pour les [expressions de copie et de mise à jour](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) sur le côté droit.</span><span class="sxs-lookup"><span data-stu-id="05e19-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand side.</span></span>
<span data-ttu-id="05e19-133">En conséquence, les instructions *Update-and-Assign* existent pour les *éléments nommés* dans les types définis par l’utilisateur, ainsi que pour les *éléments de tableau*.</span><span class="sxs-lookup"><span data-stu-id="05e19-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items*.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="05e19-134">Dans le cas de tableaux, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) dans la bibliothèque standard Q # fournit les outils nécessaires pour de nombreux besoins d’initialisation et de manipulation de tableau communs, ce qui permet d’éviter d’avoir à mettre à jour les éléments de tableau en premier lieu.</span><span class="sxs-lookup"><span data-stu-id="05e19-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) in the Q# standard library provides the necessary tools for many common array initialization and manipulation needs, and thus helps avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="05e19-135">Les instructions Update-and-Assign fournissent une alternative si nécessaire :</span><span class="sxs-lookup"><span data-stu-id="05e19-135">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

<span data-ttu-id="05e19-136">À l’aide des outils de bibliothèque pour les tableaux fournis dans [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) , vous pouvez, par exemple, définir facilement une fonction qui retourne un tableau de `Pauli` types où l’élément à l’index `i` prend une `Pauli` valeur donnée, et toutes les autres entrées sont l’identité ( `PauliI` ).</span><span class="sxs-lookup"><span data-stu-id="05e19-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), you can, for example, easily define a function that returns an array of `Pauli` types where the element at index `i` takes a given `Pauli` value, and all other entries are the identity (`PauliI`).</span></span>

<span data-ttu-id="05e19-137">Voici deux définitions d’une telle fonction, avec la seconde tirant parti des outils de notre disposition.</span><span class="sxs-lookup"><span data-stu-id="05e19-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

<span data-ttu-id="05e19-138">Au lieu d’effectuer une itération au sein de chaque index du tableau, et de le définir de manière conditionnelle sur `PauliI` ou sur le donné `pauli` , vous pouvez utiliser à la place de `ConstantArray` [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) pour créer un tableau de `PauliI` types, puis simplement retourner une expression de copie et de mise à jour dans laquelle vous avez modifié la valeur spécifique au niveau de l’index `location` :</span><span class="sxs-lookup"><span data-stu-id="05e19-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or the given `pauli`, you can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) to create an array of `PauliI` types, and then simply return a copy-and-update expression in which you've changed the specific value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="05e19-139">Déconstruction de Tuple</span><span class="sxs-lookup"><span data-stu-id="05e19-139">Tuple Deconstruction</span></span>

<span data-ttu-id="05e19-140">Outre l’affectation d’une variable unique, vous pouvez utiliser les `let` `mutable` Mots clés et, ou toute autre construction de liaison, telle que `set` -pour décompresser le contenu d’un [type de tuple](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="05e19-140">In addition to assigning a single variable, you can use the `let` and `mutable` keywords - or any other binding construct, such as `set` - to unpack the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="05e19-141">Une assignation de ce formulaire est dite pour *déconstruire* les éléments de ce tuple.</span><span class="sxs-lookup"><span data-stu-id="05e19-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="05e19-142">Si le côté droit de la liaison est un tuple, vous pouvez déconstruire ce tuple lors de l’assignation.</span><span class="sxs-lookup"><span data-stu-id="05e19-142">If the right-hand side of the binding is a tuple, then you can deconstruct that tuple upon assignment.</span></span>
<span data-ttu-id="05e19-143">Ces déconstructions peuvent impliquer des tuples imbriqués, et toute déconstruction complète ou partielle est valide tant que la forme du tuple sur le côté droit est compatible avec la forme du tuple de symbole.</span><span class="sxs-lookup"><span data-stu-id="05e19-143">Such deconstructions can involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right-hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="05e19-144">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="05e19-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="05e19-145">Portées de liaison</span><span class="sxs-lookup"><span data-stu-id="05e19-145">Binding Scopes</span></span>

<span data-ttu-id="05e19-146">En général, les liaisons de symboles sont hors de portée et deviennent inopérantes à la fin du bloc d’instructions dans lequel elles se produisent.</span><span class="sxs-lookup"><span data-stu-id="05e19-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="05e19-147">Il y a deux exceptions à cette règle :</span><span class="sxs-lookup"><span data-stu-id="05e19-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="05e19-148">La liaison de la variable de boucle d’une `for` boucle est dans la portée du corps de la boucle for, mais pas après la fin de la boucle.</span><span class="sxs-lookup"><span data-stu-id="05e19-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="05e19-149">Les trois parties d’une `repeat` / `until` boucle (le corps, le test et la correction) agissent en tant qu’étendue unique, de sorte que les symboles qui sont liés dans le corps sont disponibles dans le test et la correction.</span><span class="sxs-lookup"><span data-stu-id="05e19-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) act as a single scope, so symbols that are bound in the body are available in the test and the fixup.</span></span>

<span data-ttu-id="05e19-150">Pour les deux types de boucles, chaque passage à la boucle s’exécute dans sa propre portée, de sorte que les liaisons d’une passe antérieure ne sont pas disponibles dans une étape ultérieure.</span><span class="sxs-lookup"><span data-stu-id="05e19-150">For both types of loops, each pass through the loop runs in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="05e19-151">Pour plus d’informations sur ces boucles, consultez [Control Flow](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="05e19-151">For more information on these loops, see [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="05e19-152">Les blocs internes héritent des liaisons de symboles des blocs externes.</span><span class="sxs-lookup"><span data-stu-id="05e19-152">Inner blocks inherit symbol bindings from outer blocks.</span></span>
<span data-ttu-id="05e19-153">Vous ne pouvez lier un symbole qu’une seule fois par bloc ; Il est interdit de définir un symbole portant le même nom qu’un autre symbole dans la portée (sans « occultation »).</span><span class="sxs-lookup"><span data-stu-id="05e19-153">You can only bind a symbol once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="05e19-154">Les séquences suivantes sont valides :</span><span class="sxs-lookup"><span data-stu-id="05e19-154">The following sequences are legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="05e19-155">et</span><span class="sxs-lookup"><span data-stu-id="05e19-155">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

<span data-ttu-id="05e19-156">Mais cela ne serait pas conforme :</span><span class="sxs-lookup"><span data-stu-id="05e19-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="05e19-157">comme cela :</span><span class="sxs-lookup"><span data-stu-id="05e19-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a><span data-ttu-id="05e19-158">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="05e19-158">Next steps</span></span>

<span data-ttu-id="05e19-159">En savoir plus sur l' [utilisation de qubits](xref:microsoft.quantum.guide.qubits) dans Q #.</span><span class="sxs-lookup"><span data-stu-id="05e19-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>