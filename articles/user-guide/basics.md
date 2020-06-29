---
title: 'Notions de base sur Q #'
description: 'Concepts de base de Q #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: 45e6f2f33dafc2aec177091d3cfa94aca14fbf0a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415355"
---
# <a name="q-basics"></a>Notions de base sur Q #

Cet article présente brièvement les blocs de construction de base de Q #.

Pour obtenir une vue d’ensemble du Q # et de son emplacement dans en tant que composant fondamental du kit de développement quantique, consultez [qu’est-ce que q # ?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Qu’est-ce qu’un programme Quantum ?

D’un point de vue technique, un programme Quantum est un ensemble particulier de sous-routines classiques qui, lorsqu’il est appelé, effectue certaines opérations sur un système Quantum.
Une conséquence importante de cette vue est qu’un programme Q # ne modélise pas directement qubits, mais décrit la façon dont un ordinateur sous contrôle classique interagit avec ces qubits.
Par défaut, Q # ne définit pas les États quantiques ou d’autres propriétés de la mécanique de Quantum directement.
Par exemple, considérez l’État $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ abordé dans le guide des concepts de l' [informatique Quantum](xref:microsoft.quantum.concepts.intro) .
Pour préparer cet État dans Q #, commencez par les faits que les qubits sont initialisés dans l’État $ \ket {0} $, et que $ \ket{+} = H\ket {0} $, où $H $ est la [transformation hadarmard](xref:microsoft.quantum.glossary#hadamard), implémentée par l' [ `H` opération](xref:microsoft.quantum.intrinsic.h). Le code Q # de base pour initialiser et transformer un qubit se présente comme suit :

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
Pour plus d’informations sur l’initialisation ou l' *allocation*de qubits, consultez [utilisation de qubits](xref:microsoft.quantum.guide.qubits).

## <a name="quantum-states-in-q"></a>États de Quantum dans Q #

Plus important encore, le programme précédent ne fait pas explicitement référence à l’État dans Q #, mais décrit comment notre programme a *transformé* l’État.
Avec cette approche, vous pouvez être entièrement agnostique en ce qui concerne un état *Quantum sur chaque* ordinateur cible, qui peut avoir des interprétations différentes en fonction de la machine. 

Un programme Q # ne peut pas inverser l’état d’un qubit.
Au lieu de cela, un programme peut appeler des opérations telles que [`Measure`](xref:microsoft.quantum.intrinsic.measure) pour obtenir des informations à partir d’un qubit et appeler des opérations telles que [`X`](xref:microsoft.quantum.intrinsic.x) et [`H`](xref:microsoft.quantum.intrinsic.h) pour agir sur l’état d’un qubit.
Ces *opérations sont uniquement* rendues concrètes par l’ordinateur cible utilisé pour exécuter le programme Q # en particulier.
Par exemple, si vous exécutez le programme sur notre [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator), le simulateur effectue les opérations mathématiques correspondantes sur le système Quantum simulé.
Mais à l’avenir, lorsque l’ordinateur cible est un ordinateur Quantum réel, l’appel de ces opérations dans Q # indique à l’ordinateur Quantum d’effectuer les opérations *réelles* correspondantes sur le système Quantum *réel* , par exemple, des impulsions laser avec un délai d’attente précis.

Un programme Q # regroupe ces opérations comme défini par un ordinateur cible pour créer des opérations de niveau supérieur pour exprimer le calcul Quantum.
De cette façon, Q # permet d’exprimer facilement les algorithmes Quantum et Quantum hybrides de logique sous-jacents, tout en étant également général en ce qui concerne la structure d’un ordinateur cible ou d’un simulateur.

## <a name="q-operations-and-functions"></a>Opérations et fonctions Q #

Concrètement, un programme Q # comprend des *opérations*, des *fonctions*et des types définis par l’utilisateur. 

Les opérations sont utilisées pour décrire les transformations des systèmes quantiques et constituent le bloc de construction le plus fondamental des programmes Q #. Chaque opération définie dans Q # peut alors appeler un nombre quelconque d’autres opérations.

Contrairement aux opérations, les fonctions sont utilisées pour décrire le comportement classique purement *déterministe* et n’ont pas d’effets en plus des valeurs classiques de calcul. Supposons, par exemple, que vous souhaitiez mesurer le qubits à la fin d’un programme et ajouter les résultats des mesures à un tableau.
Dans ce cas, `Measure` est une *opération* qui indique à l’ordinateur cible d’effectuer une mesure sur le qubits (réel ou simulé). En même temps, les *fonctions* gèrent le processus classique d’ajout des résultats retournés à un tableau.

Ensemble, les opérations et les fonctions sont appelées *callables*. La structure et le comportement sous-jacents sont introduits et détaillés dans [Operations and Functions in Q #](xref:microsoft.quantum.guide.operationsfunctions).


## <a name="q-syntax-overview"></a>Vue d’ensemble de la syntaxe Q #

La syntaxe d’un langage décrit les différentes combinaisons de symboles qui forment un programme syntaxiquement correct.
Dans Q #, les éléments de syntaxe sont classés en trois groupes différents : les types, les expressions et les instructions.

### <a name="types"></a>Types
Q # est un langage fortement typé, de sorte que l’utilisation soigneuse des types peut aider le compilateur à fournir des garanties fortes sur les programmes Q # au moment de la compilation.
En plus des types primitifs intégrés spécifiques à Quantum et standard, par exemple,, `Int` , `Bool` `Qubit` et `Result` , Q # fournit la prise en charge des types définis par l’utilisateur.

Pour obtenir une description de tous les types primitifs, des détails pour les types de tableau et de tuple, ainsi que des étapes pour définir de nouveaux types dans un fichier Q #, consultez [types dans q #](xref:microsoft.quantum.guide.types).

### <a name="expressions"></a>Expressions
Une expression dans un langage de programmation est une combinaison d’une ou de plusieurs constantes, variables, opérateurs et fonctions que le langage de programmation interprète et évalue à une valeur spécifique.
Plus simplement, pour chaque type dans un langage, les expressions de ce type peuvent être des *littéraux* ou des symboles liés à une valeur de ce type.
Par exemple, `5` est un `Int` littéral (donc également une expression de type `Int` ), et si le symbole `count` est lié à la valeur entière `5` , `count` est également une expression entière.

En outre, une expression peut être constituée d’autres expressions combinées par certains opérateurs.
Par exemple, une autre `Int` expression qui prend la valeur `5` est `2+3` .

Pour plus d’informations sur les expressions et les opérateurs compatibles dans Q #, consultez [expressions de type dans q #](xref:microsoft.quantum.guide.expressions). 

### <a name="statements"></a>Instructions 
Une instruction est une unité syntaxique d’un langage de programmation impérative qui exprime une action à effectuer. Les instructions contrastent avec les expressions dans les instructions qui ne retournent pas de résultats et qui sont exécutées uniquement pour leurs effets secondaires. Toutefois, les expressions retournent toujours un résultat et n’ont souvent pas d’effets secondaires. En résumé, les instructions Q # sont exécutées, tandis que les expressions sont évaluées.

Un exemple simple d’instruction dans Q # consiste à assigner un symbole à une expression :
```qsharp
let count = 5;
```

Un exemple plus intéressant est l' `for` instruction qui prend en charge l’itération et qui comprend un *bloc d’instructions*.
Supposons que `qubits` le symbole est lié à un registre de qubits (techniquement de type `Qubit[]` , ou un tableau de `Qubit` types). Alors
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
est une instruction qui itère sur chaque qubit dans le registre, en effectuant l' `H` opération sur chacune d’elles. Notez `H(qubit);` également qu’il s’agit d’une instruction.

Vous pouvez utiliser n’importe quelle expression d’appel de type `Unit` (un `Unit` type ne retourne aucune information) en tant qu’instruction.
Ce type d’expression est utile lors de l’appel d’opérations sur des qubits qui retournent `Unit` parce que l’objectif de l’instruction est de modifier l’État Quantum implicite.
Les instructions d’évaluation d’expression requièrent un point-virgule de fin.

Vous utilisez des instructions pour générer presque tous les aspects d’un programme Q #, et aucune page ne peut englober toutes les informations qui s’y rapportent.
Pour plus d’informations sur leur structure lexicale et leur mise en forme, consultez [Q # file structure](xref:microsoft.quantum.guide.filestructure). pour l’assignation et l’étendue des liaisons de symboles, consultez [variables dans Q #](xref:microsoft.quantum.guide.variables); et pour les boucles de workflow de contrôle telles que `for` , consultez [Flow Control in Q #](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Étapes suivantes

Commencez à vous familiariser [avec les types dans Q #](xref:microsoft.quantum.guide.types).

Pour plus d’informations sur les fondations et la motivation de Q #, consultez [pourquoi est-ce que q # est nécessaire ?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
