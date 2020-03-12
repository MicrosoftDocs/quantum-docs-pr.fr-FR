---
title: Contribution du code à Microsoft QDK
description: Apprenez à contribuer à l’exemple de code de bibliothèque et à l’Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: edc52dc4434e91258bece28812fd76b66329c6f9
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022467"
---
# <a name="contributing-code"></a>Code de contribution

Outre la création de rapports sur les problèmes et l’amélioration de la documentation, le code du kit de développement quantique peut être un moyen très direct d’aider vos pairs dans la communauté de programmation quantique.
En faisant contribution du code, vous pouvez aider à résoudre les problèmes, à fournir de nouveaux exemples, à rendre les bibliothèques existantes plus faciles à utiliser, voire à ajouter des fonctionnalités entièrement nouvelles.

Dans ce guide, nous allons détailler un peu ce que nous cherchons lorsque nous examinerons des demandes de tirage pour aider votre contribution à faire le meilleur.

## <a name="what-we-look-for"></a>Ce que nous recherchons

Une contribution de code idéale s’appuie sur le travail existant dans un référentiel de kit de développement quantique pour résoudre les problèmes, étendre les fonctionnalités existantes ou ajouter de nouvelles fonctionnalités dans l’étendue d’un référentiel.
Lorsque nous acceptons une contribution au code, elle devient une partie du kit de développement quantique proprement dit, de sorte que les nouvelles fonctionnalités seront publiées, gérées et développées de la même façon que le reste du kit de développement quantique.
Par conséquent, il est utile lorsque la fonctionnalité ajoutée par une contribution est bien testée et est documentée.

### <a name="unit-tests"></a>tests unitaires

Les fonctions Q #, les opérations et les types définis par l’utilisateur qui composent les bibliothèques comme Canon sont testés automatiquement dans le cadre du développement sur le référentiel [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) .
Lors de l’ouverture d’une nouvelle demande de tirage (pull request), par exemple, notre configuration de [Azure pipelines](https://azure.microsoft.com/services/devops/pipelines/) vérifie que les modifications apportées à la requête de tirage n’interrompent pas les fonctionnalités existantes dont dépend la communauté de programmation quantique.

Avec la dernière version de Q #, le test unitaire est défini à l’aide de l’attribut `@Test("QuantumSimulator")`. L’argument peut être soit « QuantumSimulator », « ToffoliSimulator », « TraceSimulator », soit un nom qualifié complet spécifiant la cible d’exécution. Plusieurs attributs définissant différentes cibles d’exécution peuvent être attachés au même appelable. Certains de nos tests utilisent toujours le package [Microsoft. Quantum. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) déconseillé qui expose toutes les fonctions Q # et les opérations se terminant par `Test` à l’infrastructure [xUnit](https://xunit.github.io/) . Ce package n’est plus nécessaire pour définir des tests unitaires. 

La fonction suivante est utilisée pour garantir que les fonctions <xref:microsoft.quantum.canon.fst> et <xref:microsoft.quantum.canon.snd> retournent les sorties de droite dans un exemple représentatif.
Si la sortie de `Fst` ou `Snd` est incorrecte, l’instruction `fail` est utilisée pour provoquer l’échec du test.

```qsharp
@Test("QuantumSimulator")
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

Des conditions plus complexes peuvent être vérifiées à l’aide des techniques décrites dans la [section Test](xref:microsoft.quantum.libraries.diagnostics) du Guide des bibliothèques standard.
Par exemple, le test suivant vérifie que `H(q); X(q); H(q);` comme appelé par <xref:microsoft.quantum.canon.applywith> fait la même chose que `Z(q)`.

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

Quand vous ajoutez de nouvelles fonctionnalités, il est judicieux d’ajouter également de nouveaux tests pour vous assurer que votre contribution fait ce qu’elle est supposée.
Cela aide le reste de la communauté à gérer et à développer votre fonctionnalité, et en particulier permet à d’autres développeurs de savoir qu’ils peuvent compter sur votre fonctionnalité.

> [!NOTE]
> Cela fonctionne également dans l’autre sens.
> S’il existe une fonctionnalité qui ne contient pas de tests, nous vous aidons à ajouter la couverture de test, ce qui contribuera à la communauté.

Localement, les tests unitaires peuvent être exécutés à l’aide de l’Explorateur de tests Visual Studio ou de la commande `dotnet test`, afin que vous puissiez vérifier votre contribution avant d’ouvrir une demande de tirage (pull request).

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->


## <a name="when-well-reject-a-pull-request"></a>Lors du rejet d’une requête de tirage

Parfois, nous rejetterons la demande de tirage (pull request) pour une contribution.
Si cela se produit, cela ne signifie pas qu’il est mauvais, car il existe un certain nombre de raisons pour lesquelles nous pouvons ne pas être en mesure d’accepter une contribution particulière.
Le plus souvent, une contribution à la communauté de programmation quantique est très bonne, mais les référentiels du kit de développement quantique ne sont pas le bon endroit pour le développer.
Dans ce cas, nous vous encourageons fortement à créer votre propre référentiel---partie de la force du kit de développement quantique, c’est qu’il est facile de créer et de distribuer vos propres bibliothèques à l’aide de GitHub et NuGet.org, de la même façon que nous distribuons l’Canon et la chimie bibliothèques actuelles.

À d’autres moments, nous pouvons rejeter une bonne contribution simplement parce que nous ne sommes pas encore prêts à le maintenir et à le développer.
Il peut être difficile de faire tout, donc nous prévoyons les fonctionnalités sur lesquelles nous sommes le plus à même de travailler dans le cadre d’une feuille de route.
Il peut s’agir d’un autre cas dans lequel la publication d’une fonctionnalité en tant que bibliothèque tierce peut s’avérer très utile.
Vous pouvez également demander de l’aide pour modifier une fonctionnalité afin qu’elle s’adapte mieux à notre feuille de route afin que nous puissions faire le meilleur travail possible.

Nous vous demanderons également les modifications apportées à une demande de tirage (pull request) si elle nécessite davantage de documentation ou de tests unitaires pour nous aider à l’utiliser, ou si elle diffère du style des autres bibliothèques Q # qu’il est plus difficile pour les utilisateurs de trouver votre fonctionnalité.
Dans ces cas-là, nous allons essayer de proposer des avis de code sur les éléments qui peuvent être ajoutés ou modifiés pour faciliter l’inclusion de votre contribution.

Enfin, nous ne pouvons pas accepter les contributions qui causent un préjudice à la communauté de quantum computing, comme indiqué dans le [Code de réalisation de Microsoft Open source](https://opensource.microsoft.com/codeofconduct/).
Nous voulons nous assurer que les contributions servent l’ensemble de la communauté de calcul Quantum, à la fois dans sa grande diversité et dans le futur, à mesure qu’elle s’étendra pour devenir encore plus inclusive.
Nous apprécions votre aide pour la réalisation de cet objectif.

## <a name="next-steps"></a>Étapes suivantes

Merci d’avoir aidé à faire de la communauté de développement quantique une formidable ressource pour l’ensemble de la communauté de programmation quantique !
Pour plus d’informations, consultez le guide suivant sur le style Q #.

> [!div class="nextstepaction"]
> [En savoir plus sur les directives de style Q #](xref:microsoft.quantum.contributing.style)

Selon le type de code que vous contribuez, il peut y avoir des éléments supplémentaires à garder à l’esprit qui peuvent vous aider à faire en sorte que votre contribution fasse autant de choses que possible pour la communauté.

> [!div class="nextstepaction"]
> [En savoir plus sur les exemples contributeurs](xref:microsoft.quantum.contributing.samples)
