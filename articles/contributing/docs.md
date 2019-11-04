---
title: Documentation associée | Microsoft Docs
description: Contribution à la documentation
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: 1e24dd859c0b75a161f4f3c7151e2eec227075a2
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183673"
---
# <a name="improving-documentation"></a>Amélioration de la documentation #

La documentation du kit de développement quantique prend plusieurs formes, de sorte que les informations sont facilement accessibles aux développeurs Quantum.

Selon les principes de la documentation [en tant que code](https://www.writethedocs.org/guide/docs-as-code/), toute la documentation du kit de développement Quantum est mise en forme en tant que code et gérée à l’aide de git de la même façon que le code source utilisé pour créer le kit de développement quantique.
Dans la plupart des cas, la documentation de stockage du code se compose de différentes formes de [démarque](https://daringfireball.net/projects/markdown/), un langage permettant d’écrire du texte enrichi dans un format de texte brut facile à utiliser sur la ligne de commande, dans IDE et avec le contrôle de code source.
Nous adoptons de la même manière la bibliothèque [MathJax](https://www.mathjax.org/) pour permettre la mise en forme des mathématiques dans la documentation utilisant le langage latex, comme indiqué plus loin ci-dessous.


Cela dit, chaque forme de documentation varie quelque peu dans les détails :

- La **documentation conceptuelle** se compose d’un ensemble d’articles qui sont publiés sur https://docs.microsoft.com/quantum et qui décrivent tous les éléments de base de quantum computing aux spécifications techniques des formats d’échange. Ces articles sont écrits en [DocFX (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), une variante de démarque utilisée pour créer des ensembles de documentation enrichis.
- La **référence d’API** est un ensemble de pages pour chaque fonction Q #, opération et type défini par l’utilisateur, publiée sur https://docs.microsoft.com/qsharp/api/. Ces pages documentent les entrées et les opérations à chaque appel, ainsi que des exemples et des liens vers des informations supplémentaires. La référence d’API est automatiquement extraite des petits documents DFM dans le code source Q # dans le cadre de chaque version.
- Les fichiers **Lisez-moi<!---->. MD** inclus avec chaque exemple et Kata décrivent comment utiliser cet exemple ou Kata sont utilisés, ce qu’il couvre et comment il se réfère au reste du kit de développement quantique. Ces fichiers sont écrits à l’aide de la [démarque GitHub (GFM)](https://github.github.com/gfm/), une alternative plus légère à DFM qui est populaire pour l’attachement de la documentation directement aux dépôts de code.

## <a name="contributing-to-the-conceptual-documentation"></a>Contribution à la documentation conceptuelle ##

Pour apporter une amélioration à la documentation conceptuelle ou lisez-moi, commence par une demande de tirage (pull request) sur [**MicrosoftDocs/Quantum-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum)ou [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), selon le cas.
Nous décrirons plus en détail les requêtes de tirage ci-dessous, mais pour l’instant, il y a quelques éléments à prendre en compte lors de l’amélioration de la documentation :

- Les lecteurs arrivent dans la documentation du kit de développement quantique à partir d’un très grand nombre d’arrière-plans. Tout le monde des étudiants de la grande école cherchant à apprendre une nouvelle et passionnante de voir les enseignants effectuant une recherche quantum computing devrait être en mesure de lire la documentation. Dans la mesure où cela est possible, n’oubliez pas les connaissances étendues de la part de vos lecteurs, car elles peuvent simplement commencer. C’est très utile si vous pouvez fournir des descriptions claires et accessibles, ou vous pouvez fournir des liens vers d’autres ressources pour plus d’informations.
- Les jeux de documentation ne sont pas présentés comme des livres ou des papiers, dans le fait que les lecteurs arrivent dans ce qui peut paraître le « milieu ». Par exemple, les moteurs de recherche peuvent ne pas suggérer l’index ou ils peuvent avoir reçu un lien d’un ami tentant de les aider. Essayez d’aider votre lecteur en fournissant toujours un contexte clair, ainsi que des liens, le cas échéant.
- Certains lecteurs recherchent les instructions et définitions abstraites les plus utiles, tandis que les autres lecteurs fonctionnent mieux en extrapolant des exemples concrets. Le fait de fournir à la fois le cas général et des exemples spécifiques peut aider les deux lecteurs à tirer le meilleur parti de la programmation Quantum.
- En particulier, si vous avez également écrit le code documenté, il peut être évident que vous n’êtes pas du tout évident pour votre lecteur. Il n’existe pas de meilleure façon de programmer. par conséquent, quelle que soit la façon dont un lecteur est habile ou expérimenté, il ne peut pas deviner à quel modèle de conception vous avez trouvé le plus utile pour exprimer vos idées dans le code. Le fait de savoir comment un lecteur peut s’attendre à utiliser votre code peut vous aider à fournir ce contexte.
- De nombreux membres de la communauté de programmation quantique sont des chercheurs universitaires et sont reconnus principalement par des citations pour leurs contributions à la communauté. En plus d’aider les lecteurs à trouver des documents supplémentaires, en veillant à citer correctement les sorties académiques, telles que les documents, les discussions, les billets de blog et les outils logiciels, peuvent aider les contributeurs universitaires à continuer à faire leurs efforts pour améliorer la communauté.
- La communauté de programmation quantique est une communauté large et formidablement diversifiée. L’utilisation de pronoms par sexe dans des exemples de tiers (par exemple, « si un utilisateur..., il va... ») peut travailler pour exclure plutôt que d’inclure. L’Cognizant de noms de personnes dans des citations et des liens, et de l’inclusion correcte de caractères non-ASCII, peut servir la diversité de la communauté en s’expliquant à ses membres. De même, de nombreux mots de la langue anglaise sont souvent utilisés de manière Hateful, de sorte que leur utilisation dans la documentation technique peut nuire aux lecteurs individuels et à la communauté.

## <a name="contributing-to-the-api-references"></a>Contribution aux références d’API ##

Pour apporter une amélioration aux références d’API, il est plus utile d’ouvrir une requête de tirage directement sur le code documenté.
Chaque fonction, opération ou type défini par l’utilisateur prend en charge un commentaire de documentation (indiqué par `///` au lieu de `//`).
Lorsque nous compilerons chaque version du kit de développement Quantum, ces commentaires sont utilisés pour générer la référence d’API sur https://docs.microsoft.com/qsharp/api/ , y compris des détails sur les entrées et les sorties de chaque appelable, les hypothèses que chacun peut appeler et des exemples de leur utilisation.

> [!IMPORTANT]
> Veillez à ne pas modifier manuellement la documentation de l’API générée, car ces fichiers sont remplacés par chaque nouvelle version.
> Nous vous proposons votre contribution à la communauté et vous vous assurez que vos modifications continuent d’aider les utilisateurs à se lancer après la publication.

Par exemple, considérez une opération `PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`.
Un commentaire de documentation doit aider un utilisateur à apprendre à interpréter `angles`, ce que l’opération suppose à propos de l’état initial de `register`, ce que l’effet sur `register` est, et ainsi de suite.
Chacun de ces éléments d’information peut être fourni au compilateur Q # par une section de démarque spéciale dans le commentaire de la documentation.
Pour l’exemple de `PrepareTrialState`, nous pouvons écrire un code similaire à ce qui suit :

```qsharp
/// # Summary
/// Given a register of qubits, prepares them in a trial state by rotating each
/// independently.
///
/// # Description
/// This operation prepares the input register by performing a
/// $Y$ rotation on each qubit by an angle given in `angles`.
///
/// # Input
/// ## angles
/// An array of parameters
/// ## register
/// A register of qubits initially in the $\ket{00\cdots0}$ state.
///
/// # Example
/// To prepare an equal superposition $\ket{++\cdots+}$ over all input qubits:
/// ```qsharp
/// PrepareTrialState(ConstantArray(Length(register), PI() / 2.0), register);
/// ```
///
/// # Remarks
/// This operation is generally useful in the inner loop of an optimization
/// algorithm.
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.Ry
operation PrepareTrialState(angles : Double[], register : Qubit[]) : Unit {
    // ...
}
```

En plus de la pratique générale de la rédaction de documentation, l’écriture de commentaires de documentation API permet de garder à l’esprit les points suivants :

- Le format de chaque commentaire de documentation doit correspondre à ce que le compilateur Q # attend pour que votre documentation apparaisse correctement. Certaines sections, telles que `/// # Remarks` autorisent le contenu de la forme libre, tandis que les sections comme `/// # See Also` section sont plus restrictives.
- Un lecteur peut lire la documentation de votre API sur le site principal de référence des API, sur le résumé de chaque espace de noms, ou même à partir de l’environnement de développement intégré (IDE) à l’aide des informations de pointage. En veillant à ce que les `/// # Summary` ne soient pas plus longues qu’une phrase, le lecteur vous aide à vérifier rapidement s’ils ont besoin de lire à un autre emplacement, et peut vous aider à rechercher rapidement des résumés d’espaces de noms.
- Votre documentation peut s’allonger bien plus longtemps que le code lui-même, mais ce n’est pas tout ! Même un petit morceau de code peut avoir des effets inattendus pour les utilisateurs qui ne connaissent pas le contexte dans lequel ce code existe. En fournissant des exemples concrets et des explications claires, vous pouvez aider les utilisateurs à tirer le meilleur parti du code qui leur est accessible.

<!-- ## LaTeX Formatting ##

**TODO** -->
