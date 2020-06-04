---
title: 'Workflow de contrôle dans Q #'
description: Boucles, conditions, etc.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 1f1b641563fe35879abeee32b4f0aeeb7001b1a0
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84326538"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="27635-103">Workflow de contrôle dans Q #</span><span class="sxs-lookup"><span data-stu-id="27635-103">Control Flow in Q#</span></span>

<span data-ttu-id="27635-104">Au sein d’une opération ou d’une fonction, chaque instruction s’exécute dans l’ordre, de la même façon que la plupart des langages classiques impératifs.</span><span class="sxs-lookup"><span data-stu-id="27635-104">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="27635-105">Ce déroulement de contrôle peut toutefois être modifié de trois façons différentes :</span><span class="sxs-lookup"><span data-stu-id="27635-105">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="27635-106">`if`publication</span><span class="sxs-lookup"><span data-stu-id="27635-106">`if` statements</span></span>
- <span data-ttu-id="27635-107">`for`boucles</span><span class="sxs-lookup"><span data-stu-id="27635-107">`for` loops</span></span>
- <span data-ttu-id="27635-108">`repeat`-`until`boucles</span><span class="sxs-lookup"><span data-stu-id="27635-108">`repeat`-`until` loops</span></span>

<span data-ttu-id="27635-109">Nous différerons la discussion de ce dernier [pour aller plus loin.](#repeat-until-success-loop)</span><span class="sxs-lookup"><span data-stu-id="27635-109">We defer discussion of the latter to further [below](#repeat-until-success-loop).</span></span>
<span data-ttu-id="27635-110">`if` `for` Toutefois, les constructions de contrôle et de contrôle de workflow se déroulent de façon familière à la plupart des langages de programmation classiques.</span><span class="sxs-lookup"><span data-stu-id="27635-110">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>

<span data-ttu-id="27635-111">Important, les `for` boucles et les `if` instructions peuvent même être utilisées dans les opérations pour lesquelles des spécialisations sont générées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="27635-111">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="27635-112">Dans ce cas, le voisint d’une `for` boucle inverse la direction et prend la voisine de chaque itération.</span><span class="sxs-lookup"><span data-stu-id="27635-112">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="27635-113">Cela suit le principe des chaussures et des Socks : Si vous souhaitez annuler la pose sur SOCKS, puis sur des chaussures, vous devez annuler la pose des chaussures, puis annuler l’ajout de Socks.</span><span class="sxs-lookup"><span data-stu-id="27635-113">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="27635-114">Il est préférable de ne pas essayer de mettre votre Socks en marche tout en continuant à porter vos chaussures.</span><span class="sxs-lookup"><span data-stu-id="27635-114">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="if-else-if-else"></a><span data-ttu-id="27635-115">If, else-if, sinon</span><span class="sxs-lookup"><span data-stu-id="27635-115">If, Else-if, Else</span></span>

<span data-ttu-id="27635-116">L' `if` instruction prend en charge l’exécution conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="27635-116">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="27635-117">Il se compose du mot clé `if` , d’une parenthèse ouvrante `(` , d’une expression booléenne, d’une parenthèse fermante `)` et d’un bloc d’instructions (le bloc _Then_ ).</span><span class="sxs-lookup"><span data-stu-id="27635-117">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="27635-118">Il peut être suivi de n’importe quel nombre de clauses Else-If, chacune comprenant le mot clé `elif` , une parenthèse ouvrante `(` , une expression booléenne, une parenthèse fermante `)` et un bloc d’instructions (le bloc _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="27635-118">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="27635-119">Enfin, l’instruction peut éventuellement se terminer par une clause Else, qui se compose du mot clé `else` suivi d’un autre bloc d’instructions (le bloc _else_ ).</span><span class="sxs-lookup"><span data-stu-id="27635-119">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="27635-120">La `if` condition est évaluée, et si elle a la valeur true, le bloc Then est exécuté.</span><span class="sxs-lookup"><span data-stu-id="27635-120">The `if` condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="27635-121">Si la condition est false, la première condition else-if est évaluée ; Si la valeur est true, le bloc Else-If est exécuté.</span><span class="sxs-lookup"><span data-stu-id="27635-121">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="27635-122">Dans le cas contraire, le deuxième bloc Else-If est testé, puis le troisième, et ainsi de suite jusqu’à ce qu’une clause avec une condition true soit rencontrée ou qu’il n’y ait plus aucune clause else-if.</span><span class="sxs-lookup"><span data-stu-id="27635-122">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="27635-123">Si la condition if d’origine et toutes les clauses Else-If ont la valeur false, le bloc Else est exécuté s’il en a été fourni.</span><span class="sxs-lookup"><span data-stu-id="27635-123">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="27635-124">Notez que le bloc qui est exécuté est exécuté dans sa propre portée.</span><span class="sxs-lookup"><span data-stu-id="27635-124">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="27635-125">Les liaisons effectuées à l’intérieur d’un `if` `elif` bloc, ou ne `else` sont pas visibles après sa fin.</span><span class="sxs-lookup"><span data-stu-id="27635-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after its end.</span></span>

<span data-ttu-id="27635-126">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="27635-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="27635-127">or</span><span class="sxs-lookup"><span data-stu-id="27635-127">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="27635-128">Boucle For</span><span class="sxs-lookup"><span data-stu-id="27635-128">For Loop</span></span>

<span data-ttu-id="27635-129">L' `for` instruction prend en charge l’itération sur une plage d’entiers ou sur un tableau.</span><span class="sxs-lookup"><span data-stu-id="27635-129">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="27635-130">L’instruction se compose du mot clé `for` , d’une parenthèse ouvrante `(` , suivi d’un symbole ou d’un tuple de symbole, du mot clé `in` , d’une expression de type `Range` ou tableau, d’une parenthèse fermante `)` et d’un bloc d’instructions.</span><span class="sxs-lookup"><span data-stu-id="27635-130">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="27635-131">Le bloc d’instructions (corps de la boucle) est exécuté à plusieurs reprises, avec les symboles définis (la ou les variables de boucle) liés à chaque valeur dans la plage ou le tableau.</span><span class="sxs-lookup"><span data-stu-id="27635-131">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="27635-132">Notez que si l’expression de plage a la valeur d’une plage ou d’un tableau vide, le corps ne sera pas exécuté.</span><span class="sxs-lookup"><span data-stu-id="27635-132">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="27635-133">L’expression est entièrement évaluée avant d’entrer dans la boucle et ne change pas pendant l’exécution de la boucle.</span><span class="sxs-lookup"><span data-stu-id="27635-133">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="27635-134">La variable de boucle est liée à chaque entrée dans le corps de la boucle et est détachée à la fin du corps.</span><span class="sxs-lookup"><span data-stu-id="27635-134">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="27635-135">En particulier, la variable de boucle n’est pas liée après la fin de la boucle for.</span><span class="sxs-lookup"><span data-stu-id="27635-135">In particular, the loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="27635-136">La liaison du ou des symboles déclarés est immuable et suit les mêmes règles que les autres liaisons de variables.</span><span class="sxs-lookup"><span data-stu-id="27635-136">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="27635-137">Pour certains exemples, supposons qu' `qubits` il s’agit d’un registre de qubits (c’est-à-dire de type `Qubit[]` ).</span><span class="sxs-lookup"><span data-stu-id="27635-137">For some examples, supposing `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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
<span data-ttu-id="27635-138">Notez que, à la fin, nous avons utilisé l’opérateur binaire arithmétique-décalage-gauche, `<<<` , dont les détails sont disponibles aux [expressions numériques](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span><span class="sxs-lookup"><span data-stu-id="27635-138">Note that at the end we utilized the arithmetic-shift-left binary operator, `<<<`, details of which can be found at [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span></span>


## <a name="repeat-until-success-loop"></a><span data-ttu-id="27635-139">Répéter jusqu’à la réussite de la boucle</span><span class="sxs-lookup"><span data-stu-id="27635-139">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="27635-140">Le langage Q # permet au workflow de contrôle classique de dépendre des résultats de la mesure des qubits.</span><span class="sxs-lookup"><span data-stu-id="27635-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="27635-141">Cette fonctionnalité permet à son tour d’implémenter des gadgets probabilistes puissants qui peuvent réduire le coût de calcul de l’implémentation des unités.</span><span class="sxs-lookup"><span data-stu-id="27635-141">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="27635-142">Par exemple, il est facile d’implémenter des modèles de *répétition jusqu’à réussite* (RUS) dans Q #.</span><span class="sxs-lookup"><span data-stu-id="27635-142">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="27635-143">Ces modèles de RUS sont des programmes probabilistes qui ont un coût faible *attendu* en termes de portes élémentaires, mais pour lesquels le coût réel dépend d’une exécution réelle et d’un entrelacement réel de diverses branches possibles.</span><span class="sxs-lookup"><span data-stu-id="27635-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="27635-144">Pour faciliter les modèles de répétition jusqu’à réussite (RUS), Q # prend en charge les constructions</span><span class="sxs-lookup"><span data-stu-id="27635-144">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="27635-145">où `expression` est une expression valide qui correspond à une valeur de type `Bool` .</span><span class="sxs-lookup"><span data-stu-id="27635-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="27635-146">Le corps de la boucle est exécuté, puis la condition est évaluée.</span><span class="sxs-lookup"><span data-stu-id="27635-146">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="27635-147">Si la condition est true, l’instruction est terminée ; dans le cas contraire, la correction est exécutée et l’instruction est réexécutée en commençant par le corps de la boucle.</span><span class="sxs-lookup"><span data-stu-id="27635-147">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>

<span data-ttu-id="27635-148">Les trois parties d’une boucle REPEAT/UNTIL (le corps, le test et la correction) sont traitées comme une seule étendue *pour chaque répétition*, de sorte que les symboles qui sont liés dans le corps sont disponibles dans le test et dans la correction.</span><span class="sxs-lookup"><span data-stu-id="27635-148">All three portions of a repeat/until loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in the test and in the fixup.</span></span>
<span data-ttu-id="27635-149">Toutefois, l’exécution de la correction met fin à l’étendue de l’instruction, de sorte que les liaisons de symboles effectuées pendant le corps ou la correction ne sont pas disponibles dans les répétitions suivantes.</span><span class="sxs-lookup"><span data-stu-id="27635-149">However completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="27635-150">En outre, l' `fixup` instruction est souvent utile, mais pas toujours nécessaire.</span><span class="sxs-lookup"><span data-stu-id="27635-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="27635-151">Dans les cas où il n’est pas nécessaire, la construction</span><span class="sxs-lookup"><span data-stu-id="27635-151">In cases that it is not needed, the construct</span></span>
```qsharp
repeat {
    // do stuff
}
until (expression);
```
<span data-ttu-id="27635-152">est également un modèle de RUS valide.</span><span class="sxs-lookup"><span data-stu-id="27635-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="27635-153">En bas de cette page, nous présentons des [exemples de boucles de RUS](#repeat-until-success-examples).</span><span class="sxs-lookup"><span data-stu-id="27635-153">At the bottom of this page we present some [examples of RUS loops](#repeat-until-success-examples).</span></span>

> [!TIP]   
> <span data-ttu-id="27635-154">Évitez d’utiliser des boucles de répétition jusqu’à réussite dans les fonctions.</span><span class="sxs-lookup"><span data-stu-id="27635-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="27635-155">Les fonctionnalités correspondantes sont fournies par les boucles While dans les fonctions.</span><span class="sxs-lookup"><span data-stu-id="27635-155">The corresponding functionality is provided by while loops in functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="27635-156">Boucle while</span><span class="sxs-lookup"><span data-stu-id="27635-156">While Loop</span></span>

<span data-ttu-id="27635-157">Les modèles de répétition jusqu’à réussite ont un connotation très spécifique au quantum.</span><span class="sxs-lookup"><span data-stu-id="27635-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="27635-158">Elles sont largement utilisées dans des classes particulières d’algorithmes Quantum, donc la construction du langage dédié dans Q #.</span><span class="sxs-lookup"><span data-stu-id="27635-158">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="27635-159">Toutefois, les boucles qui s’arrêtent en fonction d’une condition et dont la longueur d’exécution est donc inconnue au moment de la compilation doivent être gérées avec une attention particulière dans un Runtime Quantum.</span><span class="sxs-lookup"><span data-stu-id="27635-159">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="27635-160">Leur utilisation dans les fonctions en revanche pose un problème, car celles-ci contiennent uniquement du code qui sera exécuté sur du matériel conventionnel (non Quantum).</span><span class="sxs-lookup"><span data-stu-id="27635-160">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="27635-161">Q # prend donc en charge l’utilisation de boucles While uniquement dans les fonctions.</span><span class="sxs-lookup"><span data-stu-id="27635-161">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="27635-162">Une `while` instruction se compose du mot clé `while` , d’une parenthèse ouvrante `(` , d’une condition (c’est-à-dire une expression booléenne), d’une parenthèse fermante `)` et d’un bloc d’instructions.</span><span class="sxs-lookup"><span data-stu-id="27635-162">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="27635-163">Le bloc d’instructions (corps de la boucle) est exécuté tant que la condition a la valeur `true` .</span><span class="sxs-lookup"><span data-stu-id="27635-163">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a><span data-ttu-id="27635-164">Return (instruction)</span><span class="sxs-lookup"><span data-stu-id="27635-164">Return Statement</span></span>

<span data-ttu-id="27635-165">L’instruction return termine l’exécution d’une opération ou d’une fonction et retourne une valeur à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="27635-165">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="27635-166">Il se compose du mot clé `return` , suivi d’une expression du type approprié et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="27635-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="27635-167">Un pouvant être appelé qui retourne un tuple vide, `()` , ne requiert pas d’instruction return.</span><span class="sxs-lookup"><span data-stu-id="27635-167">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="27635-168">Si vous souhaitez une sortie précoce, `return ()` peut être utilisé dans ce cas.</span><span class="sxs-lookup"><span data-stu-id="27635-168">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="27635-169">Les callables qui retournent tout autre type requièrent une instruction return finale.</span><span class="sxs-lookup"><span data-stu-id="27635-169">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="27635-170">Il n’y a pas de nombre maximal d’instructions return dans une opération.</span><span class="sxs-lookup"><span data-stu-id="27635-170">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="27635-171">Le compilateur peut émettre un avertissement si les instructions suivent une instruction return dans un bloc.</span><span class="sxs-lookup"><span data-stu-id="27635-171">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="27635-172">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="27635-172">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="27635-173">or</span><span class="sxs-lookup"><span data-stu-id="27635-173">or</span></span>
```qsharp
return ();
```
<span data-ttu-id="27635-174">or</span><span class="sxs-lookup"><span data-stu-id="27635-174">or</span></span>
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a><span data-ttu-id="27635-175">Fail (instruction)</span><span class="sxs-lookup"><span data-stu-id="27635-175">Fail Statement</span></span>

<span data-ttu-id="27635-176">L’instruction Fail termine l’exécution d’une opération et retourne une valeur d’erreur à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="27635-176">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="27635-177">Il se compose du mot clé `fail` , suivi d’une chaîne et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="27635-177">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="27635-178">La chaîne est retournée au pilote classique comme message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="27635-178">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="27635-179">Il n’existe aucune restriction sur le nombre d’instructions d’échec au sein d’une opération.</span><span class="sxs-lookup"><span data-stu-id="27635-179">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="27635-180">Le compilateur peut émettre un avertissement si les instructions suivent une instruction Fail dans un bloc.</span><span class="sxs-lookup"><span data-stu-id="27635-180">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="27635-181">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="27635-181">For example,</span></span>
```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="27635-182">ou, à l’aide de [chaînes interpolées](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span><span class="sxs-lookup"><span data-stu-id="27635-182">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="27635-183">Exemples de répétition jusqu’à réussite</span><span class="sxs-lookup"><span data-stu-id="27635-183">Repeat-Until-Success Examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="27635-184">Modèle RUS pour la rotation d’un seul qubit sur un axe irrationnelle</span><span class="sxs-lookup"><span data-stu-id="27635-184">RUS pattern for single qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="27635-185">Dans un cas d’usage courant, l’opération Q # suivante implémente une rotation autour d’un axe irrationnelle de $ (I + 2i Z)/\sqrt {5} $ sur la sphère Bloch.</span><span class="sxs-lookup"><span data-stu-id="27635-185">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="27635-186">Pour ce faire, utilisez un modèle de RUS connu :</span><span class="sxs-lookup"><span data-stu-id="27635-186">This is accomplished by using a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a><span data-ttu-id="27635-187">Boucle de RUS avec variable mutable dans l’étendue</span><span class="sxs-lookup"><span data-stu-id="27635-187">RUS loop with mutable variable in scope</span></span>

<span data-ttu-id="27635-188">Cet exemple montre l’utilisation d’une variable mutable `finished` qui est dans la portée de la boucle REPEAT-UNTIL-Fixup entière et qui est initialisée avant la boucle et mise à jour à l’étape de correction.</span><span class="sxs-lookup"><span data-stu-id="27635-188">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="27635-189">RUS sans`fixup`</span><span class="sxs-lookup"><span data-stu-id="27635-189">RUS without `fixup`</span></span>

<span data-ttu-id="27635-190">Par exemple, le code suivant est un circuit probabiliste qui implémente une porte de rotation importante $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ à l’aide des `H` `T` portes et.</span><span class="sxs-lookup"><span data-stu-id="27635-190">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="27635-191">La boucle se termine dans les répétitions de $ \frac {8} {5} $ en moyenne.</span><span class="sxs-lookup"><span data-stu-id="27635-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="27635-192">Pour plus d’informations, consultez [*répéter jusqu’à la réussite : décomposition non déterministe des unités de qubit de données uniques*](https://arxiv.org/abs/1311.1074) (Paetznick et Svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="27635-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="27635-193">RUS pour préparer un État Quantum</span><span class="sxs-lookup"><span data-stu-id="27635-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="27635-194">Enfin, nous présentons un exemple de modèle de RUS pour préparer un État Quantum $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, à partir de l’État $ \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="27635-194">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="27635-195">Consultez également l' [exemple de test unitaire fourni avec la bibliothèque standard](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="27635-195">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

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

<span data-ttu-id="27635-196">Les fonctionnalités de programmation notables présentées dans cette opération sont une partie plus complexe `fixup` de la boucle, qui implique des opérations de Quantum et l’utilisation d' `AssertProb` instructions pour déterminer la probabilité de mesurer l’État Quantum à certains points spécifiés dans le programme.</span><span class="sxs-lookup"><span data-stu-id="27635-196">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="27635-197">Pour plus d’informations sur les opérations et, consultez également [test et débogage](xref:microsoft.quantum.guide.testingdebugging) [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) .</span><span class="sxs-lookup"><span data-stu-id="27635-197">See also [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>


## <a name="next-steps"></a><span data-ttu-id="27635-198">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="27635-198">Next steps</span></span>

<span data-ttu-id="27635-199">En savoir plus sur le [test et le débogage](xref:microsoft.quantum.guide.testingdebugging) dans Q #.</span><span class="sxs-lookup"><span data-stu-id="27635-199">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>