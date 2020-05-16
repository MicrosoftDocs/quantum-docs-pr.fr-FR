---
title: 'Opérations et fonctions dans Q #'
description: Comment définir et appeler des opérations et des fonctions, ainsi que les spécialisations d’opérations contrôlées et voisines.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: bc9695b85b68807801225ccbc903a4622b450768
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431068"
---
# <a name="operations-and-functions-in-q"></a>Opérations et fonctions dans Q #

## <a name="defining-new-operations"></a>Définition de nouvelles opérations

Les opérations sont le cœur de Q #.
Une fois déclarées, elles peuvent être appelées à partir d’applications .NET classiques, par exemple, à l’aide d’un simulateur ou d’autres opérations dans Q #.
Chaque opération définie dans Q # peut alors appeler un nombre quelconque d’autres opérations, y compris les opérations intrinsèques intégrées définies par le langage. La façon dont ces opérations intrinsèques sont définies dépend de l’ordinateur cible.
Une fois compilée, chaque opération est représentée sous la forme d’un type de classe .NET qui peut être fourni aux ordinateurs cibles.

Chaque fichier source Q # peut définir n’importe quel nombre d’opérations.
Les noms d’opérations doivent être uniques au sein d’un espace de noms et peuvent ne pas être en conflit avec les noms de type ou de fonction.

Une déclaration d’opération se compose du mot clé `operation` , suivi du symbole qui est le nom de l’opération, d’un tuple d’identificateur typé qui définit les arguments de l’opération, d’un signe deux-points `:` , d’une annotation de type qui décrit le type de résultat de l’opération, éventuellement d’une annotation avec les caractéristiques de l' `{` opération `}`

Chaque opération prend une entrée, produit une sortie et spécifie l’implémentation pour une ou plusieurs spécialisations d’opérations.
Les spécialisations possibles et comment les définir/les appeler sont détaillés plus loin ci-dessous.
Pour l’instant, considérez l’opération suivante, qui définit uniquement une spécialisation de corps par défaut et qui accepte une seule qubit comme entrée, puis appelle l' <xref:microsoft.quantum.intrinsic.x> opération intégrée sur cette entrée :

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

Le mot clé `operation` commence la définition de l’opération, suivi du nom ; ici, `BitFlip` .
Ensuite, le type de l’entrée est défini en tant que `Qubit` , ainsi qu’un nom `target` pour faire référence à l’entrée dans la nouvelle opération.
De même, le `Unit` définit que la sortie de l’opération est vide.
Elle est utilisée de la même façon que `void` dans C# et d’autres langages impératifs, et est équivalente `unit` en F # et d’autres langages fonctionnels.

Les opérations peuvent également retourner des types plus intéressants que `Unit` .
Par exemple, l' <xref:microsoft.quantum.intrinsic.m> opération retourne une sortie de type `Result` , qui représente l’exécution d’une mesure. Nous pouvons soit transmettre la sortie d’une opération à une autre opération, soit l’utiliser avec le `let` mot clé pour définir une nouvelle variable.

Cela permet de représenter un calcul classique qui interagit avec les opérations de Quantum à un niveau bas, par exemple dans le [codage à haute densité](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> Chaque opération dans Q # prend exactement une entrée et retourne exactement une sortie.
> Plusieurs entrées et sorties sont ensuite représentées à l’aide de *tuples*, qui regroupent plusieurs valeurs en une seule valeur.
> De manière informelle, nous disons que Q # est un langage de type « Tuple-in-out ».
> Après ce concept, `()` doit ensuite être lu en tant que Tuple « vide », qui a le type `Unit` .


## <a name="controlled-and-adjoint-operations"></a>Opérations contrôlées et apjointes

Si une opération implémente une transformation unitaire, comme c’est le cas pour de nombreuses opérations dans Q #, il est possible de définir la façon dont l’opération agit quand *adjointed* ou *contrôlé*. Une spécialisation *voisine* d’une opération spécifie la manière dont l’inverse de l’opération agit, tandis qu’une spécialisation *contrôlée* spécifie la manière dont une opération agit quand son application est conditionnée sur l’état d’un registre Quantum particulier.

La adjoints des opérations de Quantum est cruciale pour de nombreux aspects de quantum computing. Plus loin ci-dessous, dans la section des [conjugaisons](#conjugations) , vous trouverez une telle situation abordée avec une technique de programmation Q # utile.

La version contrôlée d’une opération est une nouvelle opération qui applique efficacement l’opération de base uniquement si tous les qubits de contrôle sont dans un état spécifié.
Si le contrôle qubits est en superposition, l’opération de base est appliquée de manière cohérente à la partie appropriée de la superposition.
Ainsi, les opérations contrôlées sont souvent utilisées pour générer l’enchevêtrement.

Naturellement, une spécialisation *contrôlée* par l’application est également possible, en spécifiant l’application contrôlée du voisin de l’opération.

> [!NOTE]
> Si $U $ est la transformation unitaire implémentée par une opération `U` , `Adjoint U` représente la transformation unitaire $U ^ \dagger $, qui est la transformée conjuguée complexe.
> L’application successive d’une opération, puis son voisin à un État laisse l’État inchangé, comme illustré par le fait que $UU ^ \dagger = U ^ \dagger U = \ID $, la matrice d’identité.
> La représentation unitaire d’une opération contrôlée est légèrement plus en nuance, mais vous pouvez trouver plus de détails dans [quantum computing concepts : multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).

La section suivante décrit comment appeler ces différentes spécialisations dans votre code Q #.
Ci-dessous, nous expliquons comment définir des opérations pour les prendre en charge.

### <a name="calling-operation-specializations"></a>Appel des spécialisations d’opérations

Un *functor* dans Q # est une fabrique qui définit une nouvelle opération à partir d’une autre opération.
Les deux functors standard dans Q # sont `Adjoint` et `Controlled` .

Les functors ont accès à l’implémentation de l’opération de base lors de la définition de l’implémentation de la nouvelle opération.
Ainsi, les functors peuvent exécuter des fonctions plus complexes que les fonctions de niveau supérieur traditionnelles. Les functors n’ont pas de représentation dans le système Q # type. Il n’est donc actuellement pas possible de les lier à une variable ou de les passer comme arguments. 

Un functor est utilisé en l’appliquant à une opération, en retournant une nouvelle opération.
Par exemple, l’opération qui résulte de l’application du `Adjoint` functor à l' `Y` opération est écrite sous la forme `Adjoint Y` .
La nouvelle opération peut ensuite être appelée comme toute autre opération.
Pour qu’une opération prenne en charge l’application des `Adjoint` functors et/ou `Controlled` , son type de retour doit obligatoirement être `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint`functor

Par conséquent, `Adjoint Y(q1)` applique la functor de l’opération joint à l' `Y` opération pour générer une nouvelle opération et applique cette nouvelle opération à `q1` .
La nouvelle opération a la même signature et le même type que l’opération de base `Y` .
En particulier, la nouvelle opération autorise également `Adjoint` et autorise `Controlled` si et seulement si l’opération de base a été effectuée.
Le functor de l’Contigut est son propre inverse ; autrement dit, `Adjoint Adjoint Op` est toujours identique à `Op` .

#### <a name="controlled-functor"></a>`Controlled`functor

De même, `Controlled X(controls, target)` applique la functor contrôlée à l' `X` opération pour générer une nouvelle opération et applique cette nouvelle opération à `controls` et `target` .

> [!NOTE]
> Dans Q #, les versions contrôlées prennent toujours un tableau de qubits de contrôle et l’état spécifié est toujours pour tous les qubits de contrôle à l’État calcul ( `PauliZ` ) `One` , $ \ket {1} $.
> Le contrôle basé sur d’autres États peut être obtenu en appliquant l’opération unitaire appropriée à l’qubits de contrôle avant l’opération contrôlée, puis en appliquant les inversions de l’opération unitaire après l’opération contrôlée.
> Par exemple, l’application d’une `X` opération à un contrôle qubit avant et après une opération contrôlée entraîne le contrôle de l’état de l’opération `Zero` ($ \ket {0} $) pour ce qubit ; l’application d’une `H` opération avant et après contrôle l' `PauliX` `One` État, c’est-à-dire-1 eigenvalue de Pauli X, $ \ket {-} \mathrel{ : =} (\ket {0} -\ket {1} )/\sqrt {2} $ plutôt que l' `PauliZ` `One` État.

En fonction d’une expression d’opération, une nouvelle expression d’opération peut être formée à l’aide de `Controlled` functor.
La signature de la nouvelle opération est basée sur la signature de l’opération d’origine.
Le type de résultat est le même, mais le type d’entrée est un double Tuple avec un tableau qubit qui contient les qubit de contrôle comme premier élément et les arguments de l’opération d’origine comme second élément.
La nouvelle opération prend en charge `Controlled` et prendra en charge `Adjoint` si et seulement si l’opération d’origine a été effectuée.

Si l’opération d’origine n’a pris qu’un seul argument, l’équivalence du tuple de Singleton sera alors lue ici.
Par exemple, `Controlled X` est la version contrôlée de l' `X` opération. 
`X`a `(Qubit => Unit is Adj + Ctl)` un type, donc `Controlled X` a `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` le type ; en raison de l’équivalence de tuple de Singleton, il est identique à `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Si l’opération de base a pris plusieurs arguments, n’oubliez pas de placer les arguments correspondants de la version contrôlée de l’opération entre parenthèses pour les convertir en Tuple.
Par exemple, `Controlled Rz` est la version contrôlée de l' `Rz` opération. 
`Rz`a le type `((Double, Qubit) => Unit is Adj + Ctl)` , `Controlled Rz` a le type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
Par conséquent, `Controlled Rz(controls, (0.1, target))` serait un appel valide de `Controlled Rz` (Notez les parenthèses autour de `0.1, target` ).

Autre exemple, `CNOT(control, target)` peut être implémenté en tant que `Controlled X([control], target)` . Si une cible doit être contrôlée par deux qubits de contrôle (CCNOT), nous pouvons utiliser l' `Controlled X([control1, control2], target)` instruction.

#### `Controlled Adjoint` 

Les `Controlled` `Adjoint` functors et sont Permuted, donc il n’y a aucune différence entre l’application `Controlled Adjoint Op` de ou `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Définition des implémentations contrôlées et apjointes

Dans les exemples de déclaration de première opération ci-dessus, les opérations `BitFlip` et `DecodeSuperdense` ont été définies avec des signatures `(Qubit => Unit)` et `((Qubit, Qubit) => (Result, Result))` , respectivement.
Comme `DecodeSuperdense` comprend des mesures, il ne s’agit pas d’une opération unitaire et, par conséquent, les spécialisations non contrôlées ne peuvent pas exister (Rappelez-vous que l’exigence correspondante retourne une telle opération `Unit` ).
Toutefois, comme il `BitFlip` effectue simplement l' <xref:microsoft.quantum.intrinsic.x> opération unitaire, nous aurions pu le définir avec les deux spécialisations.

Ici, nous expliquons comment inclure l’existence de spécialisations dans vos déclarations de l’opération Q #, ce qui leur donne la possibilité d’appeler conjointement avec les `Adjoint` functors et/ou `Controlled` .
Plus [loin](#circumstances-for-validly-defining-specializations), nous décrivons certaines situations dans lesquelles il est valide ou non valide pour déclarer certaines spécialisations.

Les caractéristiques de l’opération définissent les genres d’functors qui peuvent être appliqués à l’opération déclarée et leur effet. L’existence de ces spécialisations peut être déclarée dans le cadre de la signature de l’opération, en particulier par le biais d’une annotation avec les caractéristiques de l’opération : `is Adj` , `is Ctl` ou `is Adj + Ctl` .
L’implémentation réelle de chaque spécialisation peut être définie *implicitement* ou *explicitement* .

### <a name="implicitly-specifying-implementations"></a>Spécification implicite des implémentations

Dans ce cas, le corps de la déclaration d’opération se compose uniquement de l’implémentation par défaut. Par exemple :

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
Ici, l’implémentation correspondante pour chaque spécialisation déclarée implicitement est générée automatiquement par le compilateur, pour être exécutée si les `Adjoint` `Controlled` functors ou sont utilisés.

Ainsi, un appel `Adjoint PrepareEntangledPair` à entraînerait le compilateur qui implémente le voisin de `CNOT` , puis le voisin de `H` .
Ces opérations individuelles étant à la fois autonomes, l’opération résultante `Adjoint PrepareEntangledPair` consiste simplement à appliquer, `CNOT(here, there)` puis `H(here)` .
Par conséquent, nous pouvons l’utiliser pour écrire l' `DecodeSuperdense` exemple ci-dessus de façon plus compacte, en utilisant le voisin de `PrepareEntangledPair` pour transformer l’État enchevêtré dans une paire non enchevêtrée de qubits :

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

L’annotation avec les caractéristiques de l’opération dans la déclaration est utile pour s’assurer que le compilateur génère automatiquement d’autres spécialisations en fonction de l’implémentation par défaut. 

Il existe un certain nombre de limitations importantes à prendre en compte lors de la conception d’opérations à utiliser avec functors.
Le plus important, les spécialisations pour une opération qui utilise la valeur de sortie d’une autre opération *ne peuvent pas* être générées automatiquement par le compilateur, car il est ambigu de réorganiser les instructions dans une telle opération pour obtenir le même effet.

Par conséquent, il est souvent utile de spécifier explicitement les différentes implémentations.

### <a name="explicitly-specifying-implementations"></a>Spécification explicite des implémentations

Dans le cas où l’implémentation ne peut pas être générée par le compilateur, elle peut être spécifiée explicitement. Ces déclarations de spécialisation explicites peuvent se composer d’une *directive de génération* appropriée ou d’une implémentation définie par l’utilisateur.
Nous fournissons ici la gamme complète de possibilités, avec des exemples ci-dessous.


#### <a name="explicit-specialization-declarations"></a>Déclarations de spécialisation explicites

Les opérations Q # peuvent contenir les déclarations de spécialisation explicites suivantes :

- La `body` spécialisation spécifie l’implémentation de l’opération sans les functors appliqués.
- La `adjoint` spécialisation spécifie l’implémentation de l’opération avec le `Adjoint` functor appliqué.
- La `controlled` spécialisation spécifie l’implémentation de l’opération avec le `Controlled` functor appliqué.
- La `controlled adjoint` spécialisation spécifie l’implémentation de l’opération avec `Adjoint` les `Controlled` functors et appliqués.
  Cette spécialisation peut également être nommée `adjoint controlled` , dans la mesure où les deux functors se comportent.


Une spécialisation d’opération se compose de la balise de spécialisation (par exemple `body` , ou `adjoint` , etc.) suivie de l’un des éléments suivants :

- Déclaration explicite comme décrit ci-dessous.
- *Directive* qui indique au compilateur *Comment* générer la spécialisation, l’un des éléments suivants :
  - `intrinsic`, qui indique que la spécialisation est fournie par l’ordinateur cible.
  - `distribute`, qui peut être utilisé avec les `controlled` `controlled adjoint` spécialisations et.
    Lorsqu' `controlled` il est utilisé avec, il indique que le compilateur doit calculer la spécialisation en appliquant `Controlled` à toutes les opérations dans le `body` .
    Lorsqu' `controlled adjoint` il est utilisé avec, il indique que le compilateur doit calculer la spécialisation en appliquant `Controlled` à toutes les opérations de la `adjoint` spécialisation.
  - `invert`, qui indique que le compilateur doit calculer la `adjoint` spécialisation en inversant le `body` , c’est-à-dire en inversant l’ordre des opérations et en appliquant le voisin à chacun d’entre eux.
    Lorsqu' `adjoint controlled` il est utilisé avec, cela indique que le compilateur doit calculer la spécialisation en inversant la `controlled` spécialisation.
  - `self`, pour indiquer que la spécialisation voisine est la même que la `body` spécialisation.
    Cela est légal pour les `adjoint` `adjoint controlled` spécialisations et.
    Pour `adjoint controlled` , `self` implique que la `adjoint controlled` spécialisation est la même que la `controlled` spécialisation.
  - `auto`, pour indiquer que le compilateur doit sélectionner une directive appropriée à appliquer.
    `auto`ne peut pas être utilisé pour la `body` spécialisation.

Les directives et `auto` toutes requièrent un point-virgule fermant `;` .
La `auto` directive se résout en la directive de génération suivante si une déclaration explicite de `body` est fournie :

- La `adjoint` spécialisation est générée en fonction de la directive `invert` .
- La `controlled` spécialisation est générée en fonction de la directive `distribute` .
- La `adjoint controlled` spécialisation est générée selon la directive `invert` si une déclaration explicite pour `controlled` est donnée, mais pas pour `adjoint` , et dans le `distribute` cas contraire.

> [!TIP]   
> Si une opération est auto-jointe, spécifiez explicitement le voisint ou la spécialisation voisine contrôlée à l’aide de la directive `self` de génération pour permettre au compilateur d’utiliser ces informations à des fins d’optimisation.

Une déclaration de spécialisation contenant une implémentation définie par l’utilisateur se compose d’un tuple d’argument suivi d’un bloc d’instructions avec le code Q # qui implémente la spécialisation.
Dans la liste d’arguments, `...` est utilisé pour représenter les arguments déclarés pour l’opération dans son ensemble.
Pour `body` et `adjoint` , la liste d’arguments doit toujours être `(...)` ; pour `controlled` et `adjoint controlled` , la liste d’arguments doit être un symbole qui représente le tableau de qubits de contrôle, suivi de `...` , placé entre parenthèses ; par exemple, `(controls,...)` .

### <a name="examples"></a>Exemples

Une déclaration d’opération peut être aussi simple que la suivante, qui définit l’opération Pauli X primitive :

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
Notez que la fonction joint de l’opération Pauli X est définie avec la directive `self` , car par définition `X` est sa propre inverse.

Le code ci `PrepareEntangledPair` -dessus par exemple est équivalent au code ci-dessous, contenant des déclarations de spécialisation explicites : 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
Le mot clé `auto` indique que le compilateur doit déterminer comment générer l’implémentation de la spécialisation.

#### <a name="user-defined-specialization-implementation"></a>Implémentation de spécialisation définie par l’utilisateur

Si le compilateur ne peut pas générer automatiquement l’implémentation pour une certaine spécialisation, ou si une implémentation plus efficace peut être donnée, l’implémentation peut également être définie manuellement.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
Dans l’exemple ci-dessus, `adjoint invert;` indique que la spécialisation voisine doit être générée en inversant l’implémentation du corps, et `controlled adjoint invert;` indique que la spécialisation de l’entité voisine contrôlée doit être générée en inversant l’implémentation donnée de la spécialisation contrôlée.

Si une ou plusieurs spécialisations en plus du corps par défaut doivent être déclarées explicitement, l’implémentation du corps par défaut doit également être incluse dans une déclaration de spécialisation appropriée :

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a>Circonstances de la définition correcte de spécialisations

#### <a name="operation-declarations-with-adjointcontrolled"></a>Déclarations d’opération avec le voisin/contrôlé

Il est légal de spécifier une opération sans les versions voisines ou contrôlées. Par exemple, les opérations de mesure n’ont aucune valeur, car elles ne sont pas réversibles ni contrôlables.

Une opération prend en charge les `Adjoint` functors et/ou `Controlled` si sa déclaration contient une déclaration implicite ou explicite des spécialisations respectives.

Une spécialisation dépendante ou contrôlée de manière explicite implique l’existence d’une spécialisation voisine/contrôlée. 

Pour une opération dont le corps contient des boucles de répétition jusqu’à réussite, des instructions SET, des mesures, des instructions return ou des appels à d’autres opérations qui ne prennent pas en charge le `Adjoint` functor, la génération automatique d’une spécialisation Join à la suite de la `invert` `auto` directive ou n’est pas possible.

Pour une opération dont le corps contient des appels à d’autres opérations qui ne prennent pas en charge le `Controlled` functor, la génération automatique d’une spécialisation contrôlée à la suite de la `distribute` `auto` directive ou n’est pas possible.

#### <a name="controlled-adjoint"></a>Contigut contrôlé

La version contrôlée par le contrôle contigut d’une opération spécifie la manière dont une version contrôlée par Quantum de l’opération est implémentée.
Il est possible de spécifier une opération sans contrôle de version voisine. par exemple, les opérations de mesure n’ont pas de version définie par l’utilisateur, car elles ne sont ni contrôlables ni réversibles.

Une spécialisation voisine de l’opération doit exister si et seulement si une spécialisation et une spécialisation contrôlée existent. Dans ce cas, l’existence de la spécialisation voisine contrôlée est déduite et une spécialisation appropriée est générée par le compilateur si aucune implémentation n’a été définie explicitement. 

Pour une opération dont le corps contient des appels à d’autres opérations qui n’ont pas de version définie par le contrôle, il n’est pas possible de générer automatiquement une spécialisation adjacente à la suite de la `invert` `distribute` `auto` directive ou.


### <a name="type-compatibility"></a>Compatibilité de type

Une opération avec des functors supplémentaires pris en charge peut être utilisée partout où une opération avec moins d’functors, mais la même signature est attendue.
Par exemple, une opération de type `(Qubit => Unit is Adj)` peut être utilisée partout où une opération de type `(Qubit => Unit)` est attendue.

Q # est *covariant* en ce qui concerne les types de retour pouvant être appelés : un pouvant être appelé qui retourne un type `'A` est compatible avec un pouvant être appelé avec le même type d’entrée et un type de résultat `'A` compatible avec.

Q # est *contravariant* en ce qui concerne les types d’entrée : un pouvant être appelé qui prend un type `'A` comme entrée est compatible avec un appelable avec le même type de résultat et un type d’entrée compatible avec `'A` .

Autrement dit, étant donné les définitions suivantes :

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

les conditions suivantes sont vraies :

- La fonction `ConjugateInvertWith` peut être appelée avec un `inner` argument de `Invert` ou `ApplyUnitary` .
- La fonction `ConjugateUnitaryWith` peut être appelée avec un `inner` argument de `ApplyUnitary` , mais pas `Invert` .
- Une valeur de type `(Qubit[] => Unit is Adj + Ctl)` peut être retournée à partir de `ConjugateInvertWith` .

> [!IMPORTANT]
> Q # 0,3 a introduit une différence significative dans le comportement des types définis par l’utilisateur.

Les types définis par l’utilisateur sont traités comme une version encapsulée du type sous-jacent, plutôt qu’en tant que sous-type.
Cela signifie qu’une valeur d’un type défini par l’utilisateur n’est pas utilisable quand une valeur du type sous-jacent est attendue.


### <a name="conjugations"></a>Conjugaisons

Contrairement aux bits classiques, la libération de la mémoire Quantum est un peu plus complexe, car la réinitialisation aveugle de qubits peut avoir des effets indésirables sur le calcul restant si les qubits sont toujours pris en compte. Cela peut être évité en « annulant » les calculs effectués avant la libération de la mémoire. Un modèle courant dans quantum computing est donc le suivant : 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

À partir de notre version 0,9, nous prenons en charge une instruction de conjugaison qui implémente la transformation ci-dessus. À l’aide de cette instruction, l’opération `ApplyWith` peut être implémentée de la façon suivante :

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
Une telle instruction de conjugaison devient évidemment beaucoup plus utile si les transformations externes et internes ne sont pas facilement disponibles en tant qu’opérations, mais sont plutôt plus pratiques à décrire par un bloc composé de plusieurs instructions. 

La transformation inverse pour les instructions définies dans le bloc intérieur est générée automatiquement par le compilateur et exécutée après la fin du bloc apply.
Étant donné que toutes les variables mutables utilisées dans le cadre du bloc within ne peuvent pas être reliées dans le bloc Apply, il est garanti que la transformation générée est le voisin du calcul dans le bloc intérieur. 


## <a name="defining-new-functions"></a>Définition de nouvelles fonctions

Les fonctions sont purement déterministes, les routines classiques dans Q #, qui sont distinctes des opérations en ce qu’elles ne sont pas autorisées à avoir des effets autres que le calcul d’une valeur de sortie.
En particulier, les fonctions ne peuvent pas appeler d’opérations ; agir sur, allouer ou emprunter qubits ; exemples de nombres aléatoires Sinon, dépend de l’État au-delà de la valeur d’entrée d’une fonction.
Par conséquent, les fonctions Q # sont *pures*, car elles mappent toujours les mêmes valeurs d’entrée aux mêmes valeurs de sortie.
Cela permet au compilateur Q # de réorganiser en toute sécurité le mode et le moment où les fonctions sont appelées lors de la génération de spécialisations d’opérations.

Chaque fichier source Q # peut définir un nombre quelconque de fonctions.
Les noms de fonctions doivent être uniques dans un espace de noms et peuvent ne pas être en conflit avec des noms d’opération ou de type.

La définition d’une fonction fonctionne de la même façon que la définition d’une opération, à la différence qu’il n’est pas possible de définir des spécialisations voisines ou contrôlées pour une fonction.
Exemple :

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

ou 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a>Logique classique dans les fonctions = = bonne

Chaque fois que cela est possible, il est utile d’écrire la logique classique en termes de fonctions plutôt que d’opérations, afin qu’elle puisse être utilisée plus facilement à partir des opérations.
Par exemple, si nous avions écrit la `Square` déclaration ci-dessus en tant qu' *opération*, le compilateur n’aurait pas pu garantir que l’appel de la même entrée produirait toujours les mêmes sorties.

Pour souligner la différence entre les fonctions et les opérations, envisagez le problème d’échantillonnage classique d’un nombre aléatoire à partir d’une opération Q # :

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Chaque fois que `U` est appelé, il aura une action différente sur `target` .
En particulier, le compilateur ne peut pas garantir que si nous avons ajouté une `adjoint auto` déclaration de spécialisation à `U` , `U(target); Adjoint U(target);` agit en tant qu’identité (autrement dit, en tant que non-op).
Cela viole la définition de l’voisine que nous avons vu dans les [vecteurs et les matrices](xref:microsoft.quantum.concepts.vectors), de telle sorte que la génération automatique d’une spécialisation de la version voisine dans une opération où l’opération a été appelée <xref:microsoft.quantum.math.randomreal> entraînerait la rupture des garanties fournies par le compilateur ; <xref:microsoft.quantum.math.randomreal> est une opération pour laquelle il n’existe pas de version voisine ou contrôlée.

D’un autre côté, en autorisant les appels de fonction tels que `Square` is safe, dans le sens où le compilateur peut être certain qu’il n’a besoin de conserver l’entrée que pour `Square` maintenir sa sortie stable.
Ainsi, l’isolation de la logique classique la plus possible dans les fonctions facilite la réutilisation de cette logique dans d’autres fonctions et opérations.


## <a name="generic-type-parameterized-callables"></a>Générique (paramètre de type) callables

De nombreuses fonctions et opérations que nous pouvons souhaiter définir ne s’appuient pas vraiment sur les types de leurs entrées, mais plutôt implicitement utiliser leurs types via une autre fonction ou opération.
Par exemple, considérez le concept de *carte* commun à de nombreux langages fonctionnels ; à partir d’une fonction $f (x) $ et d’une collection de valeurs $ \{ X_1, X_2, \dots, x_n \} $, Map retourne une nouvelle collection $ \{ f (X_1), f (X_2), \dots, f (x_n) \} $.
Pour l’implémenter dans Q #, nous pouvons tirer parti de la première classe de ces fonctions.
Nous allons écrire un exemple rapide de `Map` , en utilisant ★ en tant qu’espace réservé tout en décrivant les types dont nous avons besoin.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Remarque Cette fonction est très similaire, quel que soit le type réel que nous remplaçons.
Une carte des entiers à Paulis, par exemple, est similaire à une carte à partir de nombres à virgule flottante en chaînes :

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

En principe, nous pourrions écrire une version de `Map` pour chaque paire de types que nous rencontrons, mais cela présente un certain nombre de difficultés.
Par exemple, si nous trouvons un bogue dans `Map` , nous devons nous assurer que le correctif est appliqué uniformément dans toutes les versions de `Map` .
De plus, si nous créons un nouveau tuple ou un type défini par l’utilisateur, nous devons maintenant également construire un nouveau `Map` pour qu’il se présente avec le nouveau type.
Bien que cela soit tractable pour un petit nombre de ces fonctions, étant donné que nous recueillons de plus en plus de fonctions de la même forme que `Map` , le coût de l’introduction de nouveaux types devient insuffisant dans un ordre relativement court.

Toutefois, une grande partie de cette difficulté est que nous n’avons pas donné au compilateur les informations dont il a besoin pour reconnaître la manière dont les différentes versions de `Map` sont liées.
En fait, nous voulons que le compilateur traite `Map` comme une sorte de fonction mathématique des *types* q # en fonctions q #.

Cette notion est formalisée en autorisant les fonctions et les opérations à avoir des *paramètres de type*, ainsi que leurs paramètres de tuple ordinaires.
Dans les exemples ci-dessus, nous souhaitons considérer `Map` comme ayant des paramètres `Int, Pauli` de type dans le premier cas et `Double, String` dans le deuxième cas.
Dans la plupart des cas, ces paramètres de type peuvent ensuite être utilisés comme s’il s’agissait de types ordinaires : nous utilisons des valeurs de paramètres de type pour créer des tableaux et des tuples, appeler des fonctions et des opérations, et les assigner à des variables ordinaires ou mutables.

> [!NOTE]
> Le cas le plus extrême de dépendance indirecte est celui de qubits, où un programme Q # ne peut pas s’appuyer directement sur la structure du `Qubit` type, mais **doit** passer ces types à d’autres opérations et fonctions.

En revenant à l’exemple ci-dessus, nous voyons que nous avons besoin `Map` de paramètres de type, l’un pour représenter l’entrée à `fn` et l’autre pour représenter la sortie de `fn` .
Dans Q #, il est écrit en ajoutant des crochets pointus (c’est-à-dire `<>` , pas brakets $ \braket {} $ !) après le nom d’une fonction ou d’une opération dans sa déclaration, et en répertoriant chaque paramètre de type.
Le nom de chaque paramètre de type doit commencer par un battement `'` , indiquant qu’il s’agit d’un paramètre de type et non d’un type ordinaire (également connu sous le nom de type *concret* ).
Pour `Map` , nous écrivons donc :

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Notez que la définition de `Map<'Input, 'Output>` semble très similaire aux versions que nous avons écrites auparavant.
La seule différence est que nous avons explicitement informé le compilateur qui `Map` ne dépend pas directement de ce qui `'Input` `'Output` est, mais fonctionne pour deux types quelconques en les utilisant indirectement via `fn` .
Une fois que nous avons défini `Map<'Input, 'Output>` cette méthode, vous pouvez l’appeler comme s’il s’agissait d’une fonction ordinaire :

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> L’écriture de fonctions et d’opérations génériques est un emplacement où « tuple en sortie de tuple » est un moyen très utile de réfléchir aux fonctions et opérations Q #.
> Dans la mesure où chaque fonction accepte exactement une entrée et retourne une seule sortie, une entrée de type `'T -> 'U` correspond à *n’importe quelle* fonction Q # de quelque manière que ce soit.
> De même, toute opération peut être passée à une entrée de type `'T => 'U` .

En guise de deuxième exemple, considérez le défi que pose l’écriture d’une fonction qui retourne la composition de deux autres fonctions :

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Ici, nous devons spécifier exactement ce que, `A` `B` et `C` sont, par conséquent, en limitant gravement l’utilitaire de notre nouvelle `Compose` fonction.
Après tout, `Compose` dépend uniquement de `A` , et `B` `C` *via* `innerFn` et `outerFn` .
En guise d’alternative, nous pouvons ajouter des paramètres de type à `Compose` qui indiquent qu’il fonctionne pour *n’importe quel* `A` , `B` , et `C` , tant que ces paramètres correspondent à ceux attendus par `innerFn` et `outerFn` :

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Les bibliothèques standard Q # fournissent une série de ces opérations et fonctions paramétrées de type pour faciliter l’utilisation du workflow de contrôle d’ordre supérieur.
Celles-ci sont abordées plus en détail dans le Guide de la [bibliothèque standard Q #](xref:microsoft.quantum.libraries.standard.intro).


## <a name="callables-as-first-class-values"></a>Callables comme valeurs de première classe

Une technique critique pour le type de contrôle et la logique classique utilisant des fonctions plutôt que des opérations consiste à utiliser les opérations et les fonctions dans Q # qui sont de *première classe*.
En d’autres termes, il s’agit de chaque valeur de la langue, à son propre droit.
Par exemple, le code suivant est parfaitement valide Q #, si un peu indirect :

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

La valeur de la variable `ourH` dans l’extrait de code ci-dessus est ensuite l’opération <xref:microsoft.quantum.intrinsic.h> , de sorte que nous pouvons appeler cette valeur comme toute autre opération.
Cela nous permet d’écrire des opérations qui prennent des opérations dans le cadre de leur entrée, formant ainsi des concepts de contrôle d’ordre supérieur.
Par exemple, nous pourrions penser à « squareiser » une opération en l’appliquant deux fois au même qubit cible.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>Retour d’opérations à partir d’une fonction

Nous insistons sur le fait que nous pouvons également retourner des opérations dans le cadre des sorties, de telle sorte que nous puissions isoler certains genres de logique conditionnelle classique comme une fonction classique qui retourne une description d’un programme Quantum sous la forme d’une opération.
En guise d’exemple simple, prenons l’exemple de téléportage, dans lequel le tiers recevant un message classique à deux bits doit utiliser le message pour décoder leur qubit dans l’État téléporté approprié.
Nous pourrions écrire cela en termes d’une fonction qui prend ces deux bits classiques et retourne l’opération de décodage appropriée.

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

Cette nouvelle fonction est effectivement une fonction, car si nous l’appelons avec les mêmes valeurs que `hereBit` et `thereBit` , nous obtenons toujours la même opération.
Par conséquent, le décodeur peut être exécuté en toute sécurité au sein d’opérations sans avoir à expliquer comment la logique de décodage interagit avec les définitions des différentes spécialisations d’opérations.
Autrement dit, nous avons isolé la logique classique à l’intérieur d’une fonction, garantissant au compilateur que l’appel de fonction peut être réorganisé avec impunity tant que l’entrée est conservée.


## <a name="partial-application"></a>Application partielle

Nous pouvons en faire beaucoup plus avec les fonctions qui retournent des opérations à l’aide d’une *application partielle*, dans laquelle nous pouvons fournir une ou plusieurs parties de l’entrée à une fonction ou une opération sans réellement l’appeler. Par exemple, en rappelant l' `ApplyTwice` exemple ci-dessus, nous pouvons indiquer que nous ne voulons pas spécifier, immédiatement, à quel qubit l’opération d’entrée doit s’appliquer :

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

Dans ce cas, la variable locale `twiceOp` contient l’opération partiellement appliquée `ApplyTwice(op, _)` , où des parties de l’entrée qui n’ont pas encore été spécifiées sont indiquées par `_` .
Lorsque nous appelons `twiceOp` en fait la ligne suivante, nous passons comme entrée à l’opération partiellement appliquée, toutes les autres parties de l’entrée à l’opération d’origine.
Ainsi, l’extrait de code ci-dessus est effectivement identique à l’appel `ApplyTwice(op, target)` direct, économisez pour que nous ayons introduit une nouvelle variable locale qui nous permet de retarder l’appel tout en fournissant certaines parties de l’entrée.

Étant donné qu’une opération partiellement appliquée n’est pas réellement appelée tant que l’intégralité de son entrée n’a pas été fournie, nous pouvons appliquer des opérations en toute sécurité, même à partir de fonctions.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

En principe, la logique classique dans `SquareOperation` pourrait avoir été bien plus complexe, mais elle est toujours isolée du reste d’une opération par les garanties que le compilateur peut offrir sur les fonctions.
Cette approche sera utilisée dans la bibliothèque standard Q # pour exprimer le workflow de contrôle classique de manière à pouvoir l’utiliser facilement dans des programmes quantiques.


## <a name="recursion"></a>Récursivité

Q # callables peuvent être récursives directement ou indirectement.
Autrement dit, une opération ou une fonction peut s’appeler elle-même, ou elle peut appeler un autre pouvant être appelé, qui appelle directement ou indirectement l’opération pouvant être appelée.

Il existe toutefois deux commentaires importants sur l’utilisation de la récursivité :

- L’utilisation de la récursivité dans les opérations est susceptible d’interférer avec certaines optimisations.
  Cela peut avoir un impact important sur la durée d’exécution de l’algorithme.
- En cas d’exécution sur un appareil Quantum réel, l’espace de pile peut être limité et, par conséquent, une récurrence profonde peut entraîner une erreur d’exécution.
  En particulier, le compilateur et le runtime Q # n’identifient pas et n’optimisent pas la récurrence de la fin.

## <a name="whats-next"></a>Étape suivante
En savoir plus sur les [variables](xref:microsoft.quantum.guide.variables) dans Q #.