---
title: 'Structure de fichiers Q #'
description: 'Décrit la structure et la syntaxe d’un fichier Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327456"
---
# <a name="q-file-structure"></a><span data-ttu-id="9fcb4-103">Structure de fichiers Q #</span><span class="sxs-lookup"><span data-stu-id="9fcb4-103">Q# File Structure</span></span>

<span data-ttu-id="9fcb4-104">Chaque opération Q #, fonction et type défini par l’utilisateur est défini dans un espace de noms.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-104">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>

<span data-ttu-id="9fcb4-105">Un fichier Q # est constitué d’une séquence de *déclarations d’espaces de noms*.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-105">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="9fcb4-106">Chaque déclaration d’espace de noms contient des déclarations pour les types, les opérations et les fonctions définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-106">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="9fcb4-107">Une déclaration d’espace de noms peut contenir un nombre quelconque de chaque type de déclaration, et dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-107">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="9fcb4-108">Pour plus d’informations sur la déclaration des types, des [opérations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)et des [fonctions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) [définis par l’utilisateur](xref:microsoft.quantum.guide.types#user-defined-types)au sein d’un espace de noms, consultez les liens suivants.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-108">Follow these links for more details on declaring [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) within a namespace.</span></span>

<span data-ttu-id="9fcb4-109">Le seul texte qui peut apparaître en dehors d’une déclaration d’espace de noms est un commentaire.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-109">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="9fcb4-110">En particulier, les commentaires de documentation (plus de détails ci-dessous) pour un espace de noms précèdent la déclaration.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-110">In particular, documentation comments (more details below) for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="9fcb4-111">Déclarations d'espace de noms</span><span class="sxs-lookup"><span data-stu-id="9fcb4-111">Namespace Declarations</span></span>

<span data-ttu-id="9fcb4-112">Un fichier Q # dispose généralement d’une seule déclaration d’espace de noms, mais il peut avoir la valeur None (et être vide ou contenir simplement des commentaires) ou peut contenir plusieurs espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-112">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="9fcb4-113">Les déclarations d’espaces de noms ne peuvent pas être imbriquées.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-113">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="9fcb4-114">Le même espace de noms peut être déclaré dans plusieurs fichiers Q # qui sont compilés ensemble, à condition qu’il n’y ait pas de déclaration de type, d’opération ou de fonction portant le même nom.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-114">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="9fcb4-115">En particulier, il n’est pas valide de définir le même type dans le même espace de noms dans plusieurs fichiers, même si les déclarations sont identiques.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-115">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="9fcb4-116">Une déclaration d’espace de noms se compose du mot clé `namespace` , suivi du nom de l’espace de noms, d’une accolade ouvrante `{` , des déclarations contenues dans l’espace de noms et d’une accolade fermante `}` .</span><span class="sxs-lookup"><span data-stu-id="9fcb4-116">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="9fcb4-117">Les noms d’espaces de noms suivent le modèle .NET d’une séquence d’un ou de plusieurs symboles légaux séparés par des points `.` .</span><span class="sxs-lookup"><span data-stu-id="9fcb4-117">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="9fcb4-118">Par exemple, `MyQuantumStuff` et `Microsoft.Quantum.Intrinsic` sont des noms d’espaces de noms valides.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-118">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="9fcb4-119">Par Convention, les symboles d’un nom d’espace de noms sont écrits en majuscules, mais cela n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-119">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="9fcb4-120">Les références à des types ou des callables déclarés plus loin dans un fichier sont correctement résolues ; Il n’est pas nécessaire que le type, l’opération ou la déclaration de fonction précède une référence à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-120">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="9fcb4-121">Directives Open</span><span class="sxs-lookup"><span data-stu-id="9fcb4-121">Open Directives</span></span>

<span data-ttu-id="9fcb4-122">Dans un bloc d’espace de noms, la `open` directive peut être utilisée pour importer tous les types et les callables déclarés dans un certain espace de noms et y faire référence par leur nom non qualifié.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-122">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="9fcb4-123">Une telle `open` directive se compose du `open` mot clé, suivi de l’espace de noms à ouvrir et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-123">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="9fcb4-124">Toutes les `open` directives doivent apparaître avant `function` les `operation` déclarations, ou `newtype` dans le bloc d’espace de noms.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-124">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="9fcb4-125">Éventuellement, un nom abrégé pour l’espace de noms ouvert peut être défini de sorte que tous les éléments de cet espace de noms puissent (et doivent) être qualifiés par le nom abrégé défini.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-125">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="9fcb4-126">Par exemple, étant donné la déclaration d’espace de noms et les directives Open suivantes,</span><span class="sxs-lookup"><span data-stu-id="9fcb4-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="9fcb4-127">Si une opération que nous déclarons utilise une opération `Op` de `Microsoft.Quantum.Intrinsic` , nous l’appelons simplement en utilisant `Op` .</span><span class="sxs-lookup"><span data-stu-id="9fcb4-127">if an operation we declare uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, we would call it by simply using `Op`.</span></span>
<span data-ttu-id="9fcb4-128">Toutefois, si nous voulions appeler une certaine fonction `Fn` à partir de `Microsoft.Quantum.Math` , nous aurions besoin de l’appeler à l’aide de `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="9fcb4-128">However, if we wanted a call a certain function `Fn` from `Microsoft.Quantum.Math`, we would need to call it using `Math.Fn`.</span></span>

<span data-ttu-id="9fcb4-129">La `open` directive s’applique à l’intégralité du bloc d’espace de noms dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="9fcb4-130">Par conséquent, si nous devions définir un espace de noms supplémentaire dans le même fichier Q # que `NS` ci-dessus, toutes les opérations/fonctions/tous les types définis dans le deuxième espace de noms n’ont pas accès à quoi que ce soit à partir de `Microsoft.Quantum.Intrinsic` ou `Microsoft.Quantum.Math` , sauf si nous avons répété les directives ouvertes ici.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-130">Hence, if we were to define an additional namespace in the same Q# file as `NS` above, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless we repeated the open directives therein.</span></span> 

<span data-ttu-id="9fcb4-131">Un type ou un appelable défini dans un autre espace de noms qui n’est *pas* ouvert dans l’espace de noms actuel doit être référencé par son nom complet.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-131">A type or callable defined in another namespace that is *not* opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="9fcb4-132">Par exemple, une opération nommée `Op` à partir de l' `X.Y` espace de noms doit être référencée par son nom complet `X.Y.Op` , sauf si l' `X.Y` espace de noms a été ouvert plus tôt dans le bloc actuel.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-132">For example, an operation named `Op` from the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="9fcb4-133">Comme indiqué ci-dessus, même si l' `X` espace de noms a été ouvert, il n’est pas possible de faire référence à l’opération en tant que `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="9fcb4-133">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="9fcb4-134">Si un nom abrégé `Z` pour `X.Y` a été défini dans cet espace de noms et ce fichier, `Op` doit être appelé `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="9fcb4-134">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

<span data-ttu-id="9fcb4-135">Il est généralement préférable d’inclure un espace de noms à l’aide d’une `open` directive.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-135">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="9fcb4-136">L’utilisation d’un nom qualifié complet est requise si deux espaces de noms définissent des constructions portant le même nom, et la source actuelle utilise des constructions à partir des deux.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-136">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="9fcb4-137">Q # suit les mêmes règles d’affectation de noms que d’autres langages .NET.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-137">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="9fcb4-138">Toutefois, Q # ne prend pas en charge les références relatives aux espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-138">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="9fcb4-139">Autrement dit, si l’espace de noms `a.b` a été ouvert, une référence à une opération nommée `c.d` ne sera *pas* résolue en une opération portant le nom complet `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="9fcb4-139">That is, if the namespace `a.b` has been opened, a reference to an operation named `c.d` will *not* be resolved to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="9fcb4-140">Mise en forme</span><span class="sxs-lookup"><span data-stu-id="9fcb4-140">Formatting</span></span>

<span data-ttu-id="9fcb4-141">La plupart des instructions et directives Q # se terminent par un point-virgule de fin, `;` .</span><span class="sxs-lookup"><span data-stu-id="9fcb4-141">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="9fcb4-142">Les instructions et les déclarations telles que `for` et `operation` qui se terminent par un bloc d’instructions (voir ci-dessous) ne nécessitent pas de point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-142">Statements and declarations such as `for` and `operation` that end with a statement block (see below) do not require a terminating semicolon.</span></span>
<span data-ttu-id="9fcb4-143">Chaque description d’instruction indique si le point-virgule de fin est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-143">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="9fcb4-144">Les instructions, comme les expressions, les déclarations et les directives, peuvent être réparties sur plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-144">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="9fcb4-145">L’utilisation de plusieurs instructions sur une seule ligne doit être évitée.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-145">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="9fcb4-146">Blocs d’instructions</span><span class="sxs-lookup"><span data-stu-id="9fcb4-146">Statement Blocks</span></span>

<span data-ttu-id="9fcb4-147">Les instructions Q # sont regroupées dans des blocs d’instructions.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-147">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="9fcb4-148">Un bloc d’instructions commence par une ouverture `{` et se termine par une fermeture `}` .</span><span class="sxs-lookup"><span data-stu-id="9fcb4-148">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="9fcb4-149">Un bloc d’instructions placé lexicalement dans un autre bloc est considéré comme un sous-bloc du bloc conteneur. les blocs conteneur et secondaires sont également appelés blocs externes et internes.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-149">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="9fcb4-150">Commentaires</span><span class="sxs-lookup"><span data-stu-id="9fcb4-150">Comments</span></span>

<span data-ttu-id="9fcb4-151">Les commentaires commencent par deux barres obliques, `//` et continuent jusqu’à la fin de la ligne.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-151">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="9fcb4-152">Un commentaire peut apparaître n’importe où dans un fichier source Q #.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-152">A comment may appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="9fcb4-153">Commentaires de documentation</span><span class="sxs-lookup"><span data-stu-id="9fcb4-153">Documentation Comments</span></span>

<span data-ttu-id="9fcb4-154">Les commentaires qui commencent par trois barres obliques, `///` , sont traités de manière spéciale par le compilateur lorsqu’ils apparaissent immédiatement avant un espace de noms, une opération, une spécialisation, une fonction ou une définition de type.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-154">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="9fcb4-155">Dans ce cas, leur contenu est utilisé comme documentation pour le type pouvant être appelé ou défini par l’utilisateur, comme pour d’autres langages .NET.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-155">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="9fcb4-156">Dans `///` les commentaires, le texte à afficher dans le cadre de la documentation de l’API est mis en forme en tant que [démarque](https://daringfireball.net/projects/markdown/syntax), avec les différentes parties de la documentation indiquées par des en-têtes spécialement nommés.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-156">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="9fcb4-157">En tant qu’extension de la démarque, les références croisées aux opérations, aux fonctions et aux types définis par l’utilisateur dans Q # peuvent être incluses à l’aide de `@"<ref target>"` , où `<ref target>` est remplacé par le nom qualifié complet de l’objet de code référencé.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-157">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="9fcb4-158">Le cas échéant, un moteur de documentation peut également prendre en charge des extensions de démarque supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-158">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="9fcb4-159">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9fcb4-159">For example:</span></span>

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

<span data-ttu-id="9fcb4-160">Les noms suivants sont reconnus en tant qu’en-têtes de commentaires de documentation.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-160">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="9fcb4-161">**Résumé**: bref résumé du comportement d’une fonction ou d’une opération, ou de l’objectif d’un type.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-161">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="9fcb4-162">Le premier paragraphe du résumé est utilisé pour les informations de survol.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-162">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="9fcb4-163">Il doit s’agir d’un texte brut.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-163">It should be plain text.</span></span>
- <span data-ttu-id="9fcb4-164">**Description**: description du comportement d’une fonction ou d’une opération, ou de l’objectif d’un type.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-164">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="9fcb4-165">Le résumé et la description sont concaténés pour former le fichier de documentation généré pour la fonction, l’opération ou le type.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-165">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="9fcb4-166">La description peut contenir des équations et des symboles au format LaTeX en ligne.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-166">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="9fcb4-167">**Input**: description du tuple d’entrée d’une opération ou d’une fonction.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-167">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="9fcb4-168">Peut contenir des sous-sections de démarque supplémentaires indiquant chaque élément individuel du tuple d’entrée.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-168">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="9fcb4-169">**Sortie**: description du tuple retourné par une opération ou une fonction.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-169">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="9fcb4-170">**Paramètres de type**: section vide qui contient une sous-section supplémentaire pour chaque paramètre de type générique.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-170">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="9fcb4-171">**Exemple**: exemple bref de l’opération, de la fonction ou du type en cours d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-171">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="9fcb4-172">**Remarques**: divers Proseware décrivant certains aspects de l’opération, de la fonction ou du type.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-172">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="9fcb4-173">**Voir aussi**: liste de noms qualifiés complets indiquant les fonctions connexes, les opérations ou les types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-173">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="9fcb4-174">**Références**: liste de références et de citations pour l’élément documenté.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-174">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9fcb4-175">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="9fcb4-175">Next steps</span></span>

<span data-ttu-id="9fcb4-176">En savoir plus sur [les opérations et les fonctions](xref:microsoft.quantum.guide.operationsfunctions) dans Q #.</span><span class="sxs-lookup"><span data-stu-id="9fcb4-176">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>