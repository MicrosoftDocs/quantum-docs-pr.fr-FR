---
title: 'Workflow de contrôle dans Q #'
description: Boucles, conditions, etc.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 1f1b641563fe35879abeee32b4f0aeeb7001b1a0
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84326538"
---
# <a name="control-flow-in-q"></a>Workflow de contrôle dans Q #

Au sein d’une opération ou d’une fonction, chaque instruction s’exécute dans l’ordre, de la même façon que la plupart des langages classiques impératifs.
Ce déroulement de contrôle peut toutefois être modifié de trois façons différentes :

- `if`publication
- `for`boucles
- `repeat`-`until`boucles

Nous différerons la discussion de ce dernier [pour aller plus loin.](#repeat-until-success-loop)
`if` `for` Toutefois, les constructions de contrôle et de contrôle de workflow se déroulent de façon familière à la plupart des langages de programmation classiques.

Important, les `for` boucles et les `if` instructions peuvent même être utilisées dans les opérations pour lesquelles des spécialisations sont générées automatiquement. Dans ce cas, le voisint d’une `for` boucle inverse la direction et prend la voisine de chaque itération.
Cela suit le principe des chaussures et des Socks : Si vous souhaitez annuler la pose sur SOCKS, puis sur des chaussures, vous devez annuler la pose des chaussures, puis annuler l’ajout de Socks.
Il est préférable de ne pas essayer de mettre votre Socks en marche tout en continuant à porter vos chaussures.

## <a name="if-else-if-else"></a>If, else-if, sinon

L' `if` instruction prend en charge l’exécution conditionnelle.
Il se compose du mot clé `if` , d’une parenthèse ouvrante `(` , d’une expression booléenne, d’une parenthèse fermante `)` et d’un bloc d’instructions (le bloc _Then_ ).
Il peut être suivi de n’importe quel nombre de clauses Else-If, chacune comprenant le mot clé `elif` , une parenthèse ouvrante `(` , une expression booléenne, une parenthèse fermante `)` et un bloc d’instructions (le bloc _else-if_ ).
Enfin, l’instruction peut éventuellement se terminer par une clause Else, qui se compose du mot clé `else` suivi d’un autre bloc d’instructions (le bloc _else_ ).

La `if` condition est évaluée, et si elle a la valeur true, le bloc Then est exécuté.
Si la condition est false, la première condition else-if est évaluée ; Si la valeur est true, le bloc Else-If est exécuté.
Dans le cas contraire, le deuxième bloc Else-If est testé, puis le troisième, et ainsi de suite jusqu’à ce qu’une clause avec une condition true soit rencontrée ou qu’il n’y ait plus aucune clause else-if.
Si la condition if d’origine et toutes les clauses Else-If ont la valeur false, le bloc Else est exécuté s’il en a été fourni.

Notez que le bloc qui est exécuté est exécuté dans sa propre portée.
Les liaisons effectuées à l’intérieur d’un `if` `elif` bloc, ou ne `else` sont pas visibles après sa fin.

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

## <a name="for-loop"></a>Boucle For

L' `for` instruction prend en charge l’itération sur une plage d’entiers ou sur un tableau.
L’instruction se compose du mot clé `for` , d’une parenthèse ouvrante `(` , suivi d’un symbole ou d’un tuple de symbole, du mot clé `in` , d’une expression de type `Range` ou tableau, d’une parenthèse fermante `)` et d’un bloc d’instructions.

Le bloc d’instructions (corps de la boucle) est exécuté à plusieurs reprises, avec les symboles définis (la ou les variables de boucle) liés à chaque valeur dans la plage ou le tableau.
Notez que si l’expression de plage a la valeur d’une plage ou d’un tableau vide, le corps ne sera pas exécuté.
L’expression est entièrement évaluée avant d’entrer dans la boucle et ne change pas pendant l’exécution de la boucle.

La variable de boucle est liée à chaque entrée dans le corps de la boucle et est détachée à la fin du corps.
En particulier, la variable de boucle n’est pas liée après la fin de la boucle for.
La liaison du ou des symboles déclarés est immuable et suit les mêmes règles que les autres liaisons de variables. 

Pour certains exemples, supposons qu' `qubits` il s’agit d’un registre de qubits (c’est-à-dire de type `Qubit[]` ). 

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
Notez que, à la fin, nous avons utilisé l’opérateur binaire arithmétique-décalage-gauche, `<<<` , dont les détails sont disponibles aux [expressions numériques](xref:microsoft.quantum.guide.expressions#numeric-expressions)


## <a name="repeat-until-success-loop"></a>Répéter jusqu’à la réussite de la boucle

Le langage Q # permet au workflow de contrôle classique de dépendre des résultats de la mesure des qubits.
Cette fonctionnalité permet à son tour d’implémenter des gadgets probabilistes puissants qui peuvent réduire le coût de calcul de l’implémentation des unités.
Par exemple, il est facile d’implémenter des modèles de *répétition jusqu’à réussite* (RUS) dans Q #.
Ces modèles de RUS sont des programmes probabilistes qui ont un coût faible *attendu* en termes de portes élémentaires, mais pour lesquels le coût réel dépend d’une exécution réelle et d’un entrelacement réel de diverses branches possibles.

Pour faciliter les modèles de répétition jusqu’à réussite (RUS), Q # prend en charge les constructions

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
Le corps de la boucle est exécuté, puis la condition est évaluée.
Si la condition est true, l’instruction est terminée ; dans le cas contraire, la correction est exécutée et l’instruction est réexécutée en commençant par le corps de la boucle.

Les trois parties d’une boucle REPEAT/UNTIL (le corps, le test et la correction) sont traitées comme une seule étendue *pour chaque répétition*, de sorte que les symboles qui sont liés dans le corps sont disponibles dans le test et dans la correction.
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

En bas de cette page, nous présentons des [exemples de boucles de RUS](#repeat-until-success-examples).

> [!TIP]   
> Évitez d’utiliser des boucles de répétition jusqu’à réussite dans les fonctions. Les fonctionnalités correspondantes sont fournies par les boucles While dans les fonctions. 

## <a name="while-loop"></a>Boucle while

Les modèles de répétition jusqu’à réussite ont un connotation très spécifique au quantum. Elles sont largement utilisées dans des classes particulières d’algorithmes Quantum, donc la construction du langage dédié dans Q #. Toutefois, les boucles qui s’arrêtent en fonction d’une condition et dont la longueur d’exécution est donc inconnue au moment de la compilation doivent être gérées avec une attention particulière dans un Runtime Quantum. Leur utilisation dans les fonctions en revanche pose un problème, car celles-ci contiennent uniquement du code qui sera exécuté sur du matériel conventionnel (non Quantum). 

Q # prend donc en charge l’utilisation de boucles While uniquement dans les fonctions. Une `while` instruction se compose du mot clé `while` , d’une parenthèse ouvrante `(` , d’une condition (c’est-à-dire une expression booléenne), d’une parenthèse fermante `)` et d’un bloc d’instructions.
Le bloc d’instructions (corps de la boucle) est exécuté tant que la condition a la valeur `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a>Return (instruction)

L’instruction return termine l’exécution d’une opération ou d’une fonction et retourne une valeur à l’appelant.
Il se compose du mot clé `return` , suivi d’une expression du type approprié et d’un point-virgule de fin.

Un pouvant être appelé qui retourne un tuple vide, `()` , ne requiert pas d’instruction return.
Si vous souhaitez une sortie précoce, `return ()` peut être utilisé dans ce cas.
Les callables qui retournent tout autre type requièrent une instruction return finale.

Il n’y a pas de nombre maximal d’instructions return dans une opération.
Le compilateur peut émettre un avertissement si les instructions suivent une instruction return dans un bloc.

Par exemple,
```qsharp
return 1;
```
or
```qsharp
return ();
```
or
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a>Fail (instruction)

L’instruction Fail termine l’exécution d’une opération et retourne une valeur d’erreur à l’appelant.
Il se compose du mot clé `fail` , suivi d’une chaîne et d’un point-virgule de fin.
La chaîne est retournée au pilote classique comme message d’erreur.

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

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>Modèle RUS pour la rotation d’un seul qubit sur un axe irrationnelle 

Dans un cas d’usage courant, l’opération Q # suivante implémente une rotation autour d’un axe irrationnelle de $ (I + 2i Z)/\sqrt {5} $ sur la sphère Bloch. Pour ce faire, utilisez un modèle de RUS connu :

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a>Boucle de RUS avec variable mutable dans l’étendue

Cet exemple montre l’utilisation d’une variable mutable `finished` qui est dans la portée de la boucle REPEAT-UNTIL-Fixup entière et qui est initialisée avant la boucle et mise à jour à l’étape de correction.

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

### <a name="rus-without-fixup"></a>RUS sans`fixup`

Par exemple, le code suivant est un circuit probabiliste qui implémente une porte de rotation importante $V _3 = (\boldone + 2 i Z)/\sqrt {5} $ à l’aide des `H` `T` portes et.
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

Enfin, nous présentons un exemple de modèle de RUS pour préparer un État Quantum $ \frac {1} {\sqrt {3} } \left (\sqrt {2} \ket {0} + \ket {1} \right) $, à partir de l’État $ \ket{+} $.
Consultez également l' [exemple de test unitaire fourni avec la bibliothèque standard](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
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

Les fonctionnalités de programmation notables présentées dans cette opération sont une partie plus complexe `fixup` de la boucle, qui implique des opérations de Quantum et l’utilisation d' `AssertProb` instructions pour déterminer la probabilité de mesurer l’État Quantum à certains points spécifiés dans le programme.
Pour plus d’informations sur les opérations et, consultez également [test et débogage](xref:microsoft.quantum.guide.testingdebugging) [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) .


## <a name="next-steps"></a>Étapes suivantes

En savoir plus sur le [test et le débogage](xref:microsoft.quantum.guide.testingdebugging) dans Q #.