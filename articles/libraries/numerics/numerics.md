---
title: Utilisation de la bibliothèque de valeurs numériques | Microsoft Docs
description: Utilisation de la bibliothèque de valeurs numériques
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 332781a4356015461426ee7640fd931a41450367
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184608"
---
# <a name="using-the-numerics-library"></a>Utilisation de la bibliothèque de valeurs numériques

## <a name="overview"></a>Présentation

La bibliothèque de valeurs numériques est constituée de trois composants.

1. **Arithmétique d’entiers de base avec additions** d’entiers et comparateurs
1. **Fonctionnalités entières de haut niveau** qui s’appuient sur les fonctionnalités de base. Il comprend la multiplication, la Division, l’inversion, etc.  pour les entiers signés et non signés.
1. **Fonctionnalité arithmétique à virgule fixe** avec initialisation à virgule fixe, addition, multiplication, réciproque, évaluation polynomiale et mesure.

Vous pouvez accéder à tous ces composants à l’aide d’une seule instruction `open` :
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>Types

La bibliothèque de valeurs numériques prend en charge les types suivants :

1. **`LittleEndian`** : tableau qubit `qArr : Qubit[]` qui représente un entier où `qArr[0]` indique le bit le moins significatif.
1. **`SignedLittleEndian`** : identique à `LittleEndian` sauf qu’il représente un entier signé stocké dans le complément à deux.
1. **`FixedPoint`** : représente un nombre réel constitué d’un tableau qubit `qArr2 : Qubit[]` et d’une position de point binaire `pos`, qui compte le nombre de chiffres binaires à gauche du point binaire. `qArr2` est stocké de la même façon que `SignedLittleEndian`.

## <a name="operations"></a>Operations

Pour chacun des trois types ci-dessus, diverses opérations sont disponibles :

1. **`LittleEndian`**
    - Addition
    - Comparaison
    - Multiplication
    - Mise au carré
    - Division (avec reste)

1. **`SignedLittleEndian`**
    - Addition
    - Comparaison
    - Complément modulo de la version 2
    - Multiplication
    - Mise au carré

1. **`FixedPoint`**
    - Préparation/initialisation à des valeurs classiques
    - Addition (constante classique ou autre point fixe quantique)
    - Comparaison
    - Multiplication
    - Mise au carré
    - Évaluation polynomiale avec spécialisation pour les fonctions paires et impaires
    - Réciproque (1/x)
    - Mesure (double classique)

Pour plus d’informations et pour obtenir une documentation détaillée sur chacune de ces opérations, consultez les documents de référence sur la bibliothèque Q # sur [docs.Microsoft.com](https://docs.microsoft.com/en-us/quantum)

## <a name="sample-integer-addition"></a>Exemple : ajout d’un entier

À titre d’exemple, considérez l’opération $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $ autrement dit, une opération qui accepte un entier n-qubit $x $ et un n-ou (n + 1)-qubit inscrire $y $ comme entrée, le dernier mappé à la somme $ (x + y) $. Notez que la somme est calculée modulo $2 ^ n $ si $y $ est stocké dans un registre $n $ bits.

À l’aide du kit de développement quantique, cette opération peut être appliquée comme suit :
```qsharp
operation MyAdditionTest (xInt : Int, yInt : Int, n : Int) : Unit
{
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xInt, x); // initialize values
        ApplyXorInPlace(yInt, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>Exemple : évaluation des fonctions Smooth

Pour évaluer des fonctions lissées telles que $ \sin (x) $ sur un ordinateur Quantum, où $x $ est un nombre `FixedPoint` Quantum, la bibliothèque de valeurs de kit de développement quantum fournit les `EvaluatePolynomialFxP` et les `Evaluate[Even/Odd]PolynomialFxP`d’opérations.

La première `EvaluatePolynomialFxP`permet d’évaluer un polynomial au format $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $ où $d $ indique le *degré*. Pour ce faire, il suffit d’utiliser les coefficients polynomiaux `[a_0,..., a_d]` (de type `Double[]`), le `x : FixedPoint` d’entrée et le `y : FixedPoint` de sortie (initialement zéro) :
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
Le résultat, $P (x) = 1 + 2x $, est stocké dans `yFxP`.

Le deuxième, `EvaluateEvenPolynomialFxP`et le troisième, `EvaluateOddPolynomialFxP`sont des spécialisations pour les cas de fonctions paires et impaires, respectivement. Autrement dit, pour une fonction pair/impair $f (x) $ et $ $ P_ {même} (x) = a_0 + A_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2J}, $ $ $f (x) $ est bien approximatif en $P _ {même} (x) $ ou $P _ {impaire} (x) : = x\cdot P_ {même} (x) $ conséquence.
Dans Q #, ces deux cas peuvent être gérés comme suit :
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
qui évalue $P _ {même} (x) = 1 + 2x ^ 2 $, et
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
qui évalue $P _ {impair} (x) = x + 2x ^ 3 $.

## <a name="more-samples"></a>Autres exemples

Vous trouverez d’autres exemples dans le [référentiel d’exemples principal](https://github.com/Microsoft/Quantum).

Pour commencer, clonez le référentiel et ouvrez le sous-dossier `Numerics` :

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

Ensuite, `cd` dans l’un des exemples de dossiers et exécutez l’exemple via

```bash
dotnet run
```
