---
title: 'Guide de style Microsoft Q #'
description: 'Découvrez les conventions d’attribution de noms, d’entrée, de documentation et de mise en forme pour les programmes et les bibliothèques Q #.'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: f8e398b5c9932a5079222fed7ad20e54de814eb8
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274799"
---
# <a name="q-style-guide"></a><span data-ttu-id="df9f2-103">Guide de style Q #</span><span class="sxs-lookup"><span data-stu-id="df9f2-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="df9f2-104">Conventions générales</span><span class="sxs-lookup"><span data-stu-id="df9f2-104">General Conventions</span></span> ##

<span data-ttu-id="df9f2-105">Les conventions suggérées dans ce guide sont destinées à faciliter la lecture et la compréhension des programmes et des bibliothèques écrits dans Q #.</span><span class="sxs-lookup"><span data-stu-id="df9f2-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="df9f2-106">Conseils</span><span class="sxs-lookup"><span data-stu-id="df9f2-106">Guidance</span></span>

<span data-ttu-id="df9f2-107">Nous vous suggérons :</span><span class="sxs-lookup"><span data-stu-id="df9f2-107">We suggest:</span></span>

- <span data-ttu-id="df9f2-108">N’ignorez pas une convention, sauf si vous le configurez intentionnellement pour fournir du code plus lisible et plus compréhensible à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="df9f2-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="df9f2-109">Conventions d'affectation de noms</span><span class="sxs-lookup"><span data-stu-id="df9f2-109">Naming Conventions</span></span> ##

<span data-ttu-id="df9f2-110">En proposant le kit de développement quantique, nous nous efforçons d’utiliser des noms de fonctions et d’opérations qui aident les développeurs de Quantum à écrire des programmes faciles à lire et qui réduisent la surprise.</span><span class="sxs-lookup"><span data-stu-id="df9f2-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="df9f2-111">Une partie importante de cela est que lorsque nous choisissons des noms pour les fonctions, les opérations et les types, nous établissons le *vocabulaire* que les programmeurs utilisent pour exprimer les concepts quantiques. Grâce à nos choix, nous vous aidons ou les empêcherons à communiquer clairement.</span><span class="sxs-lookup"><span data-stu-id="df9f2-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="df9f2-112">Cela pose une responsabilité pour nous assurer que les noms que nous introduisons offrent une clarté plutôt qu’une obscurité.</span><span class="sxs-lookup"><span data-stu-id="df9f2-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="df9f2-113">Dans cette section, nous détaillerons la manière dont nous répondons à cette obligation en termes de conseils explicites qui nous aideront à faire le meilleur de la communauté de développement Q #.</span><span class="sxs-lookup"><span data-stu-id="df9f2-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="df9f2-114">Opérations et fonctions</span><span class="sxs-lookup"><span data-stu-id="df9f2-114">Operations and Functions</span></span> ###

<span data-ttu-id="df9f2-115">L’une des premières choses qu’un nom doit établir est si un symbole donné représente une fonction ou une opération.</span><span class="sxs-lookup"><span data-stu-id="df9f2-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="df9f2-116">La différence entre les fonctions et les opérations est essentielle pour comprendre le comportement d’un bloc de code.</span><span class="sxs-lookup"><span data-stu-id="df9f2-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="df9f2-117">Pour communiquer la distinction entre les fonctions et les opérations aux utilisateurs, nous nous appuyons sur les opérations de quantum des modèles Q # par le biais de l’utilisation d’effets secondaires.</span><span class="sxs-lookup"><span data-stu-id="df9f2-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="df9f2-118">Autrement dit, une opération *effectue* une opération.</span><span class="sxs-lookup"><span data-stu-id="df9f2-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="df9f2-119">En revanche, les fonctions décrivent les relations mathématiques entre les données.</span><span class="sxs-lookup"><span data-stu-id="df9f2-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="df9f2-120">L’expression `Sin(PI() / 2.0)` *est* `1.0` , et n’implique rien de l’état d’un programme ou de son qubits.</span><span class="sxs-lookup"><span data-stu-id="df9f2-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="df9f2-121">En résumé, les opérations effectuent des opérations alors que les fonctions sont des choses.</span><span class="sxs-lookup"><span data-stu-id="df9f2-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="df9f2-122">Cette distinction suggère que les opérations sont nommées en tant que verbes et fonctions en tant que noms.</span><span class="sxs-lookup"><span data-stu-id="df9f2-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="df9f2-123">Lorsqu’un type défini par l’utilisateur est déclaré, une nouvelle fonction qui construit des instances de ce type est implicitement définie en même temps.</span><span class="sxs-lookup"><span data-stu-id="df9f2-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="df9f2-124">À partir de cette perspective, les types définis par l’utilisateur doivent être nommés en tant que noms afin que le type lui-même et la fonction de constructeur aient des noms cohérents.</span><span class="sxs-lookup"><span data-stu-id="df9f2-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="df9f2-125">Dans la mesure du possible, assurez-vous que les noms des opérations commencent par des verbes qui indiquent clairement l’effet pris par l’opération.</span><span class="sxs-lookup"><span data-stu-id="df9f2-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="df9f2-126">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="df9f2-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="df9f2-127">Un cas qui mérite une mention spéciale est lorsqu’une opération prend une autre opération comme entrée et l’appelle.</span><span class="sxs-lookup"><span data-stu-id="df9f2-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="df9f2-128">Dans ce cas, l’action entreprise par l’opération d’entrée n’est pas claire lorsque l’opération externe est définie, de telle sorte que le verbe de droite n’est pas immédiatement clair.</span><span class="sxs-lookup"><span data-stu-id="df9f2-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="df9f2-129">Nous vous recommandons d’utiliser le verbe `Apply` , comme dans `ApplyIf` , `ApplyToEach` et `ApplyToFirst` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="df9f2-130">D’autres verbes peuvent également être utiles dans ce cas, comme dans `IterateThroughCartesianPower` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="df9f2-131">Verbe</span><span class="sxs-lookup"><span data-stu-id="df9f2-131">Verb</span></span> | <span data-ttu-id="df9f2-132">Effet attendu</span><span class="sxs-lookup"><span data-stu-id="df9f2-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="df9f2-133">Appliquer</span><span class="sxs-lookup"><span data-stu-id="df9f2-133">Apply</span></span> | <span data-ttu-id="df9f2-134">Une opération fournie en tant qu’entrée est appelée</span><span class="sxs-lookup"><span data-stu-id="df9f2-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="df9f2-135">Assert</span><span class="sxs-lookup"><span data-stu-id="df9f2-135">Assert</span></span> | <span data-ttu-id="df9f2-136">Une hypothèse sur le résultat d’une mesure de Quantum possible est vérifiée par un simulateur</span><span class="sxs-lookup"><span data-stu-id="df9f2-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="df9f2-137">Estimation</span><span class="sxs-lookup"><span data-stu-id="df9f2-137">Estimate</span></span> | <span data-ttu-id="df9f2-138">Une valeur classique est retournée, représentant une estimation dessinée à partir d’une ou de plusieurs mesures.</span><span class="sxs-lookup"><span data-stu-id="df9f2-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="df9f2-139">Measure</span><span class="sxs-lookup"><span data-stu-id="df9f2-139">Measure</span></span> | <span data-ttu-id="df9f2-140">Une mesure de Quantum est exécutée et son résultat est renvoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="df9f2-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="df9f2-141">Préparation</span><span class="sxs-lookup"><span data-stu-id="df9f2-141">Prepare</span></span> | <span data-ttu-id="df9f2-142">Un registre donné de qubits est initialisé dans un état particulier</span><span class="sxs-lookup"><span data-stu-id="df9f2-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="df9f2-143">Exemple</span><span class="sxs-lookup"><span data-stu-id="df9f2-143">Sample</span></span> | <span data-ttu-id="df9f2-144">Une valeur classique est retournée au hasard à partir d’une distribution</span><span class="sxs-lookup"><span data-stu-id="df9f2-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="df9f2-145">Pour les fonctions, nous vous suggérons d’éviter l’utilisation de verbes en faveur des noms communs (consultez les conseils sur les noms appropriés ci-dessous) ou des adjectifs :</span><span class="sxs-lookup"><span data-stu-id="df9f2-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="df9f2-146">En particulier, dans presque tous les cas, nous vous suggérons d’utiliser des participles passés, le cas échéant, pour indiquer qu’un nom de fonction est fortement connecté à une action ou à un effet secondaire ailleurs dans un programme Quantum.</span><span class="sxs-lookup"><span data-stu-id="df9f2-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="df9f2-147">Par exemple, `ControlledOnInt` utilise la forme participe du verbe « Control » pour indiquer que la fonction agit comme un adjectif pour modifier son argument.</span><span class="sxs-lookup"><span data-stu-id="df9f2-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="df9f2-148">Ce nom présente l’avantage supplémentaire de correspondre à la sémantique du `Controlled` functor intégré, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="df9f2-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="df9f2-149">De même, les noms d' _agent_ peuvent être utilisés pour construire des noms de fonction et UDT à partir de noms d’opérations, comme dans le cas du nom `Encoder` d’un UDT qui est étroitement associé à `Encode` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="df9f2-150">Assistance</span><span class="sxs-lookup"><span data-stu-id="df9f2-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="df9f2-151">Nous vous suggérons :</span><span class="sxs-lookup"><span data-stu-id="df9f2-151">We suggest:</span></span>

- <span data-ttu-id="df9f2-152">Utilisez des verbes pour les noms d’opérations.</span><span class="sxs-lookup"><span data-stu-id="df9f2-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="df9f2-153">Utilisez des noms ou des adjectifs pour les noms de fonction.</span><span class="sxs-lookup"><span data-stu-id="df9f2-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="df9f2-154">Utilisez des noms pour les attributs et les types définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="df9f2-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="df9f2-155">Pour tous les noms pouvant être appelés, utilisez une `CamelCase` préférence forte pour `pascalCase` , `snake_case` ou `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="df9f2-156">En particulier, vérifiez que les noms pouvant être appelés commencent par des lettres majuscules.</span><span class="sxs-lookup"><span data-stu-id="df9f2-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="df9f2-157">Pour toutes les variables locales, utilisez une `pascalCase` préférence forte pour `CamelCase` , `snake_case` ou `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="df9f2-158">En particulier, vérifiez que les variables locales commencent par des minuscules.</span><span class="sxs-lookup"><span data-stu-id="df9f2-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="df9f2-159">Évitez l’utilisation de traits de soulignement `_` dans les noms de fonctions et d’opérations ; lorsque des niveaux de hiérarchie supplémentaires sont nécessaires, utilisez des espaces de noms et des alias d’espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="df9f2-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examples"></a>[<span data-ttu-id="df9f2-160">Exemples</span><span class="sxs-lookup"><span data-stu-id="df9f2-160">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="df9f2-161">Nom</span><span class="sxs-lookup"><span data-stu-id="df9f2-161">Name</span></span> | <span data-ttu-id="df9f2-162">Description</span><span class="sxs-lookup"><span data-stu-id="df9f2-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="df9f2-163">☑</span><span class="sxs-lookup"><span data-stu-id="df9f2-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="df9f2-164">Effacez l’utilisation d’un verbe (« réfléchir ») pour indiquer l’effet de l’opération.</span><span class="sxs-lookup"><span data-stu-id="df9f2-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="df9f2-165">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="df9f2-166">L’utilisation de l’expression nominale suggère une fonction plutôt que l’opération.</span><span class="sxs-lookup"><span data-stu-id="df9f2-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="df9f2-167">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="df9f2-168">L’utilisation de `snake_case` transgresse la notation Q #.</span><span class="sxs-lookup"><span data-stu-id="df9f2-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="df9f2-169">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="df9f2-170">L’utilisation de traits de soulignement internes au nom de l’opération contrevient à la notation Q #.</span><span class="sxs-lookup"><span data-stu-id="df9f2-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="df9f2-171">☑</span><span class="sxs-lookup"><span data-stu-id="df9f2-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="df9f2-172">L’utilisation de l’expression nominale suggère que la fonction retourne une opération.</span><span class="sxs-lookup"><span data-stu-id="df9f2-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="df9f2-173">☑</span><span class="sxs-lookup"><span data-stu-id="df9f2-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="df9f2-174">Effacez l’utilisation du nom (« FACT ») pour indiquer qu’il s’agit d’une fonction, tandis que le adjectif.</span><span class="sxs-lookup"><span data-stu-id="df9f2-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="df9f2-175">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="df9f2-176">L’utilisation du verbe (« obten ») suggère qu’il s’agit d’une opération.</span><span class="sxs-lookup"><span data-stu-id="df9f2-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="df9f2-177">☑</span><span class="sxs-lookup"><span data-stu-id="df9f2-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="df9f2-178">L’utilisation de l’expression nominale fait clairement référence au résultat de l’appel du constructeur UDT.</span><span class="sxs-lookup"><span data-stu-id="df9f2-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="df9f2-179">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="df9f2-180">L’utilisation de l’expression verbale suggère que le constructeur UDT est une opération.</span><span class="sxs-lookup"><span data-stu-id="df9f2-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="df9f2-181">☑</span><span class="sxs-lookup"><span data-stu-id="df9f2-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="df9f2-182">L’utilisation de l’expression substantif communique l’utilisation de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="df9f2-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="df9f2-183">Raccourcis et abréviations</span><span class="sxs-lookup"><span data-stu-id="df9f2-183">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="df9f2-184">En dépit des conseils ci-dessus, il existe de nombreuses formes de raccourci qui voient une utilisation courante et généralisée dans quantum computing.</span><span class="sxs-lookup"><span data-stu-id="df9f2-184">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="df9f2-185">Nous vous suggérons d’utiliser le raccourci existant et commun là où il existe, en particulier pour les opérations qui sont intrinsèques au fonctionnement d’un ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="df9f2-185">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="df9f2-186">Par exemple, nous choisissons le nom `X` au lieu de `ApplyX` et `Rz` au lieu de `RotateAboutZ` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-186">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="df9f2-187">Lors de l’utilisation de tels raccourcis, les noms d’opérations doivent être en majuscules (par exemple : `MAJ` ).</span><span class="sxs-lookup"><span data-stu-id="df9f2-187">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="df9f2-188">Une attention particulière est nécessaire lors de l’application de cette Convention dans le cas des acronymes et des abréviations couramment utilisés, tels que « QFT » pour « transformation de Fourier quantique ».</span><span class="sxs-lookup"><span data-stu-id="df9f2-188">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="df9f2-189">Nous vous suggérons de suivre les conventions .NET générales pour l’utilisation d’acronymes et de abréviations dans les noms complets, qui prescrivent que :</span><span class="sxs-lookup"><span data-stu-id="df9f2-189">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="df9f2-190">les acronymes à deux lettres et les abréviations sont nommés en majuscules (par exemple `BE` , « Big-endian »).</span><span class="sxs-lookup"><span data-stu-id="df9f2-190">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="df9f2-191">tous les acronymes et abréviationss plus longs sont nommés dans `CamelCase` (par exemple, `Qft` pour « transformation de Fourier quantique »)</span><span class="sxs-lookup"><span data-stu-id="df9f2-191">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="df9f2-192">Par conséquent, une opération qui implémente le QFT peut être appelée `QFT` comme raccourci, ou écrite en tant que `ApplyQft` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-192">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="df9f2-193">Pour les opérations et les fonctions les plus couramment utilisées, il peut être souhaitable de fournir un nom abrégé comme _alias_ pour une forme plus longue :</span><span class="sxs-lookup"><span data-stu-id="df9f2-193">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[<span data-ttu-id="df9f2-194">Assistance</span><span class="sxs-lookup"><span data-stu-id="df9f2-194">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="df9f2-195">Nous vous suggérons :</span><span class="sxs-lookup"><span data-stu-id="df9f2-195">We suggest:</span></span>

- <span data-ttu-id="df9f2-196">Considérez les noms abrégés couramment acceptés et largement utilisés, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="df9f2-196">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="df9f2-197">Utilisez des majuscules pour les raccourcis.</span><span class="sxs-lookup"><span data-stu-id="df9f2-197">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="df9f2-198">Utilisation de majuscules pour les acronymes courts (à deux lettres) et abréviations.</span><span class="sxs-lookup"><span data-stu-id="df9f2-198">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="df9f2-199">Utilisez `CamelCase` pour des acronymes plus longs (au moins trois lettres) et abréviations.</span><span class="sxs-lookup"><span data-stu-id="df9f2-199">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examples"></a>[<span data-ttu-id="df9f2-200">Exemples</span><span class="sxs-lookup"><span data-stu-id="df9f2-200">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="df9f2-201">Nom</span><span class="sxs-lookup"><span data-stu-id="df9f2-201">Name</span></span> | <span data-ttu-id="df9f2-202">Description</span><span class="sxs-lookup"><span data-stu-id="df9f2-202">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="df9f2-203">☑</span><span class="sxs-lookup"><span data-stu-id="df9f2-203">☑</span></span> | `X` | <span data-ttu-id="df9f2-204">Raccourci bien maîtrisé pour « appliquer une transformation $X $ »</span><span class="sxs-lookup"><span data-stu-id="df9f2-204">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="df9f2-205">☑</span><span class="sxs-lookup"><span data-stu-id="df9f2-205">☑</span></span> | `CNOT` | <span data-ttu-id="df9f2-206">Raccourci bien maîtrisé pour « contrôlé-non »</span><span class="sxs-lookup"><span data-stu-id="df9f2-206">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="df9f2-207">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-207">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="df9f2-208">La forme abrégée ne doit pas être dans `CamelCase` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-208">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="df9f2-209">☑</span><span class="sxs-lookup"><span data-stu-id="df9f2-209">☑</span></span> | `ApplyQft` | <span data-ttu-id="df9f2-210">L’initialiseur commun « QFT » apparaît dans le cadre d’un nom de forme longue.</span><span class="sxs-lookup"><span data-stu-id="df9f2-210">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="df9f2-211">☑</span><span class="sxs-lookup"><span data-stu-id="df9f2-211">☑</span></span> | `QFT` | <span data-ttu-id="df9f2-212">L’initialiseur commun « QFT » apparaît dans le cadre d’un nom abrégé.</span><span class="sxs-lookup"><span data-stu-id="df9f2-212">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="df9f2-213">Noms appropriés dans les noms</span><span class="sxs-lookup"><span data-stu-id="df9f2-213">Proper Nouns in Names</span></span> ###

<span data-ttu-id="df9f2-214">En physique, il est courant de nommer les éléments après la première personne à publier à leur sujet, la plupart des non-Physicists ne sont pas familiers avec les noms de tout le monde et tout l’historique.</span><span class="sxs-lookup"><span data-stu-id="df9f2-214">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="df9f2-215">La confiance trop importante au niveau des conventions de nommage de la physique peut donc poser un obstacle important à l’entrée, car les utilisateurs des autres arrière-plans doivent apprendre un grand nombre de noms apparemment opaques afin d’utiliser des opérations et des concepts courants.</span><span class="sxs-lookup"><span data-stu-id="df9f2-215">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="df9f2-216">Par conséquent, nous vous recommandons d’adopter, à chaque fois que cela est raisonnable, des noms communs qui décrivent un concept en privilégiant les noms appropriés qui décrivent l’historique de publication d’un concept.</span><span class="sxs-lookup"><span data-stu-id="df9f2-216">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="df9f2-217">En guise d’exemple particulier, les opérations d’échange contrôlé unique et non contrôlé doublement sont souvent appelées les opérations « Fredkin » et « Toffoli » dans la documentation académique, mais elles sont identifiées dans Q # principalement comme `CSWAP` et `CCNOT` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-217">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="df9f2-218">Dans les deux cas, les commentaires de documentation de l’API fournissent des noms synonymes basés sur des noms appropriés, ainsi que toutes les citations appropriées.</span><span class="sxs-lookup"><span data-stu-id="df9f2-218">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="df9f2-219">Cette préférence est particulièrement importante, étant donné que certaines utilisations des noms corrects sont toujours nécessaires : Q # suit la tradition définie par de nombreuses langues classiques, par exemple, et fait référence aux `Bool` types en référence à la logique booléenne, qui est à son tour nommée en respectant George bool.</span><span class="sxs-lookup"><span data-stu-id="df9f2-219">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="df9f2-220">De même, quelques concepts quantiques sont nommés de la même façon, y compris le `Pauli` type intégré au langage Q #.</span><span class="sxs-lookup"><span data-stu-id="df9f2-220">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="df9f2-221">En réduisant l’utilisation des noms appropriés dans lesquels ce type d’utilisation n’est pas essentiel, nous réduisons l’impact que les noms appropriés ne peuvent pas être raisonnablement évités.</span><span class="sxs-lookup"><span data-stu-id="df9f2-221">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="df9f2-222">Assistance</span><span class="sxs-lookup"><span data-stu-id="df9f2-222">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="df9f2-223">Nous vous suggérons :</span><span class="sxs-lookup"><span data-stu-id="df9f2-223">We suggest:</span></span>

- <span data-ttu-id="df9f2-224">Évitez d’utiliser des noms corrects dans les noms.</span><span class="sxs-lookup"><span data-stu-id="df9f2-224">Avoid the use of proper nouns in names.</span></span>

# <a name="examples"></a>[<span data-ttu-id="df9f2-225">Exemples</span><span class="sxs-lookup"><span data-stu-id="df9f2-225">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="df9f2-226">Conversions de type</span><span class="sxs-lookup"><span data-stu-id="df9f2-226">Type Conversions</span></span> ###

<span data-ttu-id="df9f2-227">Comme Q # est un langage fortement et statiquement typé, une valeur d’un type ne peut être utilisée qu’en tant que valeur d’un autre type à l’aide d’un appel explicite à une fonction de conversion de type.</span><span class="sxs-lookup"><span data-stu-id="df9f2-227">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="df9f2-228">Cela diffère des langages qui permettent aux valeurs de changer les types implicitement (par exemple, la promotion de type) ou en effectuant une conversion.</span><span class="sxs-lookup"><span data-stu-id="df9f2-228">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="df9f2-229">Par conséquent, les fonctions de conversion de type jouent un rôle important dans le développement de bibliothèque Q #, et constituent l’une des décisions les plus fréquemment rencontrées sur l’affectation de noms.</span><span class="sxs-lookup"><span data-stu-id="df9f2-229">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="df9f2-230">Toutefois, étant donné que les conversions de type sont toujours _déterministes_, elles peuvent être écrites en tant que fonctions et, par conséquent, tomber sous les conseils ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="df9f2-230">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="df9f2-231">En particulier, nous suggérons que les fonctions de conversion de type ne doivent jamais être nommées en tant que verbes (par exemple, `ConvertToX` ) ou des expressions prépositionnelles adverbes ( `ToX` ), mais doivent être nommées en tant qu’expressions prépositionnelles avec adjectif qui indiquent les types source et de destination ( `XAsY` ).</span><span class="sxs-lookup"><span data-stu-id="df9f2-231">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="df9f2-232">Lors de la liste des types de tableau dans les noms de fonctions de conversion de type, nous vous recommandons le raccourci `Arr` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-232">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="df9f2-233">Dans des circonstances exceptionnelles, nous recommandons que toutes les fonctions de conversion de type soient nommées à l’aide `As` de afin qu’elles puissent être identifiées rapidement.</span><span class="sxs-lookup"><span data-stu-id="df9f2-233">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="df9f2-234">Assistance</span><span class="sxs-lookup"><span data-stu-id="df9f2-234">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="df9f2-235">Nous vous suggérons :</span><span class="sxs-lookup"><span data-stu-id="df9f2-235">We suggest:</span></span>

- <span data-ttu-id="df9f2-236">Si une fonction convertit une valeur de type `X` en une valeur de type `Y` , utilisez le nom `AsY` ou `XAsY` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-236">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examples"></a>[<span data-ttu-id="df9f2-237">Exemples</span><span class="sxs-lookup"><span data-stu-id="df9f2-237">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="df9f2-238">Nom</span><span class="sxs-lookup"><span data-stu-id="df9f2-238">Name</span></span> | <span data-ttu-id="df9f2-239">Description</span><span class="sxs-lookup"><span data-stu-id="df9f2-239">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="df9f2-240">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-240">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="df9f2-241">La préposition « to » génère une expression verbale, indiquant une opération et non une fonction.</span><span class="sxs-lookup"><span data-stu-id="df9f2-241">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="df9f2-242">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-242">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="df9f2-243">Le type d’entrée n’est pas clair dans le nom de la fonction.</span><span class="sxs-lookup"><span data-stu-id="df9f2-243">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="df9f2-244">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-244">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="df9f2-245">Les types d’entrée et de sortie apparaissent dans un ordre incorrect.</span><span class="sxs-lookup"><span data-stu-id="df9f2-245">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="df9f2-246">☑</span><span class="sxs-lookup"><span data-stu-id="df9f2-246">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="df9f2-247">Les types d’entrée et de sortie sont tous les deux clairs.</span><span class="sxs-lookup"><span data-stu-id="df9f2-247">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="df9f2-248">Noms privés ou internes</span><span class="sxs-lookup"><span data-stu-id="df9f2-248">Private or Internal Names</span></span> ###

<span data-ttu-id="df9f2-249">Dans de nombreux cas, un nom est strictement destiné à une utilisation interne à une bibliothèque ou à un projet, et n’est pas une partie garantie de l’API offerte par une bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="df9f2-249">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="df9f2-250">Il est utile d’indiquer clairement que c’est le cas lorsque vous nommez des fonctions et des opérations afin que les dépendances accidentelles sur le code interne uniquement soient rendues évidentes.</span><span class="sxs-lookup"><span data-stu-id="df9f2-250">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="df9f2-251">Si une opération ou une fonction n’est pas destinée à une utilisation directe, mais doit plutôt être utilisée par un Callable correspondant qui agit par une application partielle, envisagez d’utiliser un nom commençant par le `internal` mot clé pour l’appelable partiellement appliqué.</span><span class="sxs-lookup"><span data-stu-id="df9f2-251">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with the `internal` keyword for the callable that is partially applied.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="df9f2-252">Assistance</span><span class="sxs-lookup"><span data-stu-id="df9f2-252">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="df9f2-253">Nous vous suggérons :</span><span class="sxs-lookup"><span data-stu-id="df9f2-253">We suggest:</span></span>

- <span data-ttu-id="df9f2-254">Lorsqu’une fonction, une opération ou un type défini par l’utilisateur ne fait pas partie de l’API publique d’une bibliothèque ou d’un programme Q #, assurez-vous qu’elle est marquée comme étant interne en plaçant le `internal` mot clé avant la `function` `operation` déclaration, ou `newtype` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-254">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that it is marked as internal by placing the `internal` keyword before the `function`, `operation`, or `newtype` declaration.</span></span>

# <a name="examples"></a>[<span data-ttu-id="df9f2-255">Exemples</span><span class="sxs-lookup"><span data-stu-id="df9f2-255">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="df9f2-256">Nom</span><span class="sxs-lookup"><span data-stu-id="df9f2-256">Name</span></span> | <span data-ttu-id="df9f2-257">Description</span><span class="sxs-lookup"><span data-stu-id="df9f2-257">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="df9f2-258">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-258">☒</span></span> | <s>`operation _ApplyDecomposedOperation`</s> | <span data-ttu-id="df9f2-259">N’utilisez pas de trait de soulignement `_` pour indiquer que cette opération est réservée à un usage interne.</span><span class="sxs-lookup"><span data-stu-id="df9f2-259">Do not use an underscore `_` to indicate that this operation is for internal use only.</span></span> |
| <span data-ttu-id="df9f2-260">☑</span><span class="sxs-lookup"><span data-stu-id="df9f2-260">☑</span></span> | `internal operation ApplyDecomposedOperation` | <span data-ttu-id="df9f2-261">Le `internal` mot clé au début indique clairement que cette opération est réservée à un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="df9f2-261">The `internal` keyword at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***
### <a name="variants"></a><span data-ttu-id="df9f2-262">Variantes</span><span class="sxs-lookup"><span data-stu-id="df9f2-262">Variants</span></span> ###

<span data-ttu-id="df9f2-263">Bien que cette limitation puisse ne pas persister dans les versions ultérieures de Q #, c’est pour l’instant le cas qu’il y aura souvent des groupes d’opérations ou de fonctions connexes qui se distinguent par les functors pris en charge par leurs entrées, ou par les types concrets de leurs arguments.</span><span class="sxs-lookup"><span data-stu-id="df9f2-263">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="df9f2-264">Ces groupes peuvent être distingués à l’aide du même nom racine, suivi d’une ou de deux lettres indiquant sa variante.</span><span class="sxs-lookup"><span data-stu-id="df9f2-264">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="df9f2-265">Suffixe</span><span class="sxs-lookup"><span data-stu-id="df9f2-265">Suffix</span></span> | <span data-ttu-id="df9f2-266">Signification</span><span class="sxs-lookup"><span data-stu-id="df9f2-266">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="df9f2-267">Entrée attendue pour la prise en charge`Adjoint`</span><span class="sxs-lookup"><span data-stu-id="df9f2-267">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="df9f2-268">Entrée attendue pour la prise en charge`Controlled`</span><span class="sxs-lookup"><span data-stu-id="df9f2-268">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="df9f2-269">Entrée attendue pour prendre en charge `Controlled` et`Adjoint`</span><span class="sxs-lookup"><span data-stu-id="df9f2-269">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="df9f2-270">L’entrée ou les entrées sont de type`Int`</span><span class="sxs-lookup"><span data-stu-id="df9f2-270">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="df9f2-271">L’entrée ou les entrées sont de type`Double`</span><span class="sxs-lookup"><span data-stu-id="df9f2-271">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="df9f2-272">L’entrée ou les entrées sont de type`BigInt`</span><span class="sxs-lookup"><span data-stu-id="df9f2-272">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidance"></a>[<span data-ttu-id="df9f2-273">Assistance</span><span class="sxs-lookup"><span data-stu-id="df9f2-273">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="df9f2-274">Nous vous suggérons :</span><span class="sxs-lookup"><span data-stu-id="df9f2-274">We suggest:</span></span>

- <span data-ttu-id="df9f2-275">Si une fonction ou une opération n’est pas liée à des fonctions ou des opérations similaires par les types et la prise en charge de functor de leurs entrées, n’utilisez pas de suffixe.</span><span class="sxs-lookup"><span data-stu-id="df9f2-275">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="df9f2-276">Si une fonction ou une opération est liée à des fonctions ou des opérations similaires par les types et la prise en charge de functor de leurs entrées, utilisez des suffixes comme dans le tableau ci-dessus pour distinguer les variantes.</span><span class="sxs-lookup"><span data-stu-id="df9f2-276">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examples"></a>[<span data-ttu-id="df9f2-277">Exemples</span><span class="sxs-lookup"><span data-stu-id="df9f2-277">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="df9f2-278">Arguments et variables</span><span class="sxs-lookup"><span data-stu-id="df9f2-278">Arguments and Variables</span></span> ###

<span data-ttu-id="df9f2-279">L’un des objectifs clés du code Q # pour une fonction ou une opération est qu’il soit facile à lire et à comprendre.</span><span class="sxs-lookup"><span data-stu-id="df9f2-279">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="df9f2-280">De même, les noms des entrées et des arguments de type doivent indiquer comment une fonction ou un argument sera utilisé une fois fourni.</span><span class="sxs-lookup"><span data-stu-id="df9f2-280">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="df9f2-281">Assistance</span><span class="sxs-lookup"><span data-stu-id="df9f2-281">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="df9f2-282">Nous vous suggérons :</span><span class="sxs-lookup"><span data-stu-id="df9f2-282">We suggest:</span></span>

- <span data-ttu-id="df9f2-283">Pour tous les noms de variable et d’entrée, utilisez une `pascalCase` préférence forte pour `CamelCase` , `snake_case` ou `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-283">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="df9f2-284">Les noms d’entrée doivent être descriptifs ; Évitez une ou deux noms de lettres dans la mesure du possible.</span><span class="sxs-lookup"><span data-stu-id="df9f2-284">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="df9f2-285">Les opérations et les fonctions acceptant exactement un argument de type doivent désigner cet argument de type par `T` lorsque son rôle est évident.</span><span class="sxs-lookup"><span data-stu-id="df9f2-285">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="df9f2-286">Si une fonction ou une opération accepte plusieurs arguments de type, ou si le rôle d’un argument de type unique n’est pas évident, envisagez d’utiliser un mot en majuscules `T` (par exemple : `TOutput` ) pour chaque type.</span><span class="sxs-lookup"><span data-stu-id="df9f2-286">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="df9f2-287">N’incluez pas de noms de types dans les noms d’arguments et de variables ; ces informations peuvent et doivent être fournies par votre environnement de développement.</span><span class="sxs-lookup"><span data-stu-id="df9f2-287">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="df9f2-288">Dénotez les types scalaires par leurs noms littéraux ( `flagQubit` ) et les types de tableau par un pluriel ( `measResults` ).</span><span class="sxs-lookup"><span data-stu-id="df9f2-288">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="df9f2-289">Pour les tableaux de qubits en particulier, envisagez de dénoter ces types en fonction de `Register` l’emplacement où le nom fait référence à une séquence de qubits étroitement liée d’une certaine façon.</span><span class="sxs-lookup"><span data-stu-id="df9f2-289">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="df9f2-290">Les variables utilisées en tant qu’index dans des tableaux doivent commencer par `idx` et doivent être singulières (par exemple : `things[idxThing]` ).</span><span class="sxs-lookup"><span data-stu-id="df9f2-290">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="df9f2-291">En particulier, évitez fortement d’utiliser des noms de variable à une seule lettre comme index ; envisagez `idx` d’utiliser au minimum.</span><span class="sxs-lookup"><span data-stu-id="df9f2-291">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="df9f2-292">Les variables utilisées pour contenir les longueurs des tableaux doivent commencer par `n` et être plurielées (par exemple : `nThings` ).</span><span class="sxs-lookup"><span data-stu-id="df9f2-292">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="df9f2-293">Exemples</span><span class="sxs-lookup"><span data-stu-id="df9f2-293">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="df9f2-294">Éléments nommés d’un type défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="df9f2-294">User-Defined Type Named Items</span></span> ###

<span data-ttu-id="df9f2-295">Les éléments nommés dans les types définis par l’utilisateur doivent être nommés `CamelCase` , même dans l’entrée des constructeurs UDT.</span><span class="sxs-lookup"><span data-stu-id="df9f2-295">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="df9f2-296">Cela permet de séparer clairement les éléments nommés des références aux variables de portée locale lors de l’utilisation de la notation d’accesseur (par exemple : `callable::Apply` ) ou de la notation de copie et de mise à jour ( `set arr w/= Data <- newData` ).</span><span class="sxs-lookup"><span data-stu-id="df9f2-296">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidance"></a>[<span data-ttu-id="df9f2-297">Assistance</span><span class="sxs-lookup"><span data-stu-id="df9f2-297">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="df9f2-298">Nous vous suggérons :</span><span class="sxs-lookup"><span data-stu-id="df9f2-298">We suggest:</span></span>

- <span data-ttu-id="df9f2-299">Les éléments nommés dans les constructeurs UDT doivent être nommés comme `CamelCase` ; autrement dit, ils doivent commencer par une majuscule initiale.</span><span class="sxs-lookup"><span data-stu-id="df9f2-299">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="df9f2-300">Les éléments nommés qui sont résolus en opérations doivent être nommés comme phases de verbe.</span><span class="sxs-lookup"><span data-stu-id="df9f2-300">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="df9f2-301">Les éléments nommés qui ne sont pas résolus en opérations doivent être nommés comme des expressions nominales.</span><span class="sxs-lookup"><span data-stu-id="df9f2-301">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="df9f2-302">Pour les UDT qui encapsulent des opérations, un seul élément nommé appelé `Apply` doit être défini.</span><span class="sxs-lookup"><span data-stu-id="df9f2-302">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examples"></a>[<span data-ttu-id="df9f2-303">Exemples</span><span class="sxs-lookup"><span data-stu-id="df9f2-303">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="df9f2-304">Extrait</span><span class="sxs-lookup"><span data-stu-id="df9f2-304">Snippet</span></span> | <span data-ttu-id="df9f2-305">Description</span><span class="sxs-lookup"><span data-stu-id="df9f2-305">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="df9f2-306">☑</span><span class="sxs-lookup"><span data-stu-id="df9f2-306">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="df9f2-307">Le nom `Apply` est une `CamelCase` expression verbale au format, suggérant que l’élément nommé est une opération.</span><span class="sxs-lookup"><span data-stu-id="df9f2-307">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="df9f2-308">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-308">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="df9f2-309">Les éléments nommés doivent commencer par une lettre majuscule initiale.</span><span class="sxs-lookup"><span data-stu-id="df9f2-309">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="df9f2-310">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-310">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="df9f2-311">Les éléments nommés qui sont résolus en fonctions doivent être nommés comme des expressions nominales, et non comme des expressions verbales.</span><span class="sxs-lookup"><span data-stu-id="df9f2-311">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="df9f2-312">Conventions d’entrée</span><span class="sxs-lookup"><span data-stu-id="df9f2-312">Input Conventions</span></span> ##

<span data-ttu-id="df9f2-313">Quand un développeur appelle une opération ou une fonction, les différentes entrées de cette opération ou fonction doivent être spécifiées dans un ordre particulier, ce qui a pour but d’augmenter la charge cognitive qu’un développeur doit utiliser pour utiliser une bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="df9f2-313">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="df9f2-314">En particulier, la tâche de mémorisation des commandes d’entrée est souvent une gêne de la tâche en cours : programmation d’une implémentation d’un algorithme Quantum.</span><span class="sxs-lookup"><span data-stu-id="df9f2-314">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="df9f2-315">Bien que la prise en charge de l’IDE riche puisse atténuer ce risque dans une large mesure, la bonne conception et l’adhésion aux conventions communes peuvent également aider à réduire la charge cognitive imposée par une API.</span><span class="sxs-lookup"><span data-stu-id="df9f2-315">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="df9f2-316">Dans la mesure du possible, il peut être utile de réduire le nombre d’entrées attendues par une opération ou une fonction, afin que le rôle de chaque entrée soit immédiatement visible pour les développeurs qui appellent dans cette opération ou cette fonction, et pour les développeurs qui lisent ce code ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="df9f2-316">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="df9f2-317">En particulier lorsqu’il n’est pas possible ou raisonnable de réduire le nombre d’arguments d’une opération ou d’une fonction, il est important de disposer d’un ordre cohérent qui minimise la surprise qu’un utilisateur fait face lors de la prédiction de l’ordre des entrées.</span><span class="sxs-lookup"><span data-stu-id="df9f2-317">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="df9f2-318">Nous recommandons une convention de classement d’entrée qui dérive largement de la réflexion de l’application partielle comme une généralisation de la curryfication f (x, y) ≡ f (x) (y).</span><span class="sxs-lookup"><span data-stu-id="df9f2-318">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="df9f2-319">Ainsi, l’application partielle des premiers arguments doit entraîner l’appel d’un pouvant être appelé de manière appropriée chaque fois que cela est raisonnable.</span><span class="sxs-lookup"><span data-stu-id="df9f2-319">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="df9f2-320">En suivant ce principe, envisagez d’utiliser l’ordre des arguments suivant :</span><span class="sxs-lookup"><span data-stu-id="df9f2-320">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="df9f2-321">Arguments non pouvant être appelés classiques, tels que des angles, des vecteurs de puissances, etc.</span><span class="sxs-lookup"><span data-stu-id="df9f2-321">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="df9f2-322">Arguments pouvant être appelés (fonctions et arguments).</span><span class="sxs-lookup"><span data-stu-id="df9f2-322">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="df9f2-323">Si les fonctions et les opérations sont prises comme arguments, envisagez de placer des opérations après les fonctions.</span><span class="sxs-lookup"><span data-stu-id="df9f2-323">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="df9f2-324">Collections traitées par des arguments pouvant être appelés de la même façon `Map` que,, `Iter` `Enumerate` et `Fold` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-324">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="df9f2-325">Arguments qubit utilisés comme contrôles.</span><span class="sxs-lookup"><span data-stu-id="df9f2-325">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="df9f2-326">Arguments qubit utilisés comme cibles.</span><span class="sxs-lookup"><span data-stu-id="df9f2-326">Qubit arguments used as targets.</span></span>

<span data-ttu-id="df9f2-327">Envisagez une opération à `ApplyPhaseEstimationIteration` utiliser dans l’estimation de phase qui prend un angle et un Oracle, passe l’angle à `Rz` modifié par un tableau de facteurs d’échelle différents, puis contrôle les applications d’Oracle.</span><span class="sxs-lookup"><span data-stu-id="df9f2-327">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="df9f2-328">Nous allons trier les entrées de `ApplyPhaseEstimationIteration` la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="df9f2-328">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
<span data-ttu-id="df9f2-329">Dans le cas particulier de la minimisation de surprise, certaines fonctions et opérations imitent le comportement des functors intégrés `Adjoint` et `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="df9f2-329">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="df9f2-330">Par exemple, `ControlledOnInt<'T>` a `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` le type, qui `ControlledOnInt<Qubit[]>(5, _)` agit comme `Controlled` functor, mais sur la condition que le registre de contrôle représente l’État $ \ket {5} = \ket {101} $.</span><span class="sxs-lookup"><span data-stu-id="df9f2-330">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="df9f2-331">Ainsi, un développeur s’attend à ce que les entrées qui `ControlledOnInt` placent l’appel soient transformées en dernier, et que l’opération résultante prenne comme entrée `(Qubit[], 'T)` ---le même ordre que celui suivi par la sortie du `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="df9f2-331">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="df9f2-332">Assistance</span><span class="sxs-lookup"><span data-stu-id="df9f2-332">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="df9f2-333">Nous vous suggérons :</span><span class="sxs-lookup"><span data-stu-id="df9f2-333">We suggest:</span></span>

- <span data-ttu-id="df9f2-334">Utilisez des ordres d’entrée cohérents avec l’utilisation d’une application partielle.</span><span class="sxs-lookup"><span data-stu-id="df9f2-334">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="df9f2-335">Utilisez des ordres d’entrée cohérents avec les functors intégrés.</span><span class="sxs-lookup"><span data-stu-id="df9f2-335">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="df9f2-336">Placez toutes les entrées classiques avant toute entrée quantique.</span><span class="sxs-lookup"><span data-stu-id="df9f2-336">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examples"></a>[<span data-ttu-id="df9f2-337">Exemples</span><span class="sxs-lookup"><span data-stu-id="df9f2-337">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="df9f2-338">Conventions de documentation</span><span class="sxs-lookup"><span data-stu-id="df9f2-338">Documentation Conventions</span></span> ##

<span data-ttu-id="df9f2-339">Le langage Q # permet d’attacher une documentation à des opérations, des fonctions et des types définis par l’utilisateur à l’aide de commentaires de documentation spécialement mis en forme.</span><span class="sxs-lookup"><span data-stu-id="df9f2-339">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="df9f2-340">Dénotés par des barres obliques ( `///` ), ces commentaires de documentation sont de petits documents de [démarque DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) qui peuvent être utilisés pour décrire l’objectif de chaque opération, fonction et type défini par l’utilisateur, les entrées attendues et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="df9f2-340">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="df9f2-341">Le compilateur fourni avec le kit de développement Quantum extrait ces commentaires et les utilise pour aider composer documentation similaire à celle de https://docs.microsoft.com/quantum .</span><span class="sxs-lookup"><span data-stu-id="df9f2-341">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="df9f2-342">De même, le serveur de langage fourni avec le kit de développement quantum utilise ces commentaires pour fournir de l’aide aux utilisateurs lorsqu’ils pointent sur des symboles dans leur code Q #.</span><span class="sxs-lookup"><span data-stu-id="df9f2-342">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="df9f2-343">L’utilisation de commentaires de documentation peut aider les utilisateurs à obtenir un sens du code en fournissant une référence utile pour les détails qui ne sont pas facilement exprimés à l’aide des autres conventions de ce document.</span><span class="sxs-lookup"><span data-stu-id="df9f2-343">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="df9f2-344">
    [Référence de la syntaxe des commentaires de documentation](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</span><span class="sxs-lookup"><span data-stu-id="df9f2-344">
    [Documentation comment syntax reference](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</span></span></div>

<span data-ttu-id="df9f2-345">Afin d’utiliser efficacement cette fonctionnalité pour aider les utilisateurs, nous vous recommandons de garder certaines choses à l’esprit lorsque vous écrivez des commentaires de documentation.</span><span class="sxs-lookup"><span data-stu-id="df9f2-345">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="df9f2-346">Assistance</span><span class="sxs-lookup"><span data-stu-id="df9f2-346">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="df9f2-347">Nous vous suggérons :</span><span class="sxs-lookup"><span data-stu-id="df9f2-347">We suggest:</span></span>

- <span data-ttu-id="df9f2-348">Chaque fonction publique, opération et type défini par l’utilisateur doit être immédiatement précédé d’un commentaire de documentation.</span><span class="sxs-lookup"><span data-stu-id="df9f2-348">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="df9f2-349">Au minimum, chaque commentaire de documentation doit inclure les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="df9f2-349">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="df9f2-350">Résumé</span><span class="sxs-lookup"><span data-stu-id="df9f2-350">Summary</span></span>
    - <span data-ttu-id="df9f2-351">Entrée</span><span class="sxs-lookup"><span data-stu-id="df9f2-351">Input</span></span>
    - <span data-ttu-id="df9f2-352">Sortie (le cas échéant)</span><span class="sxs-lookup"><span data-stu-id="df9f2-352">Output (if applicable)</span></span>
- <span data-ttu-id="df9f2-353">Assurez-vous que tous les résumés sont au moins deux phrases.</span><span class="sxs-lookup"><span data-stu-id="df9f2-353">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="df9f2-354">Si de l’espace supplémentaire est nécessaire, fournissez une `# Description` section immédiatement après `# Summary` les détails complets.</span><span class="sxs-lookup"><span data-stu-id="df9f2-354">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="df9f2-355">Dans la mesure du possible, n’incluez pas de maths dans les résumés, car tous les clients ne prennent pas en charge la notation TeX dans les résumés.</span><span class="sxs-lookup"><span data-stu-id="df9f2-355">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="df9f2-356">Notez que lors de l’écriture de documents Proseware (par exemple, TeX ou démarque), il peut être préférable d’utiliser des longueurs de ligne plus longues.</span><span class="sxs-lookup"><span data-stu-id="df9f2-356">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="df9f2-357">Fournissez toutes les expressions mathématiques pertinentes dans la `# Description` section.</span><span class="sxs-lookup"><span data-stu-id="df9f2-357">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="df9f2-358">Lors de la description des entrées, ne répétez pas les types de chaque entrée, car ceux-ci peuvent être déduits par le compilateur et risquent d’introduire une incohérence.</span><span class="sxs-lookup"><span data-stu-id="df9f2-358">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="df9f2-359">Fournissez des exemples appropriés, chacun dans sa propre `# Example` section.</span><span class="sxs-lookup"><span data-stu-id="df9f2-359">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="df9f2-360">Décrivez brièvement chaque exemple avant de répertorier le code.</span><span class="sxs-lookup"><span data-stu-id="df9f2-360">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="df9f2-361">Citez toutes les publications académiques pertinentes (par exemple, les documents, les procédures, les billets de blog et les autres implémentations) dans une `# References` section sous la forme d’une liste à puces de liens.</span><span class="sxs-lookup"><span data-stu-id="df9f2-361">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="df9f2-362">Assurez-vous que, dans la mesure du possible, tous les liens de citation sont vers des identificateurs permanents et immuables (numéros de arXiv DOIs ou avec version).</span><span class="sxs-lookup"><span data-stu-id="df9f2-362">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="df9f2-363">Lorsqu’une opération ou une fonction est liée à d’autres opérations ou fonctions par des variantes de functor, répertoriez les autres variantes comme puces dans la `# See Also` section.</span><span class="sxs-lookup"><span data-stu-id="df9f2-363">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="df9f2-364">Laissez une ligne de commentaire vide entre les sections Level-1 ( `/// #` ), mais ne laissez pas une ligne vide entre les sections Level-2 ( `/// ##` ).</span><span class="sxs-lookup"><span data-stu-id="df9f2-364">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examples"></a>[<span data-ttu-id="df9f2-365">Exemples</span><span class="sxs-lookup"><span data-stu-id="df9f2-365">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="df9f2-366">☑</span><span class="sxs-lookup"><span data-stu-id="df9f2-366">☑</span></span> ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a><span data-ttu-id="df9f2-367">Conventions de mise en forme</span><span class="sxs-lookup"><span data-stu-id="df9f2-367">Formatting Conventions</span></span> ##

<span data-ttu-id="df9f2-368">Outre les suggestions précédentes, il est utile de rendre le code aussi lisible que possible afin d’utiliser des règles de mise en forme cohérentes.</span><span class="sxs-lookup"><span data-stu-id="df9f2-368">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="df9f2-369">Ces règles de mise en forme par nature ont tendance à être quelque peu arbitraires et se caractérisent par des esthétiques personnelles.</span><span class="sxs-lookup"><span data-stu-id="df9f2-369">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="df9f2-370">Néanmoins, nous vous recommandons de conserver un ensemble cohérent de conventions de mise en forme au sein d’un groupe de collaborateurs, et en particulier pour les grands projets Q # tels que le kit de développement quantique lui-même.</span><span class="sxs-lookup"><span data-stu-id="df9f2-370">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="df9f2-371">Ces règles peuvent être appliquées automatiquement à l’aide de l’outil de mise en forme intégré au compilateur Q #.</span><span class="sxs-lookup"><span data-stu-id="df9f2-371">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="df9f2-372">Assistance</span><span class="sxs-lookup"><span data-stu-id="df9f2-372">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="df9f2-373">Nous vous suggérons :</span><span class="sxs-lookup"><span data-stu-id="df9f2-373">We suggest:</span></span>

- <span data-ttu-id="df9f2-374">Utilisez quatre espaces au lieu de tabulations pour la portabilité.</span><span class="sxs-lookup"><span data-stu-id="df9f2-374">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="df9f2-375">Par exemple, dans VS Code :</span><span class="sxs-lookup"><span data-stu-id="df9f2-375">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="df9f2-376">Retour à la ligne à 79 caractères lorsque cela est raisonnable.</span><span class="sxs-lookup"><span data-stu-id="df9f2-376">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="df9f2-377">Utilisez des espaces autour des opérateurs binaires.</span><span class="sxs-lookup"><span data-stu-id="df9f2-377">Use spaces around binary operators.</span></span>
- <span data-ttu-id="df9f2-378">Utilisez des espaces de part et d’autre des deux-points utilisés pour les annotations de type.</span><span class="sxs-lookup"><span data-stu-id="df9f2-378">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="df9f2-379">Utilisez un espace unique après les virgules utilisées dans les littéraux de tableau et de Tuple (par exemple, dans les entrées des fonctions et opérations).</span><span class="sxs-lookup"><span data-stu-id="df9f2-379">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="df9f2-380">N’utilisez pas d’espaces après les noms de fonctions, d’opérations ou d’UDT, ou après les `@` déclarations d’attribut dans.</span><span class="sxs-lookup"><span data-stu-id="df9f2-380">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="df9f2-381">Chaque déclaration d’attribut doit être sur sa propre ligne.</span><span class="sxs-lookup"><span data-stu-id="df9f2-381">Each attribute declaration should be on its own line.</span></span>

# <a name="examples"></a>[<span data-ttu-id="df9f2-382">Exemples</span><span class="sxs-lookup"><span data-stu-id="df9f2-382">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="df9f2-383">Extrait</span><span class="sxs-lookup"><span data-stu-id="df9f2-383">Snippet</span></span> | <span data-ttu-id="df9f2-384">Description</span><span class="sxs-lookup"><span data-stu-id="df9f2-384">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="df9f2-385">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-385">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="df9f2-386">Utilisez des espaces autour des opérateurs binaires.</span><span class="sxs-lookup"><span data-stu-id="df9f2-386">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="df9f2-387">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-387">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="df9f2-388">Utilisez des espaces autour des deux-points d’annotation de type.</span><span class="sxs-lookup"><span data-stu-id="df9f2-388">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="df9f2-389">☑</span><span class="sxs-lookup"><span data-stu-id="df9f2-389">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="df9f2-390">Les éléments du tuple d’entrée sont correctement espacés pour une meilleure lisibilité.</span><span class="sxs-lookup"><span data-stu-id="df9f2-390">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="df9f2-391">☒</span><span class="sxs-lookup"><span data-stu-id="df9f2-391">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="df9f2-392">Les espaces doivent être supprimés après les noms des fonctions, des opérations ou des UDT.</span><span class="sxs-lookup"><span data-stu-id="df9f2-392">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***