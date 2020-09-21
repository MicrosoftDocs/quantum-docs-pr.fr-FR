---
title: Expressions dans Q#
description: Comprenez comment spécifier, référencer et combiner des constantes, des variables, des opérateurs, des opérations et des fonctions en tant qu’expressions dans Q# .
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9bf28e3854eae1892692d7ca840e1860de2e2934
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835840"
---
# <a name="expressions-in-no-locq"></a><span data-ttu-id="22644-103">Expressions dans Q#</span><span class="sxs-lookup"><span data-stu-id="22644-103">Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="22644-104">Expressions numériques</span><span class="sxs-lookup"><span data-stu-id="22644-104">Numeric Expressions</span></span>

<span data-ttu-id="22644-105">Les expressions numériques sont des expressions de type `Int` , `BigInt` ou `Double` .</span><span class="sxs-lookup"><span data-stu-id="22644-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="22644-106">Autrement dit, il s’agit de nombres entiers ou à virgule flottante.</span><span class="sxs-lookup"><span data-stu-id="22644-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="22644-107">`Int` les littéraux dans Q# sont écrits sous la forme d’une séquence de chiffres.</span><span class="sxs-lookup"><span data-stu-id="22644-107">`Int` literals in Q# are written as a sequence of digits.</span></span>
<span data-ttu-id="22644-108">Les entiers hexadécimaux et binaires sont pris en charge et écrits avec un `0x` `0b` préfixe et, respectivement.</span><span class="sxs-lookup"><span data-stu-id="22644-108">Hexadecimal and binary integers are supported and written with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="22644-109">`BigInt` les littéraux dans Q# ont un `l` suffixe ou de fin `L` .</span><span class="sxs-lookup"><span data-stu-id="22644-109">`BigInt` literals in Q# have a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="22644-110">Les entiers hexadécimaux Big sont pris en charge et écrits avec un préfixe « 0x ».</span><span class="sxs-lookup"><span data-stu-id="22644-110">Hexadecimal big integers are supported and written with a "0x" prefix.</span></span>
<span data-ttu-id="22644-111">Par conséquent, Voici toutes les utilisations valides des `BigInt` littéraux :</span><span class="sxs-lookup"><span data-stu-id="22644-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="22644-112">`Double` les littéraux dans Q# sont des nombres à virgule flottante écrits à l’aide de chiffres décimaux.</span><span class="sxs-lookup"><span data-stu-id="22644-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="22644-113">Elles peuvent être écrites avec ou sans virgule décimale, `.` , ou une partie exponentielle indiquée par « e » ou « e » (après quoi seuls un signe négatif et des chiffres décimaux possibles sont valides).</span><span class="sxs-lookup"><span data-stu-id="22644-113">They can be written with or without a decimal point, `.`, or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="22644-114">Les littéraux valides sont les suivants `Double` : `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="22644-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="22644-115">À partir d’une expression de tableau de tout type d’élément, vous pouvez former une `Int` expression à l’aide de la [`Length`](xref:microsoft.quantum.core.length) fonction intégrée, avec l’expression de tableau placée entre parenthèses.</span><span class="sxs-lookup"><span data-stu-id="22644-115">Given an array expression of any element type, you can form an `Int` expression using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses.</span></span>
<span data-ttu-id="22644-116">Par exemple, si `a` est lié à un tableau, `Length(a)` est une expression d’entier.</span><span class="sxs-lookup"><span data-stu-id="22644-116">For example, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="22644-117">Si `b` est un tableau de tableaux d’entiers, `Int[][]` , `Length(b)` est le nombre de sous-tableaux dans `b` , et `Length(b[1])` est le nombre d’entiers dans le deuxième sous-tableau de `b` .</span><span class="sxs-lookup"><span data-stu-id="22644-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="22644-118">À partir de deux expressions numériques du même type, les opérateurs binaires `+` , `-` , `*` et `/` peuvent être utilisés pour former une nouvelle expression numérique.</span><span class="sxs-lookup"><span data-stu-id="22644-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="22644-119">Le type de la nouvelle expression est le même que les types des expressions constituantes.</span><span class="sxs-lookup"><span data-stu-id="22644-119">The type of the new expression is the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="22644-120">À partir de deux expressions entières, utilisez l’opérateur binaire `^` (Power) pour former une nouvelle expression entière.</span><span class="sxs-lookup"><span data-stu-id="22644-120">Given two integer expressions, use the binary operator `^` (power) to form a new integer expression.</span></span>
<span data-ttu-id="22644-121">De même, vous pouvez également utiliser `^` avec deux expressions double pour former une nouvelle expression double.</span><span class="sxs-lookup"><span data-stu-id="22644-121">Similarly, you can also use `^` with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="22644-122">Enfin, vous pouvez utiliser `^` avec un grand entier à gauche et un entier sur la droite pour former une nouvelle expression d’entier Big.</span><span class="sxs-lookup"><span data-stu-id="22644-122">Finally, you can use `^` with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="22644-123">Dans ce cas, le deuxième paramètre doit être contenu dans 32 bits ; Si ce n’est pas le cas, il déclenche une erreur d’exécution.</span><span class="sxs-lookup"><span data-stu-id="22644-123">In this case, the second parameter must fit into 32 bits; if not, it raises a runtime error.</span></span>

<span data-ttu-id="22644-124">À partir de deux expressions entières ou d’entiers Big, forment une nouvelle expression de type entier ou entier Big à l’aide des `%` opérateurs (modulo), (opérateur de bits and), (au niveau du bit or `&&&` `|||` ) ou `^^^` (opérateur de bits XOR).</span><span class="sxs-lookup"><span data-stu-id="22644-124">Given two integer or big integer expressions, form a new integer or big integer expression using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="22644-125">À partir d’une expression d’entier ou d’entier Big à gauche, et d’une expression d’entier à droite, utilisez les `<<<` opérateurs (décalage arithmétique vers la gauche) ou `>>>` (décalage vers la droite) pour créer une nouvelle expression avec le même type que l’expression de gauche.</span><span class="sxs-lookup"><span data-stu-id="22644-125">Given either an integer or big integer expression on the left, and an integer expression on the right, use the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="22644-126">Le deuxième paramètre (la valeur de décalage) pour l’opération de décalage doit être supérieur ou égal à zéro ; le comportement des valeurs de décalage négatives n’est pas défini.</span><span class="sxs-lookup"><span data-stu-id="22644-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="22644-127">La valeur de décalage pour l’opération de décalage doit également tenir dans 32 bits ; Si ce n’est pas le cas, il déclenche une erreur d’exécution.</span><span class="sxs-lookup"><span data-stu-id="22644-127">The shift amount for either shift operation must also fit into 32 bits; if not, it raises a runtime error.</span></span>
<span data-ttu-id="22644-128">Si le nombre décalé est un entier, la valeur de décalage est interprétée `mod 64` ; autrement dit, un décalage de 1 et un décalage de 65 ont le même effet.</span><span class="sxs-lookup"><span data-stu-id="22644-128">If the number shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="22644-129">Pour les valeurs entières et de type entier Big, les décalages sont arithmétiques.</span><span class="sxs-lookup"><span data-stu-id="22644-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="22644-130">Le décalage d’une valeur négative à gauche ou à droite produit un nombre négatif.</span><span class="sxs-lookup"><span data-stu-id="22644-130">Shifting a negative value either left or right results in a negative number.</span></span>
<span data-ttu-id="22644-131">Autrement dit, le décalage d’une étape vers la gauche ou vers la droite est identique à la multiplication ou à la division par 2, respectivement.</span><span class="sxs-lookup"><span data-stu-id="22644-131">That is, shifting one step to the left or right is the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="22644-132">Le modulo de la division entière et de l’entier suit le même comportement pour les nombres négatifs que C#.</span><span class="sxs-lookup"><span data-stu-id="22644-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span> <span data-ttu-id="22644-133">Autrement dit, `a % b` a toujours le même signe que `a` et est `b * (a / b) + a % b` toujours égal à `a` .</span><span class="sxs-lookup"><span data-stu-id="22644-133">That is, `a % b` always has the same sign as `a`, and `b * (a / b) + a % b` always equals `a`.</span></span> <span data-ttu-id="22644-134">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="22644-134">For example:</span></span>

|`A` | `B` | `A / B` | `A % B`|
|:---------:|:----------:|:---------:|:---------:|
| <span data-ttu-id="22644-135">5</span><span class="sxs-lookup"><span data-stu-id="22644-135">5</span></span> | <span data-ttu-id="22644-136">2</span><span class="sxs-lookup"><span data-stu-id="22644-136">2</span></span> | <span data-ttu-id="22644-137">2</span><span class="sxs-lookup"><span data-stu-id="22644-137">2</span></span> | <span data-ttu-id="22644-138">1</span><span class="sxs-lookup"><span data-stu-id="22644-138">1</span></span> |
| <span data-ttu-id="22644-139">5</span><span class="sxs-lookup"><span data-stu-id="22644-139">5</span></span> | <span data-ttu-id="22644-140">-2</span><span class="sxs-lookup"><span data-stu-id="22644-140">-2</span></span> | <span data-ttu-id="22644-141">-2</span><span class="sxs-lookup"><span data-stu-id="22644-141">-2</span></span> | <span data-ttu-id="22644-142">1</span><span class="sxs-lookup"><span data-stu-id="22644-142">1</span></span> |
| <span data-ttu-id="22644-143">-5</span><span class="sxs-lookup"><span data-stu-id="22644-143">-5</span></span> | <span data-ttu-id="22644-144">2</span><span class="sxs-lookup"><span data-stu-id="22644-144">2</span></span> | <span data-ttu-id="22644-145">-2</span><span class="sxs-lookup"><span data-stu-id="22644-145">-2</span></span> | <span data-ttu-id="22644-146">-1</span><span class="sxs-lookup"><span data-stu-id="22644-146">-1</span></span> |
| <span data-ttu-id="22644-147">-5</span><span class="sxs-lookup"><span data-stu-id="22644-147">-5</span></span> | <span data-ttu-id="22644-148">-2</span><span class="sxs-lookup"><span data-stu-id="22644-148">-2</span></span> | <span data-ttu-id="22644-149">2</span><span class="sxs-lookup"><span data-stu-id="22644-149">2</span></span> | <span data-ttu-id="22644-150">-1</span><span class="sxs-lookup"><span data-stu-id="22644-150">-1</span></span> |

<span data-ttu-id="22644-151">Les opérations de division d’entiers et de modulo fonctionnent de la même façon.</span><span class="sxs-lookup"><span data-stu-id="22644-151">Big integer division and modulus operations work the same way.</span></span>

<span data-ttu-id="22644-152">À partir de toute expression numérique, vous pouvez former une nouvelle expression à l’aide de l' `-` opérateur unaire.</span><span class="sxs-lookup"><span data-stu-id="22644-152">Given any numeric expression, you can form a new expression using the `-` unary operator.</span></span>
<span data-ttu-id="22644-153">La nouvelle expression est du même type que l’expression constitutive.</span><span class="sxs-lookup"><span data-stu-id="22644-153">The new expression is the same type as the constituent expression.</span></span>

<span data-ttu-id="22644-154">À partir de toute expression d’entier ou d’entier Big, vous pouvez former une nouvelle expression du même type à l’aide de l' `~~~` opérateur unaire (complément de bits).</span><span class="sxs-lookup"><span data-stu-id="22644-154">Given any integer or big integer expression, you can form a new expression of the same type using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="22644-155">Expressions booléennes</span><span class="sxs-lookup"><span data-stu-id="22644-155">Boolean Expressions</span></span>

<span data-ttu-id="22644-156">Les deux `Bool` valeurs littérales sont `true` et `false` .</span><span class="sxs-lookup"><span data-stu-id="22644-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="22644-157">Compte tenu des deux expressions du même type primitif, les `==` `!=` opérateurs binaires et peuvent être utilisés pour construire une `Bool` expression.</span><span class="sxs-lookup"><span data-stu-id="22644-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="22644-158">L’expression a la valeur true si les deux expressions sont égales et false dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="22644-158">The expression is true if the two expressions are equal and false if not.</span></span>

<span data-ttu-id="22644-159">Les valeurs des types définis par l’utilisateur ne peuvent pas être comparées, seules leurs valeurs désencapsulées peuvent être comparées.</span><span class="sxs-lookup"><span data-stu-id="22644-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="22644-160">Par exemple, à l’aide de l’opérateur « Unwrap » `!` (expliqué en détail dans les [types dans Q# ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span><span class="sxs-lookup"><span data-stu-id="22644-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="22644-161">La comparaison d’égalité pour les `Qubit` valeurs est l’égalité d’identité ; autrement dit, si les deux expressions identifient le même qubit.</span><span class="sxs-lookup"><span data-stu-id="22644-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="22644-162">Les États des deux qubits ne sont pas comparés, consultés, mesurés ou modifiés par cette comparaison.</span><span class="sxs-lookup"><span data-stu-id="22644-162">The states of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="22644-163">La comparaison d’égalité des `Double` valeurs peut être trompeuse en raison des effets arrondis.</span><span class="sxs-lookup"><span data-stu-id="22644-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="22644-164">Par exemple : `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="22644-164">For example, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="22644-165">Compte tenu de deux expressions numériques, les opérateurs binaires `>` , `<` , `>=` et `<=` peuvent être utilisés pour construire une nouvelle expression booléenne qui a la valeur true si la première expression est respectivement supérieure à, inférieure à, supérieure ou égale à, ou inférieure ou égale à la seconde.</span><span class="sxs-lookup"><span data-stu-id="22644-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="22644-166">Compte tenu de deux expressions booléennes, utilisez l' `and` opérateur binaire pour construire une nouvelle expression booléenne qui a la valeur true si les deux expressions ont la valeur true.</span><span class="sxs-lookup"><span data-stu-id="22644-166">Given any two Boolean expressions, use the `and` binary operator to construct a new Boolean expression that is true if both of the two expressions are true.</span></span> <span data-ttu-id="22644-167">De même, l’utilisation `or` de l’opérateur crée une expression qui a la valeur true si l’une des deux expressions a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="22644-167">Likewise, using the `or` operator creates an expression that is true if either of the two expressions is true.</span></span>

<span data-ttu-id="22644-168">À partir de toute expression booléenne, l' `not` opérateur unaire peut être utilisé pour construire une nouvelle expression booléenne qui a la valeur true si l’expression constitutive est false.</span><span class="sxs-lookup"><span data-stu-id="22644-168">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="22644-169">Expressions de chaîne</span><span class="sxs-lookup"><span data-stu-id="22644-169">String expressions</span></span>

<span data-ttu-id="22644-170">Q# autorise l’utilisation de chaînes dans l' `fail` instruction (expliquée dans le [Workflow de contrôle](xref:microsoft.quantum.guide.controlflow#fail-statement)) et dans la [`Message`](xref:microsoft.quantum.intrinsic.message) fonction standard.</span><span class="sxs-lookup"><span data-stu-id="22644-170">Q# allows strings to be used in the `fail` statement (explained in [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span> <span data-ttu-id="22644-171">Le comportement spécifique de ce dernier dépend du simulateur utilisé, mais écrit généralement un message dans la console hôte lorsqu’il est appelé pendant un Q# programme.</span><span class="sxs-lookup"><span data-stu-id="22644-171">The specific behavior of the latter depends on the simulator used but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="22644-172">Les chaînes dans Q# sont des littéraux ou des chaînes interpolées.</span><span class="sxs-lookup"><span data-stu-id="22644-172">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="22644-173">Les littéraux de chaîne sont similaires aux littéraux de chaîne simples dans la plupart des langues : une séquence de caractères Unicode placée entre guillemets doubles `" "` .</span><span class="sxs-lookup"><span data-stu-id="22644-173">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double-quotes `" "`.</span></span>
<span data-ttu-id="22644-174">À l’intérieur d’une chaîne, utilisez la barre oblique inverse `\` pour échapper un caractère de guillemet double ( `\"` ), ou pour insérer une nouvelle ligne ( `\n` ), un retour chariot ( `\r` ) ou un onglet ( `\t` ).</span><span class="sxs-lookup"><span data-stu-id="22644-174">Inside of a string, use the backslash character `\` to escape a double-quote character (`\"`), or to insert a new-line ( `\n` ), a carriage return (`\r`), or a tab (`\t`).</span></span>
<span data-ttu-id="22644-175">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="22644-175">For example:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="22644-176">Chaînes interpolées</span><span class="sxs-lookup"><span data-stu-id="22644-176">Interpolated strings</span></span>

<span data-ttu-id="22644-177">La Q# syntaxe pour les interpolations de chaînes est un sous-ensemble de la syntaxe C#.</span><span class="sxs-lookup"><span data-stu-id="22644-177">The Q# syntax for string interpolations is a subset of the C# syntax.</span></span> <span data-ttu-id="22644-178">Voici les points clés auxquels ils se rapportent Q# :</span><span class="sxs-lookup"><span data-stu-id="22644-178">Following are the key points as they pertain to Q#:</span></span>

* <span data-ttu-id="22644-179">Pour identifier un littéral de chaîne comme chaîne interpolée, préfixez-la du symbole `$`.</span><span class="sxs-lookup"><span data-stu-id="22644-179">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="22644-180">Il ne peut pas y avoir d’espace blanc entre le `$` et le `"` qui démarre un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="22644-180">There can be no white space between the `$` and the `"` that starts a string literal.</span></span>

* <span data-ttu-id="22644-181">L’exemple suivant est un exemple de base [`Message`](xref:microsoft.quantum.intrinsic.message) qui utilise la fonction pour écrire le résultat d’une mesure dans la console, en même temps que d’autres Q# expressions.</span><span class="sxs-lookup"><span data-stu-id="22644-181">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* <span data-ttu-id="22644-182">Toute Q# expression valide peut apparaître dans une chaîne interpolée.</span><span class="sxs-lookup"><span data-stu-id="22644-182">Any valid Q# expression may appear in an interpolated string.</span></span>

* <span data-ttu-id="22644-183">Les expressions à l’intérieur d’une chaîne interpolée suivent la Q# syntaxe, et non la syntaxe C#.</span><span class="sxs-lookup"><span data-stu-id="22644-183">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span> <span data-ttu-id="22644-184">La distinction la plus notable est que Q# ne prend pas en charge les chaînes interpolées textuelles (multiligne).</span><span class="sxs-lookup"><span data-stu-id="22644-184">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>

<span data-ttu-id="22644-185">Pour plus d’informations sur la syntaxe C#, consultez [*chaînes interpolées*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="22644-185">For more details about the C# syntax, see [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>

## <a name="range-expressions"></a><span data-ttu-id="22644-186">Expressions de plage</span><span class="sxs-lookup"><span data-stu-id="22644-186">Range Expressions</span></span>

<span data-ttu-id="22644-187">Compte tenu des trois `Int` expressions `start` , `step` et `stop` , l’expression `start .. step .. stop` est une expression de plage dont le premier élément est `start` , le deuxième élément est, le `start+step` troisième élément est `start+step+step` , et ainsi de suite, jusqu’à ce que vous passiez `stop` .</span><span class="sxs-lookup"><span data-stu-id="22644-187">Given any three `Int` expressions `start`, `step`, and `stop`, the expression `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, and so on, until you pass `stop`.</span></span>
<span data-ttu-id="22644-188">Une plage peut être vide si, par exemple, `step` est positif et `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="22644-188">A range may be empty if, for example, `step` is positive and `stop < start`.</span></span>

<span data-ttu-id="22644-189">La plage est comprise entre les deux extrémités.</span><span class="sxs-lookup"><span data-stu-id="22644-189">The range is inclusive at both ends.</span></span> <span data-ttu-id="22644-190">Autrement dit, si la différence entre `start` et `stop` est un entier multiple de `step` , le dernier élément de la plage est `stop` .</span><span class="sxs-lookup"><span data-stu-id="22644-190">That is, if the difference between `start` and `stop` is an integer multiple of `step`, the last element of the range will be `stop`.</span></span>

<span data-ttu-id="22644-191">Compte tenu des deux `Int` expressions `start` et `stop` , l’expression `start .. stop` est une expression de plage qui est égale à `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="22644-191">Given any two `Int` expressions `start` and `stop`, the expression `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="22644-192">Notez que le implicite `step` est + 1 même si `stop` est inférieur à `start` ; dans ce cas, la plage est vide.</span><span class="sxs-lookup"><span data-stu-id="22644-192">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="22644-193">Voici quelques exemples de plages :</span><span class="sxs-lookup"><span data-stu-id="22644-193">Some example ranges are:</span></span>

- <span data-ttu-id="22644-194">`1..3` est la plage 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="22644-194">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="22644-195">`2..2..5` est la plage 2, 4.</span><span class="sxs-lookup"><span data-stu-id="22644-195">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="22644-196">`2..2..6` est la plage 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="22644-196">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="22644-197">`6..-2..2` est la plage 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="22644-197">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="22644-198">`2..1` est la plage vide.</span><span class="sxs-lookup"><span data-stu-id="22644-198">`2..1` is the empty range.</span></span>
- <span data-ttu-id="22644-199">`2..6..7` est la plage 2.</span><span class="sxs-lookup"><span data-stu-id="22644-199">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="22644-200">`2..2..1` est la plage vide.</span><span class="sxs-lookup"><span data-stu-id="22644-200">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="22644-201">`1..-1..2` est la plage vide.</span><span class="sxs-lookup"><span data-stu-id="22644-201">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="22644-202">Expressions qubit</span><span class="sxs-lookup"><span data-stu-id="22644-202">Qubit Expressions</span></span>

<span data-ttu-id="22644-203">Les seules `Qubit` expressions sont des symboles liés à `Qubit` des valeurs ou à des éléments de tableau de `Qubit` tableaux.</span><span class="sxs-lookup"><span data-stu-id="22644-203">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="22644-204">Il n’existe aucun `Qubit` littéral.</span><span class="sxs-lookup"><span data-stu-id="22644-204">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="22644-205">Expressions Pauli</span><span class="sxs-lookup"><span data-stu-id="22644-205">Pauli Expressions</span></span>

<span data-ttu-id="22644-206">Les quatre `Pauli` valeurs,,, `PauliI` `PauliX` `PauliY` et `PauliZ` , sont toutes des expressions valides `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="22644-206">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="22644-207">À part cela, les seules `Pauli` expressions sont des symboles liés à `Pauli` des valeurs ou à des éléments de tableau de `Pauli` tableaux.</span><span class="sxs-lookup"><span data-stu-id="22644-207">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="22644-208">Expressions de résultat</span><span class="sxs-lookup"><span data-stu-id="22644-208">Result Expressions</span></span>

<span data-ttu-id="22644-209">Les deux `Result` valeurs, `One` et `Zero` , sont des `Result` expressions valides.</span><span class="sxs-lookup"><span data-stu-id="22644-209">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="22644-210">À part cela, les seules `Result` expressions sont des symboles liés à `Result` des valeurs ou à des éléments de tableau de `Result` tableaux.</span><span class="sxs-lookup"><span data-stu-id="22644-210">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="22644-211">En particulier, Notez que `One` n’est pas le même que l’entier `1` et qu’il n’y a pas de conversion directe entre eux.</span><span class="sxs-lookup"><span data-stu-id="22644-211">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="22644-212">Il en va de même pour `Zero` et `0` .</span><span class="sxs-lookup"><span data-stu-id="22644-212">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="22644-213">Expressions de Tuple</span><span class="sxs-lookup"><span data-stu-id="22644-213">Tuple Expressions</span></span>

<span data-ttu-id="22644-214">Un littéral de tuple est une séquence d’expressions d’élément du type approprié, séparées par des virgules, placées entre parenthèses.</span><span class="sxs-lookup"><span data-stu-id="22644-214">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in parentheses.</span></span>
<span data-ttu-id="22644-215">Par exemple, `(1, One)` est une `(Int, Result)` expression.</span><span class="sxs-lookup"><span data-stu-id="22644-215">For example, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="22644-216">À part les littéraux, les seules expressions de tuple sont des symboles liés à des valeurs de tuple, des éléments de tableau de tableaux de tuples et des appels pouvant être appelés qui retournent des tuples.</span><span class="sxs-lookup"><span data-stu-id="22644-216">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="22644-217">Expressions de type défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="22644-217">User-Defined Type Expressions</span></span>

<span data-ttu-id="22644-218">Un littéral d’un type défini par l’utilisateur se compose du nom du type suivi d’un littéral de tuple du type de tuple de base du type.</span><span class="sxs-lookup"><span data-stu-id="22644-218">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="22644-219">Par exemple, si `IntPair` est un type défini par l’utilisateur basé sur `(Int, Int)` , `IntPair(2, 3)` est un littéral valide de ce type.</span><span class="sxs-lookup"><span data-stu-id="22644-219">For example, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` is a valid literal of that type.</span></span>

<span data-ttu-id="22644-220">À part les littéraux, les seules expressions d’un type défini par l’utilisateur sont les symboles liés aux valeurs de ce type, les éléments de tableau des tableaux de ce type et les appels pouvant être appelés qui retournent ce type.</span><span class="sxs-lookup"><span data-stu-id="22644-220">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="22644-221">Désencapsuler les expressions</span><span class="sxs-lookup"><span data-stu-id="22644-221">Unwrap Expressions</span></span>

<span data-ttu-id="22644-222">Dans Q# , l’opérateur Unwrap est un point d’exclamation de fin `!` .</span><span class="sxs-lookup"><span data-stu-id="22644-222">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="22644-223">Par exemple, si `IntPair` est un type défini par l’utilisateur avec le type sous-jacent `(Int, Int)` et qu' `s` il s’agit d’une variable de valeur `IntPair(2, 3)` , `s!` est `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="22644-223">For example, if `IntPair` is a user-defined type with the underlying type `(Int, Int)` and `s` is a variable with value `IntPair(2, 3)`, then `s!` is `(2, 3)`.</span></span>

<span data-ttu-id="22644-224">Pour les types définis par l’utilisateur définis en termes d’autres types définis par l’utilisateur, vous pouvez répéter l’opérateur Unwrap.</span><span class="sxs-lookup"><span data-stu-id="22644-224">For user-defined types defined in terms of other user-defined types, you can repeat the unwrap operator.</span></span> <span data-ttu-id="22644-225">Par exemple, `s!!` indique la valeur doublement désencapsulée de `s` .</span><span class="sxs-lookup"><span data-stu-id="22644-225">For example, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="22644-226">Ainsi, si `WrappedPair` est un type défini par l’utilisateur avec le type sous-jacent `IntPair` , et `t` est une variable avec la valeur `WrappedPair(IntPair(1,2))` , `t!!` est alors `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="22644-226">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` is `(1,2)`.</span></span>

<span data-ttu-id="22644-227">L' `!` opérateur a une priorité plus élevée que tous les autres opérateurs autres que `[]` pour l’indexation et le découpage de tableau.</span><span class="sxs-lookup"><span data-stu-id="22644-227">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="22644-228">`!` et `[]` lient la position. autrement dit, `a[i]![3]` est lu comme `((a[i])!)[3]` : prenez le `i` th élément de `a` , Désencapsulez-le, puis récupérez le troisième élément de la valeur désencapsulée (qui doit être un tableau).</span><span class="sxs-lookup"><span data-stu-id="22644-228">`!` and `[]` bind positionally; that is, `a[i]![3]` is read as `((a[i])!)[3]`: take the `i`th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="22644-229">La priorité de l' `!` opérateur a un impact qui peut ne pas être évident.</span><span class="sxs-lookup"><span data-stu-id="22644-229">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="22644-230">Si une fonction ou une opération retourne une valeur qui est ensuite désencapsulée, l’appel de fonction ou d’opération doit être mis entre parenthèses afin que le tuple d’argument soit lié à l’appel plutôt qu’à la désencapsulation.</span><span class="sxs-lookup"><span data-stu-id="22644-230">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="22644-231">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="22644-231">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="22644-232">Expressions de tableau</span><span class="sxs-lookup"><span data-stu-id="22644-232">Array Expressions</span></span>

<span data-ttu-id="22644-233">Un littéral de tableau est une séquence d’une ou plusieurs expressions d’élément, séparées par des virgules, placées entre crochets `[]` .</span><span class="sxs-lookup"><span data-stu-id="22644-233">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in square brackets `[]`.</span></span>
<span data-ttu-id="22644-234">Tous les éléments doivent être compatibles avec le même type.</span><span class="sxs-lookup"><span data-stu-id="22644-234">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="22644-235">À partir de deux tableaux du même type, utilisez l' `+` opérateur binaire pour former un nouveau tableau qui est la concaténation des deux tableaux.</span><span class="sxs-lookup"><span data-stu-id="22644-235">Given two arrays of the same type, use the binary `+` operator to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="22644-236">Par exemple : `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="22644-236">For example, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="22644-237">Création de tableau</span><span class="sxs-lookup"><span data-stu-id="22644-237">Array Creation</span></span>

<span data-ttu-id="22644-238">À partir d’un type et d’une `Int` expression, utilisez l' `new` opérateur pour allouer un nouveau tableau de la taille donnée.</span><span class="sxs-lookup"><span data-stu-id="22644-238">Given a type and an `Int` expression, use the `new` operator to allocate a new array of the given size.</span></span>
<span data-ttu-id="22644-239">Par exemple, `new Int[i + 1]` alloue un nouveau `Int` tableau avec des `i + 1` éléments.</span><span class="sxs-lookup"><span data-stu-id="22644-239">For example, `new Int[i + 1]` allocates a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="22644-240">Les littéraux de tableaux vides, tels que `[]` , ne sont pas autorisés.</span><span class="sxs-lookup"><span data-stu-id="22644-240">Empty array literals, such as `[]`, are not allowed.</span></span>
<span data-ttu-id="22644-241">Au lieu de cela, vous pouvez créer un tableau de longueur égale à zéro à l’aide de `new T[0]` , où `T` est un espace réservé pour un type approprié.</span><span class="sxs-lookup"><span data-stu-id="22644-241">Instead, you can create an array of length zero by using `new T[0]`, where `T` is a placeholder for a suitable type.</span></span>

<span data-ttu-id="22644-242">Les éléments d’un nouveau tableau sont initialisés à une valeur par défaut dépendante du type.</span><span class="sxs-lookup"><span data-stu-id="22644-242">The elements of a new array initialize to a type-dependent default value.</span></span>
<span data-ttu-id="22644-243">Dans la plupart des cas, il s’agit d’une variante de zéro.</span><span class="sxs-lookup"><span data-stu-id="22644-243">In most cases, this is some variation of zero.</span></span>

<span data-ttu-id="22644-244">Pour qubits et callables, qui sont des références à des entités, il n’existe pas de valeur par défaut raisonnable.</span><span class="sxs-lookup"><span data-stu-id="22644-244">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="22644-245">Par conséquent, pour ces types, la valeur par défaut est une référence non valide que vous ne pouvez pas utiliser sans générer d’erreur d’exécution, similaire à une référence null dans des langages tels que C# ou Java.</span><span class="sxs-lookup"><span data-stu-id="22644-245">Thus, for these types, the default is an invalid reference that you cannot use without causing a runtime error, similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="22644-246">Les tableaux contenant qubits ou callables doivent être initialisés avec des valeurs autres que celles par défaut avant de pouvoir utiliser leurs éléments en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="22644-246">Arrays containing qubits or callables must be initialized with non-default values before you can use their elements safely.</span></span> <span data-ttu-id="22644-247">Pour les routines d’initialisation appropriées, consultez <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="22644-247">For suitable initialization routines, see <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="22644-248">Les valeurs par défaut pour chaque type sont :</span><span class="sxs-lookup"><span data-stu-id="22644-248">The default values for each type are:</span></span>

<span data-ttu-id="22644-249">Type</span><span class="sxs-lookup"><span data-stu-id="22644-249">Type</span></span> | <span data-ttu-id="22644-250">Default</span><span class="sxs-lookup"><span data-stu-id="22644-250">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="22644-251">_qubit non valide_</span><span class="sxs-lookup"><span data-stu-id="22644-251">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="22644-252">La plage vide, `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="22644-252">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="22644-253">_appelable non valide_</span><span class="sxs-lookup"><span data-stu-id="22644-253">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="22644-254">Les types Tuple initialisent élément par élément.</span><span class="sxs-lookup"><span data-stu-id="22644-254">Tuple types initialize element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="22644-255">Éléments de tableau</span><span class="sxs-lookup"><span data-stu-id="22644-255">Array Elements</span></span>

<span data-ttu-id="22644-256">À partir d’une expression de tableau et d’une `Int` expression, forment une nouvelle expression à l’aide de l’opérateur d’élément de tableau `[]` .</span><span class="sxs-lookup"><span data-stu-id="22644-256">Given an array expression and an `Int` expression, form a new expression using the array element operator `[]`.</span></span>
<span data-ttu-id="22644-257">La nouvelle expression est du même type que le type d’élément du tableau.</span><span class="sxs-lookup"><span data-stu-id="22644-257">The new expression is the same type as the element type of the array.</span></span>
<span data-ttu-id="22644-258">Par exemple, si `a` est lié à un tableau de type `Double` , `a[4]` est une `Double` expression.</span><span class="sxs-lookup"><span data-stu-id="22644-258">For example, if `a` is bound to an array of type `Double`, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="22644-259">Si l’expression de tableau n’est pas un identificateur simple, vous devez la placer entre parenthèses pour sélectionner un élément.</span><span class="sxs-lookup"><span data-stu-id="22644-259">If the array expression is not a simple identifier, you must enclose it in parentheses to select an element.</span></span>
<span data-ttu-id="22644-260">Par exemple, si `a` et `b` sont tous deux des tableaux de type `Int` , un élément de la concaténation est exprimé comme suit :</span><span class="sxs-lookup"><span data-stu-id="22644-260">For example, if `a` and `b` are both arrays of type `Int`, an element from the concatenation is expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="22644-261">Tous les tableaux dans Q# sont de base zéro.</span><span class="sxs-lookup"><span data-stu-id="22644-261">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="22644-262">Autrement dit, le premier élément d’un tableau `a` est toujours `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="22644-262">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="22644-263">Tranches de tableau</span><span class="sxs-lookup"><span data-stu-id="22644-263">Array Slices</span></span>

<span data-ttu-id="22644-264">À partir d’une expression de tableau et d’une `Range` expression, forment une nouvelle expression à l’aide de l’opérateur de tranche de tableau `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="22644-264">Given an array expression and a `Range` expression, form a new expression using the array slice operator `[ ]`.</span></span>
<span data-ttu-id="22644-265">La nouvelle expression est du même type que le tableau et contient les éléments de tableau indexés par les éléments de `Range` , dans l’ordre défini par le `Range` .</span><span class="sxs-lookup"><span data-stu-id="22644-265">The new expression is the same type as the array and contains the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="22644-266">Par exemple, si `a` est lié à un tableau de type `Double` , `a[3..-1..0]` est une `Double[]` expression qui contient les quatre premiers éléments de, `a` mais dans l’ordre inverse, tels qu’ils apparaissent dans `a` .</span><span class="sxs-lookup"><span data-stu-id="22644-266">For example, if `a` is bound to an array of type `Double`, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="22644-267">Si `Range` est vide, la tranche de tableau résultante a une longueur de zéro.</span><span class="sxs-lookup"><span data-stu-id="22644-267">If the `Range` is empty, then the resulting array slice is zero length.</span></span>

<span data-ttu-id="22644-268">Tout comme pour le référencement d’éléments de tableau, si l’expression de tableau n’est pas un identificateur simple, vous devez la placer entre parenthèses pour la découper.</span><span class="sxs-lookup"><span data-stu-id="22644-268">Just as with referencing array elements, if the array expression is not a simple identifier, you must enclose it in parentheses to slice it.</span></span>
<span data-ttu-id="22644-269">Par exemple, si `a` et `b` sont tous deux des tableaux de type `Int` , un segment de la concaténation est exprimé comme suit :</span><span class="sxs-lookup"><span data-stu-id="22644-269">For example, if `a` and `b` are both arrays of type `Int`, a slice from the concatenation is expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="22644-270">Valeurs de début/fin déduites</span><span class="sxs-lookup"><span data-stu-id="22644-270">Inferred start/end values</span></span>

<span data-ttu-id="22644-271">À partir de notre [version 0,8](xref:microsoft.quantum.relnotes), nous prenons en charge les expressions contextuelles pour le découpage de plage.</span><span class="sxs-lookup"><span data-stu-id="22644-271">Starting with our [0.8 release](xref:microsoft.quantum.relnotes), we support contextual expressions for range slicing.</span></span> <span data-ttu-id="22644-272">En particulier, vous pouvez omettre les valeurs de début et de fin de plage dans le contexte d’une expression de découpage de plage.</span><span class="sxs-lookup"><span data-stu-id="22644-272">In particular, you may omit range start and end values in the context of a range slicing expression.</span></span> <span data-ttu-id="22644-273">Dans ce cas, le compilateur applique les règles suivantes pour déduire les délimiteurs prévus pour la plage :</span><span class="sxs-lookup"><span data-stu-id="22644-273">In that case, the compiler applies the following rules to infer the intended delimiters for the range:</span></span>

* <span data-ttu-id="22644-274">Si la valeur de *début* de la plage est omise, la valeur de début déduite</span><span class="sxs-lookup"><span data-stu-id="22644-274">If the range *start* value is omitted, then the inferred start value</span></span>
  * <span data-ttu-id="22644-275">est égal à zéro si aucune étape n’est spécifiée ou si l’étape spécifiée est positive.</span><span class="sxs-lookup"><span data-stu-id="22644-275">is zero if no step is specified or the specified step is positive.</span></span>  
  * <span data-ttu-id="22644-276">longueur du tableau découpé moins un si l’étape spécifiée est négative.</span><span class="sxs-lookup"><span data-stu-id="22644-276">is the length of the sliced array minus one if the specified step is negative.</span></span>

* <span data-ttu-id="22644-277">Si la valeur de *fin* de la plage est omise, la valeur de fin déduite</span><span class="sxs-lookup"><span data-stu-id="22644-277">If the range *end* value is omitted, then the inferred end value</span></span>
  * <span data-ttu-id="22644-278">longueur du tableau découpé moins un si aucune étape n’est spécifiée ou si l’étape spécifiée est positive.</span><span class="sxs-lookup"><span data-stu-id="22644-278">is the length of the sliced array minus one if no step is specified or the specified step is positive.</span></span>
  * <span data-ttu-id="22644-279">est égal à zéro si l’étape spécifiée est négative.</span><span class="sxs-lookup"><span data-stu-id="22644-279">is zero if the specified step is negative.</span></span>

<span data-ttu-id="22644-280">Quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="22644-280">Some examples are:</span></span>

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

### <a name="copy-and-update-expressions"></a><span data-ttu-id="22644-281">Expressions de copie et de mise à jour</span><span class="sxs-lookup"><span data-stu-id="22644-281">Copy-and-Update Expressions</span></span>

<span data-ttu-id="22644-282">Étant donné que tous les Q# types sont des types valeur (avec le qubits qui prend un rôle un peu spécial), une « copie » est formellement créée lorsqu’une valeur est liée à un symbole ou lorsqu’un symbole est relié.</span><span class="sxs-lookup"><span data-stu-id="22644-282">Since all Q# types are value types (with the qubits taking a somewhat special role), formally a "copy" is created when a value is bound to a symbol or when a symbol is rebound.</span></span> <span data-ttu-id="22644-283">Autrement dit, le comportement de Q# est le même que si une copie a été créée à l’aide d’un opérateur d’assignation.</span><span class="sxs-lookup"><span data-stu-id="22644-283">That is to say, the behavior of Q# is the same as if a copy were created using an assignment operator.</span></span> 

<span data-ttu-id="22644-284">Bien entendu, dans la pratique, seuls les éléments pertinents sont recréés en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="22644-284">Of course, in practice, only the relevant pieces are recreated as needed.</span></span> <span data-ttu-id="22644-285">Cela affecte la façon dont vous copiez les tableaux, car il n’est pas possible de mettre à jour les éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="22644-285">This affects how you copy arrays because it is not possible to update array items.</span></span> <span data-ttu-id="22644-286">La modification d’un tableau existant requiert l’utilisation d’un mécanisme de *copie et de mise à jour* .</span><span class="sxs-lookup"><span data-stu-id="22644-286">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="22644-287">Vous pouvez créer un nouveau tableau à partir d’un tableau existant à l’aide d’expressions de *copie et de mise à jour* , qui utilisent les opérateurs `w/` et `<-` .</span><span class="sxs-lookup"><span data-stu-id="22644-287">You can create a new array from an existing array via *copy-and-update* expressions, which use the operators `w/` and `<-`.</span></span>
<span data-ttu-id="22644-288">Une expression de copie et de mise à jour est une expression de la forme `expression1 w/ expression2 <- expression3` , où</span><span class="sxs-lookup"><span data-stu-id="22644-288">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where</span></span>

* <span data-ttu-id="22644-289">`expression1` doit être `T[]` de type pour un certain type `T` .</span><span class="sxs-lookup"><span data-stu-id="22644-289">`expression1` must be type `T[]` for some type `T`.</span></span>
* <span data-ttu-id="22644-290">`expression2` définit les index dans le tableau spécifié dans `expression1` à modifier.</span><span class="sxs-lookup"><span data-stu-id="22644-290">`expression2` defines which indices in the array specified in `expression1` to modify.</span></span> <span data-ttu-id="22644-291">`expression2` doit être de type `Int` ou `Range` .</span><span class="sxs-lookup"><span data-stu-id="22644-291">`expression2` must be either type `Int` or type `Range`.</span></span>
* <span data-ttu-id="22644-292">`expression3` valeur (s) utilisée (s) pour mettre à jour les éléments dans `expression1` , en fonction des index spécifiés dans `expression2` .</span><span class="sxs-lookup"><span data-stu-id="22644-292">`expression3` is the value(s) used to update elements in `expression1`, based on the indices specified in `expression2`.</span></span> <span data-ttu-id="22644-293">Si `expression2` est `Int` de type, `expression3` doit être de type `T` .</span><span class="sxs-lookup"><span data-stu-id="22644-293">If `expression2` is type `Int`, `expression3` must be type `T`.</span></span> <span data-ttu-id="22644-294">Si `expression2` est `Range` de type, `expression3` doit être de type `T[]` .</span><span class="sxs-lookup"><span data-stu-id="22644-294">If `expression2` is type `Range`, `expression3` must be type `T[]`.</span></span>

<span data-ttu-id="22644-295">Par exemple, l’expression copy-and-Update `arr w/ idx <- value` construit un nouveau tableau avec tous les éléments définis sur les éléments correspondants dans `arr` , à l’exception des éléments spécifiés par `idx` , qui est défini sur la ou les valeurs dans `value` .</span><span class="sxs-lookup"><span data-stu-id="22644-295">For example, the copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding elements in `arr`, except for the element(s) specified by `idx`, which is set to the value(s) in `value`.</span></span> 

<span data-ttu-id="22644-296">Indiqué `arr` contient le tableau `[0,1,2,3]` , puis</span><span class="sxs-lookup"><span data-stu-id="22644-296">Given `arr` contains the array `[0,1,2,3]`, then</span></span> 

- <span data-ttu-id="22644-297">`arr w/ 0 <- 10` est le tableau `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="22644-297">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="22644-298">`arr w/ 2 <- 10` est le tableau `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="22644-298">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="22644-299">`arr w/ 0..2..3 <- [10,12]` est le tableau `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="22644-299">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="22644-300">Expressions de copie et de mise à jour pour les éléments nommés</span><span class="sxs-lookup"><span data-stu-id="22644-300">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="22644-301">Des expressions similaires existent pour les éléments nommés dans les types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="22644-301">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="22644-302">Par exemple, considérez le type</span><span class="sxs-lookup"><span data-stu-id="22644-302">For example, consider the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="22644-303">Si `c` contient la valeur de type `Complex(1., -1.)` , `c w/ Re <- 0.` est une expression de type qui prend la valeur `Complex` `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="22644-303">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="22644-304">Tableaux en escalier</span><span class="sxs-lookup"><span data-stu-id="22644-304">Jagged Arrays</span></span>

<span data-ttu-id="22644-305">Un tableau en escalier, parfois appelé « tableau de tableaux », est un tableau dont les éléments sont des tableaux.</span><span class="sxs-lookup"><span data-stu-id="22644-305">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="22644-306">Les éléments d’un tableau en escalier peuvent être de différentes tailles.</span><span class="sxs-lookup"><span data-stu-id="22644-306">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="22644-307">L’exemple suivant montre comment déclarer et initialiser un tableau en escalier représentant une table de multiplication.</span><span class="sxs-lookup"><span data-stu-id="22644-307">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {
    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```

### <a name="arrays-of-callables"></a><span data-ttu-id="22644-308">Tableaux de callables</span><span class="sxs-lookup"><span data-stu-id="22644-308">Arrays of callables</span></span> 

<span data-ttu-id="22644-309">Vous pouvez également créer un tableau de callables.</span><span class="sxs-lookup"><span data-stu-id="22644-309">You can also create an array of callables.</span></span>

* <span data-ttu-id="22644-310">Si le type d’élément commun est un type d’opération ou de fonction, tous les éléments doivent avoir les mêmes types d’entrée et de sortie.</span><span class="sxs-lookup"><span data-stu-id="22644-310">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
* <span data-ttu-id="22644-311">Le type d’élément du tableau prend en charge tous les [functors](xref:microsoft.quantum.guide.operationsfunctions) pris en charge par tous les éléments.</span><span class="sxs-lookup"><span data-stu-id="22644-311">The element type of the array supports any [functors](xref:microsoft.quantum.guide.operationsfunctions) that are supported by all of the elements.</span></span>
<span data-ttu-id="22644-312">Par exemple, si `Op1` , `Op2` et `Op3` sont tous des `Qubit[] => Unit` opérations, mais `Op1` prend en charge `Adjoint` , `Op2` prend en charge `Controlled` et `Op3` prend en charge les deux :</span><span class="sxs-lookup"><span data-stu-id="22644-312">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit` operations, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>
  * <span data-ttu-id="22644-313">`[Op1, Op2]` est un tableau d' `(Qubit[] => Unit)` opérations.</span><span class="sxs-lookup"><span data-stu-id="22644-313">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
  * <span data-ttu-id="22644-314">`[Op1, Op3]` est un tableau d' `(Qubit[] => Unit is Adj)` opérations.</span><span class="sxs-lookup"><span data-stu-id="22644-314">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
  * <span data-ttu-id="22644-315">`[Op2, Op3]` est un tableau d' `(Qubit[] => Unit is Ctl)` opérations.</span><span class="sxs-lookup"><span data-stu-id="22644-315">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="22644-316">Toutefois, alors que les opérations `(Qubit[] => Unit is Adj)` et  `(Qubit[] => Unit is Ctl)` ont le type de base commun de `(Qubit[] => Unit)` , les *tableaux* de ces opérations ne partagent pas un type de base commun.</span><span class="sxs-lookup"><span data-stu-id="22644-316">However, while the operations `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` have the common base type of `(Qubit[] => Unit)`, *arrays* of these operations do not share a common base type.</span></span>

<span data-ttu-id="22644-317">Par exemple, `[[Op1], [Op2]]` génère actuellement une erreur, car elle tente de créer un tableau des deux types de tableau incompatibles `(Qubit[] => Unit is Adj)[]` et `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="22644-317">For example, `[[Op1], [Op2]]` would currently raise an error because it attempts to create an array of the two incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>

<span data-ttu-id="22644-318">Pour plus d’informations sur callables, consultez [expressions pouvant être appelées](#callable-expressions) sur cette page ou [opérations Q# et fonctions dans ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="22644-318">For more information on callables, see [Callable expressions](#callable-expressions)  on this page or [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="22644-319">Expressions conditionnelles</span><span class="sxs-lookup"><span data-stu-id="22644-319">Conditional Expressions</span></span>

<span data-ttu-id="22644-320">À partir de deux expressions du même type et d’une expression booléenne, forment une expression conditionnelle à l’aide du point d’interrogation, de `?` et de la barre verticale `|` .</span><span class="sxs-lookup"><span data-stu-id="22644-320">Given two expressions of the same type and a Boolean expression, form a conditional expression using the question mark, `?`, and the vertical bar `|`.</span></span> <span data-ttu-id="22644-321">Indiqué `a==b ? c | d` , la valeur de l’expression conditionnelle est `c` si `a==b` a la valeur true et `d` si elle est false.</span><span class="sxs-lookup"><span data-stu-id="22644-321">Given `a==b ? c | d`, the value of the conditional expression is `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="22644-322">Expressions conditionnelles avec callables</span><span class="sxs-lookup"><span data-stu-id="22644-322">Conditional expressions with callables</span></span>

<span data-ttu-id="22644-323">Les expressions conditionnelles peuvent correspondre à des opérations qui ont les mêmes entrées et sorties, mais prennent en charge différents functors.</span><span class="sxs-lookup"><span data-stu-id="22644-323">Conditional expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span> <span data-ttu-id="22644-324">Dans ce cas, le type de l’expression conditionnelle est une opération avec des entrées et des sorties qui prennent en charge tous les functors pris en charge par les deux expressions.</span><span class="sxs-lookup"><span data-stu-id="22644-324">In this case, the type of the conditional expression is an operation with inputs and outputs that support any functors supported by both expressions.</span></span>
<span data-ttu-id="22644-325">Par exemple, si `Op1` , `Op2` et `Op3` sont tous des `Qubit[]=>Unit` , mais prend en charge, prend en charge `Op1` `Adjoint` `Op2` `Controlled` et `Op3` prend en charge les deux :</span><span class="sxs-lookup"><span data-stu-id="22644-325">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="22644-326">`flag ? Op1 | Op2` est une `(Qubit[] => Unit)` opération.</span><span class="sxs-lookup"><span data-stu-id="22644-326">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="22644-327">`flag ? Op1 | Op3` est une `(Qubit[] => Unit is Adj)` opération.</span><span class="sxs-lookup"><span data-stu-id="22644-327">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="22644-328">`flag ? Op2 | Op3` est une `(Qubit[] => Unit is Ctl)` opération.</span><span class="sxs-lookup"><span data-stu-id="22644-328">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="22644-329">Si l’une des deux expressions de résultat possibles inclut une fonction ou un appel d’opération, cet appel a lieu uniquement si le résultat est celui qui correspond à la valeur de l’appel.</span><span class="sxs-lookup"><span data-stu-id="22644-329">If either of the two possible result expressions include a function or operation call, that call only takes place if that result is the one that is the value of the call.</span></span> <span data-ttu-id="22644-330">Par exemple, dans le cas `a==b ? C(qs) | D(qs)` , si `a==b` a la valeur true, l' `C` opération est appelée, et si elle a la valeur false, seule l' `D` opération est appelée.</span><span class="sxs-lookup"><span data-stu-id="22644-330">For example, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true, then the `C` operation is invoked, and if it is false then only the `D` operation is invoked.</span></span> <span data-ttu-id="22644-331">Cette approche est similaire à *un court-circuit* dans d’autres langages.</span><span class="sxs-lookup"><span data-stu-id="22644-331">This approach is similar to *short-circuiting* in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="22644-332">Expressions pouvant être appelées</span><span class="sxs-lookup"><span data-stu-id="22644-332">Callable Expressions</span></span>

<span data-ttu-id="22644-333">Un littéral pouvant être appelé est le nom d’une opération ou d’une fonction définie dans la portée de compilation.</span><span class="sxs-lookup"><span data-stu-id="22644-333">A callable literal is the name of an operation or function defined in the compilation scope.</span></span> <span data-ttu-id="22644-334">Par exemple, `X` est un littéral d’opération qui fait référence à l’opération de bibliothèque standard `X` , et `Message` est un littéral de fonction qui fait référence à la fonction de bibliothèque standard `Message` .</span><span class="sxs-lookup"><span data-stu-id="22644-334">For example, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="22644-335">Si une opération prend en charge `Adjoint` functor, `Adjoint op` est une expression d’opération.</span><span class="sxs-lookup"><span data-stu-id="22644-335">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="22644-336">De même, si l’opération prend en charge `Controlled` functor, `Controlled op` est une expression d’opération.</span><span class="sxs-lookup"><span data-stu-id="22644-336">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="22644-337">Pour plus d’informations sur les types de ces expressions, consultez [appel des spécialisations d’opérations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="22644-337">For more information about the types of these expressions, see [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="22644-338">Les functors ( `Adjoint` et `Controlled` ) lient plus étroitement que tous les autres opérateurs, à l’exception de l’opérateur Unwrap et de l' `!` indexation de tableau avec `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="22644-338">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[ ]`.</span></span>
<span data-ttu-id="22644-339">Par conséquent, les éléments suivants sont tous valides, en supposant que les opérations prennent en charge les functors utilisés :</span><span class="sxs-lookup"><span data-stu-id="22644-339">Thus, the following are all valid, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="22644-340">Expressions pouvant être appelées par type paramétrable</span><span class="sxs-lookup"><span data-stu-id="22644-340">Type-parameterized callable expressions</span></span>

<span data-ttu-id="22644-341">Vous pouvez utiliser un littéral pouvant être appelé comme valeur, par exemple, pour l’assigner à une variable ou le passer à un autre pouvant être appelé.</span><span class="sxs-lookup"><span data-stu-id="22644-341">You can use a callable literal as a value, for example, to assign it to a variable or pass it to another callable.</span></span> <span data-ttu-id="22644-342">Dans ce cas, si l’élément pouvant être appelé a des [paramètres de type](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), vous devez fournir les paramètres dans le cadre de la valeur pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="22644-342">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), you must provide the parameters as part of the callable value.</span></span>

<span data-ttu-id="22644-343">Une valeur pouvant être appelée ne peut pas avoir de paramètres de type non spécifiés.</span><span class="sxs-lookup"><span data-stu-id="22644-343">A callable value cannot have any unspecified type parameters.</span></span> <span data-ttu-id="22644-344">Par exemple, si `Fun` est une fonction avec la signature `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="22644-344">For example, if `Fun` is a function with the signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="22644-345">Expressions d’appel pouvant être appelées</span><span class="sxs-lookup"><span data-stu-id="22644-345">Callable Invocation Expressions</span></span>

<span data-ttu-id="22644-346">À partir d’une expression pouvant être appelée (opération ou fonction) et d’une expression de tuple du type d’entrée de la signature de l’appel, vous pouvez former une *expression* d’appel en ajoutant l’expression de tuple à l’expression pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="22644-346">Given a callable expression (operation or function) and a tuple expression of the input type of the callable's signature, you can form an *invocation expression* by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="22644-347">Le type de l’expression d’appel est le type de sortie de la signature de l’appelable.</span><span class="sxs-lookup"><span data-stu-id="22644-347">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="22644-348">Par exemple, si `Op` est une opération avec la signature `((Int, Qubit) => Double)` , `Op(3, qubit1)` est une expression de type `Double` .</span><span class="sxs-lookup"><span data-stu-id="22644-348">For example, if `Op` is an operation with the signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="22644-349">De même, si `Sin` est une fonction avec la signature `(Double -> Double)` , `Sin(0.1)` est une expression de type `Double` .</span><span class="sxs-lookup"><span data-stu-id="22644-349">Similarly, if `Sin` is a function with the signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="22644-350">Enfin, si `Builder` est une fonction avec la signature `(Int -> (Int -> Int))` , `Builder(3)` est une fonction de `Int` à `Int` .</span><span class="sxs-lookup"><span data-stu-id="22644-350">Finally, if `Builder` is a function with the signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from `Int` to `Int`.</span></span>

<span data-ttu-id="22644-351">L’appel du résultat d’une expression de valeur pouvant être appelée nécessite une paire de parenthèses supplémentaires autour de l’expression pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="22644-351">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="22644-352">Ainsi, pour appeler le résultat de l’appel `Builder` à partir du paragraphe précédent, la syntaxe correcte est la suivante :</span><span class="sxs-lookup"><span data-stu-id="22644-352">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="22644-353">Lors de l’appel d’un pouvant être appelé [par un type paramétrable](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , vous pouvez spécifier les paramètres de type réels entre crochets pointus `< >` après l’expression pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="22644-353">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, you can specify the actual type parameters within angle brackets `< >` after the callable expression.</span></span>
<span data-ttu-id="22644-354">Cette action n’est généralement pas nécessaire, car le Q# compilateur déduit les types réels.</span><span class="sxs-lookup"><span data-stu-id="22644-354">This action is usually unnecessary as the Q# compiler infers the actual types.</span></span>
<span data-ttu-id="22644-355">Toutefois, elle *est* requise pour une [application partielle](xref:microsoft.quantum.guide.operationsfunctions#partial-application) si un argument de type paramétrable n’est pas spécifié.</span><span class="sxs-lookup"><span data-stu-id="22644-355">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="22644-356">Elle est également utile lors du passage d’opérations avec des prises en charge de functor différentes à un pouvant être appelé.</span><span class="sxs-lookup"><span data-stu-id="22644-356">It is also useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="22644-357">Par exemple, si `Func` a une signature, et possède la signature `('T1, 'T2, 'T1) -> 'T2` et la `Op1` `Op2` `(Qubit[] => Unit is Adj)` `Op3` signature `(Qubit[] => Unit)` , pour appeler en `Func` `Op1` tant que premier argument `Op2` , comme deuxième argument, et `Op3` comme troisième :</span><span class="sxs-lookup"><span data-stu-id="22644-357">For example, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="22644-358">La spécification de type est requise, car `Op3` et `Op1` ont des types différents, de sorte que le compilateur traite cette opération comme ambiguë sans la spécification.</span><span class="sxs-lookup"><span data-stu-id="22644-358">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="22644-359">Priorité des opérateurs</span><span class="sxs-lookup"><span data-stu-id="22644-359">Operator Precedence</span></span>

* <span data-ttu-id="22644-360">Tous les opérateurs binaires sont associatifs à droite, à l’exception de `^` .</span><span class="sxs-lookup"><span data-stu-id="22644-360">All binary operators are right-associative, except for `^`.</span></span>

* <span data-ttu-id="22644-361">Les crochets, `[ ]` , pour le découpage et l’indexation de tableaux, sont liés avant tout opérateur.</span><span class="sxs-lookup"><span data-stu-id="22644-361">Brackets, `[ ]`, for array slicing and indexing, bind before any operator.</span></span>

* <span data-ttu-id="22644-362">Functors `Adjoint` et `Controlled` Bind après l’indexation de tableau, mais avant tous les autres opérateurs.</span><span class="sxs-lookup"><span data-stu-id="22644-362">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

* <span data-ttu-id="22644-363">Les parenthèses pour l’appel de l’opération et de la fonction sont également liées avant tout opérateur, mais après l’indexation et les functors du tableau.</span><span class="sxs-lookup"><span data-stu-id="22644-363">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="22644-364">Q# opérateurs par ordre de priorité, du plus élevé au plus bas :</span><span class="sxs-lookup"><span data-stu-id="22644-364">Q# operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="22644-365">Opérateur</span><span class="sxs-lookup"><span data-stu-id="22644-365">Operator</span></span> | <span data-ttu-id="22644-366">Arité</span><span class="sxs-lookup"><span data-stu-id="22644-366">Arity</span></span> | <span data-ttu-id="22644-367">Description</span><span class="sxs-lookup"><span data-stu-id="22644-367">Description</span></span> | <span data-ttu-id="22644-368">Types d’opérandes</span><span class="sxs-lookup"><span data-stu-id="22644-368">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="22644-369">fin `!`</span><span class="sxs-lookup"><span data-stu-id="22644-369">trailing `!`</span></span> | <span data-ttu-id="22644-370">Unaire</span><span class="sxs-lookup"><span data-stu-id="22644-370">Unary</span></span> | <span data-ttu-id="22644-371">Désencapsuler</span><span class="sxs-lookup"><span data-stu-id="22644-371">Unwrap</span></span> | <span data-ttu-id="22644-372">Tout type défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="22644-372">Any user-defined type</span></span>
 <span data-ttu-id="22644-373">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="22644-373">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="22644-374">Unaire</span><span class="sxs-lookup"><span data-stu-id="22644-374">Unary</span></span> | <span data-ttu-id="22644-375">Valeur numérique négative, complément au niveau du bit, négation logique</span><span class="sxs-lookup"><span data-stu-id="22644-375">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="22644-376">`Int`, `BigInt` ou pour, `Double` ou pour `-` `Int` `BigInt` `~~~` , `Bool` pour `not`</span><span class="sxs-lookup"><span data-stu-id="22644-376">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="22644-377">Binary</span><span class="sxs-lookup"><span data-stu-id="22644-377">Binary</span></span> | <span data-ttu-id="22644-378">Puissance entière</span><span class="sxs-lookup"><span data-stu-id="22644-378">Integer power</span></span> | <span data-ttu-id="22644-379">`Int` ou `BigInt` pour la base, `Int` pour l’exposant</span><span class="sxs-lookup"><span data-stu-id="22644-379">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="22644-380">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="22644-380">`/`, `*`, `%`</span></span> | <span data-ttu-id="22644-381">Binary</span><span class="sxs-lookup"><span data-stu-id="22644-381">Binary</span></span> | <span data-ttu-id="22644-382">Division, multiplication, modulo entier</span><span class="sxs-lookup"><span data-stu-id="22644-382">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="22644-383">`Int`, `BigInt` ou `Double` pour `/` et `*` , `Int` ou `BigInt` pour `%`</span><span class="sxs-lookup"><span data-stu-id="22644-383">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="22644-384">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="22644-384">`+`, `-`</span></span> | <span data-ttu-id="22644-385">Binary</span><span class="sxs-lookup"><span data-stu-id="22644-385">Binary</span></span> | <span data-ttu-id="22644-386">Addition ou concaténation de chaînes et de tableaux, soustraction</span><span class="sxs-lookup"><span data-stu-id="22644-386">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="22644-387">`Int`, `BigInt` ou `Double` , en plus `String` ou n’importe quel type de tableau pour `+`</span><span class="sxs-lookup"><span data-stu-id="22644-387">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="22644-388">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="22644-388">`<<<`, `>>>`</span></span> | <span data-ttu-id="22644-389">Binary</span><span class="sxs-lookup"><span data-stu-id="22644-389">Binary</span></span> | <span data-ttu-id="22644-390">Décalage vers la gauche, décalage vers la droite</span><span class="sxs-lookup"><span data-stu-id="22644-390">Left shift, right shift</span></span> | <span data-ttu-id="22644-391">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="22644-391">`Int` or `BigInt`</span></span>
 <span data-ttu-id="22644-392">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="22644-392">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="22644-393">Binary</span><span class="sxs-lookup"><span data-stu-id="22644-393">Binary</span></span> | <span data-ttu-id="22644-394">Comparaisons « inférieur à », « inférieur à », « supérieur à », « supérieur à » ou « égal à »</span><span class="sxs-lookup"><span data-stu-id="22644-394">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="22644-395">`Int`, `BigInt` ou `Double`</span><span class="sxs-lookup"><span data-stu-id="22644-395">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="22644-396">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="22644-396">`==`, `!=`</span></span> | <span data-ttu-id="22644-397">Binary</span><span class="sxs-lookup"><span data-stu-id="22644-397">Binary</span></span> | <span data-ttu-id="22644-398">comparaisons égales et non égales</span><span class="sxs-lookup"><span data-stu-id="22644-398">equal, not-equal comparisons</span></span> | <span data-ttu-id="22644-399">tout type primitif</span><span class="sxs-lookup"><span data-stu-id="22644-399">any primitive type</span></span>
 `&&&` | <span data-ttu-id="22644-400">Binary</span><span class="sxs-lookup"><span data-stu-id="22644-400">Binary</span></span> | <span data-ttu-id="22644-401">ET au niveau du bit</span><span class="sxs-lookup"><span data-stu-id="22644-401">Bitwise AND</span></span> | <span data-ttu-id="22644-402">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="22644-402">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="22644-403">Binary</span><span class="sxs-lookup"><span data-stu-id="22644-403">Binary</span></span> | <span data-ttu-id="22644-404">Opération de bits XOR</span><span class="sxs-lookup"><span data-stu-id="22644-404">Bitwise XOR</span></span> | <span data-ttu-id="22644-405">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="22644-405">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="22644-406">Binary</span><span class="sxs-lookup"><span data-stu-id="22644-406">Binary</span></span> | <span data-ttu-id="22644-407">Opération de bits OR</span><span class="sxs-lookup"><span data-stu-id="22644-407">Bitwise OR</span></span> | <span data-ttu-id="22644-408">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="22644-408">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="22644-409">Binary</span><span class="sxs-lookup"><span data-stu-id="22644-409">Binary</span></span> | <span data-ttu-id="22644-410">ET logique</span><span class="sxs-lookup"><span data-stu-id="22644-410">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="22644-411">Binary</span><span class="sxs-lookup"><span data-stu-id="22644-411">Binary</span></span> | <span data-ttu-id="22644-412">OU logique</span><span class="sxs-lookup"><span data-stu-id="22644-412">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="22644-413">Binaire/ternaire</span><span class="sxs-lookup"><span data-stu-id="22644-413">Binary/Ternary</span></span> | <span data-ttu-id="22644-414">Opérateur de plage</span><span class="sxs-lookup"><span data-stu-id="22644-414">Range operator</span></span> | `Int`
 <span data-ttu-id="22644-415">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="22644-415">`?` `|`</span></span> | <span data-ttu-id="22644-416">Gradient</span><span class="sxs-lookup"><span data-stu-id="22644-416">Ternary</span></span> | <span data-ttu-id="22644-417">Logique conditionnelle</span><span class="sxs-lookup"><span data-stu-id="22644-417">Conditional</span></span> | <span data-ttu-id="22644-418">`Bool` pour le côté gauche</span><span class="sxs-lookup"><span data-stu-id="22644-418">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="22644-419">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="22644-419">`w/` `<-`</span></span> | <span data-ttu-id="22644-420">Gradient</span><span class="sxs-lookup"><span data-stu-id="22644-420">Ternary</span></span> | <span data-ttu-id="22644-421">Copier et mettre à jour</span><span class="sxs-lookup"><span data-stu-id="22644-421">Copy-and-update</span></span> | <span data-ttu-id="22644-422">Voir les [expressions copy-and-Update](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="22644-422">See [Copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="22644-423">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="22644-423">Next steps</span></span>

<span data-ttu-id="22644-424">Maintenant que vous pouvez utiliser des expressions dans Q# , passez à [ Q# opérations et fonctions dans](xref:microsoft.quantum.guide.operationsfunctions) pour apprendre à définir et appeler des opérations et des fonctions.</span><span class="sxs-lookup"><span data-stu-id="22644-424">Now that you can work with expressions in Q#, move on to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
