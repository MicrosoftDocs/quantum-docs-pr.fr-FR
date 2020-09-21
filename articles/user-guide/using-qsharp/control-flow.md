---
title: Workflow de contrôle dans Q#
description: Boucles, conditions, etc.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: 547c57cab67443e8b487bf817eb79fc922b43cdc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833518"
---
# <a name="control-flow-in-no-locq"></a>Workflow de contrôle dans Q#

Au sein d’une opération ou d’une fonction, chaque instruction s’exécute dans l’ordre, de la même façon que d’autres langages classiques impératifs.
Toutefois, vous pouvez modifier le déroulement du contrôle de trois façons distinctes :

* `if` publication
* `for` boucles
* `repeat-until-success` boucles
* conjugués ( `apply-within` instructions)

Les `if` `for` constructions de workflow et de contrôle se poursuivent de manière familière à la plupart des langages de programmation classiques. [`Repeat-until-success`](#repeat-until-success-loop) les boucles et les [conjugués](#conjugations) sont abordés plus loin dans cet article.

Important, les `for` boucles et les `if` instructions peuvent être utilisées dans les opérations pour lesquelles les [spécialisations](xref:microsoft.quantum.guide.operationsfunctions) sont générées automatiquement. Dans ce scénario, le voisint d’une `for` boucle inverse la direction et prend le voisin de chaque itération.
Cette action suit le principe « chaussures-and-Socks » : Si vous souhaitez annuler la pose sur SOCKS, puis sur chaussures, vous devez annuler la pose des chaussures, puis annuler l’introduction sur Socks. 

## <a name="if-else-if-else"></a>If, else-if, sinon

L' `if` instruction prend en charge le traitement conditionnel.
Il se compose du mot clé `if` , d’une expression booléenne entre parenthèses et d’un bloc d’instructions (bloc _Then_ ).
Si vous le souhaitez, un nombre quelconque de clauses Else-If peuvent suivre, chacune comprenant le mot clé `elif` , une expression booléenne entre parenthèses et un bloc d’instructions (le bloc _else-if_ ).
Enfin, l’instruction peut éventuellement se terminer par une clause Else, qui se compose du mot clé `else` suivi d’un autre bloc d’instructions (le bloc _else_ ).

La `if` condition est évaluée, et si elle a la *valeur true*, le bloc *Then* est exécuté.
Si la condition est *false*, la première condition else-if est évaluée ; Si la valeur est true, le bloc *else-if* est exécuté.
Dans le cas contraire, le deuxième bloc Else-If prend la valeur, puis le troisième, et ainsi de suite jusqu’à ce qu’une clause avec une condition true soit rencontrée ou qu’il n’y ait plus aucune clause else-if.
Si la condition *If* d’origine et toutes les clauses Else-If ont la *valeur false*, le bloc *else* est exécuté, s’il est fourni.

Notez que, quel que soit le bloc exécuté, il s’exécute dans sa propre portée.
Les liaisons effectuées à l’intérieur d’un `if` `elif` bloc, ou ne `else` sont pas visibles après la fin du bloc.

Par exemple,

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
or
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a>Boucle for

L' `for` instruction prend en charge l’itération sur une plage d’entiers ou un tableau.
L’instruction se compose du mot clé `for` , suivi d’un symbole ou d’un tuple de symbole, du mot clé et d’une `in` expression de type `Range` ou tableau, tous entre parenthèses et un bloc d’instructions.

Le bloc d’instructions (le corps de la boucle) s’exécute à plusieurs reprises, avec le symbole défini (la variable de boucle) lié à chaque valeur dans la plage ou le tableau.
Notez que si l’expression de plage prend la valeur d’une plage ou d’un tableau vide, le corps ne s’exécute pas du tout.
L’expression est entièrement évaluée avant d’entrer dans la boucle et ne change pas pendant l’exécution de la boucle.

La variable de boucle est liée à chaque entrée dans le corps de la boucle et est détachée à la fin du corps.
La variable de boucle n’est pas liée après la fin de la boucle for.
La liaison de la variable de boucle est immuable et suit les mêmes règles que les autres liaisons de variables. 

Dans ces exemples, `qubits` est un registre de qubits (c’est-à-dire de type `Qubit[]` ). 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

Notez qu’à la fin, nous avons utilisé l’opérateur binaire arithmétique-décalage-gauche, `<<<` . Pour plus d’informations, consultez [expressions numériques](xref:microsoft.quantum.guide.expressions#numeric-expressions).

## <a name="repeat-until-success-loop"></a>Répéter jusqu’à la réussite de la boucle

Le Q# langage permet au workflow de contrôle classique de dépendre des résultats de la mesure de qubits.
Cette fonctionnalité permet, à son tour, d’implémenter des gadgets probabilistes puissants qui peuvent réduire le coût de calcul de l’implémentation des unités.
Voici des exemples de modèles de *répétition jusqu’à réussite* (RUS) dans Q# .
Ces modèles de RUS sont des programmes probabilistes qui ont un coût faible *attendu* en termes de portes élémentaires ; le coût encouru dépend de l’exécution réelle et de l’entrelacement des différentes branches possibles.

Pour faciliter les modèles de répétition jusqu’à réussite (RUS), Q# prend en charge les constructions

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

où `expression` est une expression valide qui correspond à une valeur de type `Bool` .
Le corps de la boucle s’exécute, puis la condition est évaluée.
Si la condition est true, l’instruction est terminée ; dans le cas contraire, la correction s’exécute et l’instruction s’exécute à nouveau, en commençant par le corps de la boucle.

Les trois parties d’une boucle de service de contrôle d’accès (corps, test et correction) sont traitées comme une seule étendue *pour chaque répétition*, de sorte que les symboles liés dans le corps sont disponibles à la fois dans le test et dans la correction.
Toutefois, l’exécution de la correction met fin à l’étendue de l’instruction, de sorte que les liaisons de symboles effectuées pendant le corps ou la correction ne sont pas disponibles dans les répétitions suivantes.

En outre, l' `fixup` instruction est souvent utile, mais pas toujours nécessaire.
Dans les cas où il n’est pas nécessaire, la construction

```qsharp
repeat {
    // do stuff
}
until (expression);
```

est également un modèle de RUS valide.

Pour obtenir plus d’exemples et de détails, consultez la section [exemples de répétition jusqu’à réussite](#repeat-until-success-examples) dans cet article.

> [!TIP]   
> Évitez d’utiliser des boucles de répétition jusqu’à réussite dans les fonctions. Utilisez des boucles *while* pour fournir la fonctionnalité correspondante à l’intérieur des fonctions. 

## <a name="while-loop"></a>Boucle while

Les modèles de répétition jusqu’à réussite ont un connotation très spécifique au quantum. Elles sont largement utilisées dans des classes particulières d’algorithmes Quantum, donc la construction du langage dédié dans Q# . Toutefois, les boucles qui s’arrêtent en fonction d’une condition et dont la longueur d’exécution est donc inconnue au moment de la compilation sont gérées avec une attention particulière dans un Runtime Quantum. Toutefois, leur utilisation dans les fonctions ne pose pas de problème, car ces boucles contiennent uniquement du code qui s’exécute sur du matériel conventionnel (non Quantum). 

Q#, par conséquent, prend en charge l’utilisation de boucles While uniquement dans les fonctions.
Une `while` instruction se compose du mot clé `while` , d’une expression booléenne entre parenthèses et d’un bloc d’instructions.
Le bloc d’instructions (corps de la boucle) s’exécute tant que la condition a la valeur `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="conjugations"></a>Conjugaisons

Contrairement aux bits classiques, la libération de la mémoire Quantum est un peu plus complexe, car la réinitialisation aveugle de qubits peut avoir des effets indésirables sur le calcul restant si les qubits sont toujours pris en compte. Ces effets peuvent être évités en « annulant » les calculs effectués avant la libération de la mémoire. Un modèle courant dans quantum computing est donc le suivant : 

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

Q# prend en charge une instruction de conjugaison qui implémente la transformation précédente. À l’aide de cette instruction, l’opération `ApplyWith` peut être implémentée de la façon suivante :

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
Une telle instruction de conjugaison devient utile si les transformations externes et internes ne sont pas facilement disponibles en tant qu’opérations, mais sont plutôt plus pratiques à décrire par un bloc composé de plusieurs instructions. 

La transformation inverse pour les instructions définies dans le bloc intérieur est générée automatiquement par le compilateur et exécutée après la fin du bloc apply.
Étant donné que toutes les variables mutables utilisées dans le cadre du bloc within ne peuvent pas être reliées dans le bloc Apply, il est garanti que la transformation générée est le voisin du calcul dans le bloc intérieur. 

## <a name="return-statement"></a>Return (instruction)

L’instruction return termine l’exécution d’une opération ou d’une fonction et retourne une valeur à l’appelant.
Il se compose du mot clé `return` , suivi d’une expression du type approprié et d’un point-virgule de fin.

Par exemple,
```qsharp
return 1;
```
or
```qsharp
return (results, qubits);
```

* Un pouvant être appelé qui retourne un tuple vide, `()` , ne requiert pas d’instruction return.
* Pour spécifier une sortie précoce de l’opération ou de la fonction, utilisez `return ();` .
Les callables qui retournent tout autre type requièrent une instruction return finale.
* Il n’y a pas de nombre maximal d’instructions return dans une opération.
Le compilateur peut émettre un avertissement si les instructions suivent une instruction return dans un bloc.

   
## <a name="fail-statement"></a>Fail (instruction)

L’instruction Fail met fin à l’exécution d’une opération et retourne une valeur d’erreur à l’appelant.
Il se compose du mot clé `fail` , suivi d’une chaîne et d’un point-virgule de fin.
L’instruction retourne la chaîne au pilote classique comme message d’erreur.

Il n’existe aucune restriction sur le nombre d’instructions d’échec au sein d’une opération.
Le compilateur peut émettre un avertissement si les instructions suivent une instruction Fail dans un bloc.

Par exemple,

```qsharp
fail $"Impossible state reached";
```
ou, à l’aide de [chaînes interpolées](xref:microsoft.quantum.guide.expressions#interpolated-strings),
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>Exemples de répétition jusqu’à réussite

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>Modèle RUS pour la rotation d’un qubit sur un axe irrationnelle 

Dans un cas d’usage typique, l' Q# opération suivante implémente une rotation autour d’un axe irrationnelle de $ (I + 2i Z)/\sqrt {5} $ sur la sphère Bloch. L’implémentation utilise un modèle de RUS connu :

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a>Boucle de RUS avec une variable mutable dans l’étendue

Cet exemple illustre l’utilisation d’une variable mutable, `finished` , qui se trouve dans l’étendue de la boucle REPEAT-UNTIL-Fixup entière et qui est initialisée avant la boucle et mise à jour à l’étape de correction.

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a>RUS sans `fixup`

Cet exemple montre une boucle de RUS sans l’étape de correction. Le code est un circuit probabiliste qui implémente une porte de rotation importante $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ à l’aide des `H` `T` portes et.
La boucle se termine dans les répétitions de $ \frac {8} {5} $ en moyenne.
Pour plus d’informations, consultez [*répéter jusqu’à la réussite : décomposition non déterministe des unités de qubit de données uniques*](https://arxiv.org/abs/1311.1074) (Paetznick et Svore, 2014).

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a>RUS pour préparer un État Quantum

Enfin, voici un exemple de modèle de RUS pour préparer un État Quantum $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, à partir de l’État $ \ket{+} $.

Les fonctionnalités de programmation notables présentées dans cette opération sont les suivantes :

* Une partie plus complexe `fixup` de la boucle, qui implique des opérations Quantum. 
* L’utilisation d' `AssertMeasurementProbability` instructions pour déterminer la probabilité de mesurer l’État Quantum à certains points spécifiés dans le programme.

Pour plus d’informations sur [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) les [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) opérations et, consultez [test et débogage](xref:microsoft.quantum.guide.testingdebugging).

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

Pour plus d’informations, consultez [exemple de test unitaire fourni avec la bibliothèque standard](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

## <a name="next-steps"></a>Étapes suivantes

En savoir plus sur le [test et le débogage](xref:microsoft.quantum.guide.testingdebugging) dans Q# .
