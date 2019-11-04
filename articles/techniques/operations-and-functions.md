---
title: 'Techniques Q #-opérations et fonctions | Microsoft Docs'
description: 'Techniques Q #-opérations et fonctions'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 06da09dc9c6e0ba0331db6bc0cd3d2ddeb287113
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183452"
---
# <a name="q-operations-and-functions"></a>Opérations et fonctions Q #

Q # les programmes se composent d’une ou plusieurs *opérations* qui décrivent les effets secondaires que les opérations de Quantum peuvent avoir sur les données Quantum et une ou plusieurs *fonctions* qui permettent de modifier les données classiques. Contrairement aux opérations, les fonctions sont utilisées pour décrire le comportement purement classique et n’ont aucun effet en plus des valeurs de sortie classiques.

Chaque opération définie dans Q # peut alors appeler un nombre quelconque d’autres opérations, y compris les opérations intrinsèques intégrées définies par le langage. La façon dont ces opérations intrinsèques sont définies dépend de l’ordinateur cible. Une fois compilée, chaque opération est représentée sous la forme d’un type de classe .NET qui peut être fourni aux ordinateurs cibles.

## <a name="defining-new-operations"></a>Définition de nouvelles opérations

Comme décrit ci-dessus, le bloc de construction le plus basique d’un programme Quantum écrit en Q # est une *opération*qui peut être appelée à partir d’applications .net classiques, par exemple, à l’aide d’un simulateur ou d’autres opérations dans Q #.
Chaque opération prend une entrée, produit une sortie et spécifie l’implémentation pour une ou plusieurs spécialisations d’opérations.
Par exemple, l’opération suivante définit uniquement une spécialisation de corps par défaut et prend un qubit unique comme entrée, puis appelle l’opération de `X` intégrée sur cette entrée :

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

Le mot clé `operation` commence la définition de l’opération, suivi du nom ; ici, `BitFlip`.
Ensuite, le type de l’entrée est défini en tant que `Qubit`, ainsi qu’un nom `target` pour faire référence à l’entrée dans la nouvelle opération.
De même, le `Unit` définit que la sortie de l’opération est vide.
Cela est utilisé de la même façon que C# `void` dans et d’autres langages impératifs, et F# équivaut à `unit` dans et dans d’autres langages fonctionnels.

> [!NOTE]
> Nous allons l’explorer plus en détail ci-dessous, mais chaque opération dans Q # prend exactement une entrée et retourne exactement une sortie.
> Plusieurs entrées et sorties sont ensuite représentées à l’aide de *tuples*, qui regroupent plusieurs valeurs en une seule valeur.
> De manière informelle, nous disons que Q # est un langage de type « Tuple-in-out ».
> À la suite de ce concept, `()` doit ensuite être lu en tant que Tuple « vide », qui a le type `Unit`.

Dans la nouvelle opération, l’implémentation peut être spécifiée directement dans la déclaration si seule l’implémentation de la spécialisation du corps par défaut doit être spécifiée explicitement. En outre, il est possible de définir les implémentations de, par exemple, une ou plusieurs opérations de `functor`, comme indiqué ci-dessous. Dans l’exemple ci-dessus, la seule instruction consiste à appeler l’opération Q # intégrée <xref:microsoft.quantum.intrinsic.x>.

Les opérations peuvent également retourner des types plus intéressants que `Unit`.
Par exemple, l’opération <xref:microsoft.quantum.intrinsic.m> retourne une sortie de type `Result`, qui représente l’exécution d’une mesure. Nous pouvons soit transmettre la sortie d’une opération à une autre opération, soit l’utiliser avec le mot clé `let` pour définir une nouvelle variable.
<!-- Link to UID for superdense conceptual and example documentation. -->
Cela permet de représenter un calcul classique qui interagit avec les opérations de Quantum à un niveau bas, par exemple dans le codage à haute densité :

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a>Functors, contigut et contrôlé
Si une opération implémente une transformation unitaire, il est possible de définir la façon dont l’opération agit quand *adjointed* ou *contrôlé*. Une spécialisation voisine d’une opération spécifie la manière dont elle agit lorsqu’elle est exécutée en sens inverse, tandis qu’une spécialisation contrôlée spécifie la manière dont une opération agit lorsqu’elle est appliquée en fonction de l’état d’un registre Quantum.
L’existence de ces spécialisations peut être déclarée dans le cadre de la signature de l’opération : `is Adj + Ctl` dans l’exemple suivant. L’implémentation correspondante pour chaque spécialisation déclarée implicitement est ensuite générée par le compilateur. 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> De nombreuses opérations dans Q # représentent des portes unitaires.
> Si $U $ est la porte unitaire représentée par une `U`d’opération, `Adjoint U` représente la porte d’unité $U ^ \dagger $.

Dans le cas où l’implémentation ne peut pas être générée par le compilateur, elle peut être spécifiée explicitement. Ces déclarations de spécialisation explicites peuvent se composer d’une directive de génération appropriée ou d’une implémentation définie par l’utilisateur. Le code de `PrepareEntangledPair` ci-dessus, par exemple, est équivalent au code ci-dessous, contenant des déclarations de spécialisation explicites : 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
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
Dans l’exemple ci-dessus, `adjoint invert;` indique que la spécialisation voisine doit être générée en inversant l’implémentation du corps, et `controlled adjoint invert;` indique que la spécialisation de l’entité voisine doit être générée en inversant l’implémentation donnée du spécialisation contrôlée.

Nous verrons plus d’exemples dans le [processus de contrôle d’ordre supérieur](xref:microsoft.quantum.concepts.control-flow).

Pour appeler une spécialisation d’une opération, utilisez les mots clés `Adjoint` ou `Controlled`.
Par exemple, l’exemple de codage superdense ci-dessus peut être écrit plus compact en utilisant le voisin de `PrepareEntangledPair` pour transformer l’État enchevêtré dans une paire non enchevêtrée de qubits :

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Il existe un certain nombre de limitations importantes à prendre en compte lors de la conception d’opérations à utiliser avec functors.
Le plus important, les spécialisations pour une opération qui utilise la valeur de sortie d’une autre opération ne peuvent pas être générées automatiquement par le compilateur, car il est ambigu de réorganiser les instructions dans une telle opération pour obtenir le même effet.


## <a name="defining-new-functions"></a>Définition de nouvelles fonctions

Q # permet également de définir des *fonctions*, qui sont distinctes des opérations en ce qu’elles ne sont pas autorisées à avoir des effets autres que le calcul d’une valeur de sortie.
En particulier, les fonctions ne peuvent pas appeler d’opérations, agir sur qubits, échantillonner des nombres aléatoires ou dépendre de l’État au-delà de la valeur d’entrée d’une fonction.
Par conséquent, les fonctions Q # sont *pures*, car elles mappent toujours les mêmes valeurs d’entrée aux mêmes valeurs de sortie.
Cela permet au compilateur Q # de réorganiser en toute sécurité le mode et le moment où les fonctions sont appelées lors de la génération de spécialisations d’opérations.

La définition d’une fonction fonctionne de la même façon que la définition d’une opération, à la différence qu’il n’est pas possible de définir des spécialisations voisines ou contrôlées pour une fonction.
Par exemple :

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
Chaque fois que cela est possible, il est utile d’écrire la logique classique en termes de fonctions plutôt que d’opérations, afin qu’elle puisse être utilisée plus facilement à partir des opérations.
Si nous avions écrit `Square` en tant qu’opération, par exemple, le compilateur n’aurait pas pu garantir que l’appel de cette même entrée produirait toujours les mêmes sorties.

Pour souligner la différence entre les fonctions et les opérations, envisagez le problème d’échantillonnage classique d’un nombre aléatoire à partir d’une opération Q # :

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Chaque fois que `U` est appelé, il aura une action différente sur `target`.
En particulier, le compilateur ne peut pas garantir que si nous avons ajouté une déclaration de spécialisation `adjoint auto` à `U`, `U(target); Adjoint U(target);` agit comme une identité (autrement dit, une absence d’opération).
Cela ne respecte pas la définition de l’voisine que nous avons vu dans les [vecteurs et les matrices](xref:microsoft.quantum.concepts.vectors), ce qui permet de générer automatiquement une spécialisation de la personne voisine dans une opération où nous avons appelé l’opération <xref:microsoft.quantum.math.randomreal> arrêterait les garanties fournies par le compilateur. ; <xref:microsoft.quantum.math.randomreal> est une opération pour laquelle il n’existe aucune version voisine ou contrôlée.

D’un autre côté, il est possible d’autoriser les appels de fonction tels que `Square`, dans la mesure où le compilateur peut être certain qu’il n’a besoin de conserver l’entrée que pour `Square` afin de maintenir la stabilité de la sortie.
Ainsi, l’isolation de la logique classique la plus possible dans les fonctions facilite la réutilisation de cette logique dans d’autres fonctions et opérations.

## <a name="control-flow"></a>Flux de contrôle

Au sein d’une opération ou d’une fonction, chaque instruction s’exécute dans l’ordre, de la même façon que la plupart des langages classiques impératifs.
Ce déroulement de contrôle peut toutefois être modifié de trois façons différentes :

- Instructions `if`
- `for` boucles
- `repeat`-boucles `until`

Nous différerons la discussion de ce dernier jusqu’à ce que nous ayons abordé les circuits de [répétition jusqu’à la réussite (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) .
Toutefois, les constructions de workflow de contrôle `if` et `for` se déroulent dans une certaine mesure pour la plupart des langages de programmation classiques.
En particulier, une instruction `if` peut prendre une condition, peut être suivie d’une ou de plusieurs instructions `elif` et peut se terminer par une `else`:

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

De même, `for` boucles indiquent une itération sur une plage d’entiers ou sur les éléments d’un tableau :

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

Important, `for` boucles et les instructions `if` peuvent même être utilisées dans des opérations pour lesquelles des spécialisations sont générées automatiquement. Dans ce cas, le voisin d’une boucle de `for` inverse la direction et prend la voisine de chaque itération.
Cela suit le principe des chaussures et des Socks : Si vous souhaitez annuler la pose sur SOCKS, puis sur des chaussures, vous devez annuler la pose des chaussures, puis annuler l’ajout de Socks.
Il est préférable de ne pas essayer de mettre votre Socks en marche tout en continuant à porter vos chaussures.

## <a name="operations-and-functions-as-first-class-values"></a>Opérations et fonctions comme valeurs de première classe

Une technique critique pour le type de contrôle et la logique classique utilisant des fonctions plutôt que des opérations consiste à utiliser les opérations et les fonctions dans Q # qui sont de *première classe*.
En d’autres termes, il s’agit de chaque valeur de la langue, à son propre droit.
Par exemple, le code suivant est parfaitement valide Q #, si un peu indirect :

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

La valeur de la variable `ourH` dans l’extrait de code ci-dessus est l’opération <xref:microsoft.quantum.intrinsic.h>, de sorte que nous pouvons appeler cette valeur comme n’importe quelle autre opération.
Cela nous permet d’écrire des opérations qui prennent des opérations dans le cadre de leur entrée, formant ainsi des concepts de contrôle d’ordre supérieur.
Par exemple, nous pourrions penser à « squareiser » une opération en l’appliquant deux fois au même qubit cible.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

Dans cet exemple, la `=>` flèche qui apparaît dans le type `(Qubit => Unit)` indique que le champ d’entrée `op` est une opération qui prend comme entrée le type `Qubit` et produit un tuple vide comme sortie.
En outre, nous spécifions les caractéristiques de ce type d’opération, qui contiennent les informations sur les functors pris en charge.
Une opération de type `(Qubit => Unit)` ne prend en charge ni l' `Adjoint` ni le `Controlled` functor. Si vous souhaitez indiquer qu’une opération de ce type doit prendre en charge, par exemple, le `Adjoint` functor, nous devons le déclarer comme étant adjointable. Pour ce faire, utilisez l’annotation `is Adj` au type. De même, `(Qubit => Unit is Ctl)` indique qu’une opération de ce type prend en charge l' `Controlled` functor. Nous étudierons ce point plus en détail lorsque nous aborderons les [types dans Q #] (XREF : Microsoft. Quantum. Language. type-Model) plus généralement.

Pour le moment, nous insistons sur le fait que nous pouvons également retourner des opérations dans le cadre des sorties, de telle sorte que nous puissions isoler certains genres de logique conditionnelle classique comme une fonction classique qui retourne une description d’un programme Quantum sous la forme d’une opération.
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

Cette nouvelle fonction est effectivement une fonction, car si nous l’appelons avec les mêmes valeurs de `hereBit` et `thereBit`, nous obtenons toujours la même opération.
Par conséquent, le décodeur peut être exécuté en toute sécurité au sein d’opérations sans avoir à expliquer comment la logique de décodage interagit avec les définitions des différentes spécialisations d’opérations.
Autrement dit, nous avons isolé la logique classique à l’intérieur d’une fonction, garantissant au compilateur que l’appel de fonction peut être réorganisé avec impunity tant que l’entrée est conservée.

Nous pouvons également traiter les fonctions comme des valeurs de première classe, comme nous le verrons plus en détail lorsque nous aborderons [les types d’opérations et de fonctions](#operations-and-functions-as-first-class-values).

## <a name="partially-applying-operations-and-functions"></a>Application partielle des opérations et des fonctions

Nous pouvons en faire beaucoup plus avec les fonctions qui retournent des opérations à l’aide d’une *application partielle*, dans laquelle nous pouvons fournir une ou plusieurs parties de l’entrée à une fonction ou une opération sans réellement l’appeler. Par exemple, si vous rappelez l’exemple de `ApplyTwice` ci-dessus, nous pouvons indiquer que nous ne voulons pas spécifier, immédiatement, à quel qubit l’opération d’entrée doit s’appliquer :

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

Dans ce cas, la variable locale `twiceOp` contient l’opération partiellement appliquée `ApplyTwice(op, _)`, où des parties de l’entrée qui n’ont pas encore été spécifiées sont indiquées par `_`.
Lorsque nous appelons `twiceOp` dans la ligne suivante, nous passons comme entrée à l’opération partiellement appliquée, toutes les autres parties de l’entrée à l’opération d’origine.
Par conséquent, l’extrait de code ci-dessus est effectivement identique à l’appel de `ApplyTwice(op, target)` directement, économisez pour que nous ayons introduit une nouvelle variable locale qui nous permet de retarder l’appel tout en fournissant certaines parties de l’entrée.

Étant donné qu’une opération partiellement appliquée n’est pas réellement appelée tant que l’intégralité de son entrée n’a pas été fournie, nous pouvons appliquer des opérations en toute sécurité, même à partir de fonctions.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

En principe, la logique classique dans `SquareOperation` peut avoir été bien plus complexe, mais elle est toujours isolée du reste d’une opération par les garanties que le compilateur peut offrir sur les fonctions.
Cette approche sera utilisée dans la bibliothèque standard Q # pour exprimer le workflow de contrôle classique de manière à pouvoir l’utiliser facilement dans des programmes quantiques.
