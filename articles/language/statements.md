---
title: 'Instructions Q # | Microsoft Docs'
description: 'Instructions Q #'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 9157cf3336ce0894816dbfbaf13ce0e712a6b096
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821063"
---
# <a name="statements-and-other-constructs"></a><span data-ttu-id="aaf6a-103">Instructions et autres constructions</span><span class="sxs-lookup"><span data-stu-id="aaf6a-103">Statements and Other Constructs</span></span>

## <a name="comments"></a><span data-ttu-id="aaf6a-104">Commentaires</span><span class="sxs-lookup"><span data-stu-id="aaf6a-104">Comments</span></span>

<span data-ttu-id="aaf6a-105">Les commentaires commencent par deux barres obliques, `//`et continuent jusqu’à la fin de la ligne.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-105">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="aaf6a-106">Un commentaire peut apparaître n’importe où dans un fichier source Q #.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-106">A comment may appear anywhere in a Q# source file.</span></span>

### <a name="documentation-comments"></a><span data-ttu-id="aaf6a-107">Commentaires sur la documentation</span><span class="sxs-lookup"><span data-stu-id="aaf6a-107">Documentation Comments</span></span>

<span data-ttu-id="aaf6a-108">Les commentaires qui commencent par trois barres obliques, `///`, sont traités spécialement par le compilateur lorsqu’ils apparaissent immédiatement avant un espace de noms, une opération, une spécialisation, une fonction ou une définition de type.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-108">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="aaf6a-109">Dans ce cas, leur contenu est utilisé comme documentation pour le type pouvant être appelé ou défini par l’utilisateur, comme pour d’autres langages .NET.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-109">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="aaf6a-110">Dans `///` commentaires, le texte à afficher dans le cadre de la documentation de l’API est mis en forme en tant que [démarque](https://daringfireball.net/projects/markdown/syntax), avec les différentes parties de la documentation indiquées par des en-têtes spécialement nommés.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-110">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="aaf6a-111">En tant qu’extension de la démarque, les références croisées aux opérations, aux fonctions et aux types définis par l’utilisateur dans Q # peuvent être incluses à l’aide de la `@"<ref target>"`, où `<ref target>` est remplacé par le nom qualifié complet de l’objet de code référencé.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-111">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="aaf6a-112">Le cas échéant, un moteur de documentation peut également prendre en charge des extensions de démarque supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-112">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="aaf6a-113">Exemple :</span><span class="sxs-lookup"><span data-stu-id="aaf6a-113">For example:</span></span>

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="aaf6a-114">Les noms suivants sont reconnus en tant qu’en-têtes de commentaires de documentation.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-114">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="aaf6a-115">**Résumé**: bref résumé du comportement d’une fonction ou d’une opération, ou de l’objectif d’un type.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-115">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="aaf6a-116">Le premier paragraphe du résumé est utilisé pour les informations de survol.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-116">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="aaf6a-117">Il doit s’agir d’un texte brut.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-117">It should be plain text.</span></span>
- <span data-ttu-id="aaf6a-118">**Description**: description du comportement d’une fonction ou d’une opération, ou de l’objectif d’un type.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-118">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="aaf6a-119">Le résumé et la description sont concaténés pour former le fichier de documentation généré pour la fonction, l’opération ou le type.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-119">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="aaf6a-120">La description peut contenir des équations et des symboles au format LaTeX en ligne.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-120">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="aaf6a-121">**Input**: description du tuple d’entrée d’une opération ou d’une fonction.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-121">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="aaf6a-122">Peut contenir des sous-sections de démarque supplémentaires indiquant chaque élément individuel du tuple d’entrée.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-122">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="aaf6a-123">**Sortie**: description du tuple retourné par une opération ou une fonction.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-123">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="aaf6a-124">**Paramètres de type**: section vide qui contient une sous-section supplémentaire pour chaque paramètre de type générique.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-124">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="aaf6a-125">**Exemple**: exemple bref de l’opération, de la fonction ou du type en cours d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-125">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="aaf6a-126">**Remarques**: divers Proseware décrivant certains aspects de l’opération, de la fonction ou du type.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-126">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="aaf6a-127">**Voir aussi**: liste de noms qualifiés complets indiquant les fonctions connexes, les opérations ou les types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-127">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="aaf6a-128">**Références**: liste de références et de citations pour l’élément documenté.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-128">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="namespaces"></a><span data-ttu-id="aaf6a-129">Espaces de noms</span><span class="sxs-lookup"><span data-stu-id="aaf6a-129">Namespaces</span></span>

<span data-ttu-id="aaf6a-130">Chaque opération Q #, fonction et type défini par l’utilisateur est défini dans un espace de noms.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-130">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>
<span data-ttu-id="aaf6a-131">Q # suit les mêmes règles d’affectation de noms que d’autres langages .NET.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-131">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="aaf6a-132">Toutefois, Q # ne prend pas en charge les références relatives aux espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-132">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="aaf6a-133">Autrement dit, si l’espace de noms `a.b` a été ouvert, une référence à des noms d’opérations `c.d` ne sera pas résolue en une opération portant le nom complet `a.b.c.d`.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-133">That is, if the namespace `a.b` has been opened, a reference to an operation names `c.d` will not be resolved to an operation with full name `a.b.c.d`.</span></span>

<span data-ttu-id="aaf6a-134">Dans un bloc d’espace de noms, la directive `open` peut être utilisée pour importer tous les types et callables déclarés dans un espace de noms donné et y faire référence par leur nom non qualifié.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-134">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span> <span data-ttu-id="aaf6a-135">Éventuellement, un nom abrégé pour l’espace de noms ouvert peut être défini de sorte que tous les éléments de cet espace de noms puissent (et doivent) être qualifiés par le nom abrégé défini.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-135">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="aaf6a-136">La directive `open` s’applique à l’intégralité du bloc d’espace de noms dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-136">The `open` directive applies to the entire namespace block within a file.</span></span>

<span data-ttu-id="aaf6a-137">Un type ou un appelable défini dans un autre espace de noms qui n’est pas ouvert dans l’espace de noms actuel doit être référencé par son nom complet.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-137">A type or callable defined in another namespace that is not opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="aaf6a-138">Par exemple, une opération nommée `Op` dans l’espace de noms `X.Y` doit être référencée par son nom qualifié complet `X.Y.Op`, sauf si l’espace de noms `X.Y` a été ouvert précédemment dans le bloc actuel.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-138">For example, an operation named `Op` in the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="aaf6a-139">Comme indiqué ci-dessus, même si l’espace de noms `X` a été ouvert, il n’est pas possible de faire référence à l’opération comme `Y.Op`.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-139">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="aaf6a-140">Si un nom abrégé `Z` pour `X.Y` a été défini dans cet espace de noms et dans ce fichier, `Op` doit être référencé comme `Z.Op`.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-140">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

<span data-ttu-id="aaf6a-141">Il est généralement préférable d’inclure un espace de noms à l’aide d’une directive `open`.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-141">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="aaf6a-142">L’utilisation d’un nom qualifié complet est requise si deux espaces de noms définissent des constructions portant le même nom, et la source actuelle utilise des constructions à partir des deux.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-142">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

## <a name="formatting"></a><span data-ttu-id="aaf6a-143">Mise en forme</span><span class="sxs-lookup"><span data-stu-id="aaf6a-143">Formatting</span></span>

<span data-ttu-id="aaf6a-144">La plupart des instructions et directives Q # se terminent par un point-virgule de fin, `;`.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-144">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="aaf6a-145">Les instructions et les déclarations, telles que `for` et `operation` qui se terminent par un bloc d’instructions, ne nécessitent pas de point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-145">Statements and declarations such as `for` and `operation` that end with a statement block do not require a terminating semicolon.</span></span>
<span data-ttu-id="aaf6a-146">Chaque description d’instruction indique si le point-virgule de fin est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-146">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="aaf6a-147">Les instructions, comme les expressions, les déclarations et les directives, peuvent être réparties sur plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-147">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="aaf6a-148">L’utilisation de plusieurs instructions sur une seule ligne doit être évitée.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-148">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="aaf6a-149">Blocs d’instructions</span><span class="sxs-lookup"><span data-stu-id="aaf6a-149">Statement Blocks</span></span>

<span data-ttu-id="aaf6a-150">Les instructions Q # sont regroupées dans des blocs d’instructions.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-150">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="aaf6a-151">Un bloc d’instructions commence par un `{` ouvrant et se termine par un `}`de fermeture.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-151">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="aaf6a-152">Un bloc d’instructions placé lexicalement dans un autre bloc est considéré comme un sous-bloc du bloc conteneur. les blocs conteneur et secondaires sont également appelés blocs externes et internes.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-152">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="symbol-binding-and-assignment"></a><span data-ttu-id="aaf6a-153">Liaison et assignation de symboles</span><span class="sxs-lookup"><span data-stu-id="aaf6a-153">Symbol Binding and Assignment</span></span>

<span data-ttu-id="aaf6a-154">Q # distingue les symboles mutables et immuables.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-154">Q# distinguishes between mutable and immutable symbols.</span></span>
<span data-ttu-id="aaf6a-155">En général, l’utilisation de symboles immuables est encouragée, car elle permet au compilateur d’effectuer des optimisations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-155">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="aaf6a-156">La partie gauche de la liaison se compose d’un tuple de symboles et de la partie droite d’une expression.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-156">The left-hand-side of the binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

<span data-ttu-id="aaf6a-157">Étant donné que tous les types Q # sont des types valeur, avec le qubits qui prend un rôle un peu spécial, il est formellement créé une « copie » lorsqu’une valeur est liée à un symbole, ou lorsqu’un symbole est relié.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-157">Since all Q# types are value types - with the qubits taking a somewhat special role - formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="aaf6a-158">Autrement dit, le comportement de Q # est le même que si une copie a été créée lors de l’assignation.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-158">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span> <span data-ttu-id="aaf6a-159">En particulier, cela comprend également des tableaux.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-159">This in particular also includes arrays.</span></span> <span data-ttu-id="aaf6a-160">Bien entendu, dans la pratique, seuls les éléments pertinents sont recréés en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-160">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

### <a name="tuple-deconstruction"></a><span data-ttu-id="aaf6a-161">Déconstruction de Tuple</span><span class="sxs-lookup"><span data-stu-id="aaf6a-161">Tuple Deconstruction</span></span>

<span data-ttu-id="aaf6a-162">Si le côté droit de la liaison est un tuple, ce tuple peut être déconstruit lors de l’assignation.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-162">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="aaf6a-163">Ces déconstructions peuvent impliquer des tuples imbriqués, et toute déconstruction complète ou partielle est valide tant que la forme du tuple sur le côté droit est compatible avec la forme du tuple de symbole.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-163">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>
<span data-ttu-id="aaf6a-164">La déconstruction de tuple peut également être utilisée lorsque le côté droit du `=` est une expression de valeur de Tuple.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-164">Tuple deconstruction can in particular also be used when the right-hand side of the `=` is a tuple-valued expression.</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a><span data-ttu-id="aaf6a-165">Symboles immuables</span><span class="sxs-lookup"><span data-stu-id="aaf6a-165">Immutable Symbols</span></span>

<span data-ttu-id="aaf6a-166">Les symboles immuables sont liés à l’aide de l’instruction `let`.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-166">Immutable symbols are bound using the `let` statement.</span></span>
<span data-ttu-id="aaf6a-167">Cela équivaut à peu près à la déclaration et à l’initialisation des variables C#dans des langages tels que, sauf que les symboles Q #, une fois liés, ne peuvent pas être modifiés. les liaisons de `let` sont immuables.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-167">This is roughly equivalent to variable declaration and initialization in languages such as C#, except that Q# symbols, once bound, may not be changed; `let` bindings are immutable.</span></span>

<span data-ttu-id="aaf6a-168">Une liaison immuable se compose du mot clé `let`, suivi d’un symbole ou d’un tuple de symboles, d’un signe égal `=`, d’une expression pour lier le ou des symboles à et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-168">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="aaf6a-169">Le type du ou des symboles liés est déduit en fonction de l’expression sur le côté droit.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-169">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span>

### <a name="mutable-symbols"></a><span data-ttu-id="aaf6a-170">Symboles mutables</span><span class="sxs-lookup"><span data-stu-id="aaf6a-170">Mutable Symbols</span></span>

<span data-ttu-id="aaf6a-171">Les symboles mutables sont définis et initialisés à l’aide de l’instruction `mutable`.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-171">Mutable symbols are defined and initialized using the `mutable` statement.</span></span>
<span data-ttu-id="aaf6a-172">Les symboles déclarés et liés dans le cadre d’une instruction `mutable` peuvent être reliés à une valeur différente ultérieurement dans le code.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-172">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> 

<span data-ttu-id="aaf6a-173">Une instruction de liaison mutable se compose du mot clé `mutable`, suivi d’un symbole ou d’un tuple de symbole, d’un signe égal `=`, d’une expression pour lier le ou des symboles à et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-173">A mutable binding statement consists of the keyword `mutable`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="aaf6a-174">Le type du ou des symboles liés est déduit en fonction de l’expression sur le côté droit.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-174">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span> <span data-ttu-id="aaf6a-175">Si un symbole est relié ultérieurement dans le code, son type ne change pas et la valeur liée doit être compatible avec ce type.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-175">If a symbol is rebound later in the code, its type does not change, and the bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="aaf6a-176">Reliaison de symboles mutables</span><span class="sxs-lookup"><span data-stu-id="aaf6a-176">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="aaf6a-177">Une variable mutable peut être reliée à l’aide d’une instruction `set`.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-177">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="aaf6a-178">Une telle reliaison se compose du mot clé `set`, suivi d’un symbole ou d’un tuple de symbole, d’un signe égal `=`, d’une expression pour relier le ou des symboles à et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-178">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="aaf6a-179">La valeur doit être compatible avec le ou les types du ou des symboles auxquels elle est liée.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-179">The value must be compatible with the type(s) of the symbol(s) it is bound to.</span></span>

#### <a name="apply-and-reassign-statement"></a><span data-ttu-id="aaf6a-180">Apply-and-réassign (instruction)</span><span class="sxs-lookup"><span data-stu-id="aaf6a-180">Apply-and-Reassign Statement</span></span>

<span data-ttu-id="aaf6a-181">Un type particulier d’instruction SET, que nous appelons instruction Apply-and-réassign, offre un moyen pratique de concaténer si le côté droit est constitué de l’application d’un opérateur binaire et que le résultat doit être relié à l’argument Left à l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-181">A particular kind of set-statement we refer to as an apply-and-reassign statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="aaf6a-182">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="aaf6a-182">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="aaf6a-183">incrémente la valeur du compteur `counter` dans chaque itération de la boucle `for`.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-183">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="aaf6a-184">Le code ci-dessus équivaut à</span><span class="sxs-lookup"><span data-stu-id="aaf6a-184">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
<span data-ttu-id="aaf6a-185">Des instructions similaires sont disponibles pour tous les opérateurs binaires dans lesquels le type du côté gauche correspond au type d’expression.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-185">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="aaf6a-186">Cela fournit un moyen pratique pour accumuler les valeurs :</span><span class="sxs-lookup"><span data-stu-id="aaf6a-186">This provides for example a convenient way to accumulate values:</span></span>
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a><span data-ttu-id="aaf6a-187">Instruction Update-and-Assign</span><span class="sxs-lookup"><span data-stu-id="aaf6a-187">Update-and-Reassign Statement</span></span>

<span data-ttu-id="aaf6a-188">Une concaténation similaire existe pour les expressions de copie et de mise à jour sur le côté droit.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-188">A similar concatenation exists for copy-and-update expressions on the right hand side.</span></span> <span data-ttu-id="aaf6a-189">En conséquence, les instructions Update-and-Assign existent pour les éléments nommés dans les types définis par l’utilisateur, ainsi que pour les éléments de tableau.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-189">Correspondingly, update-and-reassign statements exist for named items in user-defined types as well as for array items.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ElementwisePlus(reals : Double[], ims : Double[]) : Complex[] {
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

<span data-ttu-id="aaf6a-190">Dans le cas de tableaux, nos bibliothèques standard contiennent les outils nécessaires pour de nombreux besoins d’initialisation et de manipulation de tableaux courants, et permettent ainsi d’éviter d’avoir à mettre à jour les éléments de tableau en premier lieu.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-190">In the case of arrays, our standard libraries contain the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> <span data-ttu-id="aaf6a-191">Les instructions Update-and-Assign fournissent une alternative si nécessaire :</span><span class="sxs-lookup"><span data-stu-id="aaf6a-191">Update-and-reassign statements provide an alternative if needed:</span></span>

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

> [!TIP]   
> <span data-ttu-id="aaf6a-192">Évitez l’utilisation inutile des instructions Update-and-Assign en tirant parti des outils fournis dans <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-192">Avoid unnecessary use of update-and-reassign statements by leveraging the tools provided in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="aaf6a-193">La fonction</span><span class="sxs-lookup"><span data-stu-id="aaf6a-193">The function</span></span>
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
<span data-ttu-id="aaf6a-194">par exemple, il est simple de simplifier l’utilisation de la fonction `ConstantArray` dans `Microsoft.Quantum.Arrays`, et de retourner une expression de copie et de mise à jour :</span><span class="sxs-lookup"><span data-stu-id="aaf6a-194">for example can simply be simplified using the function `ConstantArray` in `Microsoft.Quantum.Arrays`, and returning a copy-and-update expression:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a><span data-ttu-id="aaf6a-195">Portées de liaison</span><span class="sxs-lookup"><span data-stu-id="aaf6a-195">Binding Scopes</span></span>

<span data-ttu-id="aaf6a-196">En général, les liaisons de symboles sont hors de portée et deviennent inopérantes à la fin du bloc d’instructions dans lequel elles se produisent.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-196">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="aaf6a-197">Il y a deux exceptions à cette règle :</span><span class="sxs-lookup"><span data-stu-id="aaf6a-197">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="aaf6a-198">La liaison de la variable de boucle d’une boucle `for` se trouve dans la portée du corps de la boucle for, mais pas après la fin de la boucle.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-198">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="aaf6a-199">Les trois parties d’une `repeat`/`until` boucle (le corps, le test et la correction) sont traitées comme une seule portée. les symboles liés dans le corps sont donc disponibles dans le test et dans la correction.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-199">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="aaf6a-200">Pour les deux types de boucles, chaque passe dans la boucle s’exécute dans sa propre portée, de sorte que les liaisons d’une passe antérieure ne sont pas disponibles dans une étape ultérieure.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-200">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>

<span data-ttu-id="aaf6a-201">Les liaisons de symboles des blocs externes sont héritées par les blocs internes.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-201">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="aaf6a-202">Un symbole ne peut être lié qu’une seule fois par bloc ; Il est interdit de définir un symbole portant le même nom qu’un autre symbole dans la portée (sans « occultation »).</span><span class="sxs-lookup"><span data-stu-id="aaf6a-202">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="aaf6a-203">Les séquences suivantes sont valides :</span><span class="sxs-lookup"><span data-stu-id="aaf6a-203">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="aaf6a-204">et la</span><span class="sxs-lookup"><span data-stu-id="aaf6a-204">and</span></span>

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
```

<span data-ttu-id="aaf6a-205">Mais cela ne serait pas conforme :</span><span class="sxs-lookup"><span data-stu-id="aaf6a-205">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="aaf6a-206">comme cela :</span><span class="sxs-lookup"><span data-stu-id="aaf6a-206">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a><span data-ttu-id="aaf6a-207">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="aaf6a-207">Control Flow</span></span>

### <a name="for-loop"></a><span data-ttu-id="aaf6a-208">Boucle For</span><span class="sxs-lookup"><span data-stu-id="aaf6a-208">For Loop</span></span>

<span data-ttu-id="aaf6a-209">L’instruction `for` prend en charge l’itération sur une plage d’entiers ou sur un tableau.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-209">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="aaf6a-210">L’instruction se compose du mot clé `for`, d’une parenthèse ouvrante `(`, suivi d’un symbole ou d’un tuple de symbole, du mot clé `in`, d’une expression de type `Range` ou tableau, d’une parenthèse fermante `)`et d’un bloc d’instructions.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-210">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="aaf6a-211">Le bloc d’instructions (corps de la boucle) est exécuté à plusieurs reprises, avec les symboles définis (la ou les variables de boucle) liés à chaque valeur dans la plage ou le tableau.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-211">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="aaf6a-212">Notez que si l’expression de plage a la valeur d’une plage ou d’un tableau vide, le corps ne sera pas exécuté.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-212">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="aaf6a-213">L’expression est entièrement évaluée avant d’entrer dans la boucle et ne change pas pendant l’exécution de la boucle.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-213">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="aaf6a-214">La liaison du ou des symboles déclarés est immuable et suit les mêmes règles que les autres liaisons de variables.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-214">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> <span data-ttu-id="aaf6a-215">En particulier, il est possible de détruire, par exemple, les éléments de tableau pour une itération sur un tableau lors de l’assignation à la ou aux variables de boucle.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-215">In particular, it is possible to destruct e.g. array items for an iteration over an array upon assignment to the loop variable(s).</span></span>

<span data-ttu-id="aaf6a-216">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="aaf6a-216">For example,</span></span>

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="aaf6a-217">La variable de boucle est liée à chaque entrée dans le corps de la boucle et est détachée à la fin du corps.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-217">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="aaf6a-218">En particulier, la variable de boucle n’est pas liée après la fin de la boucle for.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-218">In particular, the loop variable is not bound after the for loop is completed.</span></span>

### <a name="repeat-until-success-loop"></a><span data-ttu-id="aaf6a-219">Répéter jusqu’à la réussite de la boucle</span><span class="sxs-lookup"><span data-stu-id="aaf6a-219">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="aaf6a-220">L’instruction `repeat` prend en charge le modèle Quantum « répéter jusqu’à la réussite ».</span><span class="sxs-lookup"><span data-stu-id="aaf6a-220">The `repeat` statement supports the quantum “repeat until success” pattern.</span></span>
<span data-ttu-id="aaf6a-221">Il se compose du mot clé `repeat`, suivi d’un bloc d’instructions (corps de la _boucle_ ), du mot clé `until`, d’une expression booléenne et d’un point-virgule de fin ou du mot clé `fixup` suivi d’un autre bloc d’instructions (la _Correction_).</span><span class="sxs-lookup"><span data-stu-id="aaf6a-221">It consists of the keyword `repeat`, followed by a statement block (the _loop_ body), the keyword `until`, a Boolean expression, and either a terminating semicolon or the keyword `fixup` followed by another statement block (the _fixup_).</span></span>
<span data-ttu-id="aaf6a-222">Le corps de la boucle, la condition et la correction sont tous considérés comme une seule étendue, de sorte que les symboles liés dans le corps sont disponibles dans la condition et la correction.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-222">The loop body, condition, and fixup are all considered to be a single scope, so symbols bound in the body are available in the condition and fixup.</span></span>

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

<span data-ttu-id="aaf6a-223">Le corps de la boucle est exécuté, puis la condition est évaluée.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-223">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="aaf6a-224">Si la condition est true, l’instruction est terminée ; dans le cas contraire, la correction est exécutée et l’instruction est réexécutée en commençant par le corps de la boucle.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-224">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>
<span data-ttu-id="aaf6a-225">Notez que l’exécution de la correction met fin à l’étendue de l’instruction, de sorte que les liaisons de symboles effectuées pendant le corps ou la correction ne sont pas disponibles dans les répétitions suivantes.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-225">Note that completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="aaf6a-226">Par exemple, le code suivant est un circuit probabiliste qui implémente une porte de rotation importante $V _3 = (\boldone + 2 i Z)/\sqrt{5}$ à l’aide des portes Hadarmard et T.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-226">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the Hadamard and T gates.</span></span>
<span data-ttu-id="aaf6a-227">La boucle se termine dans $ \frac{8}{5}$ répétitions en moyenne.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-227">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="aaf6a-228">Pour plus d’informations, consultez [*répéter jusqu’à la réussite : décomposition non déterministe des unités de qubit de données uniques*](https://arxiv.org/abs/1311.1074) (Paetznick et Svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="aaf6a-228">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for details.</span></span>

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

> [!TIP]   
> <span data-ttu-id="aaf6a-229">Évitez d’utiliser des boucles de répétition jusqu’à réussite dans les fonctions.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-229">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="aaf6a-230">Les fonctionnalités correspondantes sont fournies par les boucles While dans les fonctions.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-230">The corresponding functionality is provided by while loops in functions.</span></span> 

### <a name="while-loop"></a><span data-ttu-id="aaf6a-231">Boucle while</span><span class="sxs-lookup"><span data-stu-id="aaf6a-231">While Loop</span></span>

<span data-ttu-id="aaf6a-232">Les modèles de répétition jusqu’à réussite ont un connotation très spécifique au quantum.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-232">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="aaf6a-233">Elles sont largement utilisées dans des classes particulières d’algorithmes Quantum, donc la construction du langage dédié dans Q #.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-233">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="aaf6a-234">Toutefois, les boucles qui s’arrêtent en fonction d’une condition et dont la longueur d’exécution est donc inconnue au moment de la compilation doivent être gérées avec une attention particulière dans un Runtime Quantum.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-234">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="aaf6a-235">Leur utilisation dans les fonctions en revanche pose un problème, car celles-ci contiennent uniquement du code qui sera exécuté sur du matériel conventionnel (non Quantum).</span><span class="sxs-lookup"><span data-stu-id="aaf6a-235">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="aaf6a-236">Q # prend donc en charge l’utilisation de boucles While uniquement dans les fonctions.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-236">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="aaf6a-237">Une instruction `while` se compose du mot clé `while`, d’une parenthèse ouvrante `(`, d’une condition (c’est-à-dire une expression booléenne), d’une parenthèse fermante `)`et d’un bloc d’instructions.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-237">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="aaf6a-238">Le bloc d’instructions (corps de la boucle) est exécuté tant que la condition a la valeur `true`.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-238">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a><span data-ttu-id="aaf6a-239">Instruction conditionnelle</span><span class="sxs-lookup"><span data-stu-id="aaf6a-239">Conditional Statement</span></span>

<span data-ttu-id="aaf6a-240">L’instruction `if` prend en charge l’exécution conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-240">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="aaf6a-241">Il se compose du mot clé `if`, d’une parenthèse ouvrante `(`, d’une expression booléenne, d’une parenthèse fermante `)`et d’un bloc d’instructions (bloc _Then_ ).</span><span class="sxs-lookup"><span data-stu-id="aaf6a-241">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="aaf6a-242">Il peut être suivi d’un nombre quelconque de clauses Else-If, chacune comprenant le mot clé `elif`, une parenthèse ouvrante `(`, une expression booléenne, une parenthèse fermante `)`et un bloc d’instructions (le bloc _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="aaf6a-242">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="aaf6a-243">Enfin, l’instruction peut éventuellement se terminer par une clause Else, qui se compose du mot clé `else` suivi d’un autre bloc d’instructions (le bloc _else_ ).</span><span class="sxs-lookup"><span data-stu-id="aaf6a-243">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>
<span data-ttu-id="aaf6a-244">La condition est évaluée, et si elle a la valeur true, le bloc Then est exécuté.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-244">The condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="aaf6a-245">Si la condition est false, la première condition else-if est évaluée ; Si la valeur est true, le bloc Else-If est exécuté.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-245">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="aaf6a-246">Dans le cas contraire, le deuxième bloc Else-If est testé, puis le troisième, et ainsi de suite jusqu’à ce qu’une clause avec une condition true soit rencontrée ou qu’il n’y ait plus aucune clause else-if.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-246">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="aaf6a-247">Si la condition if d’origine et toutes les clauses Else-If ont la valeur false, le bloc Else est exécuté s’il en a été fourni.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-247">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="aaf6a-248">Notez que le bloc qui est exécuté est exécuté dans sa propre portée.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-248">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="aaf6a-249">Les liaisons effectuées à l’intérieur d’un bloc Then, else-if ou Else ne sont pas visibles après la fin de l’instruction if.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-249">Bindings made inside of a then, else-if, or else block are not visible after the end of the if statement.</span></span>

<span data-ttu-id="aaf6a-250">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="aaf6a-250">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
} 
```

<span data-ttu-id="aaf6a-251">ou</span><span class="sxs-lookup"><span data-stu-id="aaf6a-251">or</span></span>

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a><span data-ttu-id="aaf6a-252">Renvoie</span><span class="sxs-lookup"><span data-stu-id="aaf6a-252">Return</span></span>

<span data-ttu-id="aaf6a-253">L’instruction return termine l’exécution d’une opération ou d’une fonction et retourne une valeur à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-253">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="aaf6a-254">Il se compose du mot clé `return`, suivi d’une expression du type approprié et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-254">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="aaf6a-255">Un pouvant être appelé qui retourne un tuple vide, `()`, ne requiert pas d’instruction return.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-255">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="aaf6a-256">Si vous souhaitez une sortie précoce, `return ()` peut être utilisée dans ce cas.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-256">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="aaf6a-257">Les callables qui retournent tout autre type requièrent une instruction return finale.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-257">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="aaf6a-258">Il n’y a pas de nombre maximal d’instructions return dans une opération.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-258">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="aaf6a-259">Le compilateur peut émettre un avertissement si les instructions suivent une instruction return dans un bloc.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-259">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="aaf6a-260">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="aaf6a-260">For example,</span></span>

```qsharp
return 1;
```

<span data-ttu-id="aaf6a-261">ou</span><span class="sxs-lookup"><span data-stu-id="aaf6a-261">or</span></span>

```qsharp
return ();
```

<span data-ttu-id="aaf6a-262">ou</span><span class="sxs-lookup"><span data-stu-id="aaf6a-262">or</span></span>

```qsharp
return (results, qubits);
```

### <a name="fail"></a><span data-ttu-id="aaf6a-263">Échec</span><span class="sxs-lookup"><span data-stu-id="aaf6a-263">Fail</span></span>

<span data-ttu-id="aaf6a-264">L’instruction Fail termine l’exécution d’une opération et retourne une valeur d’erreur à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-264">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="aaf6a-265">Il se compose du mot clé `fail`, suivi d’une chaîne et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-265">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="aaf6a-266">La chaîne est retournée au pilote classique comme message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-266">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="aaf6a-267">Il n’existe aucune restriction sur le nombre d’instructions d’échec au sein d’une opération.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-267">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="aaf6a-268">Le compilateur peut émettre un avertissement si les instructions suivent une instruction Fail dans un bloc.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-268">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="aaf6a-269">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="aaf6a-269">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```

<span data-ttu-id="aaf6a-270">ou</span><span class="sxs-lookup"><span data-stu-id="aaf6a-270">or</span></span>

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a><span data-ttu-id="aaf6a-271">Gestion de qubit</span><span class="sxs-lookup"><span data-stu-id="aaf6a-271">Qubit Management</span></span>

<span data-ttu-id="aaf6a-272">Notez qu’aucune de ces instructions n’est autorisée dans le corps d’une fonction.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-272">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="aaf6a-273">Elles ne sont valides que dans les opérations.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-273">They are only valid within operations.</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="aaf6a-274">Nettoyer qubits</span><span class="sxs-lookup"><span data-stu-id="aaf6a-274">Clean Qubits</span></span>

<span data-ttu-id="aaf6a-275">L’instruction `using` permet d’acquérir de nouvelles qubits à utiliser lors d’un bloc d’instructions.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-275">The `using` statement is used to acquire new qubits for use during a statement block.</span></span>
<span data-ttu-id="aaf6a-276">Les qubits sont assurés d’être initialisés à l’état de `Zero` de calcul.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-276">The qubits are guaranteed to be initialized to the computational `Zero` state.</span></span>
<span data-ttu-id="aaf6a-277">Le qubits doit être dans l’état de `Zero` de calcul à la fin du bloc d’instructions ; les simulateurs sont encouragés à appliquer cela.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-277">The qubits should be in the computational `Zero` state at the end of the statement block; simulators are encouraged to enforce this.</span></span>

<span data-ttu-id="aaf6a-278">L’instruction se compose du mot clé `using`, suivi d’une parenthèse ouvrante `(`, d’une liaison, d’une parenthèse fermante `)`et du bloc d’instructions dans lequel qubits sera disponible.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-278">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="aaf6a-279">La liaison suit le même modèle que `let` instructions : un symbole unique ou un tuple de symboles, suivi d’un signe égal `=`et une valeur unique ou un tuple correspondant d’initialiseurs.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-279">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of initializers.</span></span>
<span data-ttu-id="aaf6a-280">Les initialiseurs sont disponibles pour un qubit unique, indiqué comme `Qubit()`, ou un tableau de qubits, indiqué par `Qubit[`, une expression `Int` et `]`.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-280">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, indicated by `Qubit[`, an `Int` expression, and `]`.</span></span>

<span data-ttu-id="aaf6a-281">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="aaf6a-281">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a><span data-ttu-id="aaf6a-282">Qubits empruntés</span><span class="sxs-lookup"><span data-stu-id="aaf6a-282">Borrowed Qubits</span></span>

<span data-ttu-id="aaf6a-283">L’instruction `borrowing` permet d’obtenir des qubits pour une utilisation temporaire.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-283">The `borrowing` statement is used to obtain qubits for temporary use.</span></span> <span data-ttu-id="aaf6a-284">L’instruction se compose du mot clé `borrowing`, suivi d’une parenthèse ouvrante `(`, d’une liaison, d’une parenthèse fermante `)`et du bloc d’instructions dans lequel qubits sera disponible.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-284">The statement consists of the keyword `borrowing`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="aaf6a-285">La liaison suit le même modèle et les mêmes règles que celle d’une instruction `using`.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-285">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>

<span data-ttu-id="aaf6a-286">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="aaf6a-286">For example,</span></span>

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

<span data-ttu-id="aaf6a-287">Le qubits emprunté est dans un état inconnu et est hors de portée à la fin du bloc d’instructions.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-287">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="aaf6a-288">L’emprunteur s’engage à laisser le qubits dans le même État que celui dans lequel il se trouvait lorsqu’il a été emprunté, c’est-à-dire que son état au début et à la fin du bloc d’instructions est supposé être le même.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-288">The borrower commits to leaving the qubits in the same state they were in when they were borrowed, i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="aaf6a-289">En particulier, cet État n’est pas nécessairement un État classique, ce qui signifie que dans la plupart des cas, les étendues d’emprunt ne doivent pas contenir de mesures.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-289">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="aaf6a-290">Pour obtenir un exemple d’utilisation Svore empruntée, voir [*factorisation à l’aide de 2n + 2 qubits avec la multiplication modulaire basée sur Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler et qubit 2017).</span><span class="sxs-lookup"><span data-stu-id="aaf6a-290">See [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an example of borrowed qubit use.</span></span>

<span data-ttu-id="aaf6a-291">Lorsque vous empruntez des qubits, le système tente d’abord de remplir la demande à partir de qubits qui sont en cours d’utilisation, mais qui ne sont pas accessibles pendant le corps de l’instruction `borrowing`.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-291">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="aaf6a-292">S’il n’y a pas suffisamment de qubits, il allouera de nouvelles qubits pour terminer la demande.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-292">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>

## <a name="conjugations"></a><span data-ttu-id="aaf6a-293">Conjugaisons</span><span class="sxs-lookup"><span data-stu-id="aaf6a-293">Conjugations</span></span>

<span data-ttu-id="aaf6a-294">Contrairement aux bits classiques, la libération de la mémoire Quantum est un peu plus complexe, car la réinitialisation aveugle de qubits peut avoir des effets indésirables sur le calcul restant si les qubits sont toujours pris en compte.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-294">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="aaf6a-295">Cela peut être évité en « annulant » les calculs effectués avant la libération de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-295">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="aaf6a-296">Un modèle courant dans quantum computing est donc le suivant :</span><span class="sxs-lookup"><span data-stu-id="aaf6a-296">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="aaf6a-297">: nouveauté : à partir de notre version 0,9, nous prenons en charge une instruction de conjugaison qui implémente la transformation ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-297">:new: Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="aaf6a-298">À l’aide de cette instruction, l’opération `ApplyWith` peut être implémentée de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="aaf6a-298">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="aaf6a-299">Une telle instruction de conjugaison devient évidemment beaucoup plus utile si les transformations externes et internes ne sont pas facilement disponibles en tant qu’opérations, mais sont plutôt plus pratiques à décrire par un bloc composé de plusieurs instructions.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-299">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="aaf6a-300">La transformation inverse pour les instructions définies dans le bloc intérieur est générée automatiquement par le compilateur et exécutée après la fin du bloc apply.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-300">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span> <span data-ttu-id="aaf6a-301">Étant donné que toutes les variables mutables utilisées dans le cadre du bloc within ne peuvent pas être reliées dans le bloc Apply, il est garanti que la transformation générée est le voisin du calcul dans le bloc intérieur.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-301">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="expression-evaluation-statements"></a><span data-ttu-id="aaf6a-302">Instructions d’évaluation d’expression</span><span class="sxs-lookup"><span data-stu-id="aaf6a-302">Expression Evaluation Statements</span></span>

<span data-ttu-id="aaf6a-303">Toute expression d’appel de type `Unit` peut être utilisée en tant qu’instruction.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-303">Any call expression of type `Unit` may be used as a statement.</span></span>
<span data-ttu-id="aaf6a-304">Cela est principalement utilisé lors de l’appel d’opérations sur des qubits qui retournent `Unit`, car l’objectif de l’instruction est de modifier l’État Quantum implicite.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-304">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="aaf6a-305">Les instructions d’évaluation d’expression requièrent un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="aaf6a-305">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="aaf6a-306">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="aaf6a-306">For example,</span></span>

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
