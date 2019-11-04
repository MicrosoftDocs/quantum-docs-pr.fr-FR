---
title: 'Guide de style Q # | Microsoft Docs'
description: 'Guide de style Q #'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 56455e9d5cd452b8620ee794f40563d1d3040193
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183843"
---
# <a name="q-style-guide"></a>Guide de style Q # #
## <a name="general-conventions"></a>Conventions générales ##

Les conventions suggérées dans ce guide sont destinées à faciliter la lecture et la compréhension des programmes et des bibliothèques écrits dans Q #.

# <a name="guidancetabguidance"></a>[Assistance](#tab/guidance)

Nous vous suggérons :

- N’ignorez pas une convention, sauf si vous le configurez intentionnellement pour fournir du code plus lisible et plus compréhensible à vos utilisateurs.

# <a name="examplestabexamples"></a>[Exemples](#tab/examples)

***

## <a name="naming-conventions"></a>Conventions de nommage ##

En proposant le kit de développement quantique, nous nous efforçons d’utiliser des noms de fonctions et d’opérations qui aident les développeurs de Quantum à écrire des programmes faciles à lire et qui réduisent la surprise.
Une partie importante de cela est que lorsque nous choisissons des noms pour les fonctions, les opérations et les types, nous établissons le *vocabulaire* que les programmeurs utilisent pour exprimer les concepts quantiques. Grâce à nos choix, nous vous aidons ou les empêcherons à communiquer clairement.
Cela pose une responsabilité pour nous assurer que les noms que nous introduisons offrent une clarté plutôt qu’une obscurité.
Dans cette section, nous détaillerons la manière dont nous répondons à cette obligation en termes de conseils explicites qui nous aideront à faire le meilleur de la communauté de développement Q #.

### <a name="operations-and-functions"></a>Opérations et fonctions ###

L’une des premières choses qu’un nom doit établir est si un symbole donné représente une fonction ou une opération.
La différence entre les fonctions et les opérations est essentielle pour comprendre le comportement d’un bloc de code.
Pour communiquer la distinction entre les fonctions et les opérations aux utilisateurs, nous nous appuyons sur les opérations de quantum des modèles Q # par le biais de l’utilisation d’effets secondaires.
Autrement dit, une opération *effectue* une opération.

En revanche, les fonctions décrivent les relations mathématiques entre les données.
L’expression `Sin(PI() / 2.0)` *est* `1.0`et n’implique rien de l’état d’un programme ou de son qubits.

En résumé, les opérations effectuent des opérations alors que les fonctions sont des choses.
Cette distinction suggère que les opérations sont nommées en tant que verbes et fonctions en tant que noms.

> [!NOTE]
> Lorsqu’un type défini par l’utilisateur est déclaré, une nouvelle fonction qui construit des instances de ce type est implicitement définie en même temps.
> À partir de cette perspective, les types définis par l’utilisateur doivent être nommés en tant que noms afin que le type lui-même et la fonction de constructeur aient des noms cohérents.

Dans la mesure du possible, assurez-vous que les noms des opérations commencent par des verbes qui indiquent clairement l’effet pris par l’opération.
Exemple :

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

Un cas qui mérite une mention spéciale est lorsqu’une opération prend une autre opération comme entrée et l’appelle.
Dans ce cas, l’action entreprise par l’opération d’entrée n’est pas claire lorsque l’opération externe est définie, de telle sorte que le verbe de droite n’est pas immédiatement clair.
Nous vous recommandons d’utiliser le verbe `Apply`, comme dans `ApplyIf`, `ApplyToEach`et `ApplyToFirst`.
D’autres verbes peuvent également être utiles dans ce cas, comme dans `IterateThroughCartesianPower`.

| Verbe | Effet attendu |
| ---- | ------ |
| Appliquer | Une opération fournie en tant qu’entrée est appelée |
| Assert | Une hypothèse sur le résultat d’une mesure de Quantum possible est vérifiée par un simulateur |
| Estimation | Une valeur classique est retournée, représentant une estimation dessinée à partir d’une ou de plusieurs mesures. |
| Measure | Une mesure de Quantum est exécutée et son résultat est renvoyé à l’utilisateur. |
| Préparer | Un registre donné de qubits est initialisé dans un état particulier |
| Exemple | Une valeur classique est retournée au hasard à partir d’une distribution |

Pour les fonctions, nous vous suggérons d’éviter l’utilisation de verbes en faveur des noms communs (consultez les conseils sur les noms appropriés ci-dessous) ou des adjectifs :

- `ConstantArray`
- `Head`
- `LookupFunction`

En particulier, dans presque tous les cas, nous vous suggérons d’utiliser des participles passés, le cas échéant, pour indiquer qu’un nom de fonction est fortement connecté à une action ou à un effet secondaire ailleurs dans un programme Quantum.
Par exemple, `ControlledOnInt` utilise la forme participe du verbe « Control » pour indiquer que la fonction agit comme un adjectif pour modifier son argument.
Ce nom présente l’avantage supplémentaire de correspondre à la sémantique du `Controlled` functor intégré, comme indiqué ci-dessous.
De même, les noms d' _agent_ peuvent être utilisés pour construire des noms de fonction et UDT à partir de noms d’opérations, comme dans le cas du nom `Encoder` pour un UDT qui est fortement associé à `Encode`.

# <a name="guidancetabguidance"></a>[Assistance](#tab/guidance)

Nous vous suggérons :

- Utilisez des verbes pour les noms d’opérations.
- Utilisez des noms ou des adjectifs pour les noms de fonction.
- Utilisez des noms pour les attributs et les types définis par l’utilisateur.
- Pour tous les noms pouvant être appelés, utilisez `CamelCase` dans des préférences fortes pour `pascalCase`, `snake_case`ou `ANGRY_CASE`. En particulier, vérifiez que les noms pouvant être appelés commencent par des lettres majuscules.
- Pour toutes les variables locales, utilisez `pascalCase` en priorité pour `CamelCase`, `snake_case`ou `ANGRY_CASE`. En particulier, vérifiez que les variables locales commencent par des minuscules.
- Évitez l’utilisation de traits de soulignement `_` dans les noms de fonctions et d’opérations ; quand des niveaux de hiérarchie supplémentaires sont nécessaires, utilisez des espaces de noms et des alias d’espaces de noms.

# <a name="examplestabexamples"></a>[Exemples](#tab/examples)

|   | NOM | description |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | Effacez l’utilisation d’un verbe (« réfléchir ») pour indiquer l’effet de l’opération. |
| ☒ | <s>`operation XRotation`</s> | L’utilisation de l’expression nominale suggère une fonction plutôt que l’opération. |
| ☒ | <s>`operation search_oracle`</s> | L’utilisation de `snake_case` enfreint la notation Q #. |
| ☒ | <s>`operation Search_Oracle`</s> | L’utilisation de traits de soulignement internes au nom de l’opération contrevient à la notation Q #. |
| ☑ | `function StatePreparationOracle` | L’utilisation de l’expression nominale suggère que la fonction retourne une opération. |
| ☑ | `function EqualityFact` | Effacez l’utilisation du nom (« FACT ») pour indiquer qu’il s’agit d’une fonction, tandis que le adjectif. |
| ☒ | <s>`function GetRotationAngles`</s> | L’utilisation du verbe (« obten ») suggère qu’il s’agit d’une opération. |
| ☑ | `newtype GeneratorTerm` | L’utilisation de l’expression nominale fait clairement référence au résultat de l’appel du constructeur UDT. |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | L’utilisation de l’expression verbale suggère que le constructeur UDT est une opération. |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | L’utilisation de l’expression substantif communique l’utilisation de l’attribut. |

***

### <a name="shorthand-and-abbreviations"></a>Raccourcis et abréviations ###

En dépit des conseils ci-dessus, il existe de nombreuses formes de raccourci qui voient une utilisation courante et généralisée dans quantum computing.
Nous vous suggérons d’utiliser le raccourci existant et commun là où il existe, en particulier pour les opérations qui sont intrinsèques au fonctionnement d’un ordinateur cible.
Par exemple, nous choisissons le nom `X` au lieu de `ApplyX`et `Rz` au lieu de `RotateAboutZ`.
Lors de l’utilisation de tels raccourcis, les noms d’opérations doivent être en majuscules (par exemple : `MAJ`).

Une attention particulière est nécessaire lors de l’application de cette Convention dans le cas des acronymes et des abréviations couramment utilisés, tels que « QFT » pour « transformation de Fourier quantique ».
Nous vous suggérons de suivre les conventions .NET générales pour l’utilisation d’acronymes et de abréviations dans les noms complets, qui prescrivent que :

- les acronymes à deux lettres et les abréviations sont nommés en majuscules (par exemple : `BE` pour « Big endian »).
- tous les acronymes et les abréviations sont nommés dans `CamelCase` (par exemple : `Qft` pour « transformation de Fourier quantique »)

Par conséquent, une opération qui implémente QFT peut être appelée `QFT` comme raccourci, ou écrite en tant que `ApplyQft`.

Pour les opérations et les fonctions les plus couramment utilisées, il peut être souhaitable de fournir un nom abrégé comme _alias_ pour une forme plus longue :

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidancetabguidance"></a>[Assistance](#tab/guidance)

Nous vous suggérons :

- Considérez les noms abrégés couramment acceptés et largement utilisés, le cas échéant.
- Utilisez des majuscules pour les raccourcis.
- Utilisation de majuscules pour les acronymes courts (à deux lettres) et abréviations.
- Utilisez `CamelCase` pour des acronymes plus longs (au moins trois lettres) et abréviations.

# <a name="examplestabexamples"></a>[Exemples](#tab/examples)

|   | NOM | description |
|---|------|-------------|
| ☑ | `X` | Raccourci bien maîtrisé pour « appliquer une transformation $X $ » |
| ☑ | `CNOT` | Raccourci bien maîtrisé pour « contrôlé-non » |
| ☒ | <s>`Cnot`</s> | La forme abrégée ne doit pas être dans `CamelCase`. |
| ☑ | `ApplyQft` | L’initialiseur commun « QFT » apparaît dans le cadre d’un nom de forme longue. |
| ☑ | `QFT` | L’initialiseur commun « QFT » apparaît dans le cadre d’un nom abrégé. |



***


### <a name="proper-nouns-in-names"></a>Noms appropriés dans les noms ###

En physique, il est courant de nommer les éléments après la première personne à publier à leur sujet, la plupart des non-Physicists ne sont pas familiers avec les noms de tout le monde et tout l’historique.
La confiance trop importante au niveau des conventions de nommage de la physique peut donc poser un obstacle important à l’entrée, car les utilisateurs des autres arrière-plans doivent apprendre un grand nombre de noms apparemment opaques afin d’utiliser des opérations et des concepts courants.
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
Par conséquent, nous vous recommandons d’adopter, à chaque fois que cela est raisonnable, des noms communs qui décrivent un concept en privilégiant les noms appropriés qui décrivent l’historique de publication d’un concept.
En guise d’exemple particulier, les opérations d’échange contrôlé unique et non contrôlé doublement sont souvent appelées les opérations « Fredkin » et « Toffoli » dans la documentation académique, mais sont identifiées dans Q # principalement comme `CSWAP` et `CCNOT`.
Dans les deux cas, les commentaires de documentation de l’API fournissent des noms synonymes basés sur des noms appropriés, ainsi que toutes les citations appropriées.

Cette préférence est particulièrement importante, étant donné que certaines utilisations des noms corrects sont toujours nécessaires. Q # suit le jeu de tradition dans de nombreuses langues classiques, par exemple, et fait référence aux types de `Bool` en référence à la logique booléenne, qui est à son tour nommée en respect de George bool.
De même, quelques concepts quantiques sont nommés de la même façon, y compris le type de `Pauli` intégré au langage Q #.
En réduisant l’utilisation des noms appropriés dans lesquels ce type d’utilisation n’est pas essentiel, nous réduisons l’impact que les noms appropriés ne peuvent pas être raisonnablement évités.

# <a name="guidancetabguidance"></a>[Assistance](#tab/guidance) 

Nous vous suggérons :

- Évitez d’utiliser des noms corrects dans les noms.

# <a name="examplestabexamples"></a>[Exemples](#tab/examples)

***

### <a name="type-conversions"></a>Conversions de type ###

Comme Q # est un langage fortement et statiquement typé, une valeur d’un type ne peut être utilisée qu’en tant que valeur d’un autre type à l’aide d’un appel explicite à une fonction de conversion de type.
Cela diffère des langages qui permettent aux valeurs de changer les types implicitement (par exemple, la promotion de type) ou en effectuant une conversion.
Par conséquent, les fonctions de conversion de type jouent un rôle important dans le développement de bibliothèque Q #, et constituent l’une des décisions les plus fréquemment rencontrées sur l’affectation de noms.
Toutefois, étant donné que les conversions de type sont toujours _déterministes_, elles peuvent être écrites en tant que fonctions et, par conséquent, tomber sous les conseils ci-dessus.
Nous suggérons, en particulier, que les fonctions de conversion de type ne doivent jamais être nommées en tant que verbes (par exemple, `ConvertToX`) ou des expressions prépositionnelles d’adverbes (`ToX`), mais doivent être nommées en tant qu’expressions prépositionnelles avec adjectif qui indiquent les types source et de destination (`XAsY`).
Lors de la liste de types de tableau dans les noms de fonctions de conversion de type, nous vous recommandons le raccourci `Arr`.
Dans des circonstances exceptionnelles, nous recommandons que toutes les fonctions de conversion de type soient nommées à l’aide d' `As` afin qu’elles puissent être identifiées rapidement.

# <a name="guidancetabguidance"></a>[Assistance](#tab/guidance)

Nous vous suggérons :

- Si une fonction convertit une valeur de type `X` en une valeur de type `Y`, utilisez le nom `AsY` ou `XAsY`.

# <a name="examplestabexamples"></a>[Exemples](#tab/examples)

|   | NOM | description |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | La préposition « to » génère une expression verbale, indiquant une opération et non une fonction. |
| ☒ | <s>`AsDouble`</s> | Le type d’entrée n’est pas clair dans le nom de la fonction. |
| ☒ | <s>`PauliArrFromBoolArr`</s> | Les types d’entrée et de sortie apparaissent dans un ordre incorrect. |
| ☑ | `ResultArrAsBoolArr` | Les types d’entrée et de sortie sont tous les deux clairs. |

***

### <a name="private-or-internal-names"></a>Noms privés ou internes ###

Dans de nombreux cas, un nom est strictement destiné à une utilisation interne à une bibliothèque ou à un projet, et n’est pas une partie garantie de l’API offerte par une bibliothèque.
Il est utile d’indiquer clairement que c’est le cas lorsque vous nommez des fonctions et des opérations afin que les dépendances accidentelles sur le code interne uniquement soient rendues évidentes.
Si une opération ou une fonction n’est pas destinée à une utilisation directe, mais doit plutôt être utilisée par un Callable correspondant qui agit par une application partielle, envisagez d’utiliser un nom commençant par `_` pour que l’appelabilité soit partiellement appliqué.

# <a name="guidancetabguidance"></a>[Assistance](#tab/guidance)

Nous vous suggérons :

- Lorsqu’une fonction, une opération ou un type défini par l’utilisateur ne fait pas partie de l’API publique d’une bibliothèque ou d’un programme Q #, assurez-vous que son nom commence par un trait de soulignement de début (`_`).

# <a name="examplestabexamples"></a>[Exemples](#tab/examples)

|   | NOM | description |
|---|------|-------------|
| ☒ | <s>`ApplyDecomposedOperation_`</s> | Le trait de soulignement `_` ne doit pas apparaître à la fin du nom. |
| ☑ | `_ApplyDecomposedOperation` | Le trait de soulignement `_` au début indique clairement que cette opération est réservée à un usage interne. |

***

### <a name="variants"></a>Variantes ###

Bien que cette limitation puisse ne pas persister dans les versions ultérieures de Q #, c’est pour l’instant le cas qu’il y aura souvent des groupes d’opérations ou de fonctions connexes qui se distinguent par les functors pris en charge par leurs entrées, ou par les types concrets de leurs arguments.
Ces groupes peuvent être distingués à l’aide du même nom racine, suivi d’une ou de deux lettres indiquant sa variante.

| Suffixe | Signification |
|--------|---------|
| `A` | Entrée attendue pour prendre en charge `Adjoint` |
| `C` | Entrée attendue pour prendre en charge `Controlled` |
| `CA` | Entrée attendue pour prendre en charge `Controlled` et `Adjoint` |
| `I` | Les entrées ou entrées sont de type `Int` |
| `D` | Les entrées ou entrées sont de type `Double` |
| `L` | Les entrées ou entrées sont de type `BigInt` |

# <a name="guidancetabguidance"></a>[Assistance](#tab/guidance)

Nous vous suggérons :

- Si une fonction ou une opération n’est pas liée à des fonctions ou des opérations similaires par les types et la prise en charge de functor de leurs entrées, n’utilisez pas de suffixe.
- Si une fonction ou une opération est liée à des fonctions ou des opérations similaires par les types et la prise en charge de functor de leurs entrées, utilisez des suffixes comme dans le tableau ci-dessus pour distinguer les variantes.

# <a name="examplestabexamples"></a>[Exemples](#tab/examples)

***

### <a name="arguments-and-variables"></a>Arguments et variables ###

L’un des objectifs clés du code Q # pour une fonction ou une opération est qu’il soit facile à lire et à comprendre.
De même, les noms des entrées et des arguments de type doivent indiquer comment une fonction ou un argument sera utilisé une fois fourni.


# <a name="guidancetabguidance"></a>[Assistance](#tab/guidance)

Nous vous suggérons :

- Pour tous les noms de variable et d’entrée, utilisez `pascalCase` en priorité pour `CamelCase`, `snake_case`ou `ANGRY_CASE`.
- Les noms d’entrée doivent être descriptifs ; Évitez une ou deux noms de lettres dans la mesure du possible.
- Les opérations et les fonctions acceptant exactement un argument de type doivent désigner cet argument de type par `T` lorsque son rôle est évident.
- Si une fonction ou une opération accepte plusieurs arguments de type, ou si le rôle d’un argument de type unique n’est pas évident, envisagez d’utiliser un mot en majuscules de petite taille précédé d' `T` (par exemple, `TOutput`) pour chaque type.
- N’incluez pas de noms de types dans les noms d’arguments et de variables ; ces informations peuvent et doivent être fournies par votre environnement de développement.
- Dénotez les types scalaires par leurs noms littéraux (`flagQubit`) et les types de tableau par un pluriel (`measResults`).
  Pour les tableaux de qubits en particulier, envisagez de dénoter ces types par `Register` où le nom fait référence à une séquence de qubits étroitement liée d’une certaine façon.
- Les variables utilisées en tant qu’index dans des tableaux doivent commencer par `idx` et doivent être singulières (par exemple : `things[idxThing]`).
  En particulier, évitez fortement d’utiliser des noms de variable à une seule lettre comme index ; envisagez d’utiliser `idx` au minimum.
- Les variables utilisées pour contenir les longueurs des tableaux doivent commencer par `n` et doivent être plurielées (par exemple : `nThings`).

# <a name="examplestabexamples"></a>[Exemples](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>Éléments nommés d’un type défini par l’utilisateur ###

Les éléments nommés dans les types définis par l’utilisateur doivent être nommés `CamelCase`, même dans l’entrée des constructeurs UDT.
Cela permet de séparer clairement les éléments nommés des références aux variables de portée locale lors de l’utilisation de la notation d’accesseur (par exemple : `callable::Apply`) ou de la notation de copie et de mise à jour (`set arr w/= Data <- newData`).

# <a name="guidancetabguidance"></a>[Assistance](#tab/guidance)

Nous vous suggérons :

- Les éléments nommés dans les constructeurs UDT doivent être nommés `CamelCase`; autrement dit, ils doivent commencer par une majuscule initiale.
- Les éléments nommés qui sont résolus en opérations doivent être nommés comme phases de verbe.
- Les éléments nommés qui ne sont pas résolus en opérations doivent être nommés comme des expressions nominales.
- Pour les UDT qui encapsulent des opérations, un seul élément nommé appelé `Apply` doit être défini.

# <a name="examplestabexamples"></a>[Exemples](#tab/examples)

|   | Extrait | description |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | Le nom `Apply` est une expression de verbe au format `CamelCase`, suggérant que l’élément nommé est une opération. |
| ☒ | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | Les éléments nommés doivent commencer par une lettre majuscule initiale. |
| ☒ | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | Les éléments nommés qui sont résolus en fonctions doivent être nommés comme des expressions nominales, et non comme des expressions verbales. |

***

## <a name="input-conventions"></a>Conventions d’entrée ##

Quand un développeur appelle une opération ou une fonction, les différentes entrées de cette opération ou fonction doivent être spécifiées dans un ordre particulier, ce qui a pour but d’augmenter la charge cognitive qu’un développeur doit utiliser pour utiliser une bibliothèque.
En particulier, la tâche de mémorisation des commandes d’entrée est souvent une gêne de la tâche en cours : programmation d’une implémentation d’un algorithme Quantum.
Bien que la prise en charge de l’IDE riche puisse atténuer ce risque dans une large mesure, la bonne conception et l’adhésion aux conventions communes peuvent également aider à réduire la charge cognitive imposée par une API.

Dans la mesure du possible, il peut être utile de réduire le nombre d’entrées attendues par une opération ou une fonction, afin que le rôle de chaque entrée soit immédiatement visible pour les développeurs qui appellent dans cette opération ou cette fonction, et pour les développeurs qui lisent ce code ultérieurement.
En particulier lorsqu’il n’est pas possible ou raisonnable de réduire le nombre d’arguments d’une opération ou d’une fonction, il est important de disposer d’un ordre cohérent qui minimise la surprise qu’un utilisateur fait face lors de la prédiction de l’ordre des entrées.

Nous recommandons une convention de classement d’entrée qui dérive largement de la réflexion de l’application partielle comme une généralisation de la curryfication f (x, y) ≡ f (x) (y).
Ainsi, l’application partielle des premiers arguments doit entraîner l’appel d’un pouvant être appelé de manière appropriée chaque fois que cela est raisonnable.
En suivant ce principe, envisagez d’utiliser l’ordre des arguments suivant :

- Arguments non pouvant être appelés classiques, tels que des angles, des vecteurs de puissances, etc.
- Arguments pouvant être appelés (fonctions et arguments).
  Si les fonctions et les opérations sont prises comme arguments, envisagez de placer des opérations après les fonctions.
- Collections traitées par des arguments pouvant être appelés de façon similaire à `Map`, `Iter`, `Enumerate`et `Fold`.
- Arguments qubit utilisés comme contrôles.
- Arguments qubit utilisés comme cibles.

Prenons l’exemple d’une opération `ApplyPhaseEstimationIteration` pour une utilisation dans une estimation de phase qui prend un angle et un Oracle, passe l’angle à `Rz` modifié par un tableau de différents facteurs de mise à l’échelle, puis contrôle les applications d’Oracle.
Nous ordonnons les entrées à `ApplyPhaseEstimationIteration` de la manière suivante :

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
Dans le cas particulier de la minimisation de surprise, certaines fonctions et opérations imitent le comportement des functors intégrés `Adjoint` et `Controlled`.
Par exemple, `ControlledOnInt<'T>` a le type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, de sorte que `ControlledOnInt<Qubit[]>(5, _)` agisse comme le `Controlled` functor, mais sur la condition que le registre de contrôle représente l’État $ \ket{5} = \ket{101}$.
Ainsi, un développeur s’attend à ce que les entrées `ControlledOnInt` placent l’objet pouvant être appelé en dernier, et que l’opération résultante prenne comme entrée `(Qubit[], 'T)`---le même ordre que celui suivi par la sortie de l' `Controlled` functor.

# <a name="guidancetabguidance"></a>[Assistance](#tab/guidance)

Nous vous suggérons :

- Utilisez des ordres d’entrée cohérents avec l’utilisation d’une application partielle.
- Utilisez des ordres d’entrée cohérents avec les functors intégrés.
- Placez toutes les entrées classiques avant toute entrée quantique.

# <a name="examplestabexamples"></a>[Exemples](#tab/examples)

***

## <a name="documentation-conventions"></a>Conventions de la documentation ##

Le langage Q # permet d’attacher une documentation à des opérations, des fonctions et des types définis par l’utilisateur à l’aide de commentaires de documentation spécialement mis en forme.
Dénotés par des barres obliques inverses (`///`), ces commentaires de documentation sont de petits documents de [démarque DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) qui peuvent être utilisés pour décrire l’objectif de chaque opération, fonction et type défini par l’utilisateur, les entrées attendues et ainsi de suite.
Le compilateur fourni avec le kit de développement Quantum extrait ces commentaires et les utilise pour aider composer documentation similaire à celle de https://docs.microsoft.com/quantum.
De même, le serveur de langage fourni avec le kit de développement quantum utilise ces commentaires pour fournir de l’aide aux utilisateurs lorsqu’ils pointent sur des symboles dans leur code Q #.
L’utilisation de commentaires de documentation peut aider les utilisateurs à obtenir un sens du code en fournissant une référence utile pour les détails qui ne sont pas facilement exprimés à l’aide des autres conventions de ce document.

<div class="nextstepaction">
    [Informations de référence sur la syntaxe des commentaires de Documentation](xref:microsoft.quantum.language.statements#documentation-comments)
</div>

Afin d’utiliser efficacement cette fonctionnalité pour aider les utilisateurs, nous vous recommandons de garder certaines choses à l’esprit lorsque vous écrivez des commentaires de documentation.

# <a name="guidancetabguidance"></a>[Assistance](#tab/guidance)

Nous vous suggérons :

- Chaque fonction publique, opération et type défini par l’utilisateur doit être immédiatement précédé d’un commentaire de documentation.
- Au minimum, chaque commentaire de documentation doit inclure les sections suivantes :
    - Résumé
    - Entrée
    - Sortie (le cas échéant)
- Assurez-vous que tous les résumés sont au moins deux phrases. Si de l’espace supplémentaire est nécessaire, fournissez une section `# Description` qui suit immédiatement `# Summary` avec des détails complets.
- Dans la mesure du possible, n’incluez pas de maths dans les résumés, car tous les clients ne prennent pas en charge la notation TeX dans les résumés. Notez que lors de l’écriture de documents Proseware (par exemple, TeX ou démarque), il peut être préférable d’utiliser des longueurs de ligne plus longues.
- Fournissez toutes les expressions mathématiques pertinentes dans la section `# Description`.
- Lors de la description des entrées, ne répétez pas les types de chaque entrée, car ceux-ci peuvent être déduits par le compilateur et risquent d’introduire une incohérence.
- Fournissez les exemples appropriés, chacun dans sa propre section `# Example`.
- Décrivez brièvement chaque exemple avant de répertorier le code.
- Citez toutes les publications académiques pertinentes (par exemple, les documents, les procédures, les billets de blog et les autres implémentations) dans une section `# References` sous la forme d’une liste à puces de liens.
- Assurez-vous que, dans la mesure du possible, tous les liens de citation sont vers des identificateurs permanents et immuables (numéros de arXiv DOIs ou avec version).
- Lorsqu’une opération ou une fonction est liée à d’autres opérations ou fonctions par des variantes de functor, répertoriez les autres variantes comme des puces dans la section `# See Also`.
- Laissez une ligne de commentaire vide entre les sections Level-1 (`/// #`), mais ne laissez pas une ligne vide entre les sections Level-2 (`/// ##`).

# <a name="examplestabexamples"></a>[Exemples](#tab/examples)

#### <a name=""></a>☑ ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a>Conventions de mise en forme ##

Outre les suggestions précédentes, il est utile de rendre le code aussi lisible que possible afin d’utiliser des règles de mise en forme cohérentes.
Ces règles de mise en forme par nature ont tendance à être quelque peu arbitraires et se caractérisent par des esthétiques personnelles.
Néanmoins, nous vous recommandons de conserver un ensemble cohérent de conventions de mise en forme au sein d’un groupe de collaborateurs, et en particulier pour les grands projets Q # tels que le kit de développement quantique lui-même.
Ces règles peuvent être appliquées automatiquement à l’aide de l’outil de mise en forme intégré au compilateur Q #.

# <a name="guidancetabguidance"></a>[Assistance](#tab/guidance) 

Nous vous suggérons :

- Utilisez quatre espaces au lieu de tabulations pour la portabilité.
  Par exemple, dans VS Code :
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- Retour à la ligne à 79 caractères lorsque cela est raisonnable.
- Utilisez des espaces autour des opérateurs binaires.
- Utilisez des espaces de part et d’autre des deux-points utilisés pour les annotations de type.
- Utilisez un espace unique après les virgules utilisées dans les littéraux de tableau et de Tuple (par exemple, dans les entrées des fonctions et opérations).
- N’utilisez pas d’espaces après les noms de fonctions, d’opérations ou d’UDT, ou après l' `@` dans les déclarations d’attribut.
- Chaque déclaration d’attribut doit être sur sa propre ligne.

# <a name="examplestabexamples"></a>[Exemples](#tab/examples)

|   | Extrait | description |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | Utilisez des espaces autour des opérateurs binaires. |
| ☒ | <s>`target:Qubit`</s> | Utilisez des espaces autour des deux-points d’annotation de type. |
| ☑ | `Example(a, b, c)` | Les éléments du tuple d’entrée sont correctement espacés pour une meilleure lisibilité. |
| ☒ | <s>`Example (a, b, c)`</s> | Les espaces doivent être supprimés après les noms des fonctions, des opérations ou des UDT. |

***

