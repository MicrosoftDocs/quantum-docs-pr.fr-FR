---
title: Q# Structure de fichier
description: Décrit la structure et la syntaxe d’un Q# fichier.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: 98b3a2e35186989b8191cc566a5d5310bc26eafc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833305"
---
# <a name="no-locq-file-structure"></a>Q# Structure de fichier

Un Q# fichier se compose d’une séquence de *déclarations d’espaces de noms*.
Chaque déclaration d’espace de noms contient des déclarations pour les types, les opérations et les fonctions définis par l’utilisateur, et peut contenir n’importe quel nombre de chaque type de déclaration et dans n’importe quel ordre.
Pour plus d’informations sur les déclarations au sein d’un espace de noms, consultez types, [opérations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)et [fonctions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) [définis par l’utilisateur](xref:microsoft.quantum.guide.types#user-defined-types).

Le seul texte qui peut apparaître en dehors d’une déclaration d’espace de noms est un commentaire.
En particulier, les commentaires de documentation pour un espace de noms précèdent la déclaration. Pour plus d’informations, consultez [Commentaires sur la documentation](#documentation-comments) dans cet article. 

## <a name="namespace-declarations"></a>Déclarations d'espace de noms

Q#En général, un fichier n’a qu’une seule déclaration d’espace de noms, mais peut en avoir un (et être vide ou ne contenir que des commentaires) ou peut contenir plusieurs espaces de noms.
Les déclarations d’espaces de noms ne peuvent pas être imbriquées.

Vous pouvez déclarer le même espace de noms dans plusieurs Q# fichiers qui sont compilés ensemble, à condition qu’il n’y ait pas de déclaration de type, d’opération ou de fonction portant le même nom.
En particulier, il n’est pas valide de définir le même type dans le même espace de noms dans plusieurs fichiers, même si les déclarations sont identiques.

Une déclaration d’espace de noms se compose du mot clé `namespace` , suivi du nom de l’espace de noms, et des déclarations contenues dans l’espace de noms, placées entre accolades `{ }` .
Les noms d’espaces de noms suivent le modèle .NET d’une séquence d’un ou de plusieurs symboles légaux séparés par des points `.` .
Par exemple, `MyQuantumStuff` et `Microsoft.Quantum.Intrinsic` sont des noms d’espaces de noms valides.
Par Convention, mettez en majuscules les symboles dans un nom d’espace de noms, mais cela n’est pas obligatoire.

Les références à des types ou à des callables déclarés plus loin dans un fichier sont correctement résolues ; Il n’est pas nécessaire que le type, l’opération ou la déclaration de fonction précède une référence à celui-ci.

## <a name="open-directives"></a>Directives Open

Dans un bloc d’espace de noms, utilisez la `open` directive pour importer tous les types et les callables déclarés dans un certain espace de noms et y faire référence par leur nom non qualifié.
Une telle `open` directive se compose du `open` mot clé, suivi de l’espace de noms à ouvrir et d’un point-virgule de fin.

> [!NOTE] 
> Toutes les `open` directives doivent apparaître avant `function` les `operation` déclarations, ou `newtype` dans le bloc d’espace de noms.

Si vous le souhaitez, vous pouvez définir un nom abrégé pour l’espace de noms ouvert. Si un nom abrégé est défini, vous devez qualifier tous les éléments de cet espace de noms à l’aide du nom abrégé défini. Par exemple, étant donné la déclaration d’espace de noms et les directives Open suivantes,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

Si une opération déclarée utilise une opération `Op` de `Microsoft.Quantum.Intrinsic` , vous l’appelez simplement à l’aide de `Op` .
Toutefois, pour appeler une certaine fonction `Fn` à partir de `Microsoft.Quantum.Math` , vous devez l’appeler à l’aide de `Math.Fn` .

La `open` directive s’applique à l’intégralité du bloc d’espace de noms dans un fichier.
Par conséquent, si vous définissez un espace de noms supplémentaire dans le même Q# fichier que `NS` précédemment, les opérations/fonctions/types définis dans le deuxième espace de noms n’ont pas accès à quoi que ce soit à partir de `Microsoft.Quantum.Intrinsic` ou `Microsoft.Quantum.Math` , sauf si vous avez répété les directives ouvertes dans celui-ci. 

Pour référencer un type ou un appelable défini dans un autre espace de noms qui n’est *pas* ouvert dans l’espace de noms actuel, vous devez le référencer par son nom complet.
Prenons l’exemple d’une opération nommée `Op` à partir de l' `X.Y` espace de noms :

* Vous devez le référencer par son nom complet `X.Y.Op` , sauf si l' `X.Y` espace de noms a été ouvert plus tôt dans le bloc actuel. 
* Même si l' `X` espace de noms est ouvert, il n’est pas possible de faire référence à l’opération en tant que `Y.Op` .
* Si vous avez défini le nom abrégé `Z` pour `X.Y` dans cet espace de noms et ce fichier, vous devez faire référence `Op` à `Z.Op` . 

Il est généralement préférable d’inclure un espace de noms à l’aide d’une `open` directive.
L’utilisation d’un nom qualifié complet est requise si deux espaces de noms définissent des constructions portant le même nom, et la source actuelle utilise des constructions à partir des deux.

Q# suit les mêmes règles d’affectation de noms que d’autres langages .NET.
Toutefois, Q# ne prend pas en charge les références relatives aux espaces de noms.
Par exemple, si l’espace de noms `a.b` est ouvert, une référence à une opération nommée `c.d` n’est *pas* résolue en une opération portant le nom complet `a.b.c.d` .

## <a name="formatting"></a>Mise en forme

La plupart des Q# instructions et des directives se terminent par un point-virgule de fin, `;` .
Les instructions et les déclarations telles que `for` et `operation` qui se terminent par un bloc d’instructions (voir la section suivante) ne nécessitent pas de point-virgule de fin.
Chaque description d’instruction indique si le point-virgule de fin est obligatoire.

Les instructions, comme les expressions, les déclarations et les directives, peuvent être réparties sur plusieurs lignes.
Évitez de placer plusieurs instructions sur une seule ligne.

## <a name="statement-blocks"></a>Blocs d’instructions

Q# les instructions sont regroupées dans des blocs d’instructions, qui sont contenus avec des accolades `{ }` . Un bloc d’instructions commence par une ouverture `{` et se termine par une fermeture `}` .

Un bloc d’instructions placé lexicalement dans un autre bloc est considéré comme un sous-bloc du bloc conteneur. les blocs conteneur et secondaires sont également appelés blocs externes et internes.

## <a name="comments"></a>Commentaires

Les commentaires commencent par deux barres obliques, `//` et continuent jusqu’à la fin de la ligne.
Un commentaire peut apparaître n’importe où dans un Q# fichier source.

## <a name="documentation-comments"></a>Commentaires de documentation

Les commentaires qui commencent par trois barres obliques, `///` , sont traités de manière spéciale par le compilateur lorsqu’ils apparaissent immédiatement avant un espace de noms, une opération, une spécialisation, une fonction ou une définition de type.
Dans ce cas, le compilateur les traite comme une documentation pour le type pouvant être appelé par l’utilisateur ou défini par l’utilisateur, de la même façon que d’autres langages .NET.

Dans `///` les commentaires, le texte à afficher dans le cadre de la documentation de l’API est mis en forme en tant que [démarque](https://daringfireball.net/projects/markdown/syntax), avec les différentes parties de la documentation indiquées par des en-têtes spécialement nommés.
Dans démarque, utilisez l' `@"<ref target>"` extension pour les opérations de référence croisée, les fonctions et les types définis par l’utilisateur dans Q# . Remplacez `<ref target>` par le nom qualifié complet de l’objet de code référencé.
Des moteurs de documentation différents peuvent également prendre en charge des extensions de démarque supplémentaires.

Par exemple :

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

Les noms suivants sont valides en tant qu’en-têtes de commentaires de documentation.

- **Résumé**: bref résumé du comportement d’une fonction ou d’une opération, ou de l’objectif d’un type. Le premier paragraphe du résumé est utilisé pour les informations de survol. Il doit s’agir d’un texte brut.
- **Description**: description du comportement d’une fonction ou d’une opération, ou de l’objectif d’un type. Ensemble, le résumé et la description constituent le fichier de documentation généré pour la fonction, l’opération ou le type.
  La description prend en charge les symboles et les équations au format LaTeX en ligne.
- **Input**: description du tuple d’entrée d’une opération ou d’une fonction.
  Peut contenir des sous-sections de démarque supplémentaires indiquant chaque élément du tuple d’entrée.
- **Sortie**: description du tuple retourné par une opération ou une fonction.
- **Paramètres de type**: section vide qui contient une sous-section supplémentaire pour chaque paramètre de type générique.
- **Exemple**: exemple bref de l’opération, de la fonction ou du type en cours d’utilisation.
- **Remarques**: divers Proseware décrivant certains aspects de l’opération, de la fonction ou du type.
- **Voir aussi**: liste de noms qualifiés complets indiquant les fonctions connexes, les opérations ou les types définis par l’utilisateur.
- **Références**: liste de références et de citations pour l’élément documenté.

## <a name="next-steps"></a>Étapes suivantes

En savoir plus sur [les opérations et les fonctions](xref:microsoft.quantum.guide.operationsfunctions) dans Q# .