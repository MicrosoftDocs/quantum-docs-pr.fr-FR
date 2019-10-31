---
title: Contribution au Quantum Development Kit | Microsoft Docs
description: Contribution au Quantum Development Kit
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing
ms.openlocfilehash: 4be86c5045ece62ae3af40090a2cd344d965e65f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035165"
---
# <a name="contributing-to-the-quantum-development-kit"></a>Contribution au Quantum Development Kit #

Le Quantum Development Kit est plus qu’un ensemble d’outils permettant d’écrire des programmes quantiques.
Il fait partie d’une vaste communauté de personnes qui découvrent l’informatique quantique, font de la recherche sur les algorithmes quantiques, développent de nouvelles applications pour les appareils quantiques ou encore travaillent à tirer le meilleur parti possible de la programmation quantique.
En tant que membre de cette communauté, le Quantum Development Kit vise à offrir aux développeurs quantiques issus d’horizons très variés les fonctionnalités dont ils ont besoin.
Vos contributions au Quantum Development Kit aident à la réalisation de cet objectif en améliorant les outils utilisés par d’autres développeurs quantiques et la façon dont ces outils sont documentés, et même en créant de nouvelles fonctions et fonctionnalités qui aident à faire de la communauté de programmation quantique un meilleur endroit pour découvrir et créer.
Nous vous sommes très reconnaissants de votre aimable contribution et de l’occasion qui nous est donnée de travailler avec vous pour faire de notre communauté ce qu’elle peut être de mieux.

Dans ce guide, nous vous donnons quelques conseils sur la façon de rendre votre contribution aussi utile que possible à l’ensemble de la communauté de programmation quantique.

## <a name="building-community"></a>Développement de la communauté ##

La toute première chose à faire lorsqu’il s’agit d’apporter une contribution est de toujours garder à l’esprit la communauté à laquelle vous contribuez.
En faisant preuve de respect et de professionnalisme à l’égard de vos pairs au sein de la communauté de programmation quantique et plus généralement, vous pouvez faire en sorte que vos efforts contribuent à bâtir la communauté la meilleure et la plus accueillante possible.

Dans le cadre de cet effort, tous les projets du Quantum Development Kit ont adopté le [code de conduite Open Source de Microsoft](https://opensource.microsoft.com/codeofconduct/).
Pour plus d’informations, veuillez consulter la [FAQ sur le code de conduite](https://opensource.microsoft.com/codeofconduct/faq/) ou envoyez vos questions ou vos commentaires à l’adresse [opencode@microsoft.com](mailto:opencode@microsoft.com).

## <a name="what-kinds-of-contributions-help-the-community"></a>Quels types de contributions aident la communauté ? ##

Il existe de nombreuses façons d’aider la communauté de programmation quantique grâce à vos contributions.
Dans ce guide, nous nous concentrerons sur trois moyens particulièrement pertinents pour le Quantum Development Kit.
Tous ces moyens sont essentiels au développement d’une communauté quantique qui responsabilise les personnes.
Cela dit, cette liste n’est certainement pas exhaustive ; nous vous encourageons à explorer d’autres façons d’aider la communauté à se développer sur la promesse de la programmation quantique !

- **Signalement des bogues.** La première étape pour corriger les bogues et d’autres types de problèmes consiste à les identifier. Si vous avez trouvé un bogue dans le Quantum Development Kit, nous le faire savoir nous aide à le corriger et à créer un meilleur ensemble d’outils pour la communauté de programmation quantique.
- **Amélioration de la documentation.** Toute documentation peut toujours être améliorée, plus détaillée et plus accessible.
- **Contribution au code.** Bien entendu, l’un des moyens les plus directs de contribuer consiste à ajouter du nouveau code au Quantum Development Kit.

Ces différents types de contributions sont d’une immense valeur et sont très appréciés.
Dans la suite du guide, nous vous donnerons des conseils sur la façon d’apporter chaque type de contribution.

## <a name="where-do-contributions-go"></a>Où vont les contributions ? ##

Le Quantum Development Kit comprend un certain nombre d’éléments qui fonctionnent tous ensemble pour réaliser une plateforme d’écriture de programmes quantiques.
Chacun de ces différents éléments trouve sa place dans un référentiel différent, de sorte que l’une des premières choses à faire est de déterminer auquel chaque contribution correspond le mieux.

- [**microsoft/Quantum**](https://github.com/Microsoft/Quantum) : Échantillons et outils pour vous aider à prendre en main le Quantum Development Kit.
- [**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries) : Bibliothèques standard et spécifiques au domaine pour le Quantum Development Kit.
- [**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas) : Exercices de programmation en autonomie pour l’apprentissage de l’informatique quantique et du langage de programmation Q#.
- [**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler) : Le compilateur Q#, l’extension Visual Studio et l’extension Visual Studio Code.
- [**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime) : Infrastructure de simulation, génération de code et machines cibles de simulation pour le Quantum Development Kit.
- [**microsoft/iqsharp**](https://github.com/microsoft/iqsharp) : Fonctionnalités du noyau Jupyter et de l’hôte Python pour Q#, ainsi que des images Docker pour utiliser IQ# dans les environnements cloud.
- [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr) : Code source de la documentation publiée sur https://docs.microsoft.com/quantum.

> [!NOTE]
> Nous ne pouvons malheureusement pas accepter de contributions de code et de documentation sur le référentiel [**microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC) à ce stade, mais nous continuons d’apprécier les rapports de bogues.

Il existe également quelques autres référentiels plus spécialisés qui se concentrent sur différents événements ou sur des fonctionnalités auxiliaires liées au Quantum Development Kit.

- [**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty) : Prise en charge du formatage LaTeX pour la syntaxe Q#.
- [**msr-quarc/intern-workshop-2019**](https://github.com/msr-quarc/intern-workshop-2019) : Notebook IQ# pour le tutoriel Deutsch-Jozsa donné lors de l’atelier interne 2019.

## <a name="next-steps"></a>Étapes suivantes ##

Merci de faire partie de la communauté du Quantum Development Kit, nous sommes ravis de vos contributions !
Si vous souhaitez en savoir plus sur la façon de contribuer, veuillez continuer avec l’un des guides suivants.

> [!div class="nextstepaction"]
> [Découvrir comment signaler des bogues](xref:microsoft.quantum.contributing.reporting)

> [!div class="nextstepaction"]
> [Découvrir comment contribuer à la documentation](xref:microsoft.quantum.contributing.docs)

> [!div class="nextstepaction"]
> [Découvrir comment ouvrir des demandes de tirage (pull requests)](xref:microsoft.quantum.contributing.pulls)

