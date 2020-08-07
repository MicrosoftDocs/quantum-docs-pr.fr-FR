---
title: Q#Structure de fichier
description: Décrit la structure et la syntaxe d’un Q# fichier.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: ac73962b1a718cd04aa87ee3476c66781fe3ac2b
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867928"
---
# <a name="no-locq-file-structure"></a><span data-ttu-id="77d56-103">Q#Structure de fichier</span><span class="sxs-lookup"><span data-stu-id="77d56-103">Q# File Structure</span></span>

<span data-ttu-id="77d56-104">Un Q# fichier se compose d’une séquence de *déclarations d’espaces de noms*.</span><span class="sxs-lookup"><span data-stu-id="77d56-104">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="77d56-105">Chaque déclaration d’espace de noms contient des déclarations pour les types, les opérations et les fonctions définis par l’utilisateur, et peut contenir n’importe quel nombre de chaque type de déclaration et dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="77d56-105">Each namespace declaration contains declarations for user-defined types, operations, and functions, and can contain any number of each type of declaration and in any order.</span></span>
<span data-ttu-id="77d56-106">Pour plus d’informations sur les déclarations au sein d’un espace de noms, consultez types, [opérations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)et [fonctions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) [définis par l’utilisateur](xref:microsoft.quantum.guide.types#user-defined-types).</span><span class="sxs-lookup"><span data-stu-id="77d56-106">For more information on declarations within a namespace, see [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span></span>

<span data-ttu-id="77d56-107">Le seul texte qui peut apparaître en dehors d’une déclaration d’espace de noms est un commentaire.</span><span class="sxs-lookup"><span data-stu-id="77d56-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="77d56-108">En particulier, les commentaires de documentation pour un espace de noms précèdent la déclaration.</span><span class="sxs-lookup"><span data-stu-id="77d56-108">In particular, documentation comments for a namespace precede the declaration.</span></span> <span data-ttu-id="77d56-109">Pour plus d’informations, consultez [Commentaires sur la documentation](#documentation-comments) dans cet article.</span><span class="sxs-lookup"><span data-stu-id="77d56-109">For more information, see [Documentation comments](#documentation-comments) in this article.</span></span> 

## <a name="namespace-declarations"></a><span data-ttu-id="77d56-110">Déclarations d'espace de noms</span><span class="sxs-lookup"><span data-stu-id="77d56-110">Namespace Declarations</span></span>

<span data-ttu-id="77d56-111">Q#En général, un fichier n’a qu’une seule déclaration d’espace de noms, mais peut en avoir un (et être vide ou ne contenir que des commentaires) ou peut contenir plusieurs espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="77d56-111">A Q# file typically has just one namespace declaration, but could have none (and be empty or just contain comments) or could contain multiple namespaces.</span></span>
<span data-ttu-id="77d56-112">Les déclarations d’espaces de noms ne peuvent pas être imbriquées.</span><span class="sxs-lookup"><span data-stu-id="77d56-112">Namespace declarations can not be nested.</span></span>

<span data-ttu-id="77d56-113">Vous pouvez déclarer le même espace de noms dans plusieurs Q# fichiers qui sont compilés ensemble, à condition qu’il n’y ait pas de déclaration de type, d’opération ou de fonction portant le même nom.</span><span class="sxs-lookup"><span data-stu-id="77d56-113">You can declare the same namespace in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="77d56-114">En particulier, il n’est pas valide de définir le même type dans le même espace de noms dans plusieurs fichiers, même si les déclarations sont identiques.</span><span class="sxs-lookup"><span data-stu-id="77d56-114">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="77d56-115">Une déclaration d’espace de noms se compose du mot clé `namespace` , suivi du nom de l’espace de noms, et des déclarations contenues dans l’espace de noms, placées entre accolades `{ }` .</span><span class="sxs-lookup"><span data-stu-id="77d56-115">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, and the declarations contained in the namespace enclosed in braces `{ }`.</span></span>
<span data-ttu-id="77d56-116">Les noms d’espaces de noms suivent le modèle .NET d’une séquence d’un ou de plusieurs symboles légaux séparés par des points `.` .</span><span class="sxs-lookup"><span data-stu-id="77d56-116">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="77d56-117">Par exemple, `MyQuantumStuff` et `Microsoft.Quantum.Intrinsic` sont des noms d’espaces de noms valides.</span><span class="sxs-lookup"><span data-stu-id="77d56-117">For example, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="77d56-118">Par Convention, mettez en majuscules les symboles dans un nom d’espace de noms, mais cela n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="77d56-118">By convention, capitalize the symbols in a namespace name, however, this is not required.</span></span>

<span data-ttu-id="77d56-119">Les références à des types ou à des callables déclarés plus loin dans un fichier sont correctement résolues ; Il n’est pas nécessaire que le type, l’opération ou la déclaration de fonction précède une référence à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="77d56-119">References to types or callables declared further down in a file resolve properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="77d56-120">Directives Open</span><span class="sxs-lookup"><span data-stu-id="77d56-120">Open Directives</span></span>

<span data-ttu-id="77d56-121">Dans un bloc d’espace de noms, utilisez la `open` directive pour importer tous les types et les callables déclarés dans un certain espace de noms et y faire référence par leur nom non qualifié.</span><span class="sxs-lookup"><span data-stu-id="77d56-121">Within a namespace block, use the `open` directive to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="77d56-122">Une telle `open` directive se compose du `open` mot clé, suivi de l’espace de noms à ouvrir et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="77d56-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="77d56-123">Toutes les `open` directives doivent apparaître avant `function` les `operation` déclarations, ou `newtype` dans le bloc d’espace de noms.</span><span class="sxs-lookup"><span data-stu-id="77d56-123">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="77d56-124">Si vous le souhaitez, vous pouvez définir un nom abrégé pour l’espace de noms ouvert.</span><span class="sxs-lookup"><span data-stu-id="77d56-124">Optionally, you can define a short name for the opened namespace.</span></span> <span data-ttu-id="77d56-125">Si un nom abrégé est défini, vous devez qualifier tous les éléments de cet espace de noms à l’aide du nom abrégé défini.</span><span class="sxs-lookup"><span data-stu-id="77d56-125">If a short name is defined, you must qualify all elements from that namespace by the defined short name.</span></span> <span data-ttu-id="77d56-126">Par exemple, étant donné la déclaration d’espace de noms et les directives Open suivantes,</span><span class="sxs-lookup"><span data-stu-id="77d56-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="77d56-127">Si une opération déclarée utilise une opération `Op` de `Microsoft.Quantum.Intrinsic` , vous l’appelez simplement à l’aide de `Op` .</span><span class="sxs-lookup"><span data-stu-id="77d56-127">if a declared operation uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, you call it by simply using `Op`.</span></span>
<span data-ttu-id="77d56-128">Toutefois, pour appeler une certaine fonction `Fn` à partir de `Microsoft.Quantum.Math` , vous devez l’appeler à l’aide de `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="77d56-128">However, to call a certain function `Fn` from `Microsoft.Quantum.Math`, you must call it using `Math.Fn`.</span></span>

<span data-ttu-id="77d56-129">La `open` directive s’applique à l’intégralité du bloc d’espace de noms dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="77d56-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="77d56-130">Par conséquent, si vous définissez un espace de noms supplémentaire dans le même Q# fichier que `NS` précédemment, les opérations/fonctions/types définis dans le deuxième espace de noms n’ont pas accès à quoi que ce soit à partir de `Microsoft.Quantum.Intrinsic` ou `Microsoft.Quantum.Math` , sauf si vous avez répété les directives ouvertes dans celui-ci.</span><span class="sxs-lookup"><span data-stu-id="77d56-130">Hence, if you define an additional namespace in the same Q# file as `NS` earlier, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless you repeated the open directives therein.</span></span> 

<span data-ttu-id="77d56-131">Pour référencer un type ou un appelable défini dans un autre espace de noms qui n’est *pas* ouvert dans l’espace de noms actuel, vous devez le référencer par son nom complet.</span><span class="sxs-lookup"><span data-stu-id="77d56-131">To reference a type or callable defined in another namespace that is *not* opened in the current namespace, you must reference it by its fully-qualified name.</span></span>
<span data-ttu-id="77d56-132">Prenons l’exemple d’une opération nommée `Op` à partir de l' `X.Y` espace de noms :</span><span class="sxs-lookup"><span data-stu-id="77d56-132">For example, given an operation named `Op` from the `X.Y` namespace:</span></span>

* <span data-ttu-id="77d56-133">Vous devez le référencer par son nom complet `X.Y.Op` , sauf si l' `X.Y` espace de noms a été ouvert plus tôt dans le bloc actuel.</span><span class="sxs-lookup"><span data-stu-id="77d56-133">You must reference it by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> 
* <span data-ttu-id="77d56-134">Même si l' `X` espace de noms est ouvert, il n’est pas possible de faire référence à l’opération en tant que `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="77d56-134">Even if the `X` namespace is opened, it is not possible to reference the operation as `Y.Op`.</span></span>
* <span data-ttu-id="77d56-135">Si vous avez défini le nom abrégé `Z` pour `X.Y` dans cet espace de noms et ce fichier, vous devez faire référence `Op` à `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="77d56-135">If you defined the short name `Z` for `X.Y` in that namespace and file, you must reference `Op` as `Z.Op`.</span></span> 

<span data-ttu-id="77d56-136">Il est généralement préférable d’inclure un espace de noms à l’aide d’une `open` directive.</span><span class="sxs-lookup"><span data-stu-id="77d56-136">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="77d56-137">L’utilisation d’un nom qualifié complet est requise si deux espaces de noms définissent des constructions portant le même nom, et la source actuelle utilise des constructions à partir des deux.</span><span class="sxs-lookup"><span data-stu-id="77d56-137">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="77d56-138">Q#suit les mêmes règles d’affectation de noms que d’autres langages .NET.</span><span class="sxs-lookup"><span data-stu-id="77d56-138">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="77d56-139">Toutefois, Q# ne prend pas en charge les références relatives aux espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="77d56-139">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="77d56-140">Par exemple, si l’espace de noms `a.b` est ouvert, une référence à une opération nommée `c.d` n’est *pas* résolue en une opération portant le nom complet `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="77d56-140">For example, if the namespace `a.b` is open, a reference to an operation named `c.d` does *not* resolve to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="77d56-141">Mise en forme</span><span class="sxs-lookup"><span data-stu-id="77d56-141">Formatting</span></span>

<span data-ttu-id="77d56-142">La plupart des Q# instructions et des directives se terminent par un point-virgule de fin, `;` .</span><span class="sxs-lookup"><span data-stu-id="77d56-142">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="77d56-143">Les instructions et les déclarations telles que `for` et `operation` qui se terminent par un bloc d’instructions (voir la section suivante) ne nécessitent pas de point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="77d56-143">Statements and declarations such as `for` and `operation` that end with a statement block (see the following section) do not require a terminating semicolon.</span></span>
<span data-ttu-id="77d56-144">Chaque description d’instruction indique si le point-virgule de fin est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="77d56-144">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="77d56-145">Les instructions, comme les expressions, les déclarations et les directives, peuvent être réparties sur plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="77d56-145">Statements, like expressions, declarations, and directives, can be broken out across multiple lines.</span></span>
<span data-ttu-id="77d56-146">Évitez de placer plusieurs instructions sur une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="77d56-146">Avoid putting multiple statements on a single line.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="77d56-147">Blocs d’instructions</span><span class="sxs-lookup"><span data-stu-id="77d56-147">Statement Blocks</span></span>

<span data-ttu-id="77d56-148">Q#les instructions sont regroupées dans des blocs d’instructions, qui sont contenus avec des accolades `{ }` .</span><span class="sxs-lookup"><span data-stu-id="77d56-148">Q# statements are grouped into statement blocks, which are contained with braces `{ }`.</span></span> <span data-ttu-id="77d56-149">Un bloc d’instructions commence par une ouverture `{` et se termine par une fermeture `}` .</span><span class="sxs-lookup"><span data-stu-id="77d56-149">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="77d56-150">Un bloc d’instructions placé lexicalement dans un autre bloc est considéré comme un sous-bloc du bloc conteneur. les blocs conteneur et secondaires sont également appelés blocs externes et internes.</span><span class="sxs-lookup"><span data-stu-id="77d56-150">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="77d56-151">Commentaires</span><span class="sxs-lookup"><span data-stu-id="77d56-151">Comments</span></span>

<span data-ttu-id="77d56-152">Les commentaires commencent par deux barres obliques, `//` et continuent jusqu’à la fin de la ligne.</span><span class="sxs-lookup"><span data-stu-id="77d56-152">Comments begin with two forward slashes, `//`, and continue until the end of the line.</span></span>
<span data-ttu-id="77d56-153">Un commentaire peut apparaître n’importe où dans un Q# fichier source.</span><span class="sxs-lookup"><span data-stu-id="77d56-153">A comment can appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="77d56-154">Commentaires de documentation</span><span class="sxs-lookup"><span data-stu-id="77d56-154">Documentation Comments</span></span>

<span data-ttu-id="77d56-155">Les commentaires qui commencent par trois barres obliques, `///` , sont traités de manière spéciale par le compilateur lorsqu’ils apparaissent immédiatement avant un espace de noms, une opération, une spécialisation, une fonction ou une définition de type.</span><span class="sxs-lookup"><span data-stu-id="77d56-155">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="77d56-156">Dans ce cas, le compilateur les traite comme une documentation pour le type pouvant être appelé par l’utilisateur ou défini par l’utilisateur, de la même façon que d’autres langages .NET.</span><span class="sxs-lookup"><span data-stu-id="77d56-156">In that case, the compiler treats them as documentation for the defined callable or user-defined type, the same as other .NET languages.</span></span>

<span data-ttu-id="77d56-157">Dans `///` les commentaires, le texte à afficher dans le cadre de la documentation de l’API est mis en forme en tant que [démarque](https://daringfireball.net/projects/markdown/syntax), avec les différentes parties de la documentation indiquées par des en-têtes spécialement nommés.</span><span class="sxs-lookup"><span data-stu-id="77d56-157">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation indicated by specially-named headers.</span></span>
<span data-ttu-id="77d56-158">Dans démarque, utilisez l' `@"<ref target>"` extension pour les opérations de référence croisée, les fonctions et les types définis par l’utilisateur dans Q# .</span><span class="sxs-lookup"><span data-stu-id="77d56-158">In Markdown, use the `@"<ref target>"` extension to cross-reference operations, functions, and user-defined types in Q#.</span></span> <span data-ttu-id="77d56-159">Remplacez `<ref target>` par le nom qualifié complet de l’objet de code référencé.</span><span class="sxs-lookup"><span data-stu-id="77d56-159">Replace `<ref target>` with the fully qualified name of the referenced code object.</span></span>
<span data-ttu-id="77d56-160">Des moteurs de documentation différents peuvent également prendre en charge des extensions de démarque supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="77d56-160">Different documentation engines may also support additional Markdown extensions.</span></span>

<span data-ttu-id="77d56-161">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="77d56-161">For example:</span></span>

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

<span data-ttu-id="77d56-162">Les noms suivants sont valides en tant qu’en-têtes de commentaires de documentation.</span><span class="sxs-lookup"><span data-stu-id="77d56-162">The following names are valid as documentation comment headers.</span></span>

- <span data-ttu-id="77d56-163">**Résumé**: bref résumé du comportement d’une fonction ou d’une opération, ou de l’objectif d’un type.</span><span class="sxs-lookup"><span data-stu-id="77d56-163">**Summary**: A short summary of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="77d56-164">Le premier paragraphe du résumé est utilisé pour les informations de survol.</span><span class="sxs-lookup"><span data-stu-id="77d56-164">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="77d56-165">Il doit s’agir d’un texte brut.</span><span class="sxs-lookup"><span data-stu-id="77d56-165">It should be plain text.</span></span>
- <span data-ttu-id="77d56-166">**Description**: description du comportement d’une fonction ou d’une opération, ou de l’objectif d’un type.</span><span class="sxs-lookup"><span data-stu-id="77d56-166">**Description**: A description of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="77d56-167">Ensemble, le résumé et la description constituent le fichier de documentation généré pour la fonction, l’opération ou le type.</span><span class="sxs-lookup"><span data-stu-id="77d56-167">Together, the summary and description form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="77d56-168">La description prend en charge les symboles et les équations au format LaTeX en ligne.</span><span class="sxs-lookup"><span data-stu-id="77d56-168">The description supports in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="77d56-169">**Input**: description du tuple d’entrée d’une opération ou d’une fonction.</span><span class="sxs-lookup"><span data-stu-id="77d56-169">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="77d56-170">Peut contenir des sous-sections de démarque supplémentaires indiquant chaque élément du tuple d’entrée.</span><span class="sxs-lookup"><span data-stu-id="77d56-170">Can contain additional Markdown subsections indicating each element of the input tuple.</span></span>
- <span data-ttu-id="77d56-171">**Sortie**: description du tuple retourné par une opération ou une fonction.</span><span class="sxs-lookup"><span data-stu-id="77d56-171">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="77d56-172">**Paramètres de type**: section vide qui contient une sous-section supplémentaire pour chaque paramètre de type générique.</span><span class="sxs-lookup"><span data-stu-id="77d56-172">**Type Parameters**: An empty section that contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="77d56-173">**Exemple**: exemple bref de l’opération, de la fonction ou du type en cours d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="77d56-173">**Example**: A short example of the operation, function, or type in use.</span></span>
- <span data-ttu-id="77d56-174">**Remarques**: divers Proseware décrivant certains aspects de l’opération, de la fonction ou du type.</span><span class="sxs-lookup"><span data-stu-id="77d56-174">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="77d56-175">**Voir aussi**: liste de noms qualifiés complets indiquant les fonctions connexes, les opérations ou les types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="77d56-175">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="77d56-176">**Références**: liste de références et de citations pour l’élément documenté.</span><span class="sxs-lookup"><span data-stu-id="77d56-176">**References**: A list of references and citations for the documented item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="77d56-177">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="77d56-177">Next steps</span></span>

<span data-ttu-id="77d56-178">En savoir plus sur [les opérations et les fonctions](xref:microsoft.quantum.guide.operationsfunctions) dans Q# .</span><span class="sxs-lookup"><span data-stu-id="77d56-178">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>