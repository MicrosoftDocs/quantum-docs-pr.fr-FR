---
title: 'Structure de fichiers Q #'
description: 'Décrit la structure et la syntaxe d’un fichier Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: cbee92c6d7e765237a7a42532dd7012b51421708
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430966"
---
# <a name="q-file-structure"></a>Structure de fichiers Q #

Chaque opération Q #, fonction et type défini par l’utilisateur est défini dans un espace de noms.

Un fichier Q # est constitué d’une séquence de *déclarations d’espaces de noms*.
Chaque déclaration d’espace de noms contient des déclarations pour les types, les opérations et les fonctions définis par l’utilisateur.
Une déclaration d’espace de noms peut contenir un nombre quelconque de chaque type de déclaration, et dans n’importe quel ordre.
Pour plus d’informations sur la déclaration des types, des [opérations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)et des [fonctions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) [définis par l’utilisateur](xref:microsoft.quantum.guide.types#user-defined-types)au sein d’un espace de noms, consultez les liens suivants.

Le seul texte qui peut apparaître en dehors d’une déclaration d’espace de noms est un commentaire.
En particulier, les commentaires de documentation (plus de détails ci-dessous) pour un espace de noms précèdent la déclaration.

## <a name="namespace-declarations"></a>Déclarations d'espace de noms

Un fichier Q # dispose généralement d’une seule déclaration d’espace de noms, mais il peut avoir la valeur None (et être vide ou contenir simplement des commentaires) ou peut contenir plusieurs espaces de noms.
Les déclarations d’espaces de noms ne peuvent pas être imbriquées.

Le même espace de noms peut être déclaré dans plusieurs fichiers Q # qui sont compilés ensemble, à condition qu’il n’y ait pas de déclaration de type, d’opération ou de fonction portant le même nom.
En particulier, il n’est pas valide de définir le même type dans le même espace de noms dans plusieurs fichiers, même si les déclarations sont identiques.

Une déclaration d’espace de noms se compose du mot clé `namespace` , suivi du nom de l’espace de noms, d’une accolade ouvrante `{` , des déclarations contenues dans l’espace de noms et d’une accolade fermante `}` .
Les noms d’espaces de noms suivent le modèle .NET d’une séquence d’un ou de plusieurs symboles légaux séparés par des points `.` .
Par exemple, `MyQuantumStuff` et `Microsoft.Quantum.Intrinsic` sont des noms d’espaces de noms valides.
Par Convention, les symboles d’un nom d’espace de noms sont écrits en majuscules, mais cela n’est pas obligatoire.

Les références à des types ou des callables déclarés plus loin dans un fichier sont correctement résolues ; Il n’est pas nécessaire que le type, l’opération ou la déclaration de fonction précède une référence à celui-ci.

## <a name="open-directives"></a>Directives Open

Dans un bloc d’espace de noms, la `open` directive peut être utilisée pour importer tous les types et les callables déclarés dans un certain espace de noms et y faire référence par leur nom non qualifié.
Une telle `open` directive se compose du `open` mot clé, suivi de l’espace de noms à ouvrir et d’un point-virgule de fin.

> [!NOTE] 
> Toutes les `open` directives doivent apparaître avant `function` les `operation` déclarations, ou `newtype` dans le bloc d’espace de noms.

Éventuellement, un nom abrégé pour l’espace de noms ouvert peut être défini de sorte que tous les éléments de cet espace de noms puissent (et doivent) être qualifiés par le nom abrégé défini. Par exemple, étant donné la déclaration d’espace de noms et les directives Open suivantes,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

Si une opération que nous déclarons utilise une opération `Op` de `Microsoft.Quantum.Intrinsic` , nous l’appelons simplement en utilisant `Op` .
Toutefois, si nous voulions appeler une certaine fonction `Fn` à partir de `Microsoft.Quantum.Math` , nous aurions besoin de l’appeler à l’aide de `Math.Fn` .

La `open` directive s’applique à l’intégralité du bloc d’espace de noms dans un fichier.
Par conséquent, si nous devions définir un espace de noms supplémentaire dans le même fichier Q # que `NS` ci-dessus, toutes les opérations/fonctions/tous les types définis dans le deuxième espace de noms n’ont pas accès à quoi que ce soit à partir de `Microsoft.Quantum.Intrinsic` ou `Microsoft.Quantum.Math` , sauf si nous avons répété les directives ouvertes ici. 

Un type ou un appelable défini dans un autre espace de noms qui n’est *pas* ouvert dans l’espace de noms actuel doit être référencé par son nom complet.
Par exemple, une opération nommée `Op` à partir de l' `X.Y` espace de noms doit être référencée par son nom complet `X.Y.Op` , sauf si l' `X.Y` espace de noms a été ouvert plus tôt dans le bloc actuel. Comme indiqué ci-dessus, même si l' `X` espace de noms a été ouvert, il n’est pas possible de faire référence à l’opération en tant que `Y.Op` .
Si un nom abrégé `Z` pour `X.Y` a été défini dans cet espace de noms et ce fichier, `Op` doit être appelé `Z.Op` . 

Il est généralement préférable d’inclure un espace de noms à l’aide d’une `open` directive.
L’utilisation d’un nom qualifié complet est requise si deux espaces de noms définissent des constructions portant le même nom, et la source actuelle utilise des constructions à partir des deux.

Q # suit les mêmes règles d’affectation de noms que d’autres langages .NET.
Toutefois, Q # ne prend pas en charge les références relatives aux espaces de noms.
Autrement dit, si l’espace de noms `a.b` a été ouvert, une référence à une opération nommée `c.d` ne sera *pas* résolue en une opération portant le nom complet `a.b.c.d` .

## <a name="formatting"></a>Mise en forme

La plupart des instructions et directives Q # se terminent par un point-virgule de fin, `;` .
Les instructions et les déclarations telles que `for` et `operation` qui se terminent par un bloc d’instructions (voir ci-dessous) ne nécessitent pas de point-virgule de fin.
Chaque description d’instruction indique si le point-virgule de fin est obligatoire.

Les instructions, comme les expressions, les déclarations et les directives, peuvent être réparties sur plusieurs lignes.
L’utilisation de plusieurs instructions sur une seule ligne doit être évitée.

## <a name="statement-blocks"></a>Blocs d’instructions

Les instructions Q # sont regroupées dans des blocs d’instructions.
Un bloc d’instructions commence par une ouverture `{` et se termine par une fermeture `}` .

Un bloc d’instructions placé lexicalement dans un autre bloc est considéré comme un sous-bloc du bloc conteneur. les blocs conteneur et secondaires sont également appelés blocs externes et internes.

## <a name="comments"></a>Commentaires

Les commentaires commencent par deux barres obliques, `//` et continuent jusqu’à la fin de la ligne.
Un commentaire peut apparaître n’importe où dans un fichier source Q #.

## <a name="documentation-comments"></a>Commentaires de documentation

Les commentaires qui commencent par trois barres obliques, `///` , sont traités de manière spéciale par le compilateur lorsqu’ils apparaissent immédiatement avant un espace de noms, une opération, une spécialisation, une fonction ou une définition de type.
Dans ce cas, leur contenu est utilisé comme documentation pour le type pouvant être appelé ou défini par l’utilisateur, comme pour d’autres langages .NET.

Dans `///` les commentaires, le texte à afficher dans le cadre de la documentation de l’API est mis en forme en tant que [démarque](https://daringfireball.net/projects/markdown/syntax), avec les différentes parties de la documentation indiquées par des en-têtes spécialement nommés.
En tant qu’extension de la démarque, les références croisées aux opérations, aux fonctions et aux types définis par l’utilisateur dans Q # peuvent être incluses à l’aide de `@"<ref target>"` , où `<ref target>` est remplacé par le nom qualifié complet de l’objet de code référencé.
Le cas échéant, un moteur de documentation peut également prendre en charge des extensions de démarque supplémentaires.

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

Les noms suivants sont reconnus en tant qu’en-têtes de commentaires de documentation.

- **Résumé**: bref résumé du comportement d’une fonction ou d’une opération, ou de l’objectif d’un type. Le premier paragraphe du résumé est utilisé pour les informations de survol. Il doit s’agir d’un texte brut.
- **Description**: description du comportement d’une fonction ou d’une opération, ou de l’objectif d’un type. Le résumé et la description sont concaténés pour former le fichier de documentation généré pour la fonction, l’opération ou le type.
  La description peut contenir des équations et des symboles au format LaTeX en ligne.
- **Input**: description du tuple d’entrée d’une opération ou d’une fonction.
  Peut contenir des sous-sections de démarque supplémentaires indiquant chaque élément individuel du tuple d’entrée.
- **Sortie**: description du tuple retourné par une opération ou une fonction.
- **Paramètres de type**: section vide qui contient une sous-section supplémentaire pour chaque paramètre de type générique.
- **Exemple**: exemple bref de l’opération, de la fonction ou du type en cours d’utilisation.
- **Remarques**: divers Proseware décrivant certains aspects de l’opération, de la fonction ou du type.
- **Voir aussi**: liste de noms qualifiés complets indiquant les fonctions connexes, les opérations ou les types définis par l’utilisateur.
- **Références**: liste de références et de citations pour l’élément documenté.

## <a name="whats-next"></a>Étape suivante
En savoir plus sur [les opérations et les fonctions](xref:microsoft.quantum.guide.operationsfunctions) dans Q #.