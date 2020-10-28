---
title: Q# Principes de conception d’API
description: Q# Principes de conception d’API
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6b196cf1be584a3157c7a9eb8cf497fe1121dd7a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691821"
---
# <a name="no-locq-api-design-principles"></a>Q# Principes de conception d’API

## <a name="introduction"></a>Introduction

En tant que langage et en tant que plateforme, Q# permet aux utilisateurs d’écrire, d’exécuter, de comprendre et d’explorer les applications Quantum.
Afin d’offrir aux utilisateurs, lorsque nous concevons Q# des bibliothèques, nous suivons un ensemble de principes de conception d’API pour guider nos conceptions et nous aider à créer des bibliothèques utilisables pour la communauté de développement quantique.
Cet article répertorie ces principes et donne des exemples pour vous aider à les appliquer lors de la conception d' Q# API.

> [!TIP]
> Il s’agit d’un document assez détaillé destiné à guider le développement de bibliothèque et les contributions de bibliothèque approfondies.
> Vous trouverez probablement plus utile si vous écrivez vos propres bibliothèques dans Q# , ou si vous contribuez des fonctionnalités plus importantes au [ Q# référentiel de bibliothèques](https://github.com/microsoft/QuantumLibraries).
>
> En revanche, si vous souhaitez apprendre à contribuer au kit de développement quantique plus généralement, nous vous suggérons de commencer par le Guide de [contribution](xref:microsoft.quantum.contributing).
> Si vous recherchez des informations plus générales sur la façon dont nous vous recommandons de mettre en forme votre Q# code, vous souhaiterez peut-être consulter le [Guide de style](xref:microsoft.quantum.contributing.style).

## <a name="general-principles"></a>Principes généraux

**Principe clé :** Exposez les API qui placent le focus sur les applications Quantum.

- ✅**Choisissez des** noms d’opération et de fonction qui reflètent la structure de haut niveau des algorithmes et des applications.
- ⛔️ **n'** exposez pas les API qui se concentrent principalement sur les détails d’implémentation de bas niveau.

**Principe clé :** Démarrez chaque conception d’API avec des exemples de cas d’usage pour vous assurer que les API sont intuitives à utiliser.

- ✅**Assurez-vous** que chaque composant d’une API publique a un cas d’usage correspondant, plutôt que de tenter de concevoir toutes les utilisations possibles à partir du début.
    Autrement dit, n’introduisez pas d’API publiques si elles sont utiles, mais assurez-vous que chaque partie d’une API possède un exemple *concret* dans lequel elle sera utile.

  *Exemples :*
  - @"microsoft.quantum.canon.applytoeachca" peut être utilisé en tant que `ApplyToEachCA(H, _)` pour préparer les registres dans un état de superposition uniforme, tâche courante dans de nombreux algorithmes Quantum. La même opération peut également être utilisée pour de nombreuses autres tâches dans la préparation, les valeurs numériques et les algorithmes basés sur Oracle.

- ✅**Effectuez** des conceptions d’API de brainstorming et d’atelier afin de vérifier qu’elles sont intuitives et qu’elles répondent à des cas d’usage proposés.

  *Exemples :*
  - Examinez \# le code Q actuel pour voir comment les nouvelles conceptions d’API peuvent simplifier et clarifier les implémentations existantes.
  - Passez en revue les conceptions d’API proposées avec les représentants du public principal.

**Principe clé :** Concevez les API pour prendre en charge et encourager le code lisible.

- ✅**Assurez-vous** que le code est lisible par les experts du domaine et les non-experts.
- ✅**Placez le** focus sur les effets de chaque opération et fonction au sein de l’algorithme de haut niveau, en utilisant la documentation pour examiner en détail l’implémentation, le cas échéant.
- ✅**Suivez le** Guide de [ \# style Q](xref:microsoft.quantum.contributing.style) commun le cas échéant.

**Principe clé :** Concevoir des API stables et fournir une compatibilité ascendante.

- ✅**Dépréciez** les anciennes API en douceur lorsque des modifications avec rupture sont requises.

- ✅**Fournissez** des fonctions et des opérations « shim » qui permettent au code utilisateur existant de fonctionner correctement pendant la désapprobation.

  *Exemples :*
  - Quand vous renommez une opération appelée `EstimateExpectation` en   `EstimateAverage` , introduisez une nouvelle opération appelée   `EstimateExpectation` qui appelle l’opération d’origine à son nouveau nom, afin que le code existant puisse continuer à fonctionner correctement.

- ✅**Utilisez l'** @"microsoft.quantum.core.deprecated" attribut pour communiquer des désapprobations à l’utilisateur.

- ✅ Quand vous renommez une opération ou une fonction **, fournissez** le nouveau nom en tant qu’entrée de chaîne à `@Deprecated` .

- ⛔️ **ne** supprimez pas les fonctions ou opérations existantes sans période d’obsolescence d’au moins six mois pour les versions préliminaires, ou au moins deux ans pour les versions prises en charge.

## <a name="functions-and-operations"></a>Fonctions et opérations

**Principe clé :** Assurez-vous que chaque fonction et opération a un seul objectif bien défini dans l’API.

- ⛔️ **n'** exposez pas les fonctions et les opérations qui effectuent plusieurs tâches non liées.

**Principe clé :** les fonctions et les opérations de conception peuvent être réutilisables autant que possible et anticiper les besoins futurs.

- ✅**Créez des** fonctions et des opérations pour composer correctement les autres fonctions et opérations, à la fois dans la même API et dans les bibliothèques existantes.

  *Exemples :*
  - L' @"microsoft.quantum.canon.delay" opération fait des hypothèses minimes sur son entrée et peut donc être utilisée pour retarder les applications des deux opérations dans la Q# bibliothèque standard ou comme défini par les utilisateurs.
    <!-- TODO: define bad example. -->

- ✅**Exposez** la logique classique purement déterministe comme des fonctions plutôt que des opérations.

  *Exemples :*
  - Une sous-routine qui élève en carré son entrée à virgule flottante peut être écrite de façon déterministe, et doit donc être exposée à l’utilisateur sous la forme `Squared : Double -> Double` d’une opération `Square : Double => Double` . Cela permet à la sous-routine d’être appelée à plusieurs emplacements (par exemple, à l’intérieur d’autres fonctions) et fournit des informations d’optimisation utiles au compilateur qui peuvent affecter les performances et les optimisations.
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` et `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` diffèrent dans les garanties prises en ce qui concerne le déterminisme ; les deux sont utiles dans différentes circonstances.
  - Les routines d’API qui transforment l’application des opérations de Quantum peuvent souvent être effectuées de manière déterministe et peuvent donc être rendues disponibles en tant que fonctions telles que   `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)` .

- ✅**Généralisez** le type d’entrée autant que possible pour chaque fonction et opération, à l’aide de paramètres de type en fonction des besoins.

  *Exemples :*
  - `ApplyToEach` a `<'T>(('T => Unit), 'T[]) => Unit` un type au lieu du type spécifique de son application la plus courante, `((Qubit => Unit), Qubit[]) => Unit` .

> [!TIP]
> Il est important d’anticiper les besoins futurs, mais il est également important de résoudre les problèmes concrets pour vos utilisateurs.
> En agissant sur ce principe clé, il faut donc toujours tenir compte de la prudence et de l’équilibrage afin d’éviter de développer des API « juste à la casse ».

**Principe clé :** choisissez les types d’entrée et de sortie pour les fonctions et les opérations qui sont prévisibles, et qui communiquent l’objectif d’un appelable.

- ✅**Utilisez les** types de tuples pour regrouper logiquement les entrées et les sorties qui sont significatives uniquement lorsqu’elles sont considérées ensemble. Envisagez d’utiliser un type défini par l’utilisateur dans ces cas-là.

  *Exemples :*
  - Une fonction permettant de générer les minima locaux d’une autre fonction peut avoir besoin de prendre les limites d’un intervalle de recherche comme entrée, ce qui `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` peut être une signature appropriée.
  - Une opération d’estimation d’une dérivée d’un classificateur de Machine Learning à l’aide de la technique de changement de paramètre peut nécessiter l’utilisation des vecteurs de paramètres décalés et non déplacés en tant qu’entrées. Une entrée similaire à `(unshifted : Double[], shifted : Double[])` peut être appropriée dans ce cas.

- ✅**Ordonnez** les éléments dans les tuples d’entrée et de sortie de manière cohérente entre les différentes fonctions et opérations.

  *Exemples :*
  - Si vous envisagez deux fonctions ou ou des opérations qui prennent chacune un angle de rotation et un qubit cible comme entrées, assurez-vous qu’elles sont triées de la même manière dans chaque tuple d’entrée. Il s’agit de, préférez `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` et `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` à `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` et `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` .

**Principe clé :** concevoir des fonctions et des opérations pour fonctionner correctement avec les \# fonctionnalités du langage Q, telles que l’application partielle.

- ✅**Organisez** les éléments dans les tuples d’entrée de telle sorte que les entrées les plus couramment appliquées se produisent en premier (c’est-à-dire : pour que l’application partielle agisse de la même façon que la curryfication).

  *Exemples :*
  - Une opération `ApplyRotation` qui accepte un nombre à virgule flottante et un qubit en tant qu’entrées peut souvent être partiellement appliquée avec l’entrée à virgule flottante pour une utilisation avec des opérations qui attendent une entrée de type `Qubit => Unit` . Ainsi, une signature de `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`
      fonctionnent le plus souvent avec une application partielle.
  - En règle générale, cette recommandation consiste à placer toutes les données classiques avant tous les qubits dans les tuples d’entrée, mais à utiliser un bon jugement et à examiner la manière dont votre API est appelée dans la pratique.

## <a name="user-defined-types"></a>Types définis par l'utilisateur

**Principe clé :** utilisez les types définis par l’utilisateur pour faciliter l’utilisation des API.

- ✅**Introduisez** de nouveaux types définis par l’utilisateur pour fournir un raccourci utile pour les types longs et/ou complexes.

  *Exemples :*
  - Dans les cas où un type d’opération avec trois entrées de tableau qubit est couramment utilisé comme entrée ou retourné comme sortie, en fournissant un UDT tel que `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      peut vous aider à fournir un raccourci utile.

- ✅**Introduisez** de nouveaux types définis par l’utilisateur pour indiquer qu’un type de base donné doit être utilisé uniquement dans un sens très particulier.

  *Exemples :*
  - Une opération qui doit être interprétée spécifiquement comme une opération qui encode des données classiques dans un registre Quantum peut être appropriée pour étiqueter avec un type défini par l’utilisateur `newtype InputEncoder = (Apply : (Qubit[] => Unit))` .

- ✅**Introduisez** de nouveaux types définis par l’utilisateur avec des éléments nommés qui permettent une extensibilité future (par exemple, une structure de résultats qui peut contenir des éléments nommés supplémentaires dans le futur).

  *Exemples :*
  - Lorsqu’une opération `TrainModel` expose un grand nombre d’options de configuration, l’exposition de ces options en tant que nouvel   `TrainingOptions` UDT et en fournissant une nouvelle fonction   `DefaultTrainingOptions : Unit -> TrainingOptions` permet aux utilisateurs de remplacer des éléments nommés spécifiques dans des valeurs UDT TrainingOptions, tout en permettant aux développeurs de bibliothèque d’ajouter de nouveaux éléments UDT, le cas échéant.

- ✅**Déclarez** les éléments nommés pour les nouveaux types définis par l’utilisateur de préférence pour obliger les utilisateurs à connaître la déconstruction de tuple correcte.

  *Exemples :*
  - Quand vous représente un nombre complexe dans sa décomposition polaire,   `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` préférez   `newtype ComplexPolar = (Double, Double)` .

**Principe clé :** utilisez les types définis par l’utilisateur de manière à réduire la charge cognitive et ne nécessite pas que l’utilisateur apprend d’autres concepts et nomenclature.

- ⛔️ **n'** introduisez pas de types définis par l’utilisateur qui requièrent que l’utilisateur utilise fréquemment l’opérateur Unwrap ( `!` ), ou qui nécessitent généralement plusieurs niveaux de désencapsulage. Les stratégies d’atténuation possibles sont les suivantes :

  - Quand vous exposez un type défini par l’utilisateur avec un seul élément, envisagez de définir un nom pour cet élément. Par exemple, envisagez d’utiliser la `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` préférence `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)` .

  - S’assurer que les autres fonctions et opérations peuvent accepter directement les instances UDT « encapsulées ».

- ⛔️ **n'** introduisez pas de nouveaux types définis par l’utilisateur qui dupliquent des types intégrés sans fournir d’expressivité supplémentaire.

  *Exemples :*
  - Un UDT `newtype QubitRegister = Qubit[]` ne fournit pas d’expressivité supplémentaire `Qubit[]` et est donc plus difficile à utiliser sans aucun avantage.
  - Un UDT `newtype LittleEndian = Qubit[]` documente la manière dont le Registre sous-jacent doit être utilisé et interprété, et fournit ainsi une expressivité supplémentaire par rapport à son type de base.

- ⛔️ **n'** introduisez pas de fonctions d’accesseur sauf si strictement requis ;   préférer fortement les éléments nommés dans ce cas.

  *Exemples :*
  - Lors de l’introduction d’un UDT `newtype Complex = (Double, Double)` , il est préférable de modifier la définition en   `newtype Complex = (Real : Double, Imag : Double)` pour introduire `GetReal : Complex -> Double` des fonctions et   `GetImag : Complex -> Double` .

## <a name="namespaces-and-organization"></a>Espaces de noms et organisation

**Principe clé :** choisissez des noms d’espaces de noms prévisibles et qui communiquent clairement l’objectif des fonctions, des opérations et des types définis par l’utilisateur dans chaque espace de noms.

- ✅**Nommez** les espaces de noms en tant que `Publisher.Product.DomainArea` .

  *Exemples :*
  - Les fonctions, les opérations et les UDT publiés par Microsoft dans le cadre de la fonctionnalité de simulation de Quantum du kit de développement quantique sont placés dans l'   `Microsoft.Quantum.Simulation` espace de noms.
  - `Microsoft.Quantum.Math` représente un espace de noms publié par Microsoft dans le cadre du kit de développement Quantum appartenant à la zone de domaine mathématique.

- ✅**Placez les** opérations, les fonctions et les types définis par l’utilisateur utilisés pour des fonctionnalités spécifiques dans un espace de noms qui décrit cette fonctionnalité, même si cette fonctionnalité est utilisée dans différents domaines de problème.

  *Exemples :*
  - Les API de préparation d’État publiées par Microsoft dans le cadre du kit de développement quantique sont placées dans   `Microsoft.Quantum.Preparation` .
  - Les API de simulation de Quantum publiées par Microsoft dans le cadre du kit de développement quantique sont intégrées à   `Microsoft.Quantum.Simulation` .

- ✅**Placez les** opérations, les fonctions et les types définis par l’utilisateur utilisés uniquement dans des domaines spécifiques dans des espaces de noms indiquant leur domaine d’utilitaire. Si nécessaire, utilisez des sous-espaces de noms pour indiquer des tâches ciblées dans chaque espace de noms spécifique à un domaine.

  *Exemples :*
  - La bibliothèque de Machine Learning Quantum publiée par Microsoft est en grande partie placée dans l' @"microsoft.quantum.machinelearning" espace de noms, mais des exemples de jeux de données sont fournis par l' @"microsoft.quantum.machinelearning.datasets"   espace de noms.
  - Les API de la chimie Quantum publiées par Microsoft dans le cadre du kit de développement Quantum doivent être mises en place `Microsoft.Quantum.Chemistry` . Les fonctionnalités spécifiques à l’implémentation de la décomposition Jordanie--Wigner peuvent être placées dans `Microsoft.Quantum.Chemistry.JordanWigner` , de sorte que l’interface principale pour la zone de domaine de chimie Quantum ne concerne pas les implémentations.

**Principe clé :** Utilisez les espaces de noms et les modificateurs d’accès ensemble pour être intentionnel de la surface de l’API exposée aux utilisateurs et pour masquer les détails internes relatifs à l’implémentation et au test de vos API.

- ✅ Chaque fois que **cela** est raisonnable, placez toutes les fonctions et toutes les opérations nécessaires pour implémenter une API dans le même espace de noms que l’API en cours d’implémentation, mais marquée avec les mots clés « Private » ou « Internal » pour indiquer qu’ils ne font pas partie de la surface d’API publique d’une bibliothèque. Utilisez un nom commençant par un trait de soulignement ( `_` ) pour distinguer visuellement les opérations et les fonctions privées et internes des callables publics.

  *Exemples :*
  - Le nom de l’opération `_Features` indique une fonction qui est privée pour un espace de noms et un assembly donnés, et qui doit être accompagnée du `internal` mot clé.

- ✅ Dans le cas rare où un ensemble complet de fonctions ou d’opérations privées est nécessaire pour implémenter l’API pour un espace **de noms donné, placez-** les dans un nouvel espace de noms correspondant à l’espace de noms implémenté et se terminant par `.Private` .

- ✅**Placez tous** les tests unitaires dans des espaces de noms correspondant à l’espace de noms testé et se terminant par `.Tests` .

## <a name="naming-conventions-and-vocabulary"></a>Conventions d’affectation des noms et vocabulaire

**Principe clé :** Choisissez les noms et la terminologie qui sont clairs, accessibles et lisibles à travers un large éventail d’audiences, y compris à la fois des spécialistes Quantum et des experts.

- ⛔️ **n’utilisez pas** de noms d’identificateurs discriminés ou d’exclusion, ni de terminologie dans les commentaires de documentation d’API.

- ✅**Utilisez les** commentaires de documentation de l’API pour fournir un contexte, des exemples et des références pertinents, en particulier pour les concepts plus difficiles.

- ⛔️ **n’utilisez pas** les noms d’identificateur qui sont inutilement ésotériques ou qui nécessitent des algorithmes de Quantum significatifs à lire.

  *Exemples :*
  - Préférez « itération d’amplification d’amplitude » à « itération Grover ».

- ✅**Choisissez des** opérations et des noms de fonctions qui communiquent clairement l’effet prévu d’un appelable, et non son implémentation. Notez que l’implémentation peut et doit être documentée dans les [Commentaires de documentation d’API](xref:microsoft.quantum.guide.filestructure#documentation-comments).

  *Exemples :*
  - Préférez « chevauchement d’estimation » à « Hadarmard test », car ce dernier communique la manière dont le premier est implémenté.

- ✅**Utilisez des** mots de manière cohérente dans toutes les \# API Q :

  - **Verbes**

    - **Assertion** : Vérifiez qu’une hypothèse sur l’état d’un ordinateur cible et de son qubits contient, éventuellement à l’aide de ressources non physiques. Les opérations utilisant ce verbe doivent toujours être amovibles en toute sécurité sans affecter les fonctionnalités des bibliothèques et des programmes exécutables. Notez que, contrairement aux faits, les assertions peuvent, en général, dépendre de l’état externe, par exemple l’état d’un registre qubit, l’environnement d’exécution, etc. Comme la dépendance sur l’état externe est un type d’effet secondaire, les assertions doivent être exposées comme des opérations plutôt que des fonctions.

    - **Estimation** : à l’aide d’une ou plusieurs mesures éventuellement répétées, estimez une quantité classique à partir des résultats de mesure.

      *Exemples :*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **Préparer** : appliquer une opération de Quantum ou une séquence d’opérations à un ou plusieurs qubits supposés démarrer dans un état initial particulier (en général, $ \ket{00\cdots 0} $), provoquant l’évolution de l’état de ces qubits à un état final souhaité. En règle générale, les États autres que l’état de départ donné **peuvent** entraîner une transformation unitaire non définie, mais **doivent** toujours conserver une opération et son voisin « annuler » et appliquer une absence d’opération.

      *Exemples :*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Mesure** : appliquez une opération de Quantum ou une séquence d’opérations à un ou plusieurs qubits, en lisant les données classiques à nouveau.

      *Exemples :*
      - @"Microsoft.Quantum.Intrinsic.Measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Appliquer** : appliquez une opération de Quantum ou une séquence d’opérations à un ou plusieurs qubits, ce qui entraîne la modification de l’état de ces qubits de manière cohérente. Ce verbe est le verbe le plus général de la \# nomenclature Q et ne **doit pas être** utilisé lorsqu’un verbe plus spécifique est plus directement pertinent.

  - **Noms** :

    - **Fait** : condition booléenne qui dépend uniquement de ses entrées et non de l’état d’un ordinateur cible, de son environnement ou de l’état du qubits de l’ordinateur. En revanche, avec une assertion, un fait est sensible uniquement aux *valeurs* fournies à ce fait. Par exemple :

      *Exemples :*
      - @"microsoft.quantum.diagnostics.equalityfacti": représente un fait d’égalité sur deux entrées entières ; soit les entiers fournis comme entrée sont égaux les uns des autres, soit ils ne le sont pas, indépendamment de tout autre État du programme.

    - **Options :** UDT contenant plusieurs éléments nommés qui peuvent agir comme des « arguments facultatifs » d’une fonction ou d’une opération. Par exemple :

      *Exemples :*
      - Le @"microsoft.quantum.machinelearning.trainingoptions" type défini par l’utilisateur comprend des éléments nommés pour le taux d’apprentissage, la taille de minilot et d’autres paramètres configurables pour la formation ml.

  - **Adjectifs** :

    - ⛔️ **nouveau** : cet adjectif ne **doit pas** être utilisé, car cela évite toute confusion avec son utilisation en tant que verbe dans de nombreux langages de programmation (par exemple, C++, C#, Java, machine à écrire, PowerShell).

  - **Prépositions :** Dans certains cas, les prépositions peuvent être utilisées pour lever toute ambiguïté ou clarifier les rôles des noms et des verbes dans les noms de fonctions et d’opérations. Toutefois, il convient de veiller à ce que cela ne soit pas très prudent et cohérent.

    - **Comme :** Représente que l’entrée et la sortie d’une fonction représentent les mêmes informations, mais que la sortie représente ces informations **sous** la forme d’une *Croix (X* ) au lieu de la représentation d’origine. Cela est particulièrement courant pour les fonctions de conversion de type.

      *Exemples :*
      - `IntAsDouble(2)` indique que l’entrée ( `2` ) et la sortie ( `2.0` ) représentent qualitativement les mêmes informations, mais qui utilisent différents \# types de données Q pour le faire.

    - **À partir de :** Pour garantir la cohérence, cette préposition ne   **doit pas** être utilisée pour indiquer les fonctions de conversion de type ou tout autre cas où **,** si nécessaire.

    - ⛔️ **à :** cette préposition ne **doit pas** être utilisée, afin d’éviter toute confusion avec son utilisation en tant que verbe dans de nombreux langages de programmation.
