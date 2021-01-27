---
title: Contribution à la documentation Microsoft QDK
description: Apprenez à contribuer au contenu conceptuel ou d’API dans le jeu de documentation Quantum Microsoft.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.docs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8602705d2dd071e822e2ff58a9a44cd0684f77f1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857357"
---
# <a name="improving-documentation"></a><span data-ttu-id="1645d-103">Amélioration de la documentation</span><span class="sxs-lookup"><span data-stu-id="1645d-103">Improving Documentation</span></span>

<span data-ttu-id="1645d-104">La documentation du kit de développement quantique prend plusieurs formes, de sorte que les informations sont facilement accessibles aux développeurs Quantum.</span><span class="sxs-lookup"><span data-stu-id="1645d-104">The documentation for the Quantum Development Kit takes on several different forms, such that information is readily available to quantum developers.</span></span>

<span data-ttu-id="1645d-105">Selon les principes de la documentation [en tant que code](https://www.writethedocs.org/guide/docs-as-code/), toute la documentation du kit de développement Quantum est mise en forme en tant que code et gérée à l’aide de git de la même façon que le code source utilisé pour créer le kit de développement quantique.</span><span class="sxs-lookup"><span data-stu-id="1645d-105">Following the principles of [Docs as Code](https://www.writethedocs.org/guide/docs-as-code/), all Quantum Development Kit documentation is formatted as code and is managed using Git in the same way as the source code that is used to build the Quantum Development Kit.</span></span>
<span data-ttu-id="1645d-106">Dans la plupart des cas, la documentation de stockage du code se compose de différentes formes de [démarque](https://daringfireball.net/projects/markdown/), un langage permettant d’écrire du texte enrichi dans un format de texte brut facile à utiliser sur la ligne de commande, dans IDE et avec le contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="1645d-106">For the most part, the code backing documentation consists of various forms of [Markdown](https://daringfireball.net/projects/markdown/), a language for writing out richly formatted text in a plain text format that's easy to use at the command line, in IDEs, and with source control.</span></span>
<span data-ttu-id="1645d-107">Nous adoptons de la même manière la bibliothèque [MathJax](https://www.mathjax.org/) pour permettre la mise en forme des mathématiques dans la documentation utilisant le langage latex, comme indiqué plus loin ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="1645d-107">We similarly adopt the [MathJax](https://www.mathjax.org/) library to allow for formatting mathematics in documentation using the LaTeX language, as detailed further below.</span></span>


<span data-ttu-id="1645d-108">Cela dit, chaque forme de documentation varie quelque peu dans les détails :</span><span class="sxs-lookup"><span data-stu-id="1645d-108">That said, each form of documentation does vary somewhat in the details:</span></span>

- <span data-ttu-id="1645d-109">La **documentation conceptuelle** se compose d’un ensemble d’articles publiés dans https://docs.microsoft.com/quantum et qui décrivent tous les éléments de base de quantum computing aux spécifications techniques des formats d’échange.</span><span class="sxs-lookup"><span data-stu-id="1645d-109">The **conceptual documentation** consists of a set of articles that are published to https://docs.microsoft.com/quantum, and that describe everything from the basics of quantum computing to the technical specifications for interchange formats.</span></span> <span data-ttu-id="1645d-110">Ces articles sont écrits en [DocFX (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), une variante de démarque utilisée pour créer des ensembles de documentation enrichis.</span><span class="sxs-lookup"><span data-stu-id="1645d-110">These articles are written in [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a Markdown variant used for creating rich documentation sets.</span></span>
- <span data-ttu-id="1645d-111">La **référence d’API** est un ensemble de pages pour chaque Q# fonction, opération et type défini par l’utilisateur, publié sur https://docs.microsoft.com/qsharp/api/ .</span><span class="sxs-lookup"><span data-stu-id="1645d-111">The **API reference** is a set of pages for each Q# function, operation, and user-defined type, published to https://docs.microsoft.com/qsharp/api/.</span></span> <span data-ttu-id="1645d-112">Ces pages documentent les entrées et les opérations à chaque appel, ainsi que des exemples et des liens vers des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="1645d-112">These pages document the inputs and operations to each callable, along with examples and links to more information.</span></span> <span data-ttu-id="1645d-113">La référence d’API est automatiquement extraite des petits documents DFM dans le Q# code source dans le cadre de chaque version.</span><span class="sxs-lookup"><span data-stu-id="1645d-113">The API reference is automatically extracted from small DFM documents in Q# source code as a part of each release.</span></span>
- <span data-ttu-id="1645d-114">Les fichiers **Readme <!----> . MD** inclus avec chaque exemple et Kata décrivent comment utiliser cet exemple ou Kata sont utilisés, ce qu’il couvre et comment il se réfère au reste du kit de développement quantique.</span><span class="sxs-lookup"><span data-stu-id="1645d-114">The **README<!---->.md** files included with each sample and kata describe how to use that sample or kata is used, what it covers, and how it relates to the rest of the Quantum Development Kit.</span></span> <span data-ttu-id="1645d-115">Ces fichiers sont écrits à l’aide de la [démarque GitHub (GFM)](https://github.github.com/gfm/), une alternative plus légère à DFM qui est populaire pour l’attachement de la documentation directement aux dépôts de code.</span><span class="sxs-lookup"><span data-stu-id="1645d-115">These files are written using [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), a more lightweight alternative to DFM that's popular for attaching documentation directly to code repositories.</span></span>

## <a name="contributing-to-the-conceptual-documentation"></a><span data-ttu-id="1645d-116">Contribution à la documentation conceptuelle</span><span class="sxs-lookup"><span data-stu-id="1645d-116">Contributing to the Conceptual Documentation</span></span>

<span data-ttu-id="1645d-117">Pour apporter une amélioration à la documentation conceptuelle ou lisez-moi, commence par une demande de tirage (pull request) sur [**MicrosoftDocs/Quantum-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)ou [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), selon le cas.</span><span class="sxs-lookup"><span data-stu-id="1645d-117">To contribute an improvement to the conceptual or README documentation, then, starts with a pull request onto either [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum), or [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), as is appropriate.</span></span>
<span data-ttu-id="1645d-118">Nous décrirons plus en détail les requêtes de tirage ci-dessous, mais pour l’instant, il y a quelques éléments à prendre en compte lors de l’amélioration de la documentation :</span><span class="sxs-lookup"><span data-stu-id="1645d-118">We'll describe more about pull requests below, but for now there's a few things that are good to keep in mind as you improve documentation:</span></span>

- <span data-ttu-id="1645d-119">Les lecteurs arrivent dans la documentation du kit de développement quantique à partir d’un très grand nombre d’arrière-plans.</span><span class="sxs-lookup"><span data-stu-id="1645d-119">Readers come to the Quantum Development Kit documentation from a very wide range of backgrounds.</span></span> <span data-ttu-id="1645d-120">Tout le monde des étudiants de la grande école cherchant à apprendre une nouvelle et passionnante de voir les enseignants effectuant une recherche quantum computing devrait être en mesure de lire la documentation.</span><span class="sxs-lookup"><span data-stu-id="1645d-120">Everyone from high school students looking to learn something new and exciting through to tenured faculty performing quantum computing research should be able to get something out of reading the documentation.</span></span> <span data-ttu-id="1645d-121">Dans la mesure où cela est possible, n’oubliez pas les connaissances étendues de la part de vos lecteurs, car elles peuvent simplement commencer. C’est très utile si vous pouvez fournir des descriptions claires et accessibles, ou vous pouvez fournir des liens vers d’autres ressources pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="1645d-121">To the extent that's possible, please don't assume extensive knowledge on the part of your readers, as they may just be starting out. It's most helpful if you can provide clear and accessible descriptions, or can provide links to other resources for more information.</span></span>
- <span data-ttu-id="1645d-122">Les jeux de documentation ne sont pas présentés comme des livres ou des papiers, dans le fait que les lecteurs arrivent dans ce qui peut paraître le « milieu ».</span><span class="sxs-lookup"><span data-stu-id="1645d-122">Documentation sets aren't laid out like books or papers, in that readers will arrive in what might seem like the "middle."</span></span> <span data-ttu-id="1645d-123">Par exemple, les moteurs de recherche peuvent ne pas suggérer l’index ou ils peuvent avoir reçu un lien d’un ami tentant de les aider. Essayez d’aider votre lecteur en fournissant toujours un contexte clair, ainsi que des liens, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="1645d-123">For example, search engines might not suggest the index, or they might have been sent a link by a friend trying to help them out. Try to help your reader by always providing a clear context, along with links where appropriate.</span></span>
- <span data-ttu-id="1645d-124">Certains lecteurs recherchent les instructions et définitions abstraites les plus utiles, tandis que les autres lecteurs fonctionnent mieux en extrapolant des exemples concrets.</span><span class="sxs-lookup"><span data-stu-id="1645d-124">Some readers will find abstract statements and definitions most helpful, while other readers work best by extrapolating from concrete examples.</span></span> <span data-ttu-id="1645d-125">Le fait de fournir à la fois le cas général et des exemples spécifiques peut aider les deux lecteurs à tirer le meilleur parti de la programmation Quantum.</span><span class="sxs-lookup"><span data-stu-id="1645d-125">Providing both the general case and specific examples can help both readers get the most out of quantum programming.</span></span>
- <span data-ttu-id="1645d-126">En particulier, si vous avez également écrit le code documenté, il peut être évident que vous n’êtes pas du tout évident pour votre lecteur.</span><span class="sxs-lookup"><span data-stu-id="1645d-126">Especially if you also wrote the code being documented, things may be obvious to you that are not at all obvious to your reader.</span></span> <span data-ttu-id="1645d-127">Il n’existe pas de meilleure façon de programmer. par conséquent, quelle que soit la façon dont un lecteur est habile ou expérimenté, il ne peut pas deviner à quel modèle de conception vous avez trouvé le plus utile pour exprimer vos idées dans le code.</span><span class="sxs-lookup"><span data-stu-id="1645d-127">There's no one unique best way to program, so no matter how clever or experienced a reader might be, they can't guess at what design patterns you found the most helpful to express your ideas in code.</span></span> <span data-ttu-id="1645d-128">Le fait de savoir comment un lecteur peut s’attendre à utiliser votre code peut vous aider à fournir ce contexte.</span><span class="sxs-lookup"><span data-stu-id="1645d-128">Being clear about how a reader can expect to make use of your code can help provide that context.</span></span>
- <span data-ttu-id="1645d-129">De nombreux membres de la communauté de programmation quantique sont des chercheurs universitaires et sont reconnus principalement par des citations pour leurs contributions à la communauté.</span><span class="sxs-lookup"><span data-stu-id="1645d-129">Many members of the quantum programming community are academic researchers, and are recognized mainly through citations for their contributions to the community.</span></span> <span data-ttu-id="1645d-130">En plus d’aider les lecteurs à trouver des documents supplémentaires, en veillant à citer correctement les sorties académiques, telles que les documents, les discussions, les billets de blog et les outils logiciels, peuvent aider les contributeurs universitaires à continuer à faire leurs efforts pour améliorer la communauté.</span><span class="sxs-lookup"><span data-stu-id="1645d-130">In addition to helping readers find additional materials, making sure to properly cite academic outputs such as papers, talks, blog posts, and software tools can help academic contributors to keep doing their best work to improve the community.</span></span>
- <span data-ttu-id="1645d-131">La communauté de programmation quantique est une communauté large et formidablement diversifiée.</span><span class="sxs-lookup"><span data-stu-id="1645d-131">The quantum programming community is a broad and wonderfully diverse community.</span></span> <span data-ttu-id="1645d-132">L’utilisation de pronoms par sexe dans des exemples de sociétés tierces (par exemple, «si un utilisateur..............</span><span class="sxs-lookup"><span data-stu-id="1645d-132">The use of gendered pronouns in third-person examples (e.g.: "if a user ..., they will ...") can work to exclude rather than include.</span></span> <span data-ttu-id="1645d-133">L’Cognizant de noms de personnes dans des citations et des liens, et de l’inclusion correcte de caractères non-ASCII, peut servir la diversité de la communauté en s’expliquant à ses membres.</span><span class="sxs-lookup"><span data-stu-id="1645d-133">Being cognizant of people's names in citations and links, and of the correct inclusion of non-ASCII characters can serve the diversity of the community by showing respect to its members.</span></span> <span data-ttu-id="1645d-134">De même, de nombreux mots de la langue anglaise sont souvent utilisés de manière Hateful, de sorte que leur utilisation dans la documentation technique peut nuire aux lecteurs individuels et à la communauté.</span><span class="sxs-lookup"><span data-stu-id="1645d-134">Similarly, many words in the English language are often used in a hateful manner, such that their use in technical documentation can cause harm both to individual readers and to the community at large.</span></span>

### <a name="referencing-sample-code-from-conceptual-articles"></a><span data-ttu-id="1645d-135">Référencement d’un exemple de code à partir d’articles conceptuels</span><span class="sxs-lookup"><span data-stu-id="1645d-135">Referencing Sample Code from Conceptual Articles</span></span>

<span data-ttu-id="1645d-136">Si vous souhaitez inclure du code à partir du [référentiel d’exemples](https://github.com/Microsoft/Quantum), vous pouvez le faire à l’aide d’une commande spéciale DocFX-Flavored démarque :</span><span class="sxs-lookup"><span data-stu-id="1645d-136">If you want to include code from the [samples repository](https://github.com/Microsoft/Quantum), you can do so using a special DocFX-Flavored Markdown command:</span></span>

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

<span data-ttu-id="1645d-137">Cette commande importera les lignes 4 à 8 du [ `Game.qs` fichier de l' `chsh-game` exemple](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs), en les marquant comme Q# code à des fins de mise en surbrillance de la syntaxe.</span><span class="sxs-lookup"><span data-stu-id="1645d-137">This command will import lines 4 to 8 of the [`Game.qs` file from the `chsh-game` sample](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs), marking them as Q# code for the purpose of syntax highlighting.</span></span>
<span data-ttu-id="1645d-138">À l’aide de cette commande, vous pouvez éviter de dupliquer le code entre des articles conceptuels et le référentiel d’exemples, afin que l’exemple de code dans la documentation soit toujours aussi à jour que possible.</span><span class="sxs-lookup"><span data-stu-id="1645d-138">Using this command, you can avoid duplicating code between conceptual articles and the samples repository, so that sample code in documentation is always as up to date as possible.</span></span>

### <a name="contributing-image-files"></a><span data-ttu-id="1645d-139">Contribution des fichiers image</span><span class="sxs-lookup"><span data-stu-id="1645d-139">Contributing image files</span></span>

<span data-ttu-id="1645d-140">**Important**: pour que les images soient correctement rendues en mode sombre, vous devez éviter les transparences.</span><span class="sxs-lookup"><span data-stu-id="1645d-140">**IMPORTANT**: To have the images rendering properly in dark mode you must avoid transparencies.</span></span>

- <span data-ttu-id="1645d-141">Pour les fichiers. jpg.</span><span class="sxs-lookup"><span data-stu-id="1645d-141">For .jpg files.</span></span> <span data-ttu-id="1645d-142">vous n’avez rien à faire, car le format. jpg ne prend pas en charge les éléments transparents.</span><span class="sxs-lookup"><span data-stu-id="1645d-142">you don't need to do anything as the .jpg format doesn't support transparent elements.</span></span>
- <span data-ttu-id="1645d-143">Pour les fichiers. png, vous devez ajouter un arrière-plan blanc ou modifier la valeur du canal alpha sur **100**.</span><span class="sxs-lookup"><span data-stu-id="1645d-143">For .png files, you must add a white background or change the value of the alpha channel to **100**.</span></span> <span data-ttu-id="1645d-144">Pour ce faire, le plus simple est d’ouvrir le fichier dans **Paint** et de l’enregistrer en remplaçant le fichier d’origine.</span><span class="sxs-lookup"><span data-stu-id="1645d-144">The easiest way to do this in Windows is to open the file in **Paint** and save it, overwriting the original file.</span></span>
- <span data-ttu-id="1645d-145">Pour les fichiers. svg, vous devez ajouter un rectangle blanc dans la couche la plus basse.</span><span class="sxs-lookup"><span data-stu-id="1645d-145">For .svg files you must add a white rectangle in the lowest layer.</span></span> <span data-ttu-id="1645d-146">Pour ce faire, vous pouvez utiliser **Inkscape**:</span><span class="sxs-lookup"><span data-stu-id="1645d-146">You can do this with **Inkscape**:</span></span>
  1. <span data-ttu-id="1645d-147">Ouvrez le fichier. svg.</span><span class="sxs-lookup"><span data-stu-id="1645d-147">Open the .svg file.</span></span>
  1. <span data-ttu-id="1645d-148">Sélectionnez l’outil générateur carré et dessinez un rectangle blanc en plus de la figure d’origine.</span><span class="sxs-lookup"><span data-stu-id="1645d-148">Select the square maker tool and draw a white rectangle on top of the original figure.</span></span>
  1. <span data-ttu-id="1645d-149">Sélectionnez l’outil **Sélectionner et transformer des objets** en cliquant sur la flèche foncée ou en appuyant sur **F1**.</span><span class="sxs-lookup"><span data-stu-id="1645d-149">Select the tool **Select and transform objects** by clicking in the dark arrow or pressing **F1**.</span></span>
  1. <span data-ttu-id="1645d-150">Lorsque le rectangle est sélectionné, cliquez sur l’élément de barre d’outils **de la sélection inférieure en bas (fin)**.</span><span class="sxs-lookup"><span data-stu-id="1645d-150">While having the rectangle selected, click the toolbar element **Lower selection to bottom (End)**.</span></span>
  1. <span data-ttu-id="1645d-151">Ajustez le rectangle à l’aide de la souris ou des touches de direction.</span><span class="sxs-lookup"><span data-stu-id="1645d-151">Adjust the rectangle with your mouse or the arrow keys.</span></span>

## <a name="contributing-to-the-api-references"></a><span data-ttu-id="1645d-152">Contribution aux références d’API</span><span class="sxs-lookup"><span data-stu-id="1645d-152">Contributing to the API References</span></span>

<span data-ttu-id="1645d-153">Pour apporter une amélioration aux références d’API, il est plus utile d’ouvrir une requête de tirage directement sur le code documenté.</span><span class="sxs-lookup"><span data-stu-id="1645d-153">To contribute an improvement to the API references, it's most helpful to open a pull request directly on the code being documented.</span></span>
<span data-ttu-id="1645d-154">Chaque fonction, opération ou type défini par l’utilisateur prend en charge un commentaire de documentation (indiqué par `///` au lieu de `//` ).</span><span class="sxs-lookup"><span data-stu-id="1645d-154">Each function, operation, or user-defined type supports a documentation comment (denoted with `///` instead of `//`).</span></span>
<span data-ttu-id="1645d-155">Lorsque nous compilerons chaque version du kit de développement Quantum, ces commentaires sont utilisés pour générer la référence de l’API sur https://docs.microsoft.com/qsharp/api/ , y compris les détails sur les entrées et les sorties de chaque appelable, les hypothèses que chacun peut appeler et des exemples de leur utilisation.</span><span class="sxs-lookup"><span data-stu-id="1645d-155">When we compile each release of the Quantum Development Kit, these comments are used to generate the API reference at https://docs.microsoft.com/qsharp/api/, including details about the inputs to and outputs from each callable, the assumptions each callable makes, and examples of how to use them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1645d-156">Veillez à ne pas modifier manuellement la documentation de l’API générée, car ces fichiers sont remplacés par chaque nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="1645d-156">Please make sure to not manually edit the generated API documentation, as these files are overwritten with each new release.</span></span>
> <span data-ttu-id="1645d-157">Nous vous proposons votre contribution à la communauté et vous vous assurez que vos modifications continuent d’aider les utilisateurs à se lancer après la publication.</span><span class="sxs-lookup"><span data-stu-id="1645d-157">We value your contribution to the community, and want to make sure that your changes continue to help users release after release.</span></span>

<span data-ttu-id="1645d-158">Par exemple, considérez la fonction `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="1645d-158">For example, consider the function `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="1645d-159">Un commentaire de documentation doit aider un utilisateur à apprendre à interpréter `bits` et `oracle` et à quoi la fonction est destinée.</span><span class="sxs-lookup"><span data-stu-id="1645d-159">A documentation comment should help a user learn how to interpret `bits` and `oracle` and what the function is for.</span></span>
<span data-ttu-id="1645d-160">Chacun de ces différents éléments d’information peut être fourni au Q# compilateur par une section de démarque spéciale dans le commentaire de la documentation.</span><span class="sxs-lookup"><span data-stu-id="1645d-160">Each of these different pieces of information can be provided to the Q# compiler by a specially named Markdown section in the documentation comment.</span></span>
<span data-ttu-id="1645d-161">Pour l’exemple de `ControlledOnBitString` , nous pouvons écrire une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="1645d-161">For the example of `ControlledOnBitString`, we might write something like the following:</span></span>

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```

<span data-ttu-id="1645d-162">Vous pouvez voir la version rendue du code ci-dessus dans la [documentation de l’API pour la `ControlledOnBitString` fonction](xref:Microsoft.Quantum.Canon.ControlledOnBitString).</span><span class="sxs-lookup"><span data-stu-id="1645d-162">You can see the rendered version of the code above in the [API documentation for the `ControlledOnBitString` function](xref:Microsoft.Quantum.Canon.ControlledOnBitString).</span></span>

<span data-ttu-id="1645d-163">En plus de la pratique générale de la rédaction de documentation, l’écriture de commentaires de documentation API permet de garder à l’esprit les points suivants :</span><span class="sxs-lookup"><span data-stu-id="1645d-163">In addition to the general practice of documentation writing, in writing API documentation comments it helps to keep a few things in mind:</span></span>

- <span data-ttu-id="1645d-164">Le format de chaque commentaire de documentation doit correspondre à ce que le Q# compilateur s’attend à ce que votre documentation apparaisse correctement.</span><span class="sxs-lookup"><span data-stu-id="1645d-164">The format of each documentation comment has to match what the Q# compiler expects for your documentation to appear correctly.</span></span> <span data-ttu-id="1645d-165">Certaines sections, telles que `/// # Remarks` allow pour le contenu de forme libre, les sections telles que la `/// # See Also` section sont plus restrictives.</span><span class="sxs-lookup"><span data-stu-id="1645d-165">Some sections, such as `/// # Remarks` allow for freeform content, while sections such as `/// # See Also` section are more restrictive.</span></span>
- <span data-ttu-id="1645d-166">Un lecteur peut lire la documentation de votre API sur le site principal de référence des API, sur le résumé de chaque espace de noms, ou même à partir de l’environnement de développement intégré (IDE) à l’aide des informations de pointage.</span><span class="sxs-lookup"><span data-stu-id="1645d-166">A reader may read your API documentation on the main API reference site, on the summary for each namespace, or even from within their IDE through the use of hover information.</span></span> <span data-ttu-id="1645d-167">En veillant à ce qu' `/// # Summary` il ne s’agisse pas d’une phrase plus longue, vous pouvez faire rapidement en sorte que votre lecteur effectue rapidement une recherche dans les résumés d’espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="1645d-167">Making sure that `/// # Summary` isn't longer than about a sentence helps your reader quickly sort out whether they need to read further or look elsewhere, and can help in quickly scanning through namespace summaries.</span></span>
- <span data-ttu-id="1645d-168">Votre documentation peut s’allonger bien plus longtemps que le code lui-même, mais ce n’est pas tout !</span><span class="sxs-lookup"><span data-stu-id="1645d-168">Your documentation may well wind up being much longer than the code itself, but that's OK!</span></span> <span data-ttu-id="1645d-169">Même un petit morceau de code peut avoir des effets inattendus pour les utilisateurs qui ne connaissent pas le contexte dans lequel ce code existe.</span><span class="sxs-lookup"><span data-stu-id="1645d-169">Even a small piece of code can have unexpected effects to users that don't know the context in which that code exists.</span></span> <span data-ttu-id="1645d-170">En fournissant des exemples concrets et des explications claires, vous pouvez aider les utilisateurs à tirer le meilleur parti du code qui leur est accessible.</span><span class="sxs-lookup"><span data-stu-id="1645d-170">By providing concrete examples and clear explanations, you can help users make the best use of the code that's available to them.</span></span>

<!-- ## LaTeX Formatting ##

**TODO** -->
