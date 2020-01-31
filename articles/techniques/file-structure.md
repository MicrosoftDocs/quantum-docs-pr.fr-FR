---
title: 'Q # vue d’ensemble du programme-Q # techniques | Microsoft Docs'
description: 'Q # vue d’ensemble du programme-Q # techniques'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.file-structure
ms.openlocfilehash: e8f52e6b0d4382331665a8e845ef19a3a1beabf9
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820825"
---
# <a name="q-program-overview"></a>Vue d’ensemble d’un programme Q#

Q # est un langage de programmation évolutif, à plusieurs paradigmes, spécifique à un domaine pour l’informatique Quantum. Q # est un langage de programmation Quantum dans la mesure où il peut être utilisé pour décrire comment les instructions sont exécutées sur les machines quantiques. Les machines qui peuvent être ciblées sont comprises entre les simulateurs et le matériel Quantum réel. Q # est évolutif : il peut être utilisé pour écrire des programmes de démonstration simples comme la téléchargement qui s’exécutent sur quelques qubits, mais il prend également en charge l’écriture de nombreux programmes sophistiqués, tels que les simulations de molécules complexes, qui nécessitent des machines de grande taille avec des millions de qubits. Même si les machines physiques volumineuses sont toujours à l’avenir, Q # permet à un programmeur de programmer des algorithmes Quantum complexes. En plus, Q # prend en charge différentes tâches, telles que le débogage, le profilage, l’estimation des ressources et certaines simulations à usage spécifique de manière évolutive. 

D’un point de vue technique, un programme Quantum peut être considéré comme un ensemble particulier de fonctions classiques qui, lorsqu’elles sont appelées, génèrent des circuits quantiques comme des effets secondaires. Une conséquence importante de cette vue est qu’un programme écrit en Q # ne modélise pas directement qubits, mais décrit plutôt comment un ordinateur de contrôle classique interagit avec ces qubits.
Par défaut, Q # ne définit pas les États quantiques ou d’autres propriétés de la mécanique de Quantum directement, mais le fait indirectement par le biais de l’action des différentes sous-routines définies dans la langue.
Par exemple, considérez l’État $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ abordé dans le guide des concepts de l' [informatique Quantum](xref:microsoft.quantum.concepts.intro) .
Pour préparer cet État dans Q #, nous utilisons les faits que les qubits sont initialisés dans l’État $ \ket{0}$, et que $ \ket{+} = H\ket{0}$, où $H $ est la transformation Hadarmard :

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a>Q # tranformations des États de Quantum

Important, en écrivant le programme ci-dessus, nous n’avons pas explicitement fait référence à l’État dans Q #, mais nous avons décrit la façon dont l’État a été *transformé* par notre programme.
Ainsi, de la même façon qu’un programme de nuanceur de graphiques accumule une description des transformations à chaque vertex, un programme Quantum dans Q # accumule des transformations à des États quantiques.
Cela nous permet d’être totalement agnostique quant à ce qu' *est* un État Quantum sur chaque ordinateur cible, qui peut avoir des interprétations différentes en fonction de l’ordinateur. 

Du point de vue d’un programme Q #, un qubit est une référence entièrement opaque à la structure interne d’un ordinateur cible.
Un programme Q # n’a pas la possibilité d’inverser l’état d’un qubit, sa représentation sur un ordinateur cible, ou même s’il s’agit du même qubit que les autres qubit disponibles pour le programme.
Au lieu de cela, un programme peut appeler des opérations telles que `Measure` pour obtenir des informations à partir d’un qubit et appeler des opérations telles que `X` et `H` pour agir sur l’état d’un qubit.
Ces opérations n’ont pas de définition intrinsèque dans le langage et sont rendues concrètes uniquement par l’ordinateur cible utilisé pour exécuter un programme Q # particulier.
Un programme Q # regroupe ces opérations comme défini par un ordinateur cible pour créer des opérations de niveau supérieur pour exprimer le calcul Quantum.
De cette façon, Q # permet d’exprimer facilement les algorithmes Quantum et hybride Quantum-Classic de la logique, tout en étant également général en ce qui concerne la structure d’un ordinateur cible ou d’un simulateur.

## <a name="q-operations-and-functions"></a>Opérations et fonctions Q #

Concrètement, un programme Q # est constitué d’une ou de plusieurs *opérations*, d’une ou plusieurs *fonctions*et de types définis par l’utilisateur. Les opérations sont utilisées pour décrire les transformations de l’état d’un ordinateur quantique et constituent le bloc de construction le plus basique des programmes Q #. Chaque opération définie dans Q # peut alors appeler un nombre quelconque d’autres opérations, y compris les opérations *intrinsèques* intégrées implémentées par un ordinateur cible.
Une fois compilée, chaque opération est représentée sous la forme d’un type de classe .NET qui peut être fourni aux ordinateurs cibles.

Contrairement aux opérations, les fonctions sont utilisées pour décrire le comportement purement classique et n’ont aucun effet en plus des valeurs de sortie classiques. Q # est un langage fortement typé qui est fourni avec un ensemble de types primitifs intégrés, ainsi que la prise en charge des types définis par l’utilisateur. 

Dans le reste de ce guide, nous verrons comment utiliser des structures et des concepts de langage différents pour nous aider à définir des programmes quantiques complexes par le biais des blocs de construction de base des opérations, des fonctions et des types. 

## <a name="structure-of-q-source-files"></a>Structure des fichiers sources Q #

Au minimum, un fichier source Q # se compose d’une *déclaration d’espace de noms*, qui spécifie un espace de noms .net qui contiendra les définitions dans le fichier source.
Les définitions d’autres fichiers et bibliothèques source Q # peuvent être incluses à l’aide de l’instruction `open`.
Par exemple, la plupart des opérations qui définissent les portes fondamentales sont définies dans l’espace de noms <xref:microsoft.quantum.intrinsic>.
Pour que cela soit possible pour notre code, nous `open` simplement cet espace de noms en haut de chaque fichier :

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

Dans un espace de noms, chaque fichier source Q # peut définir n’importe quelle combinaison d' *opérations*, de *fonctions*et de *types définis par l’utilisateur*.
Dans le reste de cette section, nous décrirons chacun et fournissons des exemples de la façon dont ils peuvent être utilisés dans la pratique pour créer des programmes quantiques utiles.
