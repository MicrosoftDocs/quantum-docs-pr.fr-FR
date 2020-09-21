---
title: Contribution aux exemples Microsoft QDK
description: Apprenez à contribuer à l’exemple de code dans le Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: ae29614cc9c8bf965ea3cb373dc17470aec21252
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759184"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a>Contribution des exemples au kit de développement quantique

Si vous souhaitez contribuer au code du référentiel d' [exemples](https://github.com/Microsoft/Quantum), Merci de faire de la communauté de développement quantique un meilleur endroit !

## <a name="the-quantum-development-kit-samples-repository"></a>Référentiel d’exemples du kit de développement Quantum

Pour vous aider à préparer votre contribution pour vous aider dans la mesure du possible, il est utile d’examiner rapidement la disposition du référentiel d’exemples :

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

Autrement dit, les exemples du [référentiel Microsoft/Quantum](https://github.com/microsoft/Quantum) sont répartis par zone de sujet dans différents dossiers tels que `algorithms/` , `arithmetic/` ou `characterization/` .
Dans le dossier de chaque zone de sujet, chaque exemple se compose d’un dossier unique qui collecte tout ce dont l’utilisateur aura besoin pour explorer et utiliser cet exemple.

## <a name="how-samples-are-structured"></a>Structure des exemples

En examinant les fichiers qui composent chaque dossier, observons l' [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) exemple.

| Fichier              | Description                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | Q# projet utilisé pour générer l’exemple avec le kit SDK .NET Core |
| `Game.qs`         | Q# opérations et fonctions pour l’exemple                 |
| `Host.cs`         | Programme hôte C# utilisé pour exécuter l’exemple                     |
| `host.py`         | Programme hôte python utilisé pour exécuter l’exemple                 |
| `README.md`       | Documentation sur ce que fait l’exemple et comment l’utiliser    |

Tous les exemples n’auront pas exactement le même ensemble de fichiers (par exemple : certains exemples peuvent être en C# uniquement, d’autres peuvent ne pas avoir d’hôte python ou certains exemples peuvent nécessiter le fonctionnement de fichiers de données auxiliaires).

## <a name="anatomy-of-a-helpful-readme-file"></a>Anatomie d’un fichier Lisez-moi utile

Un fichier particulièrement important, cependant, est le `README.md` fichier, car c’est ce dont les utilisateurs ont besoin pour commencer à utiliser votre exemple !

Chaque `README.md` doit commencer par certaines métadonnées qui aident docs.Microsoft.com/samples à trouver votre contribution.

> [!div class="nextstepaction"]
> [Découvrez comment l’exemple CHSH-Game est rendu](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

Ces métadonnées sont fournies sous la forme d’un [en-tête YAML](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) qui indique les langues que votre exemple couvre (en général, il s’agit de, `qsharp` `csharp` et `python` ), ainsi que des produits que votre exemple couvre (en général, simplement `qdk` ).

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> La `page_type: sample` clé dans l’en-tête est requise pour que votre exemple apparaisse dans docs.Microsoft.com/samples.
> De même, les `product` `language` clés et sont essentielles pour aider les utilisateurs à trouver et exécuter votre exemple.

Après cela, il est utile de fournir une brève introduction qui indique ce que fait votre nouvel exemple :

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

Les utilisateurs de votre exemple apprécieront également de savoir ce dont ils ont besoin pour les exécuter (par exemple : les utilisateurs ont-ils uniquement besoin du kit de développement Quantum lui-même ou nécessitent-ils des logiciels supplémentaires tels que node.js ?) :

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

Tout cela étant en place, vous pouvez indiquer aux utilisateurs comment exécuter votre exemple :

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

Enfin, il est utile d’indiquer aux utilisateurs ce que fait chaque fichier de votre exemple, et où ils peuvent accéder pour plus d’informations :

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> Veillez à utiliser des URL absolues ici, car votre exemple apparaîtra dans une autre URL lorsqu’il sera rendu sur docs.microsoft.com/samples !
