---
title: 'Expressions de type dans Q #'
description: 'Comprendre comment spécifier, référencer et combiner des constantes, des variables, des opérateurs, des opérations et des fonctions en tant qu’expressions dans Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: b32644382bb88fb11da00d0d7d78bbd797a0eaaa
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84629995"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="02898-103">Expressions de type dans Q #</span><span class="sxs-lookup"><span data-stu-id="02898-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="02898-104">Expressions numériques</span><span class="sxs-lookup"><span data-stu-id="02898-104">Numeric Expressions</span></span>

<span data-ttu-id="02898-105">Les expressions numériques sont des expressions de type `Int` , `BigInt` ou `Double` .</span><span class="sxs-lookup"><span data-stu-id="02898-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="02898-106">Autrement dit, il s’agit de nombres entiers ou à virgule flottante.</span><span class="sxs-lookup"><span data-stu-id="02898-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="02898-107">`Int`les littéraux dans Q # sont écrits simplement sous la forme d’une séquence de chiffres.</span><span class="sxs-lookup"><span data-stu-id="02898-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="02898-108">Les entiers hexadécimaux et binaires sont pris en charge avec un `0x` `0b` préfixe et, respectivement.</span><span class="sxs-lookup"><span data-stu-id="02898-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="02898-109">`BigInt`les littéraux dans Q # sont écrits avec un `l` suffixe ou de fin `L` .</span><span class="sxs-lookup"><span data-stu-id="02898-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="02898-110">Les nombres entiers hexadécimaux sont pris en charge avec un préfixe « 0x ».</span><span class="sxs-lookup"><span data-stu-id="02898-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="02898-111">Par conséquent, Voici toutes les utilisations valides des `BigInt` littéraux :</span><span class="sxs-lookup"><span data-stu-id="02898-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="02898-112">`Double`les littéraux dans Q # sont des nombres à virgule flottante écrits à l’aide de chiffres décimaux.</span><span class="sxs-lookup"><span data-stu-id="02898-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="02898-113">Elles peuvent être écrites avec une virgule décimale, `.` , et/ou une partie exponentielle indiquée par « e » ou « e » (après quoi seuls un signe négatif et des chiffres décimaux possibles sont valides).</span><span class="sxs-lookup"><span data-stu-id="02898-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="02898-114">Les littéraux valides sont les suivants `Double` : `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="02898-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="02898-115">À partir d’une expression de tableau de tout type d’élément, une `Int` expression peut être formée à l’aide de la [`Length`](xref:microsoft.quantum.core.length) fonction intégrée, avec l’expression de tableau placée entre parenthèses, `(` et `)` .</span><span class="sxs-lookup"><span data-stu-id="02898-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="02898-116">Par exemple, si `a` est lié à un tableau, `Length(a)` est une expression d’entier.</span><span class="sxs-lookup"><span data-stu-id="02898-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="02898-117">Si `b` est un tableau de tableaux d’entiers, `Int[][]` , `Length(b)` est le nombre de sous-tableaux dans `b` , et `Length(b[1])` est le nombre d’entiers dans le deuxième sous-tableau de `b` .</span><span class="sxs-lookup"><span data-stu-id="02898-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="02898-118">À partir de deux expressions numériques du même type, les opérateurs binaires `+` , `-` , `*` et `/` peuvent être utilisés pour former une nouvelle expression numérique.</span><span class="sxs-lookup"><span data-stu-id="02898-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="02898-119">Le type de la nouvelle expression sera le même que les types des expressions constituantes.</span><span class="sxs-lookup"><span data-stu-id="02898-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="02898-120">À partir de deux expressions entières, l’opérateur binaire `^` (Power) peut être utilisé pour former une nouvelle expression entière.</span><span class="sxs-lookup"><span data-stu-id="02898-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="02898-121">De même, `^` peut être utilisé avec deux expressions double pour former une nouvelle expression double.</span><span class="sxs-lookup"><span data-stu-id="02898-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="02898-122">Enfin, `^` peut être utilisé avec un grand entier à gauche et un entier sur la droite pour former une nouvelle expression d’entier Big.</span><span class="sxs-lookup"><span data-stu-id="02898-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="02898-123">Dans ce cas, le deuxième paramètre doit être contenu dans 32 bits ; Si ce n’est pas le cas, une erreur d’exécution est générée.</span><span class="sxs-lookup"><span data-stu-id="02898-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="02898-124">À partir de deux expressions entières ou d’entiers Big, une nouvelle expression de type entier ou entier Big peut être formée à l’aide des opérateurs (modulo), (opérateur and au niveau du bit), (au niveau du bit or `%` `&&&` `|||` ) ou `^^^` (opérateur de bits XOR).</span><span class="sxs-lookup"><span data-stu-id="02898-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="02898-125">En fonction d’une expression d’entier ou d’entier Big à gauche, et d’une expression d’entier à droite, les `<<<` opérateurs (décalage arithmétique vers la gauche) ou `>>>` (décalage à droite) peuvent être utilisés pour créer une nouvelle expression avec le même type que l’expression de gauche.</span><span class="sxs-lookup"><span data-stu-id="02898-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="02898-126">Le deuxième paramètre (la valeur de décalage) pour l’opération de décalage doit être supérieur ou égal à zéro ; le comportement des valeurs de décalage négatives n’est pas défini.</span><span class="sxs-lookup"><span data-stu-id="02898-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="02898-127">La valeur de décalage pour l’opération de décalage doit également tenir dans 32 bits ; Si ce n’est pas le cas, une erreur d’exécution est générée.</span><span class="sxs-lookup"><span data-stu-id="02898-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="02898-128">Si le nombre à décaler est un entier, la valeur de décalage est interprétée `mod 64` ; autrement dit, un décalage de 1 et un décalage de 65 ont le même effet.</span><span class="sxs-lookup"><span data-stu-id="02898-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="02898-129">Pour les valeurs entières et de type entier Big, les décalages sont arithmétiques.</span><span class="sxs-lookup"><span data-stu-id="02898-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="02898-130">Si vous déplacez une valeur négative à gauche ou à droite, vous obtenez un nombre négatif.</span><span class="sxs-lookup"><span data-stu-id="02898-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="02898-131">Autrement dit, le décalage d’une étape vers la gauche ou la droite est exactement identique à la multiplication ou à la division par 2, respectivement.</span><span class="sxs-lookup"><span data-stu-id="02898-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="02898-132">Le modulo de la division entière et de l’entier suit le même comportement pour les nombres négatifs que C#.</span><span class="sxs-lookup"><span data-stu-id="02898-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="02898-133">Autrement dit, `a % b` aura toujours le même signe que `a` et `b * (a / b) + a % b` sera toujours égal à `a` .</span><span class="sxs-lookup"><span data-stu-id="02898-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="02898-134">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="02898-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="02898-135">5</span><span class="sxs-lookup"><span data-stu-id="02898-135">5</span></span> | <span data-ttu-id="02898-136">2</span><span class="sxs-lookup"><span data-stu-id="02898-136">2</span></span> | <span data-ttu-id="02898-137">2</span><span class="sxs-lookup"><span data-stu-id="02898-137">2</span></span> | <span data-ttu-id="02898-138">1</span><span class="sxs-lookup"><span data-stu-id="02898-138">1</span></span>
 <span data-ttu-id="02898-139">5</span><span class="sxs-lookup"><span data-stu-id="02898-139">5</span></span> | <span data-ttu-id="02898-140">-2</span><span class="sxs-lookup"><span data-stu-id="02898-140">-2</span></span> | <span data-ttu-id="02898-141">-2</span><span class="sxs-lookup"><span data-stu-id="02898-141">-2</span></span> | <span data-ttu-id="02898-142">1</span><span class="sxs-lookup"><span data-stu-id="02898-142">1</span></span>
 <span data-ttu-id="02898-143">-5</span><span class="sxs-lookup"><span data-stu-id="02898-143">-5</span></span> | <span data-ttu-id="02898-144">2</span><span class="sxs-lookup"><span data-stu-id="02898-144">2</span></span> | <span data-ttu-id="02898-145">-2</span><span class="sxs-lookup"><span data-stu-id="02898-145">-2</span></span> | <span data-ttu-id="02898-146">-1</span><span class="sxs-lookup"><span data-stu-id="02898-146">-1</span></span>
 <span data-ttu-id="02898-147">-5</span><span class="sxs-lookup"><span data-stu-id="02898-147">-5</span></span> | <span data-ttu-id="02898-148">-2</span><span class="sxs-lookup"><span data-stu-id="02898-148">-2</span></span> | <span data-ttu-id="02898-149">2</span><span class="sxs-lookup"><span data-stu-id="02898-149">2</span></span> | <span data-ttu-id="02898-150">-1</span><span class="sxs-lookup"><span data-stu-id="02898-150">-1</span></span>

<span data-ttu-id="02898-151">La Division d’entiers Big et le modulo fonctionnent de la même façon.</span><span class="sxs-lookup"><span data-stu-id="02898-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="02898-152">Quelle que soit l’expression numérique donnée, une nouvelle expression peut être formée à l’aide de l' `-` opérateur unaire.</span><span class="sxs-lookup"><span data-stu-id="02898-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="02898-153">La nouvelle expression sera du même type que l’expression constituante.</span><span class="sxs-lookup"><span data-stu-id="02898-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="02898-154">À partir de toute expression d’entier ou d’entier Big, une nouvelle expression du même type peut être formée à l’aide de l' `~~~` opérateur unaire (complément de bits).</span><span class="sxs-lookup"><span data-stu-id="02898-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="02898-155">Expressions booléennes</span><span class="sxs-lookup"><span data-stu-id="02898-155">Boolean Expressions</span></span>

<span data-ttu-id="02898-156">Les deux `Bool` valeurs littérales sont `true` et `false` .</span><span class="sxs-lookup"><span data-stu-id="02898-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="02898-157">Compte tenu des deux expressions du même type primitif, les `==` `!=` opérateurs binaires et peuvent être utilisés pour construire une `Bool` expression.</span><span class="sxs-lookup"><span data-stu-id="02898-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="02898-158">L’expression aura la valeur true si les deux expressions sont égales et false dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="02898-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="02898-159">Les valeurs des types définis par l’utilisateur ne peuvent pas être comparées, seules leurs valeurs désencapsulées peuvent être comparées.</span><span class="sxs-lookup"><span data-stu-id="02898-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="02898-160">Par exemple, à l’aide de l’opérateur « Unwrap » `!` (expliqué en détail dans les [types dans Q #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span><span class="sxs-lookup"><span data-stu-id="02898-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="02898-161">La comparaison d’égalité pour les `Qubit` valeurs est l’égalité d’identité ; autrement dit, si les deux expressions identifient le même qubit.</span><span class="sxs-lookup"><span data-stu-id="02898-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="02898-162">L’état des deux qubits n’est pas comparé, accédé, mesuré ou modifié par cette comparaison.</span><span class="sxs-lookup"><span data-stu-id="02898-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="02898-163">La comparaison d’égalité des `Double` valeurs peut être trompeuse en raison des effets arrondis.</span><span class="sxs-lookup"><span data-stu-id="02898-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="02898-164">Par exemple, `49.0 * (1.0/49.0) != 1.0` .</span><span class="sxs-lookup"><span data-stu-id="02898-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="02898-165">Compte tenu de deux expressions numériques, les opérateurs binaires `>` , `<` , `>=` et `<=` peuvent être utilisés pour construire une nouvelle expression booléenne qui a la valeur true si la première expression est respectivement supérieure à, inférieure à, supérieure ou égale à, ou inférieure ou égale à la seconde.</span><span class="sxs-lookup"><span data-stu-id="02898-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="02898-166">À partir de deux expressions booléennes, les `and` `or` opérateurs binaires et peuvent être utilisés pour construire une nouvelle expression booléenne qui a la valeur true si les deux expressions (REEE, ou les deux) sont vraies.</span><span class="sxs-lookup"><span data-stu-id="02898-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="02898-167">À partir de toute expression booléenne, l' `not` opérateur unaire peut être utilisé pour construire une nouvelle expression booléenne qui a la valeur true si l’expression constitutive est false.</span><span class="sxs-lookup"><span data-stu-id="02898-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="02898-168">Expressions de chaîne</span><span class="sxs-lookup"><span data-stu-id="02898-168">String Expressions</span></span>

<span data-ttu-id="02898-169">Q # permet d’utiliser des chaînes dans l' `fail` instruction (expliquée dans le [contrôle Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) et dans la [`Message`](xref:microsoft.quantum.intrinsic.message) fonction standard.</span><span class="sxs-lookup"><span data-stu-id="02898-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="02898-170">Le comportement spécifique de ce dernier dépend du simulateur utilisé, mais écrit généralement un message dans la console hôte lorsqu’il est appelé pendant un programme Q #.</span><span class="sxs-lookup"><span data-stu-id="02898-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="02898-171">Dans Q #, les chaînes sont des littéraux ou des chaînes interpolées.</span><span class="sxs-lookup"><span data-stu-id="02898-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="02898-172">Les littéraux de chaîne sont similaires aux littéraux de chaîne simples dans la plupart des langues : une séquence de caractères Unicode placée entre guillemets doubles, `"` .</span><span class="sxs-lookup"><span data-stu-id="02898-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="02898-173">Dans une chaîne, le caractère de barre oblique inverse `\` peut être utilisé pour échapper un caractère de guillemet double, et pour insérer une nouvelle ligne sous `\n` la forme, un retour chariot comme et `\r` un onglet comme `\t` .</span><span class="sxs-lookup"><span data-stu-id="02898-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="02898-174">Exemple :</span><span class="sxs-lookup"><span data-stu-id="02898-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="02898-175">Chaînes interpolées</span><span class="sxs-lookup"><span data-stu-id="02898-175">Interpolated strings</span></span>

<span data-ttu-id="02898-176">La syntaxe Q # pour les interpolations de chaînes est un sous-ensemble de la syntaxe C#, mais nous résumerons ici les points clés qui se rapportent à Q #.</span><span class="sxs-lookup"><span data-stu-id="02898-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="02898-177">Les différences principales sont décrites ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="02898-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="02898-178">Pour identifier un littéral de chaîne comme chaîne interpolée, préfixez-la du symbole `$`.</span><span class="sxs-lookup"><span data-stu-id="02898-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="02898-179">Vous ne pouvez pas avoir d’espace blanc entre `$` et `"` qui démarre un littéral de chaîne.</span><span class="sxs-lookup"><span data-stu-id="02898-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="02898-180">L’exemple suivant est un exemple de base [`Message`](xref:microsoft.quantum.intrinsic.message) qui utilise la fonction pour écrire le résultat d’une mesure dans la console, en même temps que d’autres expressions Q #.</span><span class="sxs-lookup"><span data-stu-id="02898-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="02898-181">Toute expression Q # valide peut apparaître dans une chaîne interpolée.</span><span class="sxs-lookup"><span data-stu-id="02898-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="02898-182">Pour plus d’informations sur la syntaxe C#, consultez [*chaînes interpolées*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="02898-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="02898-183">La distinction la plus notable est que Q # ne prend pas en charge les chaînes interpolées textuelles (multiligne).</span><span class="sxs-lookup"><span data-stu-id="02898-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="02898-184">Les expressions à l’intérieur d’une chaîne interpolée suivent la syntaxe Q #, et non la syntaxe C#.</span><span class="sxs-lookup"><span data-stu-id="02898-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="02898-185">Expressions de plage</span><span class="sxs-lookup"><span data-stu-id="02898-185">Range Expressions</span></span>

<span data-ttu-id="02898-186">Compte tenu des trois `Int` expressions `start` , `step` , et `stop` , `start .. step .. stop` est une expression de plage dont le premier élément est, le `start` deuxième élément est, le `start+step` troisième élément est `start+step+step` , etc., jusqu’à ce que `stop` soit passé.</span><span class="sxs-lookup"><span data-stu-id="02898-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="02898-187">Une plage peut être vide si, par exemple, `step` est positif et `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="02898-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="02898-188">Le dernier élément de la plage est `stop` si la différence entre `start` et `stop` est un multiple entier de `step` ; autrement dit, la plage est incluse aux deux extrémités.</span><span class="sxs-lookup"><span data-stu-id="02898-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="02898-189">À partir de deux expressions quelconques `Int` `start` et `stop` , `start .. stop` est une expression de plage qui est égale à `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="02898-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="02898-190">Notez que le implicite `step` est + 1 même si `stop` est inférieur à `start` ; dans ce cas, la plage est vide.</span><span class="sxs-lookup"><span data-stu-id="02898-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="02898-191">Voici quelques exemples de plages :</span><span class="sxs-lookup"><span data-stu-id="02898-191">Some example ranges are:</span></span>

- <span data-ttu-id="02898-192">`1..3`est la plage 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="02898-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="02898-193">`2..2..5`est la plage 2, 4.</span><span class="sxs-lookup"><span data-stu-id="02898-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="02898-194">`2..2..6`est la plage 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="02898-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="02898-195">`6..-2..2`est la plage 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="02898-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="02898-196">`2..1`est la plage vide.</span><span class="sxs-lookup"><span data-stu-id="02898-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="02898-197">`2..6..7`est la plage 2.</span><span class="sxs-lookup"><span data-stu-id="02898-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="02898-198">`2..2..1`est la plage vide.</span><span class="sxs-lookup"><span data-stu-id="02898-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="02898-199">`1..-1..2`est la plage vide.</span><span class="sxs-lookup"><span data-stu-id="02898-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="02898-200">Expressions qubit</span><span class="sxs-lookup"><span data-stu-id="02898-200">Qubit Expressions</span></span>

<span data-ttu-id="02898-201">Les seules `Qubit` expressions sont des symboles liés à `Qubit` des valeurs ou à des éléments de tableau de `Qubit` tableaux.</span><span class="sxs-lookup"><span data-stu-id="02898-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="02898-202">Il n’existe aucun `Qubit` littéral.</span><span class="sxs-lookup"><span data-stu-id="02898-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="02898-203">Expressions Pauli</span><span class="sxs-lookup"><span data-stu-id="02898-203">Pauli Expressions</span></span>

<span data-ttu-id="02898-204">Les quatre `Pauli` valeurs,,, `PauliI` `PauliX` `PauliY` et `PauliZ` , sont toutes des expressions valides `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="02898-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="02898-205">À part cela, les seules `Pauli` expressions sont des symboles liés à `Pauli` des valeurs ou à des éléments de tableau de `Pauli` tableaux.</span><span class="sxs-lookup"><span data-stu-id="02898-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="02898-206">Expressions de résultat</span><span class="sxs-lookup"><span data-stu-id="02898-206">Result Expressions</span></span>

<span data-ttu-id="02898-207">Les deux `Result` valeurs, `One` et `Zero` , sont des `Result` expressions valides.</span><span class="sxs-lookup"><span data-stu-id="02898-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="02898-208">À part cela, les seules `Result` expressions sont des symboles liés à `Result` des valeurs ou à des éléments de tableau de `Result` tableaux.</span><span class="sxs-lookup"><span data-stu-id="02898-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="02898-209">En particulier, Notez que `One` n’est pas le même que l’entier `1` et qu’il n’y a pas de conversion directe entre eux.</span><span class="sxs-lookup"><span data-stu-id="02898-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="02898-210">Il en va de même pour `Zero` et `0` .</span><span class="sxs-lookup"><span data-stu-id="02898-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="02898-211">Expressions de Tuple</span><span class="sxs-lookup"><span data-stu-id="02898-211">Tuple Expressions</span></span>

<span data-ttu-id="02898-212">Un littéral de tuple est une séquence d’expressions d’élément du type approprié, séparées par des virgules, placées entre `(` et `)` .</span><span class="sxs-lookup"><span data-stu-id="02898-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="02898-213">Par exemple, `(1, One)` est une `(Int, Result)` expression.</span><span class="sxs-lookup"><span data-stu-id="02898-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="02898-214">À part les littéraux, les seules expressions de tuple sont des symboles liés à des valeurs de tuple, des éléments de tableau de tableaux de tuples et des appels pouvant être appelés qui retournent des tuples.</span><span class="sxs-lookup"><span data-stu-id="02898-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="02898-215">Expressions de type défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="02898-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="02898-216">Un littéral d’un type défini par l’utilisateur se compose du nom du type suivi d’un littéral de tuple du type de tuple de base du type.</span><span class="sxs-lookup"><span data-stu-id="02898-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="02898-217">Par exemple, si `IntPair` est un type défini par l’utilisateur basé sur `(Int, Int)` , est `IntPair(2, 3)` un littéral valide de ce type.</span><span class="sxs-lookup"><span data-stu-id="02898-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="02898-218">À part les littéraux, les seules expressions d’un type défini par l’utilisateur sont les symboles liés aux valeurs de ce type, les éléments de tableau des tableaux de ce type et les appels pouvant être appelés qui retournent ce type.</span><span class="sxs-lookup"><span data-stu-id="02898-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="02898-219">Désencapsuler les expressions</span><span class="sxs-lookup"><span data-stu-id="02898-219">Unwrap Expressions</span></span>

<span data-ttu-id="02898-220">Dans Q #, l’opérateur Unwrap est un point d’exclamation de fin `!` .</span><span class="sxs-lookup"><span data-stu-id="02898-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="02898-221">Par exemple, si `IntPair` est un type défini par l’utilisateur avec le type sous-jacent et qu’il s’agit d' `(Int, Int)` `s` une variable avec une valeur `IntPair(2, 3)` , est alors `s!` `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="02898-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="02898-222">Pour les types définis par l’utilisateur définis en termes d’autres types définis par l’utilisateur, l’opérateur Unwrap peut être répété. par exemple, `s!!` indique la valeur doublement désencapsulée de `s` .</span><span class="sxs-lookup"><span data-stu-id="02898-222">For user-defined types defined in terms of other user-defined types, the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="02898-223">Ainsi, si `WrappedPair` est un type défini par l’utilisateur avec le type sous-jacent `IntPair` , et `t` est une variable de valeur `WrappedPair(IntPair(1,2))` , est alors `t!!` `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="02898-223">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="02898-224">L' `!` opérateur a une priorité plus élevée que tous les autres opérateurs autres que `[]` pour l’indexation et le découpage de tableau.</span><span class="sxs-lookup"><span data-stu-id="02898-224">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="02898-225">`!`et la `[]` liaison de position ; autrement dit, `a[i]![3]` doit être lu comme `((a[i])!)[3]` : prenez le `i` 'th élément de `a` , Désencapsulez-le, puis récupérez le troisième élément de la valeur désencapsulée (qui doit être un tableau).</span><span class="sxs-lookup"><span data-stu-id="02898-225">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="02898-226">La priorité de l' `!` opérateur a un impact qui peut ne pas être évident.</span><span class="sxs-lookup"><span data-stu-id="02898-226">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="02898-227">Si une fonction ou une opération retourne une valeur qui est ensuite désencapsulée, l’appel de fonction ou d’opération doit être mis entre parenthèses afin que le tuple d’argument soit lié à l’appel plutôt qu’à la désencapsulation.</span><span class="sxs-lookup"><span data-stu-id="02898-227">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="02898-228">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="02898-228">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="02898-229">Expressions de tableau</span><span class="sxs-lookup"><span data-stu-id="02898-229">Array Expressions</span></span>

<span data-ttu-id="02898-230">Un littéral de tableau est une séquence d’une ou plusieurs expressions d’élément, séparées par des virgules, placées entre `[` et `]` .</span><span class="sxs-lookup"><span data-stu-id="02898-230">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="02898-231">Tous les éléments doivent être compatibles avec le même type.</span><span class="sxs-lookup"><span data-stu-id="02898-231">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="02898-232">À partir de deux tableaux du même type, l' `+` opérateur binaire peut être utilisé pour former un nouveau tableau qui est la concaténation des deux tableaux.</span><span class="sxs-lookup"><span data-stu-id="02898-232">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="02898-233">Par exemple, `[1,2,3] + [4,5,6]` est `[1,2,3,4,5,6]` .</span><span class="sxs-lookup"><span data-stu-id="02898-233">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="02898-234">Création de tableau</span><span class="sxs-lookup"><span data-stu-id="02898-234">Array Creation</span></span>

<span data-ttu-id="02898-235">À partir d’un type et d’une `Int` expression, l' `new` opérateur peut être utilisé pour allouer un nouveau tableau de la taille donnée.</span><span class="sxs-lookup"><span data-stu-id="02898-235">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="02898-236">Par exemple, `new Int[i + 1]` allouerait un nouveau `Int` tableau avec des `i + 1` éléments.</span><span class="sxs-lookup"><span data-stu-id="02898-236">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="02898-237">Les littéraux de tableaux vides, `[]` , ne sont pas autorisés.</span><span class="sxs-lookup"><span data-stu-id="02898-237">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="02898-238">Au lieu d’utiliser `new ★[0]` , où `★` est l’espace réservé pour un type approprié, permet de créer le tableau souhaité de longueur zéro.</span><span class="sxs-lookup"><span data-stu-id="02898-238">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="02898-239">Les éléments d’un nouveau tableau sont initialisés à une valeur par défaut dépendante du type.</span><span class="sxs-lookup"><span data-stu-id="02898-239">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="02898-240">Dans la plupart des cas, il s’agit d’une variante de zéro.</span><span class="sxs-lookup"><span data-stu-id="02898-240">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="02898-241">Pour qubits et callables, qui sont des références à des entités, il n’existe pas de valeur par défaut raisonnable.</span><span class="sxs-lookup"><span data-stu-id="02898-241">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="02898-242">Par conséquent, pour ces types, la valeur par défaut est une référence non valide qui ne peut pas être utilisée sans générer d’erreur d’exécution.</span><span class="sxs-lookup"><span data-stu-id="02898-242">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="02898-243">Cela est similaire à une référence null dans des langages tels que C# ou Java.</span><span class="sxs-lookup"><span data-stu-id="02898-243">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="02898-244">Les tableaux contenant qubits ou callables doivent être correctement initialisés avec des valeurs autres que celles par défaut avant que leurs éléments puissent être utilisés en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="02898-244">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="02898-245">Les routines d’initialisation appropriées se trouvent dans <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="02898-245">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="02898-246">Les valeurs par défaut pour chaque type sont :</span><span class="sxs-lookup"><span data-stu-id="02898-246">The default values for each type are:</span></span>

<span data-ttu-id="02898-247">Type</span><span class="sxs-lookup"><span data-stu-id="02898-247">Type</span></span> | <span data-ttu-id="02898-248">Default</span><span class="sxs-lookup"><span data-stu-id="02898-248">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="02898-249">_qubit non valide_</span><span class="sxs-lookup"><span data-stu-id="02898-249">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="02898-250">La plage vide,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="02898-250">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="02898-251">_appelable non valide_</span><span class="sxs-lookup"><span data-stu-id="02898-251">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="02898-252">Les types Tuple sont initialisés élément par élément.</span><span class="sxs-lookup"><span data-stu-id="02898-252">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="02898-253">Éléments de tableau</span><span class="sxs-lookup"><span data-stu-id="02898-253">Array Elements</span></span>

<span data-ttu-id="02898-254">À partir d’une expression de tableau et d’une `Int` expression, une nouvelle expression peut être formée à l’aide de l' `[` `]` opérateur d’élément de tableau et.</span><span class="sxs-lookup"><span data-stu-id="02898-254">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="02898-255">La nouvelle expression sera du même type que le type d’élément du tableau.</span><span class="sxs-lookup"><span data-stu-id="02898-255">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="02898-256">Par exemple, si `a` est lié à un tableau de `Double` s, `a[4]` est une `Double` expression.</span><span class="sxs-lookup"><span data-stu-id="02898-256">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="02898-257">Si l’expression de tableau n’est pas un identificateur simple, elle doit être placée entre parenthèses pour pouvoir sélectionner un élément.</span><span class="sxs-lookup"><span data-stu-id="02898-257">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="02898-258">Par exemple, si `a` et `b` sont tous deux des tableaux de `Int` s, un élément de la concaténation est exprimé comme suit :</span><span class="sxs-lookup"><span data-stu-id="02898-258">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="02898-259">Tous les tableaux dans Q # sont de base zéro.</span><span class="sxs-lookup"><span data-stu-id="02898-259">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="02898-260">Autrement dit, le premier élément d’un tableau `a` est toujours `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="02898-260">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="02898-261">Tranches de tableau</span><span class="sxs-lookup"><span data-stu-id="02898-261">Array Slices</span></span>

<span data-ttu-id="02898-262">À partir d’une expression de tableau et d’une `Range` expression, une nouvelle expression peut être formée à l’aide de l' `[` `]` opérateur de segment de tableau et.</span><span class="sxs-lookup"><span data-stu-id="02898-262">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="02898-263">La nouvelle expression est du même type que le tableau et contient les éléments de tableau indexés par les éléments de `Range` , dans l’ordre défini par le `Range` .</span><span class="sxs-lookup"><span data-stu-id="02898-263">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="02898-264">Par exemple, si `a` est lié à un tableau de `Double` s, `a[3..-1..0]` est une `Double[]` expression qui contient les quatre premiers éléments de, `a` mais dans l’ordre inverse, tels qu’ils apparaissent dans `a` .</span><span class="sxs-lookup"><span data-stu-id="02898-264">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="02898-265">Si `Range` est vide, la tranche de tableau résultante aura une longueur égale à zéro.</span><span class="sxs-lookup"><span data-stu-id="02898-265">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="02898-266">Tout comme pour le référencement d’éléments de tableau, si l’expression de tableau n’est pas un identificateur simple, elle doit être placée entre parenthèses afin de la découper.</span><span class="sxs-lookup"><span data-stu-id="02898-266">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="02898-267">Si `a` et `b` sont tous deux des tableaux de `Int` s, un segment de la concaténation est exprimé comme suit :</span><span class="sxs-lookup"><span data-stu-id="02898-267">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="02898-268">Valeurs de début/fin déduites</span><span class="sxs-lookup"><span data-stu-id="02898-268">Inferred start/end values</span></span>

<span data-ttu-id="02898-269">À partir de notre version 0,8, nous prenons en charge les expressions contextuelles pour le découpage de plage.</span><span class="sxs-lookup"><span data-stu-id="02898-269">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="02898-270">En particulier, les valeurs de début et de fin de plage peuvent être omises dans le contexte d’une expression de découpage de plage.</span><span class="sxs-lookup"><span data-stu-id="02898-270">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="02898-271">Dans ce cas, le compilateur applique les règles suivantes pour déduire les délimiteurs prévus pour la plage.</span><span class="sxs-lookup"><span data-stu-id="02898-271">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="02898-272">Par exemple, si la valeur de début de la plage est omise, la valeur de début déduite</span><span class="sxs-lookup"><span data-stu-id="02898-272">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="02898-273">est égal à zéro si aucune étape n’est spécifiée ou si l’étape spécifiée est positive, et</span><span class="sxs-lookup"><span data-stu-id="02898-273">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="02898-274">longueur du tableau découpé moins un si l’étape spécifiée est négative.</span><span class="sxs-lookup"><span data-stu-id="02898-274">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="02898-275">Si la valeur de fin de la plage est omise, la valeur de fin déduite</span><span class="sxs-lookup"><span data-stu-id="02898-275">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="02898-276">est la longueur du tableau découpé moins un si aucune étape n’est spécifiée ou si l’étape spécifiée est positive, et</span><span class="sxs-lookup"><span data-stu-id="02898-276">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="02898-277">est égal à zéro si l’étape spécifiée est négative.</span><span class="sxs-lookup"><span data-stu-id="02898-277">is zero if the specified step is negative.</span></span> 

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="02898-278">Expressions de copie et de mise à jour</span><span class="sxs-lookup"><span data-stu-id="02898-278">Copy-and-Update Expressions</span></span>

<span data-ttu-id="02898-279">Étant donné que tous les types Q # sont des types valeur, avec le qubits qui prend un rôle quelque peu spécial, une « copie » est formellement créée lorsqu’une valeur est liée à un symbole ou lorsqu’un symbole est relié.</span><span class="sxs-lookup"><span data-stu-id="02898-279">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="02898-280">Autrement dit, le comportement de Q # est le même que si une copie a été créée lors de l’assignation.</span><span class="sxs-lookup"><span data-stu-id="02898-280">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="02898-281">Bien entendu, dans la pratique, seuls les éléments pertinents sont recréés en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="02898-281">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="02898-282">En particulier, cela comprend également des tableaux.</span><span class="sxs-lookup"><span data-stu-id="02898-282">This in particular also includes arrays.</span></span>
<span data-ttu-id="02898-283">En particulier, il n’est pas possible de mettre à jour les éléments d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="02898-283">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="02898-284">La modification d’un tableau existant requiert l’utilisation d’un mécanisme de *copie et de mise à jour* .</span><span class="sxs-lookup"><span data-stu-id="02898-284">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="02898-285">Vous pouvez créer des tableaux à partir d’expressions existantes à l’aide d’expressions de *copie et de mise à jour* .</span><span class="sxs-lookup"><span data-stu-id="02898-285">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="02898-286">Une expression de copie et de mise à jour est une expression de la forme `expression1 w/ expression2 <- expression3` , où `expression1` doit être de type `T[]` pour un certain type `T` .</span><span class="sxs-lookup"><span data-stu-id="02898-286">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="02898-287">Le second `expression2` définit les index du ou des éléments à modifier par rapport au tableau dans `expression1` et doit être de type `Int` ou de type `Range` .</span><span class="sxs-lookup"><span data-stu-id="02898-287">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="02898-288">Si `expression2` est de type `Int` , `expression3` doit être de type `T` .</span><span class="sxs-lookup"><span data-stu-id="02898-288">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="02898-289">Si `expression2` est de type `Range` , `expression3` doit être de type `T[]` .</span><span class="sxs-lookup"><span data-stu-id="02898-289">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="02898-290">Une expression de copie et de mise à jour `arr w/ idx <- value` construit un nouveau tableau avec tous les éléments définis sur l’élément correspondant dans `arr` , à l’exception des éléments situés à `idx` , qui sont définis sur le ou les un (s) dans `value` .</span><span class="sxs-lookup"><span data-stu-id="02898-290">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="02898-291">Par exemple, si `arr` contient un tableau `[0,1,2,3]` ,</span><span class="sxs-lookup"><span data-stu-id="02898-291">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="02898-292">`arr w/ 0 <- 10`est le tableau `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="02898-292">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="02898-293">`arr w/ 2 <- 10`est le tableau `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="02898-293">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="02898-294">`arr w/ 0..2..3 <- [10,12]`est le tableau `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="02898-294">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="02898-295">Expressions de copie et de mise à jour pour les éléments nommés</span><span class="sxs-lookup"><span data-stu-id="02898-295">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="02898-296">Des expressions similaires existent pour les éléments nommés dans les types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="02898-296">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="02898-297">Prenons l’exemple du type</span><span class="sxs-lookup"><span data-stu-id="02898-297">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="02898-298">Si `c` contient la valeur de type `Complex(1., -1.)` , `c w/ Re <- 0.` est une expression de type qui prend la valeur `Complex` `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="02898-298">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="02898-299">Tableaux en escalier</span><span class="sxs-lookup"><span data-stu-id="02898-299">Jagged Arrays</span></span>

<span data-ttu-id="02898-300">Un tableau en escalier, parfois appelé « tableau de tableaux », est un tableau dont les éléments sont des tableaux.</span><span class="sxs-lookup"><span data-stu-id="02898-300">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="02898-301">Les éléments d’un tableau en escalier peuvent être de différentes tailles.</span><span class="sxs-lookup"><span data-stu-id="02898-301">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="02898-302">L’exemple suivant montre comment déclarer et initialiser un tableau en escalier représentant une table de multiplication.</span><span class="sxs-lookup"><span data-stu-id="02898-302">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="02898-303">Tableaux de callables</span><span class="sxs-lookup"><span data-stu-id="02898-303">Arrays of callables</span></span> 

<span data-ttu-id="02898-304">Notez qu’il est possible de trouver plus de détails sur les types pouvant être appelés ci-dessous, ainsi que sur la page suivante, [Operations and Functions in Q #](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="02898-304">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="02898-305">Si le type d’élément commun est un type d’opération ou de fonction, tous les éléments doivent avoir les mêmes types d’entrée et de sortie.</span><span class="sxs-lookup"><span data-stu-id="02898-305">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="02898-306">Le type d’élément du tableau prend en charge tous les functors pris en charge par tous les éléments.</span><span class="sxs-lookup"><span data-stu-id="02898-306">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="02898-307">Par exemple, si `Op1` , `Op2` et `Op3` sont tous des `Qubit[] => Unit` , mais prend en charge, prend en charge `Op1` `Adjoint` `Op2` `Controlled` et `Op3` prend en charge les deux :</span><span class="sxs-lookup"><span data-stu-id="02898-307">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="02898-308">`[Op1, Op2]`est un tableau d' `(Qubit[] => Unit)` opérations.</span><span class="sxs-lookup"><span data-stu-id="02898-308">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="02898-309">`[Op1, Op3]`est un tableau d' `(Qubit[] => Unit is Adj)` opérations.</span><span class="sxs-lookup"><span data-stu-id="02898-309">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="02898-310">`[Op2, Op3]`est un tableau d' `(Qubit[] => Unit is Ctl)` opérations.</span><span class="sxs-lookup"><span data-stu-id="02898-310">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="02898-311">Toutefois, tandis que `(Qubit[] => Unit is Adj)` `(Qubit[] => Unit is Ctl)` les opérations et ont le type de base commun de `(Qubit[] => Unit)` , Notez que les tableaux *de* ces opérateurs ne partagent pas un type de base commun.</span><span class="sxs-lookup"><span data-stu-id="02898-311">However, while `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` operations have the common base type of `(Qubit[] => Unit)`, note that arrays *of* these operators do not share a common base type.</span></span> <span data-ttu-id="02898-312">Par exemple, `[[Op1], [Op2]]` génère une erreur en raison d’une tentative de création d’un tableau des types de tableau incompatibles `(Qubit[] => Unit is Adj)[]` et de `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="02898-312">For example, `[[Op1], [Op2]]` would currently raise an error because it is attempting to create an array of the incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="02898-313">Expressions conditionnelles</span><span class="sxs-lookup"><span data-stu-id="02898-313">Conditional Expressions</span></span>

<span data-ttu-id="02898-314">À partir de deux autres expressions du même type et d’une expression booléenne, l’expression conditionnelle peut être formée à l’aide du point d’interrogation `?` et de la barre verticale `|` .</span><span class="sxs-lookup"><span data-stu-id="02898-314">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="02898-315">Par exemple, `a==b ? c | d` .</span><span class="sxs-lookup"><span data-stu-id="02898-315">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="02898-316">Dans cet exemple, la valeur de l’expression conditionnelle est `c` si a la valeur `a==b` true et `d` si elle est false.</span><span class="sxs-lookup"><span data-stu-id="02898-316">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="02898-317">Expressions conditionnelles avec callables</span><span class="sxs-lookup"><span data-stu-id="02898-317">Conditional expressions with callables</span></span>

<span data-ttu-id="02898-318">Les deux expressions peuvent être évaluées à des opérations qui ont les mêmes entrées et sorties, mais prennent en charge différents functors.</span><span class="sxs-lookup"><span data-stu-id="02898-318">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="02898-319">Dans ce cas, le type de l’expression conditionnelle est une opération avec les entrées et sorties qui prend en charge tous les functors pris en charge par les deux expressions.</span><span class="sxs-lookup"><span data-stu-id="02898-319">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="02898-320">Par exemple, si `Op1` , `Op2` et `Op3` sont tous des `Qubit[]=>Unit` , mais prend en charge, prend en charge `Op1` `Adjoint` `Op2` `Controlled` et `Op3` prend en charge les deux :</span><span class="sxs-lookup"><span data-stu-id="02898-320">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="02898-321">`flag ? Op1 | Op2`est une `(Qubit[] => Unit)` opération.</span><span class="sxs-lookup"><span data-stu-id="02898-321">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="02898-322">`flag ? Op1 | Op3`est une `(Qubit[] => Unit is Adj)` opération.</span><span class="sxs-lookup"><span data-stu-id="02898-322">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="02898-323">`flag ? Op2 | Op3`est une `(Qubit[] => Unit is Ctl)` opération.</span><span class="sxs-lookup"><span data-stu-id="02898-323">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="02898-324">Si l’une des deux expressions de résultat possibles inclut une fonction ou un appel d’opération, cet appel aura lieu uniquement si ce résultat est celui qui sera la valeur de l’appel.</span><span class="sxs-lookup"><span data-stu-id="02898-324">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="02898-325">Par exemple, dans le cas `a==b ? C(qs) | D(qs)` , si `a==b` a la valeur true, l' `C` opération est appelée, et si elle a la valeur false, seul `D` sera appelé.</span><span class="sxs-lookup"><span data-stu-id="02898-325">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="02898-326">Cela est similaire au court-circuit dans d’autres langages.</span><span class="sxs-lookup"><span data-stu-id="02898-326">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="02898-327">Expressions pouvant être appelées</span><span class="sxs-lookup"><span data-stu-id="02898-327">Callable Expressions</span></span>

<span data-ttu-id="02898-328">Un littéral pouvant être appelé est le nom d’une opération ou d’une fonction définie dans la portée de compilation.</span><span class="sxs-lookup"><span data-stu-id="02898-328">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="02898-329">Par exemple, `X` est un littéral d’opération qui fait référence à l’opération de bibliothèque standard `X` , et `Message` est un littéral de fonction qui fait référence à la fonction de bibliothèque standard `Message` .</span><span class="sxs-lookup"><span data-stu-id="02898-329">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="02898-330">Si une opération prend en charge `Adjoint` functor, `Adjoint op` est une expression d’opération.</span><span class="sxs-lookup"><span data-stu-id="02898-330">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="02898-331">De même, si l’opération prend en charge `Controlled` functor, `Controlled op` est une expression d’opération.</span><span class="sxs-lookup"><span data-stu-id="02898-331">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="02898-332">Les types de ces expressions sont spécifiés lors de l' [appel de spécialisations d’opérations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="02898-332">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="02898-333">Les functors ( `Adjoint` et `Controlled` ) lient plus étroitement que tous les autres opérateurs, à l’exception de l’opérateur Unwrap et de l' `!` indexation de tableau avec [] '.</span><span class="sxs-lookup"><span data-stu-id="02898-333">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="02898-334">Par conséquent, les éléments suivants sont tous valides, en supposant que les opérations prennent en charge les functors utilisés :</span><span class="sxs-lookup"><span data-stu-id="02898-334">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="02898-335">Expressions pouvant être appelées par type paramétrable</span><span class="sxs-lookup"><span data-stu-id="02898-335">Type-parameterized callable expressions</span></span>

<span data-ttu-id="02898-336">Un littéral pouvant être appelé peut être utilisé comme valeur, par exemple pour assigner à une variable ou pour passer à un autre pouvant être appelé.</span><span class="sxs-lookup"><span data-stu-id="02898-336">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="02898-337">Dans ce cas, si l’appelable possède des [paramètres de type](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), ceux-ci doivent être fournis dans le cadre de la valeur pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="02898-337">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="02898-338">Une valeur pouvant être appelée ne peut pas avoir de paramètres de type non spécifiés.</span><span class="sxs-lookup"><span data-stu-id="02898-338">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="02898-339">Par exemple, si `Fun` est une fonction avec signature `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="02898-339">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="02898-340">Expressions d’appel pouvant être appelées</span><span class="sxs-lookup"><span data-stu-id="02898-340">Callable Invocation Expressions</span></span>

<span data-ttu-id="02898-341">À partir d’une expression (opération ou fonction) pouvant être appelée et d’une expression de tuple du type d’entrée de la signature de l’appel, une expression d’appel peut être formée en ajoutant l’expression de tuple à l’expression pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="02898-341">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="02898-342">Le type de l’expression d’appel est le type de sortie de la signature de l’appelable.</span><span class="sxs-lookup"><span data-stu-id="02898-342">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="02898-343">Par exemple, si `Op` est une opération avec signature `((Int, Qubit) => Double)` , `Op(3, qubit1)` est une expression de type `Double` .</span><span class="sxs-lookup"><span data-stu-id="02898-343">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="02898-344">De même, si `Sin` est une fonction avec signature `(Double -> Double)` , `Sin(0.1)` est une expression de type `Double` .</span><span class="sxs-lookup"><span data-stu-id="02898-344">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="02898-345">Enfin, si `Builder` est une fonction avec signature `(Int -> (Int -> Int))` , `Builder(3)` est une fonction de into en int.</span><span class="sxs-lookup"><span data-stu-id="02898-345">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="02898-346">L’appel du résultat d’une expression de valeur pouvant être appelée nécessite une paire de parenthèses supplémentaires autour de l’expression pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="02898-346">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="02898-347">Ainsi, pour appeler le résultat de l’appel `Builder` à partir du paragraphe précédent, la syntaxe correcte est la suivante :</span><span class="sxs-lookup"><span data-stu-id="02898-347">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="02898-348">Lors de l’appel d’un pouvant être appelé [par un type paramétrable](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) , les paramètres de type réels peuvent être spécifiés entre crochets pointus `<` et `>` après l’expression pouvant être appelée.</span><span class="sxs-lookup"><span data-stu-id="02898-348">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="02898-349">Cela n’est généralement pas nécessaire, car le compilateur Q # déduira les types réels.</span><span class="sxs-lookup"><span data-stu-id="02898-349">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="02898-350">Toutefois, elle *est* requise pour une [application partielle](xref:microsoft.quantum.guide.operationsfunctions#partial-application) si un argument de type paramétrable n’est pas spécifié.</span><span class="sxs-lookup"><span data-stu-id="02898-350">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="02898-351">Elle est également parfois utile lors du passage d’opérations avec des prises en charge de functor différentes à un pouvant être appelé.</span><span class="sxs-lookup"><span data-stu-id="02898-351">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="02898-352">Par exemple, si `Func` a une signature, et possède la signature, `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` `(Qubit[] => Unit is Adj)` et `Op3` possède la signature `(Qubit[] => Unit)` , pour appeler en `Func` `Op1` tant que premier argument, `Op2` comme deuxième argument, et `Op3` comme troisième :</span><span class="sxs-lookup"><span data-stu-id="02898-352">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="02898-353">La spécification de type est requise, car `Op3` et `Op1` ont des types différents, de sorte que le compilateur traite cette opération comme ambiguë sans la spécification.</span><span class="sxs-lookup"><span data-stu-id="02898-353">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="02898-354">Priorité des opérateurs</span><span class="sxs-lookup"><span data-stu-id="02898-354">Operator Precedence</span></span>

<span data-ttu-id="02898-355">Tous les opérateurs binaires sont associatifs à droite, à l’exception de `^` .</span><span class="sxs-lookup"><span data-stu-id="02898-355">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="02898-356">Les crochets `[` et `]` , pour le découpage et l’indexation de tableaux, sont liés avant tout opérateur.</span><span class="sxs-lookup"><span data-stu-id="02898-356">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="02898-357">Functors `Adjoint` et `Controlled` Bind après l’indexation de tableau, mais avant tous les autres opérateurs.</span><span class="sxs-lookup"><span data-stu-id="02898-357">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="02898-358">Les parenthèses pour l’appel de l’opération et de la fonction sont également liées avant tout opérateur, mais après l’indexation et les functors du tableau.</span><span class="sxs-lookup"><span data-stu-id="02898-358">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="02898-359">Opérateurs par ordre de priorité, du plus élevé au plus bas :</span><span class="sxs-lookup"><span data-stu-id="02898-359">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="02898-360">Opérateur</span><span class="sxs-lookup"><span data-stu-id="02898-360">Operator</span></span> | <span data-ttu-id="02898-361">Arité</span><span class="sxs-lookup"><span data-stu-id="02898-361">Arity</span></span> | <span data-ttu-id="02898-362">Description</span><span class="sxs-lookup"><span data-stu-id="02898-362">Description</span></span> | <span data-ttu-id="02898-363">Types d’opérandes</span><span class="sxs-lookup"><span data-stu-id="02898-363">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="02898-364">fin`!`</span><span class="sxs-lookup"><span data-stu-id="02898-364">trailing `!`</span></span> | <span data-ttu-id="02898-365">Unaire</span><span class="sxs-lookup"><span data-stu-id="02898-365">Unary</span></span> | <span data-ttu-id="02898-366">Désencapsuler</span><span class="sxs-lookup"><span data-stu-id="02898-366">Unwrap</span></span> | <span data-ttu-id="02898-367">Tout type défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="02898-367">Any user-defined type</span></span>
 <span data-ttu-id="02898-368">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="02898-368">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="02898-369">Unaire</span><span class="sxs-lookup"><span data-stu-id="02898-369">Unary</span></span> | <span data-ttu-id="02898-370">Valeur numérique négative, complément au niveau du bit, négation logique</span><span class="sxs-lookup"><span data-stu-id="02898-370">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="02898-371">`Int`, `BigInt` ou pour, `Double` ou pour `-` `Int` `BigInt` `~~~` , `Bool` pour`not`</span><span class="sxs-lookup"><span data-stu-id="02898-371">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="02898-372">Binary</span><span class="sxs-lookup"><span data-stu-id="02898-372">Binary</span></span> | <span data-ttu-id="02898-373">Puissance entière</span><span class="sxs-lookup"><span data-stu-id="02898-373">Integer power</span></span> | <span data-ttu-id="02898-374">`Int`ou `BigInt` pour la base, `Int` pour l’exposant</span><span class="sxs-lookup"><span data-stu-id="02898-374">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="02898-375">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="02898-375">`/`, `*`, `%`</span></span> | <span data-ttu-id="02898-376">Binary</span><span class="sxs-lookup"><span data-stu-id="02898-376">Binary</span></span> | <span data-ttu-id="02898-377">Division, multiplication, modulo entier</span><span class="sxs-lookup"><span data-stu-id="02898-377">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="02898-378">`Int`, `BigInt` ou `Double` pour `/` et `*` , `Int` ou `BigInt` pour`%`</span><span class="sxs-lookup"><span data-stu-id="02898-378">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="02898-379">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="02898-379">`+`, `-`</span></span> | <span data-ttu-id="02898-380">Binary</span><span class="sxs-lookup"><span data-stu-id="02898-380">Binary</span></span> | <span data-ttu-id="02898-381">Addition ou concaténation de chaînes et de tableaux, soustraction</span><span class="sxs-lookup"><span data-stu-id="02898-381">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="02898-382">`Int`, `BigInt` ou `Double` , en plus `String` ou n’importe quel type de tableau pour`+`</span><span class="sxs-lookup"><span data-stu-id="02898-382">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="02898-383">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="02898-383">`<<<`, `>>>`</span></span> | <span data-ttu-id="02898-384">Binary</span><span class="sxs-lookup"><span data-stu-id="02898-384">Binary</span></span> | <span data-ttu-id="02898-385">Décalage vers la gauche, décalage vers la droite</span><span class="sxs-lookup"><span data-stu-id="02898-385">Left shift, right shift</span></span> | <span data-ttu-id="02898-386">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="02898-386">`Int` or `BigInt`</span></span>
 <span data-ttu-id="02898-387">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="02898-387">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="02898-388">Binary</span><span class="sxs-lookup"><span data-stu-id="02898-388">Binary</span></span> | <span data-ttu-id="02898-389">Comparaisons « inférieur à », « inférieur à », « supérieur à », « supérieur à » ou « égal à »</span><span class="sxs-lookup"><span data-stu-id="02898-389">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="02898-390">`Int`, `BigInt` ou`Double`</span><span class="sxs-lookup"><span data-stu-id="02898-390">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="02898-391">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="02898-391">`==`, `!=`</span></span> | <span data-ttu-id="02898-392">Binary</span><span class="sxs-lookup"><span data-stu-id="02898-392">Binary</span></span> | <span data-ttu-id="02898-393">comparaisons égales et non égales</span><span class="sxs-lookup"><span data-stu-id="02898-393">equal, not-equal comparisons</span></span> | <span data-ttu-id="02898-394">tout type primitif</span><span class="sxs-lookup"><span data-stu-id="02898-394">any primitive type</span></span>
 `&&&` | <span data-ttu-id="02898-395">Binary</span><span class="sxs-lookup"><span data-stu-id="02898-395">Binary</span></span> | <span data-ttu-id="02898-396">ET au niveau du bit</span><span class="sxs-lookup"><span data-stu-id="02898-396">Bitwise AND</span></span> | <span data-ttu-id="02898-397">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="02898-397">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="02898-398">Binary</span><span class="sxs-lookup"><span data-stu-id="02898-398">Binary</span></span> | <span data-ttu-id="02898-399">Opération de bits XOR</span><span class="sxs-lookup"><span data-stu-id="02898-399">Bitwise XOR</span></span> | <span data-ttu-id="02898-400">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="02898-400">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="02898-401">Binary</span><span class="sxs-lookup"><span data-stu-id="02898-401">Binary</span></span> | <span data-ttu-id="02898-402">Opération de bits OR</span><span class="sxs-lookup"><span data-stu-id="02898-402">Bitwise OR</span></span> | <span data-ttu-id="02898-403">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="02898-403">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="02898-404">Binary</span><span class="sxs-lookup"><span data-stu-id="02898-404">Binary</span></span> | <span data-ttu-id="02898-405">ET logique</span><span class="sxs-lookup"><span data-stu-id="02898-405">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="02898-406">Binary</span><span class="sxs-lookup"><span data-stu-id="02898-406">Binary</span></span> | <span data-ttu-id="02898-407">OU logique</span><span class="sxs-lookup"><span data-stu-id="02898-407">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="02898-408">Binaire/ternaire</span><span class="sxs-lookup"><span data-stu-id="02898-408">Binary/Ternary</span></span> | <span data-ttu-id="02898-409">Opérateur de plage</span><span class="sxs-lookup"><span data-stu-id="02898-409">Range operator</span></span> | `Int`
 <span data-ttu-id="02898-410">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="02898-410">`?` `|`</span></span> | <span data-ttu-id="02898-411">Gradient</span><span class="sxs-lookup"><span data-stu-id="02898-411">Ternary</span></span> | <span data-ttu-id="02898-412">Logique conditionnelle</span><span class="sxs-lookup"><span data-stu-id="02898-412">Conditional</span></span> | <span data-ttu-id="02898-413">`Bool`pour le côté gauche</span><span class="sxs-lookup"><span data-stu-id="02898-413">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="02898-414">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="02898-414">`w/` `<-`</span></span> | <span data-ttu-id="02898-415">Gradient</span><span class="sxs-lookup"><span data-stu-id="02898-415">Ternary</span></span> | <span data-ttu-id="02898-416">Copier et mettre à jour</span><span class="sxs-lookup"><span data-stu-id="02898-416">Copy-and-update</span></span> | <span data-ttu-id="02898-417">Voir les [expressions copy-and-Update](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="02898-417">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="02898-418">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="02898-418">Next steps</span></span>

<span data-ttu-id="02898-419">Maintenant que vous pouvez utiliser des expressions dans Q #, vous pouvez voir les [opérations et les fonctions dans q #](xref:microsoft.quantum.guide.operationsfunctions) pour savoir comment définir et appeler des opérations et des fonctions.</span><span class="sxs-lookup"><span data-stu-id="02898-419">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
