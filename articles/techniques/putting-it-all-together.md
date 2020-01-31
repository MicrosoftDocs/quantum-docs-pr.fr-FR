---
title: 'Ensemble-Q # techniques | Microsoft Docs'
description: 'Ensemble-Q # techniques'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3605826da159757d4b321dbf4ec6acd7f4e6be05
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820162"
---
# <a name="putting-it-all-together-teleportation"></a>Ensemble : téléportage #
Revenons à l’exemple du circuit de téléportage défini dans [circuits quantiques](xref:microsoft.quantum.concepts.circuits). Nous allons l’utiliser pour illustrer les concepts que nous avons appris jusqu’à présent. Une explication de la téléportage quantique est fournie ci-dessous pour ceux qui ne sont pas familiarisés avec la théorie, suivis d’une procédure pas à pas de l’implémentation de code dans Q #. 

## <a name="quantum-teleportation-theory"></a>Teleportage quantique : théorie
La téléportage quantique est une technique permettant d’envoyer un État Quantum inconnu (que nous appelons «__message__») à partir d’un qubit dans un emplacement vers un qubit dans un autre emplacement (nous faisons référence à ces qubits__comme suit,__ respectivement). Nous pouvons représenter notre __message__ sous forme de vecteur à l’aide de la notation Dirac : 

$ $ \ket{\Psi} = \alpha\ket{0} + \beta\ket{1} $ $

L’état du __message__ qubit est inconnu, car nous ne connaissons pas les valeurs de $ \alpha $ et $ \beta $.

### <a name="step-1-create-an-entangled-state"></a>Étape 1 : créer un État enchevêtré
Afin d’envoyer le __message__ dont nous avons besoin pour que le qubit soit associé à __l’qubit__ __ici__ . Cela est possible en appliquant une porte Hadarmard, suivie d’une porte CNOTIN. Examinons les mathématiques qui se trouvent derrière ces opérations de la porte.

Nous allons commencer par le qubits __ici__ et __dans__ l’État $ \ket{0}$. Une fois ces qubits, ils sont dans l’État :

$ $ \ket{\Phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $

### <a name="step-2-send-the-message"></a>Étape 2 : envoyer le message
Pour envoyer le __message__ , nous appliquons d’abord une porte cnotin avec le __message__ qubit et __ici__ qubit en tant qu’entrées (le __message__ qubit est le contrôle et le __ici__ qubit est le qubit cible, dans cette instance). Cet état d’entrée peut être écrit :

$ $ \ket{\Psi}\ket{\Phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $

Cela se développe en :

$ $ \ket{\Psi}\ket{\Phi ^ +} = \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $

En guise de rappel, la porte CNOTIN retourne le qubit cible lorsque le qubit de contrôle est 1. Ainsi, par exemple, une entrée de $ \ket{000}$ n’entraîne aucune modification, car le premier qubit (le contrôle) est 0. Toutefois, prenez le cas où le premier qubit est 1, par exemple une entrée de $ \ket{100}$. Dans ce cas, la sortie est $ \ket{110}$, car la deuxième qubit (la cible) est retournée par la porte CNOTIN.

Nous allons maintenant examiner notre sortie une fois que la porte CNOTIN a agi sur notre entrée ci-dessus. Le résultat est le suivant :

$ $ \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $

L’étape suivante pour envoyer le __message__ consiste à appliquer une porte hadarmard au __message__ qubit (il s’agit du premier qubit de chaque terme). 

En guise de rappel, la porte Hadarmard effectue les opérations suivantes :

Entrée | Output
---------------------------| ---------------------------------------------------------------
$ \ket{0}$  | $ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $
$ \ket{1}$  | $ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $

Si nous appliquons la porte Hadarmard au premier qubit de chaque terme de la sortie ci-dessus, nous obtenons le résultat suivant :

$ $ \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $

Notez que chaque terme a des facteurs $2 \frac{1}{\sqrt{2}} $. Nous pouvons multiplier ces valeurs pour obtenir le résultat suivant :

$ $ \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $

Le{1}$ \frac {2}$ Factor est commun à chaque terme afin que nous puissions le prendre en dehors des crochets :

$ $ \frac{1}{2}\big [\alpha (\ket{0} + \ket{1}) \ket{00} + \alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\big] $ $

Nous pouvons ensuite multiplier les crochets pour chaque terme en donnant :

$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\big] $ $

### <a name="step-3-measure-the-result"></a>Étape 3 : mesurer le résultat

En raison __de cette situation et de__ l’enchevêtrement, toute mesure sur __cet__ __objet affecte__ l' __État de cet emplacement.__ Si nous mesurons le premier et le second qubit (__message__ et __ici__), nous pouvons découvrir l’État dans lequel __il__ se trouve, en raison de cette propriété d’enchevêtrement. 

* Si nous mesurons et obtenons le résultat 00, la superposition se réduit, en laissant uniquement les termes cohérents avec ce résultat. C’est $ \alpha\ket{000} + \beta\ket{001}$. Cela peut être refactorisé en $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $. Par conséquent, si nous mesurons le premier et le second qubit à 00, nous savons que le troisième qubit, __ici__, est dans l’État $ (\alpha\ket{0} + \beta\ket{1}) $.
* Si nous mesurons et obtenons le résultat 01, la superposition se réduit, en laissant uniquement les termes cohérents avec ce résultat. C’est $ \alpha\ket{011} + \beta\ket{010}$. Cela peut être refactorisé en $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $. Par conséquent, si nous mesurons le premier et le second qubit à 01, nous savons que le troisième qubit, __ici__, est dans l’État $ (\alpha\ket{1} + \beta\ket{0}) $.
* Si nous mesurons et obtenons le résultat 10, la superposition se réduit, en laissant uniquement les termes cohérents avec ce résultat. Il s’agit de $ \alpha\ket{100}-\beta\ket{101}$. Cela peut être refactorisé en $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $. Par conséquent, si nous mesurons le premier et le second qubit à 10, nous savons que le troisième qubit, à __savoir, est__dans l’État $ (\alpha\ket{0}-\beta\ket{1}) $.
* Si nous mesurons et obtenons le résultat 11, la superposition se réduit, en laissant uniquement les termes cohérents avec ce résultat. Il s’agit de $ \alpha\ket{111}-\beta\ket{110}$. Cela peut être refactorisé en $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $. Par conséquent, si nous mesurons le premier et le second qubit sur 11, nous savons que le troisième qubit, à __savoir, est__dans l’État $ (\alpha\ket{1}-\beta\ket{0}) $.

### <a name="step-4-interpret-the-result"></a>Étape 4 : interpréter le résultat

En guise de rappel, le __message__ d’origine que nous souhaitions envoyer était :

$ $ \ket{\Psi} = \alpha\ket{0} + \beta\ket{1} $ $

Nous devons faire en sorte qu' __il__ qubit cet État, afin que l’état reçu soit celui prévu. 

* Si nous avons mesuré et obtenu le résultat 00, alors le troisième __qubit, qui__se trouve dans l’État $ (\alpha\ket{0} + \beta\ket{1}) $. Comme il s’agit du __message__souhaité, aucune modification n’est requise.
* Si nous avons mesuré et obtenu un résultat de 01, alors le troisième qubit, __il__se trouve dans l’État $ (\alpha\ket{1} + \beta\ket{0}) $. Cela diffère du __message__prévu, mais l’application d’une porte non nous donne l’état souhaité $ (\alpha\ket{0} + \beta\ket{1}) $.
* Si nous avons mesuré et obtenu un résultat de 10, alors le troisième qubit __, qui__se trouve dans l’État $ (\alpha\ket{0}-\beta\ket{1}) $. Cela diffère du __message__prévu, mais l’application d’une porte Z nous donne l’état souhaité $ (\alpha\ket{0} + \beta\ket{1}) $.
* Si nous avons mesuré et obtenu le résultat __11, alors__le troisième qubit est dans l’État $ (\alpha\ket{1}-\beta\ket{0}) $. Cela diffère du __message__prévu, mais l’application d’une porte non suivie d’une porte Z nous donne l’état souhaité $ (\alpha\ket{0} + \beta\ket{1}) $.

Pour résumer, si nous mesurons et que le premier qubit est 1, une porte Z est appliquée. Si nous mesurons et que le second qubit est 1, une porte non est appliquée.

### <a name="summary"></a>Résumé
Vous trouverez ci-dessous un circuit de quantum de livre de texte qui implémente la téléportation. En vous déplaçant de gauche à droite, vous pouvez voir :
- Étape 1 : __application de la__ porte __hadarmard et de__ la porte cnotin.
- Étape 2 : envoi du __message__ à l’aide d’une porte cnotin et d’une porte hadarmard.
- Étape 3 : exécution d’une mesure du premier et du deuxième qubits, du __message__ et __ici__.
- Étape 4 : application d’une porte non ou d’une porte Z, en fonction du résultat de la mesure à l’étape 3.

![' (MSG : qubit, IT : qubit) : unit'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Teleportage quantique : code

Nous disposons de notre circuit pour la téléportage quantique :

![' (MSG : qubit, IT : qubit) : unit'](~/media/teleportation.svg)

Nous pouvons maintenant traduire chacune des étapes de ce circuit Quantum en Q #.

### <a name="step-0-definition"></a>Étape 0 : définition
Lorsque nous effectuons une télétransmission, nous devons connaître le __message__ que nous souhaitons envoyer et l’endroit où nous voulons l’envoyer (__ici__). Pour cette raison, nous commençons par définir une nouvelle opération de redémarrage qui reçoit deux qubits comme arguments, `msg` et `there`:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Nous devons également allouer un `here` qubit que nous obtenons avec un bloc `using` :

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Étape 1 : créer un État enchevêtré
Nous pouvons ensuite créer la paire enchevêtrée entre `here` et `there` à l’aide des opérations @"microsoft.quantum.intrinsic.h" et @"microsoft.quantum.intrinsic.cnot" :

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Étape 2 : envoyer le message
Nous utilisons ensuite les \operatorname{CNOT} $ et $H $ Gates suivants pour déplacer notre qubit de message :

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Étape 3 & 4 : mesure et interprétation du résultat
Enfin, nous utilisons @"microsoft.quantum.intrinsic.m" pour effectuer les mesures et effectuer les opérations de la porte nécessaire pour atteindre l’état souhaité, comme indiqué par les instructions `if` :

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

Cela termine la définition de notre opérateur de téléportage. nous pouvons donc désallouer `here`, terminer le corps et terminer l’opération.

```qsharp
    }
}
```
