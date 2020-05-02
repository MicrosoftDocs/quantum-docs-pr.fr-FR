---
title: 'Expressions Q #'
description: 'Comprendre comment spécifier, référencer et combiner des constantes, des variables, des opérateurs, des opérations et des fonctions en tant qu’expressions dans Q #.'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 095be52af27f827f3e52d39a70702f50d6d59ee8
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82683924"
---
# <a name="expressions"></a><span data-ttu-id="130a4-103">Expressions</span><span class="sxs-lookup"><span data-stu-id="130a4-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="130a4-104">Regroupement</span><span class="sxs-lookup"><span data-stu-id="130a4-104">Grouping</span></span>

<span data-ttu-id="130a4-105">À partir de toute expression, cette même expression entre parenthèses est une expression du même type.</span><span class="sxs-lookup"><span data-stu-id="130a4-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="130a4-106">Par exemple, `(7)` est une `Int` expression, `([1,2,3])` est une expression de type tableau de `Int`s et `((1,2))` est une expression de type `(Int, Int)`.</span><span class="sxs-lookup"><span data-stu-id="130a4-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="130a4-107">L’équivalence entre les valeurs simples et les tuples à un seul élément décrit dans [le modèle de type](xref:microsoft.quantum.language.type-model#tuple-types) supprime l' `(6)` ambiguïté entre en tant `(6)` que groupe et comme tuple à un seul élément.</span><span class="sxs-lookup"><span data-stu-id="130a4-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="130a4-108">Symboles</span><span class="sxs-lookup"><span data-stu-id="130a4-108">Symbols</span></span>

<span data-ttu-id="130a4-109">Le nom d’un symbole lié ou assigné à une valeur de type `'T` est une expression de type `'T`.</span><span class="sxs-lookup"><span data-stu-id="130a4-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="130a4-110">Par exemple, si le symbole `count` est lié à la valeur `5`entière, `count` est une expression d’entier.</span><span class="sxs-lookup"><span data-stu-id="130a4-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="130a4-111">Expressions numériques</span><span class="sxs-lookup"><span data-stu-id="130a4-111">Numeric Expressions</span></span>

<span data-ttu-id="130a4-112">Les expressions numériques sont des expressions `Int`de `BigInt`type, `Double`ou.</span><span class="sxs-lookup"><span data-stu-id="130a4-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="130a4-113">Autrement dit, il s’agit de nombres entiers ou à virgule flottante.</span><span class="sxs-lookup"><span data-stu-id="130a4-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="130a4-114">`Int`les littéraux dans Q # sont identiques aux littéraux entiers en C#, sauf qu’aucun « l » ou « L » de fin n’est requis (ou autorisé).</span><span class="sxs-lookup"><span data-stu-id="130a4-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="130a4-115">Les entiers hexadécimaux et binaires sont pris en charge avec un préfixe « 0x » et « 0b » respectivement.</span><span class="sxs-lookup"><span data-stu-id="130a4-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="130a4-116">`BigInt`les littéraux dans Q # sont identiques aux chaînes d’entiers volumineuses dans .NET, avec un « l » ou « L » de fin.</span><span class="sxs-lookup"><span data-stu-id="130a4-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="130a4-117">Les nombres entiers hexadécimaux sont pris en charge avec un préfixe « 0x ».</span><span class="sxs-lookup"><span data-stu-id="130a4-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="130a4-118">Par conséquent, Voici toutes les utilisations valides `BigInt` des littéraux :</span><span class="sxs-lookup"><span data-stu-id="130a4-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="130a4-119">`Double`les littéraux dans Q # sont identiques aux littéraux doubles en C#, sauf qu’aucun « d » ou « D » de fin n’est requis (ou autorisé).</span><span class="sxs-lookup"><span data-stu-id="130a4-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="130a4-120">À partir d’une expression de tableau de tout type `Int` d’élément, une expression peut `Length` être formée à l’aide de la fonction intégrée, avec l’expression de `(` tableau `)`placée entre parenthèses, et.</span><span class="sxs-lookup"><span data-stu-id="130a4-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="130a4-121">Par exemple, si `a` est lié à un tableau, `Length(a)` est une expression d’entier.</span><span class="sxs-lookup"><span data-stu-id="130a4-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="130a4-122">Si `b` est un tableau de tableaux d’entiers `Int[][]`,, `Length(b)` est le nombre de sous-tableaux dans `b`, et `Length(b[1])` est le nombre d’entiers dans le deuxième sous-tableau de. `b`</span><span class="sxs-lookup"><span data-stu-id="130a4-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="130a4-123">À partir de deux expressions numériques du même type, les opérateurs `+` `-`binaires `*`,, `/` et peuvent être utilisés pour former une nouvelle expression numérique.</span><span class="sxs-lookup"><span data-stu-id="130a4-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="130a4-124">Le type de la nouvelle expression sera le même que les types des expressions constituantes.</span><span class="sxs-lookup"><span data-stu-id="130a4-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="130a4-125">À partir de deux expressions entières, `^` l’opérateur binaire (Power) peut être utilisé pour former une nouvelle expression entière.</span><span class="sxs-lookup"><span data-stu-id="130a4-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="130a4-126">De même, `^` peut être utilisé avec deux expressions double pour former une nouvelle expression double.</span><span class="sxs-lookup"><span data-stu-id="130a4-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="130a4-127">Enfin, `^` peut être utilisé avec un grand entier à gauche et un entier sur la droite pour former une nouvelle expression d’entier Big.</span><span class="sxs-lookup"><span data-stu-id="130a4-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="130a4-128">Dans ce cas, le deuxième paramètre doit être contenu dans 32 bits ; Si ce n’est pas le cas, une erreur d’exécution est générée.</span><span class="sxs-lookup"><span data-stu-id="130a4-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="130a4-129">À partir de deux expressions entières ou d’entiers Big, une nouvelle expression de type entier ou `%` entier Big peut être `&&&` formée à l’aide des `|||` opérateurs (modulo), ( `^^^` opérateur and au niveau du bit), (au niveau du bit or) ou (opérateur de bits XOR).</span><span class="sxs-lookup"><span data-stu-id="130a4-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="130a4-130">En fonction d’une expression d’entier ou d’entier Big à gauche, et d’une expression d’entier à `<<<` droite, les opérateurs (décalage `>>>` arithmétique vers la gauche) ou (décalage à droite) peuvent être utilisés pour créer une nouvelle expression avec le même type que l’expression de gauche.</span><span class="sxs-lookup"><span data-stu-id="130a4-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="130a4-131">Le deuxième paramètre (la valeur de décalage) pour l’opération de décalage doit être supérieur ou égal à zéro ; le comportement des valeurs de décalage négatives n’est pas défini.</span><span class="sxs-lookup"><span data-stu-id="130a4-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="130a4-132">La valeur de décalage pour l’opération de décalage doit également tenir dans 32 bits ; Si ce n’est pas le cas, une erreur d’exécution est générée.</span><span class="sxs-lookup"><span data-stu-id="130a4-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="130a4-133">Si le nombre à décaler est un entier, la valeur du décalage est interprétée `mod 64`; autrement dit, un décalage de 1 et un décalage de 65 ont le même effet.</span><span class="sxs-lookup"><span data-stu-id="130a4-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="130a4-134">Pour les valeurs entières et de type entier Big, les décalages sont arithmétiques.</span><span class="sxs-lookup"><span data-stu-id="130a4-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="130a4-135">Si vous déplacez une valeur négative à gauche ou à droite, vous obtenez un nombre négatif.</span><span class="sxs-lookup"><span data-stu-id="130a4-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="130a4-136">Autrement dit, le décalage d’une étape vers la gauche ou la droite est exactement identique à la multiplication ou à la division par 2, respectivement.</span><span class="sxs-lookup"><span data-stu-id="130a4-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="130a4-137">Le modulo de la division entière et de l’entier suit le même comportement pour les nombres négatifs que C#.</span><span class="sxs-lookup"><span data-stu-id="130a4-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="130a4-138">Autrement dit, `a % b` aura toujours le même signe que et `a` `b * (a / b) + a % b` sera toujours égal `a`à.</span><span class="sxs-lookup"><span data-stu-id="130a4-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="130a4-139">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="130a4-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="130a4-140">5</span><span class="sxs-lookup"><span data-stu-id="130a4-140">5</span></span> | <span data-ttu-id="130a4-141">2</span><span class="sxs-lookup"><span data-stu-id="130a4-141">2</span></span> | <span data-ttu-id="130a4-142">2</span><span class="sxs-lookup"><span data-stu-id="130a4-142">2</span></span> | <span data-ttu-id="130a4-143">1</span><span class="sxs-lookup"><span data-stu-id="130a4-143">1</span></span>
 <span data-ttu-id="130a4-144">5</span><span class="sxs-lookup"><span data-stu-id="130a4-144">5</span></span> | <span data-ttu-id="130a4-145">-2</span><span class="sxs-lookup"><span data-stu-id="130a4-145">-2</span></span> | <span data-ttu-id="130a4-146">-2</span><span class="sxs-lookup"><span data-stu-id="130a4-146">-2</span></span> | <span data-ttu-id="130a4-147">1</span><span class="sxs-lookup"><span data-stu-id="130a4-147">1</span></span>
 <span data-ttu-id="130a4-148">-5</span><span class="sxs-lookup"><span data-stu-id="130a4-148">-5</span></span> | <span data-ttu-id="130a4-149">2</span><span class="sxs-lookup"><span data-stu-id="130a4-149">2</span></span> | <span data-ttu-id="130a4-150">-2</span><span class="sxs-lookup"><span data-stu-id="130a4-150">-2</span></span> | <span data-ttu-id="130a4-151">-1</span><span class="sxs-lookup"><span data-stu-id="130a4-151">-1</span></span>
 <span data-ttu-id="130a4-152">-5</span><span class="sxs-lookup"><span data-stu-id="130a4-152">-5</span></span> | <span data-ttu-id="130a4-153">-2</span><span class="sxs-lookup"><span data-stu-id="130a4-153">-2</span></span> | <span data-ttu-id="130a4-154">2</span><span class="sxs-lookup"><span data-stu-id="130a4-154">2</span></span> | <span data-ttu-id="130a4-155">-1</span><span class="sxs-lookup"><span data-stu-id="130a4-155">-1</span></span>

<span data-ttu-id="130a4-156">La Division d’entiers Big et le modulo fonctionnent de la même façon.</span><span class="sxs-lookup"><span data-stu-id="130a4-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="130a4-157">Quelle que soit l’expression numérique donnée, une nouvelle expression peut être `-` formée à l’aide de l’opérateur unaire.</span><span class="sxs-lookup"><span data-stu-id="130a4-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="130a4-158">La nouvelle expression sera du même type que l’expression constituante.</span><span class="sxs-lookup"><span data-stu-id="130a4-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="130a4-159">À partir de toute expression d’entier ou d’entier Big, une nouvelle expression du même type peut être `~~~` formée à l’aide de l’opérateur unaire (complément de bits).</span><span class="sxs-lookup"><span data-stu-id="130a4-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="130a4-160">Expressions booléennes</span><span class="sxs-lookup"><span data-stu-id="130a4-160">Boolean Expressions</span></span>

<span data-ttu-id="130a4-161">Les deux `Bool` valeurs littérales `true` sont `false`et.</span><span class="sxs-lookup"><span data-stu-id="130a4-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="130a4-162">Compte tenu des deux expressions du même type primitif, les `==` opérateurs `!=` binaires et peuvent être utilisés pour construire `Bool` une expression.</span><span class="sxs-lookup"><span data-stu-id="130a4-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="130a4-163">L’expression aura la valeur true si les deux expressions sont égales et false dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="130a4-163">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="130a4-164">Les valeurs des types définis par l’utilisateur ne peuvent pas être comparées, seules leurs valeurs désencapsulées peuvent être comparées.</span><span class="sxs-lookup"><span data-stu-id="130a4-164">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="130a4-165">Par exemple, à l’aide de l’opérateur `!` « désencapsuler » (expliqué dans la page de [modèle Q # type](xref:microsoft.quantum.language.type-model#user-defined-types)),</span><span class="sxs-lookup"><span data-stu-id="130a4-165">For example, using the "unwrap" operator `!` (explained in the [Q# type model page](xref:microsoft.quantum.language.type-model#user-defined-types)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="130a4-166">La comparaison d' `Qubit` égalité pour les valeurs est l’égalité d’identité ; autrement dit, si les deux expressions identifient le même qubit.</span><span class="sxs-lookup"><span data-stu-id="130a4-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="130a4-167">L’état des deux qubits n’est pas comparé, accédé, mesuré ou modifié par cette comparaison.</span><span class="sxs-lookup"><span data-stu-id="130a4-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="130a4-168">La comparaison d' `Double` égalité des valeurs peut être trompeuse en raison des effets arrondis.</span><span class="sxs-lookup"><span data-stu-id="130a4-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="130a4-169">Par exemple, `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="130a4-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="130a4-170">Compte tenu de deux expressions numériques, les opérateurs `>` `<`binaires `>=`,, `<=` et peuvent être utilisés pour construire une nouvelle expression booléenne qui a la valeur true si la première expression est respectivement supérieure à, inférieure à, supérieure ou égale à, ou inférieure ou égale à la seconde.</span><span class="sxs-lookup"><span data-stu-id="130a4-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="130a4-171">À partir de deux expressions booléennes `and` , `or` les opérateurs binaires et peuvent être utilisés pour construire une nouvelle expression booléenne qui a la valeur true si les deux expressions (REEE, ou les deux) sont vraies.</span><span class="sxs-lookup"><span data-stu-id="130a4-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="130a4-172">À partir de toute expression booléenne `not` , l’opérateur unaire peut être utilisé pour construire une nouvelle expression booléenne qui a la valeur true si l’expression constitutive est false.</span><span class="sxs-lookup"><span data-stu-id="130a4-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="130a4-173">Expressions de chaîne</span><span class="sxs-lookup"><span data-stu-id="130a4-173">String Expressions</span></span>

<span data-ttu-id="130a4-174">Q # autorise l’utilisation de chaînes dans l' `fail` instruction et la `Log` fonction standard.</span><span class="sxs-lookup"><span data-stu-id="130a4-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="130a4-175">Dans Q #, les chaînes sont des littéraux ou des chaînes interpolées.</span><span class="sxs-lookup"><span data-stu-id="130a4-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="130a4-176">Les littéraux de chaîne sont similaires aux littéraux de chaîne simples dans la plupart des langues : une séquence de caractères Unicode `"`placée entre guillemets doubles,.</span><span class="sxs-lookup"><span data-stu-id="130a4-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="130a4-177">Dans une chaîne, le `\` caractère de barre oblique inverse peut être utilisé pour échapper un caractère de guillemet double, et pour insérer une nouvelle ligne sous `\n`la forme, un retour `\r`chariot comme et un onglet `\t`comme.</span><span class="sxs-lookup"><span data-stu-id="130a4-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="130a4-178">Exemple :</span><span class="sxs-lookup"><span data-stu-id="130a4-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="130a4-179">La syntaxe Q # pour les interpolations de chaînes est un sous-ensemble de la syntaxe C# 7,0 ; Q # ne prend pas en charge les chaînes interpolées textuelles (multiligne).</span><span class="sxs-lookup"><span data-stu-id="130a4-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="130a4-180">Consultez [*chaînes interpolées*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) pour la syntaxe C#.</span><span class="sxs-lookup"><span data-stu-id="130a4-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="130a4-181">Les expressions à l’intérieur d’une chaîne interpolée suivent la syntaxe Q #, et non la syntaxe C#.</span><span class="sxs-lookup"><span data-stu-id="130a4-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="130a4-182">Toute expression Q # valide peut apparaître dans une chaîne interpolée.</span><span class="sxs-lookup"><span data-stu-id="130a4-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="130a4-183">Expressions qubit</span><span class="sxs-lookup"><span data-stu-id="130a4-183">Qubit Expressions</span></span>

<span data-ttu-id="130a4-184">Les seules `Qubit` expressions sont des symboles liés à des `Qubit` valeurs ou à des éléments `Qubit` de tableau de tableaux.</span><span class="sxs-lookup"><span data-stu-id="130a4-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="130a4-185">Il n’existe `Qubit` aucun littéral.</span><span class="sxs-lookup"><span data-stu-id="130a4-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="130a4-186">Expressions Pauli</span><span class="sxs-lookup"><span data-stu-id="130a4-186">Pauli Expressions</span></span>

<span data-ttu-id="130a4-187">Les quatre `Pauli` valeurs, `PauliI` `PauliX` `PauliY`,, et `PauliZ`, sont toutes des expressions `Pauli` valides.</span><span class="sxs-lookup"><span data-stu-id="130a4-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="130a4-188">À part cela, les seules `Pauli` expressions sont des symboles liés à des `Pauli` valeurs ou à des éléments `Pauli` de tableau de tableaux.</span><span class="sxs-lookup"><span data-stu-id="130a4-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="130a4-189">Expressions de résultat</span><span class="sxs-lookup"><span data-stu-id="130a4-189">Result Expressions</span></span>

<span data-ttu-id="130a4-190">Les deux `Result` valeurs, `One` et `Zero`, sont des `Result` expressions valides.</span><span class="sxs-lookup"><span data-stu-id="130a4-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="130a4-191">À part cela, les seules `Result` expressions sont des symboles liés à des `Result` valeurs ou à des éléments `Result` de tableau de tableaux.</span><span class="sxs-lookup"><span data-stu-id="130a4-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="130a4-192">En particulier, Notez que `One` n’est pas le même que l' `1`entier et qu’il n’y a pas de conversion directe entre eux.</span><span class="sxs-lookup"><span data-stu-id="130a4-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="130a4-193">Il en va de même `Zero` pour `0`et.</span><span class="sxs-lookup"><span data-stu-id="130a4-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="130a4-194">Expressions de plage</span><span class="sxs-lookup"><span data-stu-id="130a4-194">Range Expressions</span></span>

<span data-ttu-id="130a4-195">Compte tenu des `Int` trois `start`expressions `step`,, `stop`et `start .. step .. stop` , est une expression de plage dont le `start`premier élément est, `start+step`le deuxième élément est `start+step+step`, le troisième élément est `stop` , etc., jusqu’à ce que soit passé.</span><span class="sxs-lookup"><span data-stu-id="130a4-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="130a4-196">Une plage peut être vide si, par exemple, `step` est positif et `stop < start`.</span><span class="sxs-lookup"><span data-stu-id="130a4-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="130a4-197">Le dernier élément de la plage `stop` est si la différence entre `start` et `stop` est un multiple entier de ; `step` autrement dit, la plage est incluse aux deux extrémités.</span><span class="sxs-lookup"><span data-stu-id="130a4-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="130a4-198">À partir de `Int` deux `start` expressions `stop`quelconques et, `start .. stop` est une expression de plage `start .. 1 .. stop`qui est égale à.</span><span class="sxs-lookup"><span data-stu-id="130a4-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="130a4-199">Notez que le implicite `step` est + 1 même `stop` si est inférieur `start`à ; dans ce cas, la plage est vide.</span><span class="sxs-lookup"><span data-stu-id="130a4-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="130a4-200">Voici quelques exemples de plages :</span><span class="sxs-lookup"><span data-stu-id="130a4-200">Some example ranges are:</span></span>

- <span data-ttu-id="130a4-201">`1..3`est la plage 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="130a4-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="130a4-202">`2..2..5`est la plage 2, 4.</span><span class="sxs-lookup"><span data-stu-id="130a4-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="130a4-203">`2..2..6`est la plage 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="130a4-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="130a4-204">`6..-2..2`est la plage 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="130a4-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="130a4-205">`2..1`est la plage vide.</span><span class="sxs-lookup"><span data-stu-id="130a4-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="130a4-206">`2..6..7`est la plage 2.</span><span class="sxs-lookup"><span data-stu-id="130a4-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="130a4-207">`2..2..1`est la plage vide.</span><span class="sxs-lookup"><span data-stu-id="130a4-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="130a4-208">`1..-1..2`est la plage vide.</span><span class="sxs-lookup"><span data-stu-id="130a4-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="130a4-209">Expressions pouvant être appelées</span><span class="sxs-lookup"><span data-stu-id="130a4-209">Callable Expressions</span></span>

<span data-ttu-id="130a4-210">Un littéral pouvant être appelé est le nom d’une opération ou d’une fonction définie dans la portée de compilation.</span><span class="sxs-lookup"><span data-stu-id="130a4-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="130a4-211">Par exemple, `X` est un littéral d’opération qui fait référence à l' `X` opération de bibliothèque `Message` standard, et est un littéral de fonction qui fait `Message` référence à la fonction de bibliothèque standard.</span><span class="sxs-lookup"><span data-stu-id="130a4-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="130a4-212">Si une opération prend en `Adjoint` charge functor, `Adjoint op` est une expression d’opération.</span><span class="sxs-lookup"><span data-stu-id="130a4-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="130a4-213">De même, si l’opération prend en `Controlled` charge functor, `Controlled op` est une expression d’opération.</span><span class="sxs-lookup"><span data-stu-id="130a4-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="130a4-214">Les types de ces expressions sont spécifiés dans les [functors](xref:microsoft.quantum.language.type-model#functors).</span><span class="sxs-lookup"><span data-stu-id="130a4-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="130a4-215">Les functors`Adjoint` ( `Controlled`et) lient plus étroitement que tous les autres opérateurs, à l’exception de `!` l’opérateur Unwrap et `[]`de l’indexation de tableau avec.</span><span class="sxs-lookup"><span data-stu-id="130a4-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="130a4-216">Par conséquent, les éléments suivants sont tous valides, en supposant que les opérations prennent en charge les functors utilisés :</span><span class="sxs-lookup"><span data-stu-id="130a4-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="130a4-217">Un littéral pouvant être appelé peut être utilisé comme valeur, par exemple pour assigner à une variable ou pour passer à un autre pouvant être appelé.</span><span class="sxs-lookup"><span data-stu-id="130a4-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="130a4-218">Dans ce cas, si l’appelable possède des paramètres de type, ceux-ci doivent être fournis dans le cadre de la valeur pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="130a4-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="130a4-219">Une valeur pouvant être appelée ne peut pas avoir de paramètres de type non spécifiés.</span><span class="sxs-lookup"><span data-stu-id="130a4-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="130a4-220">Par exemple, si `Fun` est une fonction avec signature `'T1->Unit`:</span><span class="sxs-lookup"><span data-stu-id="130a4-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomeOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="130a4-221">Expressions d’appel pouvant être appelées</span><span class="sxs-lookup"><span data-stu-id="130a4-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="130a4-222">À partir d’une expression (opération ou fonction) pouvant être appelée et d’une expression de tuple du type d’entrée de la signature de l’appel, une expression d’appel peut être formée en ajoutant l’expression de tuple à l’expression pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="130a4-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="130a4-223">Le type de l’expression d’appel est le type de sortie de la signature de l’appelable.</span><span class="sxs-lookup"><span data-stu-id="130a4-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="130a4-224">Par exemple, si `Op` est une opération avec signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` est une expression de type `Double`.</span><span class="sxs-lookup"><span data-stu-id="130a4-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="130a4-225">De même, si `Sin` est une fonction avec signature `(Double -> Double)`, `Sin(0.1)` est une expression de type `Double`.</span><span class="sxs-lookup"><span data-stu-id="130a4-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="130a4-226">Enfin, si `Builder` est une fonction avec signature `(Int -> (Int -> Int))`, `Builder(3)` est une fonction de into en int.</span><span class="sxs-lookup"><span data-stu-id="130a4-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="130a4-227">L’appel du résultat d’une expression de valeur pouvant être appelée nécessite une paire de parenthèses supplémentaires autour de l’expression pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="130a4-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="130a4-228">Ainsi, pour appeler le résultat de l' `Builder` appel à partir du paragraphe précédent, la syntaxe correcte est la suivante :</span><span class="sxs-lookup"><span data-stu-id="130a4-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="130a4-229">Lors de l’appel d’un pouvant être appelé par un type paramétrable, les paramètres de type réels peuvent `<` être `>` spécifiés entre crochets pointus et après l’expression pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="130a4-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="130a4-230">Cela n’est généralement pas nécessaire, car le compilateur Q # déduira les types réels.</span><span class="sxs-lookup"><span data-stu-id="130a4-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="130a4-231">Elle est requise pour une application partielle (voir ci-dessous) si un argument de type paramétrable n’est pas spécifié.</span><span class="sxs-lookup"><span data-stu-id="130a4-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="130a4-232">Elle est également parfois utile lors du passage d’opérations avec des prises en charge de functor différentes à un pouvant être appelé.</span><span class="sxs-lookup"><span data-stu-id="130a4-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="130a4-233">Par exemple, si `Func` a une `('T1, 'T2, 'T1) -> 'T2`signature `Op1` , `Op2` et `(Qubit[] => Unit is Adj)`possède la signature `Op3` , et `(Qubit[] => Unit)`possède la signature `Func` , `Op1` pour appeler en tant que `Op2` premier argument, comme deuxième `Op3` argument, et comme troisième :</span><span class="sxs-lookup"><span data-stu-id="130a4-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="130a4-234">La spécification de type est requise `Op3` , `Op1` car et ont des types différents, de sorte que le compilateur traite cette opération comme ambiguë sans la spécification.</span><span class="sxs-lookup"><span data-stu-id="130a4-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="130a4-235">Application partielle</span><span class="sxs-lookup"><span data-stu-id="130a4-235">Partial Application</span></span>

<span data-ttu-id="130a4-236">En fonction d’une expression pouvant être appelée, un nouvel appelable peut être créé en fournissant un sous-ensemble des arguments à l’appelable.</span><span class="sxs-lookup"><span data-stu-id="130a4-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="130a4-237">C’est ce que l’on appelle une _application partielle_.</span><span class="sxs-lookup"><span data-stu-id="130a4-237">This is called _partial application_.</span></span>

<span data-ttu-id="130a4-238">Dans Q #, un appelable partiellement appliqué est exprimé en écrivant une expression d’appel normale, mais en utilisant un trait `_`de soulignement,, pour les arguments non spécifiés.</span><span class="sxs-lookup"><span data-stu-id="130a4-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="130a4-239">L’appelable résultant a le même type de résultat que l’appel de base, et les mêmes spécialisations pour les opérations.</span><span class="sxs-lookup"><span data-stu-id="130a4-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="130a4-240">Le type d’entrée de l’application partielle est simplement le type d’origine avec les arguments spécifiés supprimés.</span><span class="sxs-lookup"><span data-stu-id="130a4-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="130a4-241">Si une variable mutable est passée comme argument spécifié lors de la création d’une application partielle, la valeur actuelle de la variable est utilisée.</span><span class="sxs-lookup"><span data-stu-id="130a4-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="130a4-242">La modification de la valeur de la variable par la suite n’aura pas d’impact sur l’application partielle.</span><span class="sxs-lookup"><span data-stu-id="130a4-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="130a4-243">Par exemple, si `Op` a le `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`type :</span><span class="sxs-lookup"><span data-stu-id="130a4-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="130a4-244">`Op(5,(_,_))`a le `(((Qubit,Qubit), Double) => Unit is Adj)`type, et ainsi `Op(5,_)`de suite.</span><span class="sxs-lookup"><span data-stu-id="130a4-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="130a4-245">`Op(_,(_,1.0))` a le type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="130a4-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="130a4-246">`Op(_,((q1,q2),_))` a le type `((Int,Double) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="130a4-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="130a4-247">Notez que nous avons appliqué ici une équivalence de tuple de Singleton.</span><span class="sxs-lookup"><span data-stu-id="130a4-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="130a4-248">Si l’appelable partiellement appliqué a des paramètres de type qui ne peuvent pas être déduits par le compilateur, ils doivent être fournis au niveau du site d’appel.</span><span class="sxs-lookup"><span data-stu-id="130a4-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="130a4-249">L’application partielle ne peut pas avoir de paramètres de type non spécifiés.</span><span class="sxs-lookup"><span data-stu-id="130a4-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="130a4-250">Par exemple, si `Op` a le `(('T1, Qubit, 'T1) => Unit : Adjoint)`type :</span><span class="sxs-lookup"><span data-stu-id="130a4-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="130a4-251">Récursivité</span><span class="sxs-lookup"><span data-stu-id="130a4-251">Recursion</span></span>

<span data-ttu-id="130a4-252">Q # callables peuvent être récursives directement ou indirectement.</span><span class="sxs-lookup"><span data-stu-id="130a4-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="130a4-253">Autrement dit, une opération ou une fonction peut s’appeler elle-même, ou elle peut appeler un autre pouvant être appelé, qui appelle directement ou indirectement l’opération pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="130a4-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="130a4-254">Il existe toutefois deux commentaires importants sur l’utilisation de la récursivité :</span><span class="sxs-lookup"><span data-stu-id="130a4-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="130a4-255">L’utilisation de la récursivité dans les opérations est susceptible d’interférer avec certaines optimisations.</span><span class="sxs-lookup"><span data-stu-id="130a4-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="130a4-256">Cela peut avoir un impact important sur la durée d’exécution de l’algorithme.</span><span class="sxs-lookup"><span data-stu-id="130a4-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="130a4-257">En cas d’exécution sur un appareil Quantum réel, l’espace de pile peut être limité et, par conséquent, une récurrence profonde peut entraîner une erreur d’exécution.</span><span class="sxs-lookup"><span data-stu-id="130a4-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="130a4-258">En particulier, le compilateur et le runtime Q # n’identifient pas et n’optimisent pas la récurrence de la fin.</span><span class="sxs-lookup"><span data-stu-id="130a4-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="130a4-259">Expressions de Tuple</span><span class="sxs-lookup"><span data-stu-id="130a4-259">Tuple Expressions</span></span>

<span data-ttu-id="130a4-260">Un littéral de tuple est une séquence d’expressions d’élément du type approprié, séparées par des virgules, `(` placées entre et `)`.</span><span class="sxs-lookup"><span data-stu-id="130a4-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="130a4-261">Par exemple, `(1, One)` est une `(Int, Result)` expression.</span><span class="sxs-lookup"><span data-stu-id="130a4-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="130a4-262">À part les littéraux, les seules expressions de tuple sont des symboles liés à des valeurs de tuple, des éléments de tableau de tableaux de tuples et des appels pouvant être appelés qui retournent des tuples.</span><span class="sxs-lookup"><span data-stu-id="130a4-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="130a4-263">Expressions de type défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="130a4-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="130a4-264">Un littéral d’un type défini par l’utilisateur se compose du nom du type suivi d’un littéral de tuple du type de tuple de base du type.</span><span class="sxs-lookup"><span data-stu-id="130a4-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="130a4-265">Par exemple, si `IntPair` est un type défini par l’utilisateur basé `(Int, Int)`sur, `IntPair(2,3)` est un littéral valide de ce type.</span><span class="sxs-lookup"><span data-stu-id="130a4-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="130a4-266">À part les littéraux, les seules expressions d’un type défini par l’utilisateur sont les symboles liés aux valeurs de ce type, les éléments de tableau des tableaux de ce type et les appels pouvant être appelés qui retournent ce type.</span><span class="sxs-lookup"><span data-stu-id="130a4-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="130a4-267">Désencapsuler les expressions</span><span class="sxs-lookup"><span data-stu-id="130a4-267">Unwrap Expressions</span></span>

<span data-ttu-id="130a4-268">Dans Q #, l’opérateur Unwrap est un point d’exclamation de fin `!`.</span><span class="sxs-lookup"><span data-stu-id="130a4-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="130a4-269">Par exemple, si `IntPair` est un type défini par l’utilisateur avec le `(Int, Int)`type sous `s` -jacent et qu’il `IntPair(2,3)`s’agit `s!` d’une `(2,3)`variable avec une valeur, est alors.</span><span class="sxs-lookup"><span data-stu-id="130a4-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="130a4-270">Pour les types définis par l’utilisateur définis en termes d’autres types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="130a4-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="130a4-271">l’opérateur Unwrap peut être répété ; par exemple, `s!!` indique la valeur doublement désencapsulée de `s`.</span><span class="sxs-lookup"><span data-stu-id="130a4-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="130a4-272">Ainsi, si `WrappedPair` est un type défini par l’utilisateur avec le `IntPair`type sous `t` -jacent, et est `WrappedPair(IntPair(1,2))`une variable `t!!` de valeur `(1,2)`, est alors.</span><span class="sxs-lookup"><span data-stu-id="130a4-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="130a4-273">L' `!` opérateur a une priorité plus élevée que tous les autres `[]` opérateurs autres que pour l’indexation et le découpage de tableau.</span><span class="sxs-lookup"><span data-stu-id="130a4-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="130a4-274">`!`et `[]` liez la position. autrement dit, `a[i]![3]` doit être lu comme `((a[i])!)[3]`: prenez le `i`'th élément de `a`, Désencapsulez-le, puis récupérez le troisième élément de la valeur désencapsulée (qui doit être un tableau).</span><span class="sxs-lookup"><span data-stu-id="130a4-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="130a4-275">La priorité de l' `!` opérateur a un impact qui peut ne pas être évident.</span><span class="sxs-lookup"><span data-stu-id="130a4-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="130a4-276">Si une fonction ou une opération retourne une valeur qui est ensuite désencapsulée, l’appel de fonction ou d’opération doit être mis entre parenthèses afin que le tuple d’argument soit lié à l’appel plutôt qu’à la désencapsulation.</span><span class="sxs-lookup"><span data-stu-id="130a4-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="130a4-277">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="130a4-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="130a4-278">Expressions de tableau</span><span class="sxs-lookup"><span data-stu-id="130a4-278">Array Expressions</span></span>

<span data-ttu-id="130a4-279">Un littéral de tableau est une séquence d’une ou plusieurs expressions d’élément, séparées par des virgules `[` , `]`placées entre et.</span><span class="sxs-lookup"><span data-stu-id="130a4-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="130a4-280">Tous les éléments doivent être compatibles avec le même type.</span><span class="sxs-lookup"><span data-stu-id="130a4-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="130a4-281">Si le type d’élément commun est un type d’opération ou de fonction, tous les éléments doivent avoir les mêmes types d’entrée et de sortie.</span><span class="sxs-lookup"><span data-stu-id="130a4-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="130a4-282">Le type d’élément du tableau prend en charge tous les functors pris en charge par tous les éléments.</span><span class="sxs-lookup"><span data-stu-id="130a4-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="130a4-283">Par exemple, si `Op1`, `Op2`et `Op3` sont tous des `Qubit[] => Unit`, mais `Op1` prend `Adjoint`en `Op2` charge `Controlled`, prend `Op3` en charge et prend en charge les deux :</span><span class="sxs-lookup"><span data-stu-id="130a4-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="130a4-284">`[Op1, Op2]`est un tableau d' `(Qubit[] => Unit)` opérations.</span><span class="sxs-lookup"><span data-stu-id="130a4-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="130a4-285">`[Op1, Op3]`est un tableau d' `(Qubit[] => Unit is Adj)` opérations.</span><span class="sxs-lookup"><span data-stu-id="130a4-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="130a4-286">`[Op2, Op3]`est un tableau d' `(Qubit[] => Unit is Ctl)` opérations.</span><span class="sxs-lookup"><span data-stu-id="130a4-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="130a4-287">Les littéraux de tableaux `[]`vides,, ne sont pas autorisés.</span><span class="sxs-lookup"><span data-stu-id="130a4-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="130a4-288">Au lieu `new ★[0]`d’utiliser `★` , où est l’espace réservé pour un type approprié, permet de créer le tableau souhaité de longueur zéro.</span><span class="sxs-lookup"><span data-stu-id="130a4-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="130a4-289">À partir de deux tableaux du même type, l’opérateur `+` binaire peut être utilisé pour former un nouveau tableau qui est la concaténation des deux tableaux.</span><span class="sxs-lookup"><span data-stu-id="130a4-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="130a4-290">Par exemple, `[1,2,3] + [4,5,6]` est `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="130a4-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="130a4-291">Création de tableau</span><span class="sxs-lookup"><span data-stu-id="130a4-291">Array Creation</span></span>

<span data-ttu-id="130a4-292">À partir d’un type `Int` et d’une `new` expression, l’opérateur peut être utilisé pour allouer un nouveau tableau de la taille donnée.</span><span class="sxs-lookup"><span data-stu-id="130a4-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="130a4-293">Par exemple, `new Int[i+1]` allouerait un `Int` nouveau tableau `i+1` avec des éléments.</span><span class="sxs-lookup"><span data-stu-id="130a4-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="130a4-294">Les éléments d’un nouveau tableau sont initialisés à une valeur par défaut dépendante du type.</span><span class="sxs-lookup"><span data-stu-id="130a4-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="130a4-295">Dans la plupart des cas, il s’agit d’une variante de zéro.</span><span class="sxs-lookup"><span data-stu-id="130a4-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="130a4-296">Pour qubits et callables, qui sont des références à des entités, il n’existe pas de valeur par défaut raisonnable.</span><span class="sxs-lookup"><span data-stu-id="130a4-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="130a4-297">Par conséquent, pour ces types, la valeur par défaut est une référence non valide qui ne peut pas être utilisée sans générer d’erreur d’exécution.</span><span class="sxs-lookup"><span data-stu-id="130a4-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="130a4-298">Cela est similaire à une référence null dans des langages tels que C# ou Java.</span><span class="sxs-lookup"><span data-stu-id="130a4-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="130a4-299">Les tableaux contenant qubits ou callables doivent être correctement initialisés avec des valeurs autres que celles par défaut avant que leurs éléments puissent être utilisés en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="130a4-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="130a4-300">Les routines d’initialisation appropriées se trouvent dans <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="130a4-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="130a4-301">Les valeurs par défaut pour chaque type sont :</span><span class="sxs-lookup"><span data-stu-id="130a4-301">The default values for each type are:</span></span>

<span data-ttu-id="130a4-302">Type</span><span class="sxs-lookup"><span data-stu-id="130a4-302">Type</span></span> | <span data-ttu-id="130a4-303">Default</span><span class="sxs-lookup"><span data-stu-id="130a4-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="130a4-304">_qubit non valide_</span><span class="sxs-lookup"><span data-stu-id="130a4-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="130a4-305">La plage vide,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="130a4-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="130a4-306">_appelable non valide_</span><span class="sxs-lookup"><span data-stu-id="130a4-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="130a4-307">Les types Tuple sont initialisés élément par élément.</span><span class="sxs-lookup"><span data-stu-id="130a4-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="130a4-308">Tableaux en escalier</span><span class="sxs-lookup"><span data-stu-id="130a4-308">Jagged Arrays</span></span>

<span data-ttu-id="130a4-309">Un tableau en escalier, parfois appelé « tableau de tableaux », est un tableau dont les éléments sont des tableaux.</span><span class="sxs-lookup"><span data-stu-id="130a4-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="130a4-310">Les éléments d’un tableau en escalier peuvent être de différentes tailles.</span><span class="sxs-lookup"><span data-stu-id="130a4-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="130a4-311">L’exemple suivant montre comment déclarer et initialiser un tableau en escalier représentant une table de multiplication.</span><span class="sxs-lookup"><span data-stu-id="130a4-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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


### <a name="array-slices"></a><span data-ttu-id="130a4-312">Tranches de tableau</span><span class="sxs-lookup"><span data-stu-id="130a4-312">Array Slices</span></span>

<span data-ttu-id="130a4-313">À partir d’une expression de `Range` tableau et d’une expression, une nouvelle expression peut `[` être `]` formée à l’aide de l’opérateur de segment de tableau et.</span><span class="sxs-lookup"><span data-stu-id="130a4-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="130a4-314">La nouvelle expression est du même type que le tableau et contient les éléments de tableau indexés par les éléments de `Range`, dans l’ordre défini par le. `Range`</span><span class="sxs-lookup"><span data-stu-id="130a4-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="130a4-315">Par exemple, si `a` est lié à un tableau de `Double`s, `a[3..-1..0]` est une `Double[]` expression qui contient les quatre premiers éléments de `a` , mais dans l’ordre inverse, tels qu’ils `a`apparaissent dans.</span><span class="sxs-lookup"><span data-stu-id="130a4-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="130a4-316">Si `Range` est vide, la tranche de tableau résultante aura une longueur égale à zéro.</span><span class="sxs-lookup"><span data-stu-id="130a4-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="130a4-317">Si l’expression de tableau n’est pas un identificateur simple, elle doit être placée entre parenthèses afin de la découper.</span><span class="sxs-lookup"><span data-stu-id="130a4-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="130a4-318">Par exemple, si `a` et `b` sont tous deux des tableaux `Int`de s, un segment de la concaténation est exprimé comme suit :</span><span class="sxs-lookup"><span data-stu-id="130a4-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="130a4-319">Tous les tableaux dans Q # sont de base zéro.</span><span class="sxs-lookup"><span data-stu-id="130a4-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="130a4-320">Autrement dit, le premier élément d’un tableau `a` est toujours `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="130a4-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="130a4-321">À partir de notre version 0,8, nous prenons en charge les expressions contextuelles pour le découpage de plage.</span><span class="sxs-lookup"><span data-stu-id="130a4-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="130a4-322">En particulier, les valeurs de début et de fin de plage peuvent être omises dans le contexte d’une expression de découpage de plage.</span><span class="sxs-lookup"><span data-stu-id="130a4-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="130a4-323">Dans ce cas, le compilateur applique les règles suivantes pour déduire les délimiteurs prévus pour la plage.</span><span class="sxs-lookup"><span data-stu-id="130a4-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="130a4-324">Par exemple, si la valeur de début de la plage est omise, la valeur de début déduite</span><span class="sxs-lookup"><span data-stu-id="130a4-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="130a4-325">est égal à zéro si aucune étape n’est spécifiée ou si l’étape spécifiée est positive, et</span><span class="sxs-lookup"><span data-stu-id="130a4-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="130a4-326">longueur du tableau découpé moins un si l’étape spécifiée est négative.</span><span class="sxs-lookup"><span data-stu-id="130a4-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="130a4-327">Si la valeur de fin de la plage est omise, la valeur de fin déduite</span><span class="sxs-lookup"><span data-stu-id="130a4-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="130a4-328">est la longueur du tableau découpé moins un si aucune étape n’est spécifiée ou si l’étape spécifiée est positive, et</span><span class="sxs-lookup"><span data-stu-id="130a4-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="130a4-329">est égal à zéro si l’étape spécifiée est négative.</span><span class="sxs-lookup"><span data-stu-id="130a4-329">is zero if the specified step is negative.</span></span> 

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

## <a name="array-element-expressions"></a><span data-ttu-id="130a4-330">Expressions d’élément de tableau</span><span class="sxs-lookup"><span data-stu-id="130a4-330">Array Element Expressions</span></span>

<span data-ttu-id="130a4-331">À partir d’une expression de `Int` tableau et d’une expression, une nouvelle expression peut `[` être `]` formée à l’aide de l’opérateur d’élément de tableau et.</span><span class="sxs-lookup"><span data-stu-id="130a4-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="130a4-332">La nouvelle expression sera du même type que le type d’élément du tableau.</span><span class="sxs-lookup"><span data-stu-id="130a4-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="130a4-333">Par exemple, si `a` est lié à un tableau de `Double`s, `a[4]` est une `Double` expression.</span><span class="sxs-lookup"><span data-stu-id="130a4-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="130a4-334">Si l’expression de tableau n’est pas un identificateur simple, elle doit être placée entre parenthèses pour pouvoir sélectionner un élément.</span><span class="sxs-lookup"><span data-stu-id="130a4-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="130a4-335">Par exemple, si `a` et `b` sont tous deux des tableaux `Int`de s, un élément de la concaténation est exprimé comme suit :</span><span class="sxs-lookup"><span data-stu-id="130a4-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="130a4-336">Tous les tableaux dans Q # sont de base zéro.</span><span class="sxs-lookup"><span data-stu-id="130a4-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="130a4-337">Autrement dit, le premier élément d’un tableau `a` est toujours `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="130a4-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="130a4-338">Expressions de copie et de mise à jour</span><span class="sxs-lookup"><span data-stu-id="130a4-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="130a4-339">Vous pouvez créer des tableaux à partir d’expressions existantes à l’aide d’expressions de copie et de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="130a4-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="130a4-340">Une expression de copie et de mise à jour est une expression de `expression1 w/ expression2 <- expression3`la forme `expression1` , où doit être de `T[]` type pour un `T`certain type.</span><span class="sxs-lookup"><span data-stu-id="130a4-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="130a4-341">Le second `expression2` définit les index du ou des éléments à modifier par rapport au tableau dans `expression1` et doit être de type `Int` ou de type. `Range`</span><span class="sxs-lookup"><span data-stu-id="130a4-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="130a4-342">Si `expression2` est de type `Int`, `expression3` doit être de type `T`.</span><span class="sxs-lookup"><span data-stu-id="130a4-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="130a4-343">Si `expression2` est de type `Range`, `expression3` doit être de type `T[]`.</span><span class="sxs-lookup"><span data-stu-id="130a4-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="130a4-344">Une expression `arr w/ idx <- value` de copie et de mise à jour construit un nouveau tableau avec tous les éléments définis sur l’élément `arr`correspondant dans, à l’exception des éléments situés `idx`à, qui sont définis sur le ou les un ( `value`s) dans.</span><span class="sxs-lookup"><span data-stu-id="130a4-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="130a4-345">Par exemple, si `arr` contient un tableau `[0,1,2,3]`,</span><span class="sxs-lookup"><span data-stu-id="130a4-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="130a4-346">`arr w/ 0 <- 10`est le tableau `[10,1,2,3]`.</span><span class="sxs-lookup"><span data-stu-id="130a4-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="130a4-347">`arr w/ 2 <- 10`est le tableau `[0,1,10,3]`.</span><span class="sxs-lookup"><span data-stu-id="130a4-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="130a4-348">`arr w/ 0..2..3 <- [10,12]`est le tableau `[10,1,12,3]`.</span><span class="sxs-lookup"><span data-stu-id="130a4-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="130a4-349">Des expressions similaires existent pour les éléments nommés dans les types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="130a4-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="130a4-350">Prenons l’exemple du type</span><span class="sxs-lookup"><span data-stu-id="130a4-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="130a4-351">Si `c` contient la valeur de type `Complex(1.,-1.)`, `c w/ Re <- 0.` est une expression de type `Complex` qui prend la valeur. `Complex(0.,-1.)`</span><span class="sxs-lookup"><span data-stu-id="130a4-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="130a4-352">Expressions conditionnelles</span><span class="sxs-lookup"><span data-stu-id="130a4-352">Conditional Expressions</span></span>

<span data-ttu-id="130a4-353">À partir de deux autres expressions du même type et d’une expression booléenne, l’expression conditionnelle peut être formée à l' `?` aide du point d' `|`interrogation et de la barre verticale.</span><span class="sxs-lookup"><span data-stu-id="130a4-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="130a4-354">Par exemple, `a==b ? c | d`.</span><span class="sxs-lookup"><span data-stu-id="130a4-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="130a4-355">Dans cet exemple, la valeur de l’expression conditionnelle est `c` si `a==b` a la valeur true `d` et si elle est false.</span><span class="sxs-lookup"><span data-stu-id="130a4-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="130a4-356">Les deux expressions peuvent être évaluées à des opérations qui ont les mêmes entrées et sorties, mais prennent en charge différents functors.</span><span class="sxs-lookup"><span data-stu-id="130a4-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="130a4-357">Dans ce cas, le type de l’expression conditionnelle est une opération avec les entrées et sorties qui prend en charge tous les functors pris en charge par les deux expressions.</span><span class="sxs-lookup"><span data-stu-id="130a4-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="130a4-358">Par exemple, si `Op1`, `Op2`et `Op3` sont tous des `Qubit[]=>Unit`, mais `Op1` prend `Adjoint`en `Op2` charge `Controlled`, prend `Op3` en charge et prend en charge les deux :</span><span class="sxs-lookup"><span data-stu-id="130a4-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="130a4-359">`flag ? Op1 | Op2`est une `(Qubit[] => Unit)` opération.</span><span class="sxs-lookup"><span data-stu-id="130a4-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="130a4-360">`flag ? Op1 | Op3`est une `(Qubit[] => Unit is Adj)` opération.</span><span class="sxs-lookup"><span data-stu-id="130a4-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="130a4-361">`flag ? Op2 | Op3`est une `(Qubit[] => Unit is Ctl)` opération.</span><span class="sxs-lookup"><span data-stu-id="130a4-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="130a4-362">Si l’une des deux expressions de résultat possibles inclut une fonction ou un appel d’opération, cet appel aura lieu uniquement si ce résultat est celui qui sera la valeur de l’appel.</span><span class="sxs-lookup"><span data-stu-id="130a4-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="130a4-363">Par exemple, dans le cas `a==b ? C(qs) | D(qs)`, si `a==b` a la valeur true `C` , l’opération est appelée, et si elle a la valeur false, seul `D` sera appelé.</span><span class="sxs-lookup"><span data-stu-id="130a4-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="130a4-364">Cela est similaire au court-circuit dans d’autres langages.</span><span class="sxs-lookup"><span data-stu-id="130a4-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="130a4-365">Priorité des opérateurs</span><span class="sxs-lookup"><span data-stu-id="130a4-365">Operator Precedence</span></span>

<span data-ttu-id="130a4-366">Tous les opérateurs binaires sont associatifs à droite, `^`à l’exception de.</span><span class="sxs-lookup"><span data-stu-id="130a4-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="130a4-367">Les crochets `[` et `]`, pour le découpage et l’indexation de tableaux, sont liés avant tout opérateur.</span><span class="sxs-lookup"><span data-stu-id="130a4-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="130a4-368">Functors `Adjoint` et Bind `Controlled` après l’indexation de tableau, mais avant tous les autres opérateurs.</span><span class="sxs-lookup"><span data-stu-id="130a4-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="130a4-369">Les parenthèses pour l’appel de l’opération et de la fonction sont également liées avant tout opérateur, mais après l’indexation et les functors du tableau.</span><span class="sxs-lookup"><span data-stu-id="130a4-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="130a4-370">Opérateurs par ordre de priorité, du plus élevé au plus bas :</span><span class="sxs-lookup"><span data-stu-id="130a4-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="130a4-371">Opérateur</span><span class="sxs-lookup"><span data-stu-id="130a4-371">Operator</span></span> | <span data-ttu-id="130a4-372">Arité</span><span class="sxs-lookup"><span data-stu-id="130a4-372">Arity</span></span> | <span data-ttu-id="130a4-373">Description</span><span class="sxs-lookup"><span data-stu-id="130a4-373">Description</span></span> | <span data-ttu-id="130a4-374">Types d’opérandes</span><span class="sxs-lookup"><span data-stu-id="130a4-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="130a4-375">fin`!`</span><span class="sxs-lookup"><span data-stu-id="130a4-375">trailing `!`</span></span> | <span data-ttu-id="130a4-376">Unaire</span><span class="sxs-lookup"><span data-stu-id="130a4-376">Unary</span></span> | <span data-ttu-id="130a4-377">Unwrap (Désencapsuler)</span><span class="sxs-lookup"><span data-stu-id="130a4-377">Unwrap</span></span> | <span data-ttu-id="130a4-378">Tout type défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="130a4-378">Any user-defined type</span></span>
 <span data-ttu-id="130a4-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="130a4-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="130a4-380">Unaire</span><span class="sxs-lookup"><span data-stu-id="130a4-380">Unary</span></span> | <span data-ttu-id="130a4-381">Valeur numérique négative, complément au niveau du bit, négation logique</span><span class="sxs-lookup"><span data-stu-id="130a4-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="130a4-382">`Int`, `BigInt` ou `Double` `-`pour, `Int` ou `BigInt` pour `~~~`, `Bool` pour`not`</span><span class="sxs-lookup"><span data-stu-id="130a4-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="130a4-383">Binary</span><span class="sxs-lookup"><span data-stu-id="130a4-383">Binary</span></span> | <span data-ttu-id="130a4-384">Puissance entière</span><span class="sxs-lookup"><span data-stu-id="130a4-384">Integer power</span></span> | <span data-ttu-id="130a4-385">`Int`ou `BigInt` pour la base, `Int` pour l’exposant</span><span class="sxs-lookup"><span data-stu-id="130a4-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="130a4-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="130a4-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="130a4-387">Binary</span><span class="sxs-lookup"><span data-stu-id="130a4-387">Binary</span></span> | <span data-ttu-id="130a4-388">Division, multiplication, modulo entier</span><span class="sxs-lookup"><span data-stu-id="130a4-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="130a4-389">`Int`, `BigInt` ou `Double` pour `/` et `*`, `Int` ou `BigInt` pour`%`</span><span class="sxs-lookup"><span data-stu-id="130a4-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="130a4-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="130a4-390">`+`, `-`</span></span> | <span data-ttu-id="130a4-391">Binary</span><span class="sxs-lookup"><span data-stu-id="130a4-391">Binary</span></span> | <span data-ttu-id="130a4-392">Addition ou concaténation de chaînes et de tableaux, soustraction</span><span class="sxs-lookup"><span data-stu-id="130a4-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="130a4-393">`Int`, `BigInt` ou `Double`, en plus `String` ou n’importe quel type de tableau pour`+`</span><span class="sxs-lookup"><span data-stu-id="130a4-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="130a4-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="130a4-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="130a4-395">Binary</span><span class="sxs-lookup"><span data-stu-id="130a4-395">Binary</span></span> | <span data-ttu-id="130a4-396">Décalage vers la gauche, décalage vers la droite</span><span class="sxs-lookup"><span data-stu-id="130a4-396">Left shift, right shift</span></span> | <span data-ttu-id="130a4-397">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="130a4-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="130a4-398">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="130a4-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="130a4-399">Binary</span><span class="sxs-lookup"><span data-stu-id="130a4-399">Binary</span></span> | <span data-ttu-id="130a4-400">Comparaisons « inférieur à », « inférieur à », « supérieur à », « supérieur à » ou « égal à »</span><span class="sxs-lookup"><span data-stu-id="130a4-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="130a4-401">`Int`, `BigInt` ou`Double`</span><span class="sxs-lookup"><span data-stu-id="130a4-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="130a4-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="130a4-402">`==`, `!=`</span></span> | <span data-ttu-id="130a4-403">Binary</span><span class="sxs-lookup"><span data-stu-id="130a4-403">Binary</span></span> | <span data-ttu-id="130a4-404">comparaisons égales et non égales</span><span class="sxs-lookup"><span data-stu-id="130a4-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="130a4-405">tout type primitif</span><span class="sxs-lookup"><span data-stu-id="130a4-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="130a4-406">Binary</span><span class="sxs-lookup"><span data-stu-id="130a4-406">Binary</span></span> | <span data-ttu-id="130a4-407">ET au niveau du bit</span><span class="sxs-lookup"><span data-stu-id="130a4-407">Bitwise AND</span></span> | <span data-ttu-id="130a4-408">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="130a4-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="130a4-409">Binary</span><span class="sxs-lookup"><span data-stu-id="130a4-409">Binary</span></span> | <span data-ttu-id="130a4-410">Opération de bits XOR</span><span class="sxs-lookup"><span data-stu-id="130a4-410">Bitwise XOR</span></span> | <span data-ttu-id="130a4-411">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="130a4-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="130a4-412">Binary</span><span class="sxs-lookup"><span data-stu-id="130a4-412">Binary</span></span> | <span data-ttu-id="130a4-413">Opération de bits OR</span><span class="sxs-lookup"><span data-stu-id="130a4-413">Bitwise OR</span></span> | <span data-ttu-id="130a4-414">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="130a4-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="130a4-415">Binary</span><span class="sxs-lookup"><span data-stu-id="130a4-415">Binary</span></span> | <span data-ttu-id="130a4-416">ET logique</span><span class="sxs-lookup"><span data-stu-id="130a4-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="130a4-417">Binary</span><span class="sxs-lookup"><span data-stu-id="130a4-417">Binary</span></span> | <span data-ttu-id="130a4-418">OU logique</span><span class="sxs-lookup"><span data-stu-id="130a4-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="130a4-419">Binaire/ternaire</span><span class="sxs-lookup"><span data-stu-id="130a4-419">Binary/Ternary</span></span> | <span data-ttu-id="130a4-420">Opérateur de plage</span><span class="sxs-lookup"><span data-stu-id="130a4-420">Range operator</span></span> | `Int`
 <span data-ttu-id="130a4-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="130a4-421">`?` `|`</span></span> | <span data-ttu-id="130a4-422">Gradient</span><span class="sxs-lookup"><span data-stu-id="130a4-422">Ternary</span></span> | <span data-ttu-id="130a4-423">Logique conditionnelle</span><span class="sxs-lookup"><span data-stu-id="130a4-423">Conditional</span></span> | <span data-ttu-id="130a4-424">`Bool`pour le côté gauche</span><span class="sxs-lookup"><span data-stu-id="130a4-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="130a4-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="130a4-425">`w/` `<-`</span></span> | <span data-ttu-id="130a4-426">Gradient</span><span class="sxs-lookup"><span data-stu-id="130a4-426">Ternary</span></span> | <span data-ttu-id="130a4-427">Copier et mettre à jour</span><span class="sxs-lookup"><span data-stu-id="130a4-427">Copy-and-update</span></span> | <span data-ttu-id="130a4-428">Voir les [expressions copy-and-Update](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="130a4-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
