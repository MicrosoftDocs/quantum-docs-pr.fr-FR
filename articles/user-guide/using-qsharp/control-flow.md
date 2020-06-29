---
title: 'Workflow de contrôle dans Q #'
description: Boucles, conditions, etc.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 0cf62a128170bd0c28ff77f00fc23414567b1ea4
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415301"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="17bfd-103">Workflow de contrôle dans Q #</span><span class="sxs-lookup"><span data-stu-id="17bfd-103">Control flow in Q#</span></span>

<span data-ttu-id="17bfd-104">Au sein d’une opération ou d’une fonction, chaque instruction s’exécute dans l’ordre, de la même façon que d’autres langages classiques impératifs.</span><span class="sxs-lookup"><span data-stu-id="17bfd-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="17bfd-105">Toutefois, vous pouvez modifier le déroulement du contrôle de trois façons distinctes :</span><span class="sxs-lookup"><span data-stu-id="17bfd-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="17bfd-106">`if`publication</span><span class="sxs-lookup"><span data-stu-id="17bfd-106">`if` statements</span></span>
* <span data-ttu-id="17bfd-107">`for`boucles</span><span class="sxs-lookup"><span data-stu-id="17bfd-107">`for` loops</span></span>
* <span data-ttu-id="17bfd-108">`repeat-until-success`boucles</span><span class="sxs-lookup"><span data-stu-id="17bfd-108">`repeat-until-success` loops</span></span>

<span data-ttu-id="17bfd-109">Les `if` `for` constructions de workflow et de contrôle se poursuivent de manière familière à la plupart des langages de programmation classiques.</span><span class="sxs-lookup"><span data-stu-id="17bfd-109">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="17bfd-110">[`Repeat-until-success`](#repeat-until-success-loop)les boucles sont abordées plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="17bfd-110">[`Repeat-until-success`](#repeat-until-success-loop) loops are discussed later in this article.</span></span>

<span data-ttu-id="17bfd-111">Important, les `for` boucles et les `if` instructions peuvent être utilisées dans les opérations pour lesquelles les [spécialisations](xref:microsoft.quantum.guide.operationsfunctions) sont générées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="17bfd-111">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="17bfd-112">Dans ce scénario, le voisint d’une `for` boucle inverse la direction et prend le voisin de chaque itération.</span><span class="sxs-lookup"><span data-stu-id="17bfd-112">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="17bfd-113">Cette action suit le principe « chaussures-and-Socks » : Si vous souhaitez annuler la pose sur SOCKS, puis sur chaussures, vous devez annuler la pose des chaussures, puis annuler l’introduction sur Socks.</span><span class="sxs-lookup"><span data-stu-id="17bfd-113">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="17bfd-114">If, else-if, sinon</span><span class="sxs-lookup"><span data-stu-id="17bfd-114">If, Else-if, Else</span></span>

<span data-ttu-id="17bfd-115">L' `if` instruction prend en charge l’exécution conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="17bfd-115">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="17bfd-116">Il se compose du mot clé `if` , d’une expression booléenne entre parenthèses et d’un bloc d’instructions (bloc _Then_ ).</span><span class="sxs-lookup"><span data-stu-id="17bfd-116">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="17bfd-117">Si vous le souhaitez, un nombre quelconque de clauses Else-If peuvent suivre, chacune comprenant le mot clé `elif` , une expression booléenne entre parenthèses et un bloc d’instructions (le bloc _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="17bfd-117">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="17bfd-118">Enfin, l’instruction peut éventuellement se terminer par une clause Else, qui se compose du mot clé `else` suivi d’un autre bloc d’instructions (le bloc _else_ ).</span><span class="sxs-lookup"><span data-stu-id="17bfd-118">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="17bfd-119">La `if` condition est évaluée, et si elle a la *valeur true*, le bloc *Then* est exécuté.</span><span class="sxs-lookup"><span data-stu-id="17bfd-119">The `if` condition is evaluated, and if it is *true*, the *then* block is run.</span></span>
<span data-ttu-id="17bfd-120">Si la condition est *false*, la première condition else-if est évaluée ; Si la valeur est true, le bloc *else-if* est exécuté.</span><span class="sxs-lookup"><span data-stu-id="17bfd-120">If the condition is *false*, then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="17bfd-121">Dans le cas contraire, le deuxième bloc Else-If prend la valeur, puis le troisième, et ainsi de suite jusqu’à ce qu’une clause avec une condition true soit rencontrée ou qu’il n’y ait plus aucune clause else-if.</span><span class="sxs-lookup"><span data-stu-id="17bfd-121">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="17bfd-122">Si la condition *If* d’origine et toutes les clauses Else-If ont la *valeur false*, le bloc *else* est exécuté, s’il est fourni.</span><span class="sxs-lookup"><span data-stu-id="17bfd-122">If the original *if* condition and all the else-if clauses evaluate to *false*, the *else* block is run, if provided.</span></span>

<span data-ttu-id="17bfd-123">Notez que, quel que soit le bloc exécuté, il s’exécute dans sa propre portée.</span><span class="sxs-lookup"><span data-stu-id="17bfd-123">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="17bfd-124">Les liaisons effectuées à l’intérieur d’un `if` `elif` bloc, ou ne `else` sont pas visibles après la fin du bloc.</span><span class="sxs-lookup"><span data-stu-id="17bfd-124">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="17bfd-125">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="17bfd-125">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="17bfd-126">ou</span><span class="sxs-lookup"><span data-stu-id="17bfd-126">or</span></span>
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a><span data-ttu-id="17bfd-127">Boucle for</span><span class="sxs-lookup"><span data-stu-id="17bfd-127">For loop</span></span>

<span data-ttu-id="17bfd-128">L' `for` instruction prend en charge l’itération sur une plage d’entiers ou un tableau.</span><span class="sxs-lookup"><span data-stu-id="17bfd-128">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="17bfd-129">L’instruction se compose du mot clé `for` , suivi d’un symbole ou d’un tuple de symbole, du mot clé et d’une `in` expression de type `Range` ou tableau, tous entre parenthèses et un bloc d’instructions.</span><span class="sxs-lookup"><span data-stu-id="17bfd-129">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="17bfd-130">Le bloc d’instructions (le corps de la boucle) s’exécute à plusieurs reprises, avec le symbole défini (la variable de boucle) lié à chaque valeur dans la plage ou le tableau.</span><span class="sxs-lookup"><span data-stu-id="17bfd-130">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="17bfd-131">Notez que si l’expression de plage prend la valeur d’une plage ou d’un tableau vide, le corps ne s’exécute pas du tout.</span><span class="sxs-lookup"><span data-stu-id="17bfd-131">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="17bfd-132">L’expression est entièrement évaluée avant d’entrer dans la boucle et ne change pas pendant l’exécution de la boucle.</span><span class="sxs-lookup"><span data-stu-id="17bfd-132">The expression is fully evaluated before entering the loop, and does not change while the loop is executing.</span></span>

<span data-ttu-id="17bfd-133">La variable de boucle est liée à chaque entrée dans le corps de la boucle et est détachée à la fin du corps.</span><span class="sxs-lookup"><span data-stu-id="17bfd-133">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="17bfd-134">La variable de boucle n’est pas liée après la fin de la boucle for.</span><span class="sxs-lookup"><span data-stu-id="17bfd-134">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="17bfd-135">La liaison de la variable de boucle est immuable et suit les mêmes règles que les autres liaisons de variables.</span><span class="sxs-lookup"><span data-stu-id="17bfd-135">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="17bfd-136">Dans ces exemples, `qubits` est un registre de qubits (c’est-à-dire de type `Qubit[]` ).</span><span class="sxs-lookup"><span data-stu-id="17bfd-136">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="17bfd-137">Notez qu’à la fin, nous avons utilisé l’opérateur binaire arithmétique-décalage-gauche, `<<<` .</span><span class="sxs-lookup"><span data-stu-id="17bfd-137">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="17bfd-138">Pour plus d’informations, consultez [expressions numériques](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span><span class="sxs-lookup"><span data-stu-id="17bfd-138">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="17bfd-139">Répéter jusqu’à la réussite de la boucle</span><span class="sxs-lookup"><span data-stu-id="17bfd-139">Repeat-until-success loop</span></span>

<span data-ttu-id="17bfd-140">Le langage Q # permet au workflow de contrôle classique de dépendre des résultats de la mesure des qubits.</span><span class="sxs-lookup"><span data-stu-id="17bfd-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="17bfd-141">Cette fonctionnalité permet, à son tour, d’implémenter des gadgets probabilistes puissants qui peuvent réduire le coût de calcul de l’implémentation des unités.</span><span class="sxs-lookup"><span data-stu-id="17bfd-141">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="17bfd-142">Voici des exemples de modèles de *répétition jusqu’à réussite* (RUS) dans Q #.</span><span class="sxs-lookup"><span data-stu-id="17bfd-142">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="17bfd-143">Ces modèles de RUS sont des programmes probabilistes qui ont un coût faible *attendu* en termes de portes élémentaires ; le coût encouru dépend de l’exécution réelle et de l’entrelacement des différentes branches possibles.</span><span class="sxs-lookup"><span data-stu-id="17bfd-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="17bfd-144">Pour faciliter les modèles de répétition jusqu’à réussite (RUS), Q # prend en charge les constructions</span><span class="sxs-lookup"><span data-stu-id="17bfd-144">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="17bfd-145">où `expression` est une expression valide qui correspond à une valeur de type `Bool` .</span><span class="sxs-lookup"><span data-stu-id="17bfd-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="17bfd-146">Le corps de la boucle s’exécute, puis la condition est évaluée.</span><span class="sxs-lookup"><span data-stu-id="17bfd-146">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="17bfd-147">Si la condition est true, l’instruction est terminée ; dans le cas contraire, la correction s’exécute et l’instruction s’exécute à nouveau, en commençant par le corps de la boucle.</span><span class="sxs-lookup"><span data-stu-id="17bfd-147">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="17bfd-148">Les trois parties d’une boucle de service de contrôle d’accès (corps, test et correction) sont traitées comme une seule étendue *pour chaque répétition*, de sorte que les symboles liés dans le corps sont disponibles à la fois dans le test et dans la correction.</span><span class="sxs-lookup"><span data-stu-id="17bfd-148">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="17bfd-149">Toutefois, l’exécution de la correction met fin à l’étendue de l’instruction, de sorte que les liaisons de symboles effectuées pendant le corps ou la correction ne sont pas disponibles dans les répétitions suivantes.</span><span class="sxs-lookup"><span data-stu-id="17bfd-149">However, completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="17bfd-150">En outre, l' `fixup` instruction est souvent utile, mais pas toujours nécessaire.</span><span class="sxs-lookup"><span data-stu-id="17bfd-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="17bfd-151">Dans les cas où il n’est pas nécessaire, la construction</span><span class="sxs-lookup"><span data-stu-id="17bfd-151">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="17bfd-152">est également un modèle de RUS valide.</span><span class="sxs-lookup"><span data-stu-id="17bfd-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="17bfd-153">Pour obtenir plus d’exemples et de détails, consultez la section [exemples de répétition jusqu’à réussite](#repeat-until-success-examples) dans cet article.</span><span class="sxs-lookup"><span data-stu-id="17bfd-153">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="17bfd-154">Évitez d’utiliser des boucles de répétition jusqu’à réussite dans les fonctions.</span><span class="sxs-lookup"><span data-stu-id="17bfd-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="17bfd-155">Utilisez des boucles *while* pour fournir la fonctionnalité correspondante à l’intérieur des fonctions.</span><span class="sxs-lookup"><span data-stu-id="17bfd-155">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="17bfd-156">Boucle while</span><span class="sxs-lookup"><span data-stu-id="17bfd-156">While loop</span></span>

<span data-ttu-id="17bfd-157">Les modèles de répétition jusqu’à réussite ont un connotation très spécifique au quantum.</span><span class="sxs-lookup"><span data-stu-id="17bfd-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="17bfd-158">Elles sont largement utilisées dans des classes particulières d’algorithmes Quantum, donc la construction du langage dédié dans Q #.</span><span class="sxs-lookup"><span data-stu-id="17bfd-158">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="17bfd-159">Toutefois, les boucles qui s’arrêtent en fonction d’une condition et dont la longueur d’exécution est donc inconnue au moment de la compilation sont gérées avec une attention particulière dans un Runtime Quantum.</span><span class="sxs-lookup"><span data-stu-id="17bfd-159">However, loops that break based on a condition and whose execution length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="17bfd-160">Toutefois, leur utilisation dans les fonctions ne pose pas de problème, car ces boucles contiennent uniquement du code qui s’exécute sur du matériel conventionnel (non Quantum).</span><span class="sxs-lookup"><span data-stu-id="17bfd-160">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="17bfd-161">Q #, par conséquent, prend en charge l’utilisation de boucles While uniquement dans les fonctions.</span><span class="sxs-lookup"><span data-stu-id="17bfd-161">Q#, therefore, supports to use of while loops within functions only.</span></span> <span data-ttu-id="17bfd-162">Une `while` instruction se compose du mot clé `while` , d’une expression booléenne entre parenthèses et d’un bloc d’instructions.</span><span class="sxs-lookup"><span data-stu-id="17bfd-162">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="17bfd-163">Le bloc d’instructions (corps de la boucle) s’exécute tant que la condition a la valeur `true` .</span><span class="sxs-lookup"><span data-stu-id="17bfd-163">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="return-statement"></a><span data-ttu-id="17bfd-164">Return (instruction)</span><span class="sxs-lookup"><span data-stu-id="17bfd-164">Return Statement</span></span>

<span data-ttu-id="17bfd-165">L’instruction return termine l’exécution d’une opération ou d’une fonction et retourne une valeur à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="17bfd-165">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="17bfd-166">Il se compose du mot clé `return` , suivi d’une expression du type approprié et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="17bfd-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="17bfd-167">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="17bfd-167">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="17bfd-168">ou</span><span class="sxs-lookup"><span data-stu-id="17bfd-168">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="17bfd-169">Un pouvant être appelé qui retourne un tuple vide, `()` , ne requiert pas d’instruction return.</span><span class="sxs-lookup"><span data-stu-id="17bfd-169">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="17bfd-170">Pour spécifier une sortie précoce de l’opération ou de la fonction, utilisez `return ();` .</span><span class="sxs-lookup"><span data-stu-id="17bfd-170">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="17bfd-171">Les callables qui retournent tout autre type requièrent une instruction return finale.</span><span class="sxs-lookup"><span data-stu-id="17bfd-171">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="17bfd-172">Il n’y a pas de nombre maximal d’instructions return dans une opération.</span><span class="sxs-lookup"><span data-stu-id="17bfd-172">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="17bfd-173">Le compilateur peut émettre un avertissement si les instructions suivent une instruction return dans un bloc.</span><span class="sxs-lookup"><span data-stu-id="17bfd-173">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="17bfd-174">Fail (instruction)</span><span class="sxs-lookup"><span data-stu-id="17bfd-174">Fail statement</span></span>

<span data-ttu-id="17bfd-175">L’instruction Fail met fin à l’exécution d’une opération et retourne une valeur d’erreur à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="17bfd-175">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="17bfd-176">Il se compose du mot clé `fail` , suivi d’une chaîne et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="17bfd-176">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="17bfd-177">L’instruction retourne la chaîne au pilote classique comme message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="17bfd-177">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="17bfd-178">Il n’existe aucune restriction sur le nombre d’instructions d’échec au sein d’une opération.</span><span class="sxs-lookup"><span data-stu-id="17bfd-178">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="17bfd-179">Le compilateur peut émettre un avertissement si les instructions suivent une instruction Fail dans un bloc.</span><span class="sxs-lookup"><span data-stu-id="17bfd-179">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="17bfd-180">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="17bfd-180">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="17bfd-181">ou, à l’aide de [chaînes interpolées](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span><span class="sxs-lookup"><span data-stu-id="17bfd-181">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="17bfd-182">Exemples de répétition jusqu’à réussite</span><span class="sxs-lookup"><span data-stu-id="17bfd-182">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="17bfd-183">Modèle RUS pour la rotation d’un qubit sur un axe irrationnelle</span><span class="sxs-lookup"><span data-stu-id="17bfd-183">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="17bfd-184">Dans un cas d’usage courant, l’opération Q # suivante implémente une rotation autour d’un axe irrationnelle de $ (I + 2i Z)/\sqrt {5} $ sur la sphère Bloch.</span><span class="sxs-lookup"><span data-stu-id="17bfd-184">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="17bfd-185">L’implémentation utilise un modèle de RUS connu :</span><span class="sxs-lookup"><span data-stu-id="17bfd-185">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="17bfd-186">Boucle de RUS avec une variable mutable dans l’étendue</span><span class="sxs-lookup"><span data-stu-id="17bfd-186">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="17bfd-187">Cet exemple illustre l’utilisation d’une variable mutable, `finished` , qui se trouve dans l’étendue de la boucle REPEAT-UNTIL-Fixup entière et qui est initialisée avant la boucle et mise à jour à l’étape de correction.</span><span class="sxs-lookup"><span data-stu-id="17bfd-187">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a><span data-ttu-id="17bfd-188">RUS sans`fixup`</span><span class="sxs-lookup"><span data-stu-id="17bfd-188">RUS without `fixup`</span></span>

<span data-ttu-id="17bfd-189">Cet exemple montre une boucle de RUS sans l’étape de correction.</span><span class="sxs-lookup"><span data-stu-id="17bfd-189">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="17bfd-190">Le code est un circuit probabiliste qui implémente une porte de rotation importante $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ à l’aide des `H` `T` portes et.</span><span class="sxs-lookup"><span data-stu-id="17bfd-190">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="17bfd-191">La boucle se termine dans les répétitions de $ \frac {8} {5} $ en moyenne.</span><span class="sxs-lookup"><span data-stu-id="17bfd-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="17bfd-192">Pour plus d’informations, consultez [*répéter jusqu’à la réussite : décomposition non déterministe des unités de qubit de données uniques*](https://arxiv.org/abs/1311.1074) (Paetznick et Svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="17bfd-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="17bfd-193">RUS pour préparer un État Quantum</span><span class="sxs-lookup"><span data-stu-id="17bfd-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="17bfd-194">Enfin, voici un exemple de modèle de RUS pour préparer un État Quantum $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, à partir de l’État $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="17bfd-194">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="17bfd-195">Les fonctionnalités de programmation notables présentées dans cette opération sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="17bfd-195">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="17bfd-196">Une partie plus complexe `fixup` de la boucle, qui implique des opérations Quantum.</span><span class="sxs-lookup"><span data-stu-id="17bfd-196">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="17bfd-197">L’utilisation d' `AssertProb` instructions pour déterminer la probabilité de mesurer l’État Quantum à certains points spécifiés dans le programme.</span><span class="sxs-lookup"><span data-stu-id="17bfd-197">The use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="17bfd-198">Pour plus d’informations sur [`Assert`](xref:microsoft.quantum.intrinsic.assert) les [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) opérations et, consultez [test et débogage](xref:microsoft.quantum.guide.testingdebugging).</span><span class="sxs-lookup"><span data-stu-id="17bfd-198">For more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
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

<span data-ttu-id="17bfd-199">Pour plus d’informations, consultez [exemple de test unitaire fourni avec la bibliothèque standard](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="17bfd-199">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="17bfd-200">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="17bfd-200">Next steps</span></span>

<span data-ttu-id="17bfd-201">En savoir plus sur le [test et le débogage](xref:microsoft.quantum.guide.testingdebugging) dans Q #.</span><span class="sxs-lookup"><span data-stu-id="17bfd-201">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>
