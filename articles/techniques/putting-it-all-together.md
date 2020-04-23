---
title: Techniques Q - Mettre tout cela ensemble
description: Promenez-vous dans le cadre d’un programme de base de QMD qui démontre la téléportation quantique.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030563"
---
# <a name="putting-it-all-together-teleportation"></a>Mettre tout cela ensemble: Téléportation #
Revenons à l’exemple du circuit de téléportation défini dans [Les circuits quantiques](xref:microsoft.quantum.concepts.circuits). Nous allons nous en servir pour illustrer les concepts que nous avons appris jusqu’à présent. Une explication de la téléportation quantique est fournie ci-dessous pour ceux qui ne sont pas familiers avec la théorie, suivie d’une procédure pas à pas de l’implémentation du code dans Q. 

## <a name="quantum-teleportation-theory"></a>Téléportation quantique : Théorie
La téléportation quantique est une technique pour envoyer un état quantique inconnu (que nous appellerons le «__message__») d’un qubit à un endroit à un qubit dans un autre endroit (nous nous référerons à ces qubits comme «__ici__» et « là »__respectivement).__ Nous pouvons représenter notre __message__ comme un vecteur en utilisant la notation Dirac: 

$$ 'ket 'psi' 'alpha’ket{0} 'beta 'ket{1} $$

L’état du __message__ qubit est inconnu pour nous car nous ne connaissons pas les valeurs de $alpha$ et $beta$.

### <a name="step-1-create-an-entangled-state"></a>Étape 1 : Créer un état empêtré
Afin d’envoyer le __message__ que nous avons besoin pour le qubit __ici__ pour être empêtré avec le qubit __là-__. Ceci est réalisé en appliquant une porte Hadamard, suivie d’une porte CNOT. Regardons les maths derrière ces opérations de porte.

Nous allons commencer avec les qubits __ici__ et{0} __là__ à la fois dans l’état de $ket $. Après avoir enchevêté ces qubits, ils sont dans l’état:

$$ 'ket 'phi{1}'''''''''''' 'frac 'sqrt'''''{2}(ket{00} ' '{11}' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '

### <a name="step-2-send-the-message"></a>Étape 2 : Envoyer le message
Pour envoyer le __message,__ nous appliquons d’abord une porte CNOT avec le __qubit message__ et __ici__ qubit comme entrées (le __qubit message__ étant le contrôle et le qubit __ici__ étant le qubit cible, dans ce cas). Cet état d’entrée peut être écrit :

$$ 'ket 'psi 'ket{0} 'phi '''''''''''''''' (alpha’ket 'beta’ket{00} {11}{1}')(frac{1}'sqrt''''''ket{2}'') $$ $$

Cela s’étend à :

$$ 'ket 'psi’ket 'phi{2}'''''''''''''''alpha’sqrt ''ket{000} 'frac 'alpha 'sqrt{2}''ket{011} ''frac{2}'beta 'sqrt ''sqrt{100} ''frac{2}'bêta''{111}

Pour rappel, la porte CNOT retourne le qubit cible lorsque le qubit de contrôle est 1. Ainsi, par exemple, une entrée{000}de $ket $ n’entraînera aucun changement que le premier qubit (le contrôle) est 0. Cependant, prenez un cas où le premier qubit est 1{100}- par exemple une entrée de $ket $. Dans ce cas, la sortie{110}est $ket $ que le deuxième qubit (la cible) est renversé par la porte CNOT.

Examinons maintenant notre sortie une fois que la porte CNOT a agi sur nos commentaires ci-dessus. Le résultat est le suivant :

$$ 'frac’alpha 'sqrt{2}'{000} 'sqrt ' 'ket 'frac{2}'alpha 'sqrt ''sqrt{011} ''ket{2}'frac{110} 'beta 'sqrt 'sqrt{2}''ket{101} 'frac 'bêta 'sqrt ''ket $$

L’étape suivante pour envoyer le __message__ est d’appliquer une porte Hadamard au __message__ qubit (c’est le premier qubit de chaque terme). 

Pour rappel, la porte Hadamard fait ce qui suit :

Entrée | Output
---------------------------| ---------------------------------------------------------------
$ket{0}$  | $-frac{1}'sqrt{2}'(ket{0} ' 'ket 'ket{1})$
$ket{1}$  | $-frac{1}'sqrt{2}'(ket{0} - 'ket{1})$

Si nous appliquons la porte Hadamard au premier qubit de chaque terme de notre sortie ci-dessus, nous obtenons le résultat suivant :

{2}$$ 'frac’alpha’sqrt '(frac{1}'sqrt '('sqrt{2}{0} ''''ket 'ket{1}{00} ')'ket 'frac{2}'alpha’sqrt{1}'(frac 'sqrt''('frac 'sqrt''''''ket{2}{0} ''ket{1}{11} ''' 'frac’beta’sqrt{2}'(frac{1}'sqrt'{2}('ket{0} {1}' ' ' ' ' ' ' ' '{10} ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '{2}' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '{1}{2}{0} {1}{01}

Notez que chaque terme a{1}deux facteurs{2}de $'frac 'sqrt '$. Nous pouvons multiplier ces en donnant le résultat suivant:

$$ 'frac’alpha'{2}{0} ('ket{1}'ket ''ket{00} ''frac’alpha'{2}('ket{0} {1}'ket{11} ''ket{2}''ket ''frac’beta' ('ket{0} {1}' ' ' ' '{0} {1}{01} {10} {2}' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '

Le facteur de{1}{2}10 $et de l’est est commun à chaque terme, de sorte que nous pouvons maintenant le prendre en dehors des parenthèses :

$$ 'frac{1}{2}'big['alpha''ket{0} 'ket{1}''ket ''ket{00} 'alpha''ket{11} {0} {1}{10} {0} {1}{01}{0} 'ket 'ket{1}'ket 'ket ' 'beta''ket ' 'ket 'ket 'beta’ket ' 'ket 'ket 'big' $$

Nous pouvons alors multiplier les parenthèses pour chaque terme donnant :

{1}{2}$$ 'frac 'big['alpha’ket{000} 'alpha’ket 'alpha’ket{100} 'alpha’ket{011} 'alpha’ket{111} 'bêta’ket{010} ' ' ' ' ' ' ' ' ' '{110} ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '{001} {101}' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '

### <a name="step-3-measure-the-result"></a>Étape 3 : Mesurer le résultat

En raison __d’ici__ et __là__ étant empêtré, toute mesure sur __ici__ affectera l’état de __là__. Si nous mesurons le premier et le deuxième qubit __(message__ et __ici__) nous pouvons apprendre dans quel état __il ya,__ en raison de cette propriété de l’enchevêtrement. 

* Si nous mesurons et obtenons un résultat 00, la superposition s’effondre, ne laissant que des termes compatibles avec ce résultat. C’est $'alpha’ket{000} 'beta’ket{001}$. Cela peut être refactorisé à{00}$'ket{0} (alpha’ket{1}'beta 'ket )$. Par conséquent, si nous mesurons le premier et le deuxième qubit __there__à 00, nous savons que{0} le troisième qubit, là , est dans l’état de $(alpha 'ket 'beta 'ket{1})$.
* Si nous mesurons et obtenons un résultat 01, la superposition s’effondre, ne laissant que des termes compatibles avec ce résultat. C’est $'alpha’ket{011} 'beta’ket{010}$. Cela peut être refactorisé à{01}$'ket{1} (alpha’ket{0}'beta 'ket )$. Par conséquent, si nous mesurons le premier et le deuxième qubit pour être 01, nous savons{1} que le troisième{0}qubit, __il__, est dans l’état de $(alpha 'ket 'beta 'ket )$.
* Si nous mesurons et obtenons un résultat 10, la superposition s’effondre, ne laissant que des termes compatibles avec ce résultat. C’est $'alpha’ket{100} -beta’ket{101}$. Cela peut être refactorisé à{10}$'ket{0} (alpha 'ket{1}-'beta 'ket )$. Par conséquent, si nous mesurons le premier et le deuxième qubit __there__à 10, nous savons que{0} le troisième qubit, il , est dans l’état de $(alpha 'ket - 'beta 'ket{1})$.
* Si nous mesurons et obtenons un résultat 11, la superposition s’effondre, ne laissant que des termes compatibles avec ce résultat. C’est $'alpha’ket{111} -beta’ket{110}$. Cela peut être refactorisé à{11}$'ket{1} (alpha 'ket{0}-'beta 'ket )$. Par conséquent, si nous mesurons le premier et le deuxième qubit pour être 11, nous savons{1} que le troisième{0}qubit, __il__, est dans l’état de $(alpha 'ket - 'beta 'ket )$.

### <a name="step-4-interpret-the-result"></a>Étape 4 : Interpréter le résultat

Pour rappel, le __message__ original que nous voulions envoyer était :

$$ 'ket 'psi' 'alpha’ket{0} 'beta 'ket{1} $$

Nous devons mettre le qubit __là__ dans cet état, de sorte que l’état reçu est celui qui était prévu. 

* Si nous avons mesuré et obtenu un résultat de 00, puis le troisième qubit, __il__, est dans l’état de $(alpha 'ket{0} 'beta 'ket{1})$. Comme il s’agit du __message__prévu, aucune modification n’est nécessaire.
* Si nous avons mesuré et obtenu un résultat de 01, puis le troisième qubit, __il__, est dans l’état de $(alpha 'ket{1} 'beta 'ket{0})$. Cela diffère du __message__prévu, mais l’application d’une porte PAS{0} nous donne l’état désiré $(alpha 'ket 'beta 'ket{1})$.
* Si nous avons mesuré et obtenu un résultat de 10, puis le troisième qubit, __il__, est dans l’état de $(alpha -ket{0} - bêta -ket{1})$. Cela diffère du __message__prévu, mais l’application d’une porte Z{0} nous donne l’état désiré $(alpha 'ket 'beta 'ket{1})$.
* Si nous avons mesuré et obtenu un résultat de 11, puis le troisième qubit, __il__, est dans l’état de $(alpha -ket{1} - bêta -ket{0})$. Cela diffère du __message__prévu, mais l’application d’une porte PAS suivie d’une{0} porte Z nous{1}donne l’état désiré $(alpha -ket 'beta 'ket )$.

Pour résumer, si nous mesurons et le premier qubit est de 1, une porte Z est appliquée. Si nous mesurons et le deuxième qubit est 1, une porte PAS est appliquée.

### <a name="summary"></a>Résumé
Ci-dessous est un circuit quantique de livre de texte qui implémente la téléportation. En se déplaçant de gauche à droite, vous pouvez voir :
- Étape 1 : Enchevêtrement __ici__ et __là__ en appliquant une porte Hadamard et une porte CNOT.
- Étape 2 : Envoi du __message__ à l’aide d’une porte CNOT et d’une porte Hadamard.
- Étape 3 : Prendre une mesure des premier et deuxième qubits, __du message__ et __ici.__
- Étape 4 : Appliquer une porte NON ou une porte Z, selon le résultat de la mesure à l’étape 3.

!['Teleport (msg : Qubit, there : Qubit) : Unit'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Téléportation quantique : Code

Nous avons notre circuit pour la téléportation quantique :

!['Teleport (msg : Qubit, there : Qubit) : Unit'](~/media/teleportation.svg)

Nous pouvons maintenant traduire chacune des étapes de ce circuit quantique en Q.

### <a name="step-0-definition"></a>Étape 0 : Définition
Lorsque nous effectuons la téléportation, nous devons connaître le __message__ que nous voulons envoyer, et où nous voulons l’envoyer __(là).__ Pour cette raison, nous commençons par définir une nouvelle opération Teleport `msg` `there`qui est donné deux qubits comme arguments, et:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Nous devons également allouer `here` un qubit `using` que nous réalisons avec un bloc:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Étape 1 : Créer un état empêtré
Nous pouvons ensuite créer la `here` `there` paire enchevêtrée entre et en utilisant le et @"microsoft.quantum.intrinsic.h" @"microsoft.quantum.intrinsic.cnot" les opérations:

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Étape 2 : Envoyer le message
Nous utilisons ensuite les prochaines portes de $-operatorname-CNOT$ et $H$ pour déplacer notre message qubit:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Étape 3 & 4 : Mesurer et interpréter le résultat
Enfin, nous @"microsoft.quantum.intrinsic.m" utilisons pour effectuer les mesures et effectuer les opérations de porte `if` nécessaires pour obtenir l’état souhaité, comme indiqué par les déclarations:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a>Étape 5 : Redémarrage du registre qubit

À la fin de chaque opération Q, nous avons besoin de{0}laisser les qubits dans l’état $ket $. Nous pouvons @"microsoft.quantum.intrinsic.reset" utiliser pour redémarrer tous les qubits à l’état zéro et cela finira notre opération.

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


