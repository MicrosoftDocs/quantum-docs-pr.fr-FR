---
title: 'Notions de base sur Q #'
description: 'Concepts de base de Q #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: e77b52d1a6eb7e2f62ab12dedd75d00ac8fec4be
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327320"
---
# <a name="q-basics"></a>Notions de base sur Q #

Dans cette section, nous présentons une brève présentation des blocs de construction de base de Q #.

Pour obtenir une vue d’ensemble rapide du Q # et de son emplacement dans un composant fondamental du kit de développement quantique, vous pouvez consulter la section [q # ?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Qu’est-ce qu’un programme Quantum ?

D’un point de vue technique, un programme Quantum peut être considéré comme un ensemble particulier de sous-routines classiques qui, lorsqu’il est appelé, effectuent certaines opérations sur un système Quantum.
Une conséquence importante de cette vue est qu’un programme écrit en Q # ne modélise pas directement qubits, mais décrit plutôt comment un ordinateur de contrôle classique interagit avec ces qubits.
Par défaut, Q # ne définit pas les États quantiques ou d’autres propriétés de la mécanique de Quantum directement.
Par exemple, considérez l’État $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ abordé dans le guide des concepts de l' [informatique Quantum](xref:microsoft.quantum.concepts.intro) .
Pour préparer cet État dans Q #, nous utilisons les faits que les qubits sont initialisés dans l’État $ \ket {0} $, et que $ \ket{+} = H\ket {0} $, où $H $ est la transformation hadarmard, implémentée par [ `H` opération] (] (XREF : Microsoft. Quantum. Intrinsic. H) :

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a>États de Quantum dans Q #

Important, en écrivant le programme ci-dessus, nous n’avons pas explicitement fait référence à l’État dans Q #, mais nous avons décrit la façon dont l’État a été *transformé* par notre programme.
Cela nous permet d’être totalement agnostique quant à ce qu' *est* un État Quantum sur chaque ordinateur cible, qui peut avoir des interprétations différentes en fonction de l’ordinateur. 

Un programme Q # n’a pas la possibilité d’inverser l’état d’un qubit.
Au lieu de cela, un programme peut appeler des opérations telles que [`Measure`](xref:microsoft.quantum.intrinsic.measure) pour obtenir des informations à partir d’un qubit et appeler des opérations telles que [`X`](xref:microsoft.quantum.intrinsic.x) et [`H`](xref:microsoft.quantum.intrinsic.h) pour agir sur l’état d’un qubit.
Ce que *font* réellement ces opérations n’est rendu concrète que par l’ordinateur cible que nous utilisons pour exécuter le programme Q # en particulier.
Par exemple, si vous exécutez le programme sur notre [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator), le simulateur effectuera les opérations mathématiques correspondantes sur le système Quantum simulé.
Mais en regardant dans le futur, lorsque l’ordinateur cible est un ordinateur Quantum réel, l’appel de ces opérations dans Q # indiquera à l’ordinateur Quantum d’effectuer les opérations *réelles* correspondantes sur le système Quantum *réel* (par exemple, des impulsions laser avec des minutages précis).

Un programme Q # regroupe ces opérations comme défini par un ordinateur cible pour créer des opérations de niveau supérieur pour exprimer le calcul Quantum.
De cette façon, Q # permet d’exprimer facilement les algorithmes Quantum et Quantum hybrides de logique sous-jacents, tout en étant également général en ce qui concerne la structure d’un ordinateur cible ou d’un simulateur.

## <a name="q-operations-and-functions"></a>Opérations et fonctions Q #

Concrètement, un programme Q # est constitué d' *opérations*, de *fonctions*et de tous les types définis par l’utilisateur. 

Les opérations sont utilisées pour décrire les transformations des systèmes quantiques et constituent le bloc de construction le plus basique des programmes Q #. Chaque opération définie dans Q # peut alors appeler un nombre quelconque d’autres opérations.

Contrairement aux opérations, les fonctions sont utilisées pour décrire le comportement classique purement *déterministe* et n’ont pas d’effets en plus des valeurs classiques de calcul. Supposons, par exemple, que nous souhaitons mesurer notre qubits à la fin d’un programme et ajouter les résultats des mesures à un tableau.
Dans ce cas `Measure` , il s’agit d’une *opération* qui indique à l’ordinateur cible d’effectuer une mesure sur le qubits (réel ou simulé), et le processus classique d’ajout des résultats retournés à un tableau sera géré par les *fonctions*.

Ensemble, les opérations et les fonctions sont appelées *callables*, et leur structure et comportement sous-jacents est introduit sur les [opérations et les fonctions dans la page Q #](xref:microsoft.quantum.guide.operationsfunctions) .


## <a name="q-syntax-overview"></a>Vue d’ensemble de la syntaxe Q #

La syntaxe d’un langage décrit les différentes combinaisons de symboles qui forment un programme syntaxiquement correct.
Dans Q #, nous pouvons classer les éléments de sa syntaxe dans trois groupes différents : les types, les expressions et les instructions.

### <a name="types"></a>Types
Q # est un langage fortement typé, de sorte que l’utilisation soigneuse des types peut aider le compilateur à fournir des garanties fortes sur les programmes Q # au moment de la compilation.
En plus des types primitifs intégrés spécifiques à Quantum et standard (par exemple, `Int` , `Bool` `Qubit` et `Result` ), Q # fournit la prise en charge des types définis par l’utilisateur.
Tous les types primitifs de Q # sont décrits sur la page [types dans q #](xref:microsoft.quantum.guide.types) , ainsi que des détails sur les types de tableau et de tuple, ainsi que sur la façon de définir de nouveaux types dans un fichier q #.

### <a name="expressions"></a>Expressions
Une expression dans un langage de programmation est une combinaison d’une ou de plusieurs constantes, variables, opérateurs et fonctions que le langage de programmation interprète et évalue à une valeur spécifique.
Plus simplement, pour chaque type dans un langage, les expressions de ce type peuvent être des *littéraux* ou des symboles liés à une valeur de ce type.
Par exemple, `5` est un `Int` littéral (donc également une expression de type `Int` ), et si le symbole `count` est lié à la valeur entière `5` , `count` est également une expression entière.

En outre, une expression peut être constituée d’autres expressions associées à certains opérateurs.
Par conséquent, un autre exemple d' `Int` expression qui prend la valeur `5` est `2+3` .

Les expressions possibles de types dans Q #, ainsi que les opérateurs compatibles qui peuvent être utilisés pour les former, sont détaillées sur les [expressions de type dans la page Q #](xref:microsoft.quantum.guide.expressions) . 

### <a name="statements"></a>Instructions 
Une instruction est une unité syntaxique d’un langage de programmation impérative qui exprime une action à effectuer. Les instructions contrastent avec les expressions dans les instructions qui ne retournent pas de résultats et qui sont exécutées uniquement pour leurs effets secondaires, tandis que les expressions retournent toujours un résultat et n’ont souvent pas d’effets secondaires.
Cette distinction est fréquemment observée dans le libellé : une expression est évaluée, tandis qu’une instruction est exécutée.

Un exemple très basique d’une instruction dans Q # consiste à assigner un symbole à une expression :
```qsharp
let count = 5;
```

Un exemple légèrement plus intéressant est l' `for` instruction qui prend en charge l’itération et qui comprend un *bloc d’instructions*.
Supposons que `qubits` le symbole est lié à un registre de qubits (techniquement de type `Qubit[]` , c’est-à-dire un tableau de `Qubit` types). Alors
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
est une instruction qui itère au sein de chaque qubit dans le registre, en effectuant l' `H` opération sur chacun. Notez `H(qubit);` également qu’il s’agit d’une instruction.

En fait, toute expression d’appel de type `Unit` (ces callables qui ne retournent aucune information) peut être utilisée comme une instruction.
Cela est principalement utilisé lors de l’appel d’opérations sur des qubits qui retournent parce que l' `Unit` objectif de l’instruction est de modifier l’État Quantum implicite.
Les instructions d’évaluation d’expression requièrent un point-virgule de fin.

Presque tous les aspects d’un programme Q # sont générés à l’aide d’instructions, donc aucune page ne peut englober toutes les informations qui s’y rapportent.
Toutefois, leur structure lexicale et leur mise en forme sont décrites sur la page de [structure de fichier q #](xref:microsoft.quantum.guide.filestructure) , l’assignation de liaison de symboles et la portée aux [variables dans q #](xref:microsoft.quantum.guide.variables), et les boucles de workflow de contrôle telles que `for` at [Control flow in Q #](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Étapes suivantes
Dans le reste de ce guide, nous vous montrerons comment utiliser Q # pour créer des programmes quantiques complexes à l’aide des blocs de construction de base des opérations, des fonctions et des types.

Pour commencer, vous pouvez commencer à vous familiariser [avec les types dans Q #](xref:microsoft.quantum.guide.types).

Si vous souhaitez en savoir plus sur les fondations et la motivation de Q #, découvrez [pourquoi nous avons besoin de q # ?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
