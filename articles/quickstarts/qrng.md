---
title: Créer un générateur de nombres aléatoires quantique
description: Générez un projet Q# qui démontre des concepts quantiques fondamentaux comme la superposition en créant un générateur de nombres aléatoires quantique.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: a7c077eda3e46430cbe6598cb899adb460451f75
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443917"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Démarrage rapide : Implémenter un générateur de nombres aléatoires quantique en Q#
Un générateur de nombres aléatoires quantique est un exemple simple d’algorithme quantique écrit en Q#. Cet algorithme exploite la nature de la mécanique quantique pour produire un nombre aléatoire. 

## <a name="prerequisites"></a>Prérequis

- Le Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Créer un projet Q#](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Écrire une opération Q#

### <a name="q-operation-code"></a>Code d’opération Q#

1. Remplacez le contenu du fichier Operation.qs par le code suivant :

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

Comme mentionné dans notre article intitulé [Qu’est-ce que l’informatique quantique ?](xref:microsoft.quantum.overview.what), un qubit est une unité d’information quantique qui peut être dans une superposition. Lorsqu’il est mesuré, un qubit peut uniquement avoir la valeur 0 ou 1. En revanche, pendant l’exécution, l’état du qubit représente la probabilité d’avoir la valeur 0 ou 1 avec une mesure. Cet état probabiliste est appelé superposition. Nous pouvons utiliser cette probabilité pour générer des nombres aléatoires.

Dans notre opération Q#, nous introduisons le type de données `Qubit`, natif en Q#. Nous pouvons uniquement allouer un `Qubit` avec une instruction `using`. Lorsqu’il est alloué, un qubit est toujours dans l’état `Zero`. 

À l’aide de l’opération `H`, nous pouvons placer notre `Qubit` dans une superposition. Pour mesurer un qubit et lire sa valeur, vous utilisez l’opération intrinsèque `M`.

En plaçant notre `Qubit` dans une superposition et en le mesurant, notre résultat est une valeur différente à chaque fois que le code est appelé. 

Quand un `Qubit` est désalloué, il doit être explicitement redéfini à l’état `Zero`. Sinon, le simulateur signale une erreur d’exécution. Un moyen simple d’y parvenir consiste à appeler `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Visualisation du code avec la sphère de Bloch

Dans la sphère de Bloch, le pôle nord représente la valeur classique **0** et le pôle sud représente la valeur classique **1**. Toute superposition peut être représentée par un point sur la sphère (représentée par une flèche). Plus l’extrémité de la flèche est proche d’un pôle, plus la probabilité est élevée que le qubit soit réduit à la valeur classique attribuée à ce pôle lors de la mesure. Par exemple, l’état du qubit représenté par la flèche rouge ci-dessous a une probabilité plus élevée de donner la valeur **0** si nous le mesurons.

<img src="./Bloch.svg" width="175">

Nous pouvons utiliser cette représentation pour visualiser ce que fait le code :

* Tout d’abord, nous commençons avec un qubit à l’état initial de **0** et nous appliquons `H` pour créer une superposition dans laquelle les probabilités d’obtenir **0** et **1** sont les mêmes.

<img src="./H.svg" width="450">

* Ensuite, nous mesurons le qubit et nous enregistrons la sortie :

<img src="./Measurement2.svg" width="450">

Étant donné que le résultat de la mesure est complètement aléatoire, nous avons obtenu un bit aléatoire. Nous pouvons appeler cette fonction plusieurs fois pour créer des entiers. Par exemple, si nous appelons la fonction trois fois pour obtenir trois bits aléatoires, nous pouvons générer des nombres de 3 bits aléatoires (c’est-à-dire un nombre aléatoire compris entre 0 et 7).
