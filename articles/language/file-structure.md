---
title: Structure de fichiers | Microsoft Docs
description: 'Structure de fichiers Q #'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 364d353c55bda38f227456909755d13dc7e67080
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821080"
---
# <a name="file-structure"></a><span data-ttu-id="53a01-103">Structure de fichiers</span><span class="sxs-lookup"><span data-stu-id="53a01-103">File Structure</span></span>

<span data-ttu-id="53a01-104">Un fichier Q # est constitué d’une séquence de déclarations d’espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="53a01-104">A Q# file consists of a sequence of namespace declarations.</span></span>
<span data-ttu-id="53a01-105">Chaque déclaration d’espace de noms contient des déclarations pour les types, les opérations et les fonctions définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="53a01-105">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="53a01-106">Une déclaration d’espace de noms peut contenir un nombre quelconque de chaque type de déclaration, et dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="53a01-106">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="53a01-107">Le seul texte qui peut apparaître en dehors d’une déclaration d’espace de noms est un commentaire.</span><span class="sxs-lookup"><span data-stu-id="53a01-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="53a01-108">En particulier, les commentaires de documentation pour un espace de noms précèdent la déclaration.</span><span class="sxs-lookup"><span data-stu-id="53a01-108">In particular, documentation comments for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="53a01-109">Déclarations d'espace de noms</span><span class="sxs-lookup"><span data-stu-id="53a01-109">Namespace Declarations</span></span>

<span data-ttu-id="53a01-110">Un fichier Q # dispose généralement d’une seule déclaration d’espace de noms, mais il peut avoir la valeur None (et être vide ou contenir simplement des commentaires) ou peut contenir plusieurs espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="53a01-110">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="53a01-111">Les déclarations d’espaces de noms ne peuvent pas être imbriquées.</span><span class="sxs-lookup"><span data-stu-id="53a01-111">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="53a01-112">Le même espace de noms peut être déclaré dans plusieurs fichiers Q # qui sont compilés ensemble, à condition qu’il n’y ait pas de déclaration de type, d’opération ou de fonction portant le même nom.</span><span class="sxs-lookup"><span data-stu-id="53a01-112">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="53a01-113">En particulier, il n’est pas valide de définir le même type dans le même espace de noms dans plusieurs fichiers, même si les déclarations sont identiques.</span><span class="sxs-lookup"><span data-stu-id="53a01-113">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="53a01-114">Une déclaration d’espace de noms se compose du mot clé `namespace`, suivi du nom de l’espace de noms, d’une accolade ouvrante `{`, des déclarations contenues dans l’espace de noms et d’une accolade fermante `}`.</span><span class="sxs-lookup"><span data-stu-id="53a01-114">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="53a01-115">Les noms d’espaces de noms suivent le modèle .NET d’une séquence d’un ou de plusieurs symboles légaux séparés par des points `.`.</span><span class="sxs-lookup"><span data-stu-id="53a01-115">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="53a01-116">Par exemple, `MyQuantumStuff` et `Microsoft.Quantum.Canon` sont des noms d’espaces de noms valides.</span><span class="sxs-lookup"><span data-stu-id="53a01-116">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Canon` are valid namespace names.</span></span>
<span data-ttu-id="53a01-117">Par Convention, les symboles d’un nom d’espace de noms sont écrits en majuscules, mais cela n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="53a01-117">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="53a01-118">Les déclarations peuvent apparaître dans n’importe quel ordre dans une déclaration d’espace de noms.</span><span class="sxs-lookup"><span data-stu-id="53a01-118">Declarations may appear in any order in a namespace declaration.</span></span>
<span data-ttu-id="53a01-119">Les références à des types ou des callables déclarés plus loin dans un fichier sont correctement résolues ; Il n’est pas nécessaire que le type, l’opération ou la déclaration de fonction précède une référence à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="53a01-119">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="53a01-120">Directives Open</span><span class="sxs-lookup"><span data-stu-id="53a01-120">Open Directives</span></span>

<span data-ttu-id="53a01-121">Dans un bloc d’espace de noms, la directive `open` peut être utilisée pour importer tous les types et callables définis dans un espace de noms donné et y faire référence par leur nom non qualifié.</span><span class="sxs-lookup"><span data-stu-id="53a01-121">Within a namespace block, the `open` directive may be used to import all types and callables defined in a certain namespace and refer to them by their unqualified name.</span></span> 

<span data-ttu-id="53a01-122">Une telle directive de `open` se compose du mot clé `open`, suivi de l’espace de noms à ouvrir et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="53a01-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

<span data-ttu-id="53a01-123">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="53a01-123">For instance,</span></span>

```qsharp
open Microsoft.Quantum.Canon;
```

<span data-ttu-id="53a01-124">Éventuellement, un nom abrégé pour l’espace de noms ouvert peut être défini de sorte que tous les éléments de cet espace de noms puissent (et doivent) être qualifiés par le nom abrégé défini.</span><span class="sxs-lookup"><span data-stu-id="53a01-124">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="53a01-125">Un nom de ce type est défini en ajoutant le mot clé `as` suivi du nom abrégé souhaité avant le point-virgule dans une directive `open` :</span><span class="sxs-lookup"><span data-stu-id="53a01-125">Such a short name is defined by adding the keyword `as` followed by the desired short name before the semicolon in an `open` directive:</span></span>

```qsharp
open Microsoft.Quantum.Math as Math;
```

<span data-ttu-id="53a01-126">Toutes les directives de `open` doivent apparaître avant toute déclaration de `function`, `operation`ou `newtype` dans le bloc d’espace de noms.</span><span class="sxs-lookup"><span data-stu-id="53a01-126">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>
<span data-ttu-id="53a01-127">La directive `open` s’applique à l’intégralité du bloc d’espace de noms dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="53a01-127">The `open` directive applies to the entire namespace block within a file.</span></span>

## <a name="user-defined-type-declarations"></a><span data-ttu-id="53a01-128">Déclarations de types définis par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="53a01-128">User-Defined Type Declarations</span></span>

<span data-ttu-id="53a01-129">Q # offre aux utilisateurs la possibilité de déclarer de nouveaux types définis par l’utilisateur, comme décrit dans la section [Q # type Model](xref:microsoft.quantum.language.type-model) .</span><span class="sxs-lookup"><span data-stu-id="53a01-129">Q# provides a way for users to declare new user-defined types, as described in the [Q# type model](xref:microsoft.quantum.language.type-model) section.</span></span>
<span data-ttu-id="53a01-130">Les types définis par l’utilisateur sont distincts même si les types de base sont identiques.</span><span class="sxs-lookup"><span data-stu-id="53a01-130">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="53a01-131">En particulier, il n’existe pas de conversion automatique entre les valeurs de deux types définis par l’utilisateur, même si les types sous-jacents sont identiques.</span><span class="sxs-lookup"><span data-stu-id="53a01-131">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

<span data-ttu-id="53a01-132">Une déclaration de type défini par l’utilisateur se compose du mot clé `newtype`, suivi du nom du type défini par l’utilisateur, d’un `=`, d’une spécification de type valide et d’un point-virgule de fin.</span><span class="sxs-lookup"><span data-stu-id="53a01-132">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="53a01-133">Exemple :</span><span class="sxs-lookup"><span data-stu-id="53a01-133">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="53a01-134">Chaque fichier source Q # peut déclarer un nombre quelconque de types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="53a01-134">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="53a01-135">Les noms de types doivent être uniques dans un espace de noms et peuvent ne pas être en conflit avec les noms d’opération et de fonction.</span><span class="sxs-lookup"><span data-stu-id="53a01-135">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="53a01-136">Il n’est pas possible de définir des dépendances circulaires entre les types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="53a01-136">It is not possible to define circular dependencies between user defined types.</span></span> <span data-ttu-id="53a01-137">Les types récursifs ne sont donc pas possibles dans Q #.</span><span class="sxs-lookup"><span data-stu-id="53a01-137">Recursive types are thus not possible within Q#.</span></span>

## <a name="operation-declarations"></a><span data-ttu-id="53a01-138">Déclarations d’opération</span><span class="sxs-lookup"><span data-stu-id="53a01-138">Operation Declarations</span></span>

<span data-ttu-id="53a01-139">Les opérations sont le cœur de Q #, à peu près analogue aux fonctions dans d’autres langages.</span><span class="sxs-lookup"><span data-stu-id="53a01-139">Operations are the core of Q#, roughly analogous to functions in other languages.</span></span>
<span data-ttu-id="53a01-140">Chaque fichier source Q # peut définir n’importe quel nombre d’opérations.</span><span class="sxs-lookup"><span data-stu-id="53a01-140">Each Q# source file may define any number of operations.</span></span>

<span data-ttu-id="53a01-141">Les noms d’opérations doivent être uniques dans un espace de noms et peuvent ne pas être en conflit avec les noms de type et de fonction.</span><span class="sxs-lookup"><span data-stu-id="53a01-141">Operation names must be unique within a namespace and may not conflict with type and function names.</span></span>

<span data-ttu-id="53a01-142">Une déclaration d’opération se compose du mot clé `operation`, suivi du symbole qui est le nom de l’opération, d’un tuple d’identificateur typé qui définit les arguments de l’opération, d’un signe deux-points `:`, d’une annotation `}`de type qui décrit le type de résultat de l’opération, éventuellement d’une annotation avec les `{`caractéristiques de l’opération</span><span class="sxs-lookup"><span data-stu-id="53a01-142">An operation declarations consists of the keyword `operation`, followed by the symbol that is the operation’s name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation’s result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="53a01-143">Le corps de la déclaration d’opération se compose de l’implémentation par défaut ou d’une liste de spécialisations.</span><span class="sxs-lookup"><span data-stu-id="53a01-143">The body of the operation declaration either consists of the default implementation or of a list of specializations.</span></span>
<span data-ttu-id="53a01-144">L’implémentation par défaut peut être spécifiée directement dans la déclaration si seule l’implémentation de la spécialisation du corps par défaut doit être spécifiée explicitement.</span><span class="sxs-lookup"><span data-stu-id="53a01-144">The default implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to specified explicitly.</span></span>
<span data-ttu-id="53a01-145">Dans ce cas, une annotation avec les caractéristiques de l’opération dans la déclaration est utile pour s’assurer que le compilateur génère automatiquement d’autres spécialisations en fonction de l’implémentation par défaut.</span><span class="sxs-lookup"><span data-stu-id="53a01-145">In this case, an annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="53a01-146">Par exemple</span><span class="sxs-lookup"><span data-stu-id="53a01-146">For example</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

<span data-ttu-id="53a01-147">Les caractéristiques de l’opération définissent les genres d’functors qui peuvent être appliqués à l’opération déclarée et leur effet.</span><span class="sxs-lookup"><span data-stu-id="53a01-147">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="53a01-148">Si une opération implémente une transformation unitaire, il est possible de définir la façon dont l’opération agit quand *adjointed* ou *contrôlé*.</span><span class="sxs-lookup"><span data-stu-id="53a01-148">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span>
<span data-ttu-id="53a01-149">L’existence de ces spécialisations peut être déclarée dans le cadre de la signature de l’opération.</span><span class="sxs-lookup"><span data-stu-id="53a01-149">The existence of these specializations can be declared as part of the operation signature.</span></span> <span data-ttu-id="53a01-150">L’implémentation correspondante pour chaque spécialisation déclarée implicitement est ensuite générée par le compilateur.</span><span class="sxs-lookup"><span data-stu-id="53a01-150">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> <span data-ttu-id="53a01-151">Dans l’exemple ci-dessus, une spécialisation voisine, contrôlée et contrôlée par le compilateur est générée.</span><span class="sxs-lookup"><span data-stu-id="53a01-151">In the example above, an adjoint, a controlled, and a controlled adjoint specialization are generated by the compiler.</span></span> 

<span data-ttu-id="53a01-152">Dans le cas où l’implémentation ne peut pas être générée par le compilateur, elle peut être spécifiée explicitement.</span><span class="sxs-lookup"><span data-stu-id="53a01-152">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="53a01-153">Ces déclarations de spécialisation explicites peuvent se composer d’une directive de génération appropriée qui clarifie la manière dont une spécialisation doit être générée, ou d’une implémentation définie par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="53a01-153">Such explicit specialization declarations can either consist of a suitable generation directive that clarify how a certain specialization is to be built, or a user defined implementation.</span></span> <span data-ttu-id="53a01-154">Le code de `PrepareEntangledPair` ci-dessus, par exemple, est équivalent au code ci-dessous, contenant des déclarations de spécialisation explicites :</span><span class="sxs-lookup"><span data-stu-id="53a01-154">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="53a01-155">Le mot clé `auto` indique que le compilateur doit déterminer comment générer l’implémentation de la spécialisation.</span><span class="sxs-lookup"><span data-stu-id="53a01-155">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="53a01-156">Si le compilateur ne peut pas générer l’implémentation pour une certaine spécialisation sans instructions supplémentaires, comme une directive de génération plus précise, ou si une implémentation plus efficace peut être donnée, l’implémentation peut également être définie manuellement.</span><span class="sxs-lookup"><span data-stu-id="53a01-156">If the compiler cannot generate the implementation for a certain specialization without further instructions - like a more precise generation directive -, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```

<span data-ttu-id="53a01-157">Dans l’exemple ci-dessus, `adjoint invert;` indique que la spécialisation voisine doit être générée en inversant l’implémentation du corps, et `controlled adjoint invert;` indique que la spécialisation de la spécialisation voisine doit être générée en inversant l’implémentation donnée de la spécialisation contrôlée.</span><span class="sxs-lookup"><span data-stu-id="53a01-157">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="53a01-158">Pour qu’une opération prenne en charge l’application du `Adjoint` et/ou `Controlled` functor, son type de retour doit obligatoirement être `Unit`.</span><span class="sxs-lookup"><span data-stu-id="53a01-158">For an operation to support application of the `Adjoint` and/or `Controlled` functor, its return type necessarily needs to be `Unit`.</span></span> 


### <a name="explicit-specialization-declarations"></a><span data-ttu-id="53a01-159">Déclarations de spécialisation explicites</span><span class="sxs-lookup"><span data-stu-id="53a01-159">Explicit Specialization Declarations</span></span>

<span data-ttu-id="53a01-160">Les opérations Q # peuvent contenir les déclarations de spécialisation explicites suivantes :</span><span class="sxs-lookup"><span data-stu-id="53a01-160">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="53a01-161">La spécialisation `body` spécifie l’implémentation de l’opération sans les functors appliqués.</span><span class="sxs-lookup"><span data-stu-id="53a01-161">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="53a01-162">La spécialisation `adjoint` spécifie l’implémentation de l’opération avec le functor `Adjoint` appliqué.</span><span class="sxs-lookup"><span data-stu-id="53a01-162">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="53a01-163">La spécialisation `controlled` spécifie l’implémentation de l’opération avec le functor `Controlled` appliqué.</span><span class="sxs-lookup"><span data-stu-id="53a01-163">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="53a01-164">La spécialisation `controlled adjoint` spécifie l’implémentation de l’opération avec les functors `Adjoint` et `Controlled` appliqués.</span><span class="sxs-lookup"><span data-stu-id="53a01-164">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="53a01-165">Cette spécialisation peut également être nommée `adjoint controlled`, puisque les deux functors se comportent.</span><span class="sxs-lookup"><span data-stu-id="53a01-165">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="53a01-166">Une spécialisation d’opération se compose de la balise de spécialisation (par exemple, `body`ou `adjoint`, etc.) suivies de l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="53a01-166">An operation specialization consists of the specialization tag (like e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="53a01-167">Déclaration explicite comme décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="53a01-167">An explicit declaration as described below.</span></span>
- <span data-ttu-id="53a01-168">Directive qui indique au compilateur comment générer la spécialisation, l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="53a01-168">A directive that tells the compiler how to generate the specialization, one of:</span></span>
  - <span data-ttu-id="53a01-169">`intrinsic`, qui indique que la spécialisation est fournie par l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="53a01-169">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="53a01-170">`distribute`, qui peut être utilisé avec les spécialisations `controlled` et `controlled adjoint`.</span><span class="sxs-lookup"><span data-stu-id="53a01-170">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="53a01-171">Lorsqu’il est utilisé avec `controlled`, il indique que le compilateur doit calculer la spécialisation en appliquant `Controlled` à toutes les opérations dans le `body`.</span><span class="sxs-lookup"><span data-stu-id="53a01-171">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="53a01-172">Lorsqu’il est utilisé avec `controlled adjoint`, il indique que le compilateur doit calculer la spécialisation en appliquant `Controlled` à toutes les opérations de la spécialisation `adjoint`.</span><span class="sxs-lookup"><span data-stu-id="53a01-172">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="53a01-173">`invert`, qui indique que le compilateur doit calculer la spécialisation `adjoint` en inversant le `body`, c’est-à-dire en inversant l’ordre des opérations et en appliquant le voisin à chacun d’entre eux.</span><span class="sxs-lookup"><span data-stu-id="53a01-173">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="53a01-174">Lorsqu’il est utilisé avec `adjoint controlled`, cela indique que le compilateur doit calculer la spécialisation en inversant la spécialisation `controlled`.</span><span class="sxs-lookup"><span data-stu-id="53a01-174">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="53a01-175">`self`, pour indiquer que la spécialisation voisine est identique à la spécialisation `body`.</span><span class="sxs-lookup"><span data-stu-id="53a01-175">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="53a01-176">Cela est légal pour les spécialisations `adjoint` et `adjoint controlled`.</span><span class="sxs-lookup"><span data-stu-id="53a01-176">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="53a01-177">Par `adjoint controlled`, `self` implique que la spécialisation de la `adjoint controlled` est la même que la spécialisation de la `controlled`.</span><span class="sxs-lookup"><span data-stu-id="53a01-177">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="53a01-178">`auto`, pour indiquer que le compilateur doit sélectionner une directive appropriée à appliquer.</span><span class="sxs-lookup"><span data-stu-id="53a01-178">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="53a01-179">`auto` ne peut pas être utilisé pour la spécialisation `body`.</span><span class="sxs-lookup"><span data-stu-id="53a01-179">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="53a01-180">Les directives et les `auto` requièrent tous un point-virgule fermant `;`.</span><span class="sxs-lookup"><span data-stu-id="53a01-180">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="53a01-181">La directive `auto` correspond à la directive de génération suivante si une déclaration explicite du `body` est fournie :</span><span class="sxs-lookup"><span data-stu-id="53a01-181">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="53a01-182">La spécialisation `adjoint` est générée en fonction de la `invert`de directive.</span><span class="sxs-lookup"><span data-stu-id="53a01-182">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="53a01-183">La spécialisation `controlled` est générée en fonction de la `distribute`de directive.</span><span class="sxs-lookup"><span data-stu-id="53a01-183">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="53a01-184">La spécialisation `adjoint controlled` est générée conformément à la directive `invert` si une déclaration explicite pour `controlled` est donnée mais pas pour `adjoint`, et `distribute` dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="53a01-184">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="53a01-185">Si une opération est autonome, spécifiez explicitement l’une ou l’autre de la spécialisation contigut à l’aide de la directive de génération `self` pour permettre au compilateur d’utiliser ces informations à des fins d’optimisation.</span><span class="sxs-lookup"><span data-stu-id="53a01-185">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="53a01-186">Une déclaration de spécialisation contenant une implémentation définie par l’utilisateur se compose d’un tuple d’argument suivi d’un bloc d’instructions avec le code Q # qui implémente la spécialisation.</span><span class="sxs-lookup"><span data-stu-id="53a01-186">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="53a01-187">Dans la liste d’arguments, `...` est utilisé pour représenter les arguments déclarés pour l’opération dans son ensemble.</span><span class="sxs-lookup"><span data-stu-id="53a01-187">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="53a01-188">Pour `body` et `adjoint`, la liste d’arguments doit toujours être `(...)`; pour `controlled` et `adjoint controlled`, la liste d’arguments doit être un symbole qui représente le tableau de qubits de contrôle, suivi par `...`, placé entre parenthèses ; par exemple, `(controls,...)`.</span><span class="sxs-lookup"><span data-stu-id="53a01-188">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

<span data-ttu-id="53a01-189">Si une ou plusieurs spécialisations en plus du corps par défaut doivent être déclarées explicitement, l’implémentation du corps par défaut doit également être incluse dans une déclaration de spécialisation appropriée :</span><span class="sxs-lookup"><span data-stu-id="53a01-189">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a><span data-ttu-id="53a01-190">Voisin</span><span class="sxs-lookup"><span data-stu-id="53a01-190">Adjoint</span></span>

<span data-ttu-id="53a01-191">Le voisin d’une opération spécifie comment la complexe conjugué de l’opération est implémentée, c’est-à-dire comment l’opération agit quand « s’exécute en sens inverse ».</span><span class="sxs-lookup"><span data-stu-id="53a01-191">The adjoint of an operation specifies how the complex conjugate transpose of the operation is implemented, i.e. how the operation acts when "run in reverse".</span></span>
<span data-ttu-id="53a01-192">Il est possible de spécifier une opération sans voisin. par exemple, les opérations de mesure n’ont pas de voisin, car elles ne sont pas réversibles.</span><span class="sxs-lookup"><span data-stu-id="53a01-192">It is legal to specify an operation with no adjoint; for instance, measurement operations have no adjoint because they are not invertible.</span></span>
<span data-ttu-id="53a01-193">Une opération prend en charge l' `Adjoint` functor si sa déclaration contient une déclaration implicite ou explicite d’une spécialisation voisine.</span><span class="sxs-lookup"><span data-stu-id="53a01-193">An operation supports the `Adjoint` functor if its declaration contains an implicit or explicit declaration of an adjoint specialization.</span></span>
<span data-ttu-id="53a01-194">Une spécialisation contiguë contrôlée explicitement déclarée implique l’existence d’une spécialisation voisine.</span><span class="sxs-lookup"><span data-stu-id="53a01-194">An explicitly declared controlled adjoint specialization implies the existence of an adjoint specialization.</span></span> 

<span data-ttu-id="53a01-195">Pour l’opération dont le corps contient des boucles REPEAT-UNTIL-Successful, des instructions SET, des mesures, des instructions return ou des appels à d’autres opérations qui ne prennent pas en charge l' `Adjoint` functor, la génération automatique d’une spécialisation Join à la suite de la directive `invert` ou `auto` n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="53a01-195">For operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

### <a name="controlled"></a><span data-ttu-id="53a01-196">Contrôl</span><span class="sxs-lookup"><span data-stu-id="53a01-196">Controlled</span></span>

<span data-ttu-id="53a01-197">La version contrôlée d’une opération spécifie comment une version contrôlée par Quantum de l’opération est implémentée, c’est-à-dire comment une opération agit quand elle est appliquée à l’état d’un registre Quantum.</span><span class="sxs-lookup"><span data-stu-id="53a01-197">The controlled version of an operation specifies how a quantum-controlled version of the operation is implemented, i.e. how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="53a01-198">Une description plus complète est fournie dans la section [contrôlé](xref:microsoft.quantum.language.type-model#controlled) .</span><span class="sxs-lookup"><span data-stu-id="53a01-198">A more complete description is provided in the [Controlled](xref:microsoft.quantum.language.type-model#controlled) section.</span></span>

<span data-ttu-id="53a01-199">Il est légal de spécifier une opération sans version contrôlée. par exemple, les opérations de mesure n’ont pas de version contrôlée, car elles ne sont pas contrôlable.</span><span class="sxs-lookup"><span data-stu-id="53a01-199">It is legal to specify an operation with no controlled version; for instance, measurement operations have no controlled version because they are not controllable.</span></span>
<span data-ttu-id="53a01-200">Une opération prend en charge l' `Controlled` functor si et seulement si sa déclaration contient une déclaration implicite ou explicite d’une spécialisation contrôlée.</span><span class="sxs-lookup"><span data-stu-id="53a01-200">An operation supports the `Controlled` functor if and only if its declaration contains an implicit or explicit declaration of a controlled specialization.</span></span>
<span data-ttu-id="53a01-201">Une spécialisation contiguë contrôlée explicitement déclarée implique l’existence d’une spécialisation contrôlée.</span><span class="sxs-lookup"><span data-stu-id="53a01-201">An explicitly declared controlled adjoint specialization implies the existence of a controlled specialization.</span></span> 

<span data-ttu-id="53a01-202">Pour une opération dont le corps contient des appels à d’autres opérations qui ne prennent pas en charge l' `Controlled` functor, la génération automatique d’une spécialisation contrôlée à la suite de la directive `distribute` ou `auto` n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="53a01-202">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

### <a name="controlled-adjoint"></a><span data-ttu-id="53a01-203">Contigut contrôlé</span><span class="sxs-lookup"><span data-stu-id="53a01-203">Controlled Adjoint</span></span>

<span data-ttu-id="53a01-204">La version contrôlée par le contrôle contigut d’une opération spécifie la manière dont une version contrôlée par Quantum de l’opération est implémentée.</span><span class="sxs-lookup"><span data-stu-id="53a01-204">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="53a01-205">Il est possible de spécifier une opération sans contrôle de version voisine. par exemple, les opérations de mesure n’ont pas de version définie par l’utilisateur, car elles ne sont ni contrôlables ni réversibles.</span><span class="sxs-lookup"><span data-stu-id="53a01-205">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="53a01-206">Une spécialisation voisine de l’opération doit exister si et seulement si une spécialisation et une spécialisation contrôlée existent.</span><span class="sxs-lookup"><span data-stu-id="53a01-206">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="53a01-207">Dans ce cas, l’existence de la spécialisation voisine contrôlée est déduite et une spécialisation appropriée est générée par le compilateur si aucune implémentation n’a été définie explicitement.</span><span class="sxs-lookup"><span data-stu-id="53a01-207">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="53a01-208">Pour une opération dont le corps contient des appels à d’autres opérations qui n’ont pas de version définie pour le contrôle joint, la génération automatique d’une spécialisation voisine à la suite de l' `invert`, `distribute` ou `auto` directive n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="53a01-208">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="examples"></a><span data-ttu-id="53a01-209">Exemples</span><span class="sxs-lookup"><span data-stu-id="53a01-209">Examples</span></span>

<span data-ttu-id="53a01-210">Une déclaration d’opération peut être aussi simple que la suivante, qui définit l’opération Pauli X primitive :</span><span class="sxs-lookup"><span data-stu-id="53a01-210">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

<span data-ttu-id="53a01-211">Les éléments suivants définissent l’opération de téléopération.</span><span class="sxs-lookup"><span data-stu-id="53a01-211">The following defines the teleport operation.</span></span>

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a><span data-ttu-id="53a01-212">Déclarations de fonction</span><span class="sxs-lookup"><span data-stu-id="53a01-212">Function Declarations</span></span>

<span data-ttu-id="53a01-213">Les fonctions sont des routines purement classiques dans Q #.</span><span class="sxs-lookup"><span data-stu-id="53a01-213">Functions are purely classical routines in Q#.</span></span>
<span data-ttu-id="53a01-214">Chaque fichier source Q # peut définir un nombre quelconque de fonctions.</span><span class="sxs-lookup"><span data-stu-id="53a01-214">Each Q# source file may define any number of functions.</span></span>

<span data-ttu-id="53a01-215">Une déclaration de fonction se compose du mot clé `function`, suivi du symbole qui est le nom de la fonction, d’un tuple d’identificateur typé, d’une annotation de type qui décrit le type de retour de la fonction, et d’un bloc d’instructions qui décrit l’implémentation de la fonction.</span><span class="sxs-lookup"><span data-stu-id="53a01-215">A function declaration consists of the keyword `function`, followed by the symbol that is the function’s name, a typed identifier tuple, a type annotation that describes the function's return type, and a statement block that describes the implementation of the function.</span></span>

<span data-ttu-id="53a01-216">Le bloc d’instructions définissant une fonction doit être placé dans `{` et `}` comme tout autre bloc d’instructions.</span><span class="sxs-lookup"><span data-stu-id="53a01-216">The statement block defining a function must be enclosed in `{` and `}` like any other statement block.</span></span>

<span data-ttu-id="53a01-217">Les noms de fonctions doivent être uniques dans un espace de noms et peuvent ne pas être en conflit avec les noms de type et d’opération.</span><span class="sxs-lookup"><span data-stu-id="53a01-217">Function names must be unique within a namespace and may not conflict with operation and type names.</span></span>
<span data-ttu-id="53a01-218">Les fonctions ne peuvent pas allouer ou emprunter des qubits ou appeler des opérations.</span><span class="sxs-lookup"><span data-stu-id="53a01-218">Functions may not allocate or borrow qubits, or call operations.</span></span> <span data-ttu-id="53a01-219">L’application partielle des opérations ou le passage autour des valeurs de type Operation est parfait.</span><span class="sxs-lookup"><span data-stu-id="53a01-219">Partial application of operations or passing around operation typed values is fine.</span></span>

<span data-ttu-id="53a01-220">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="53a01-220">For example,</span></span>

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```
