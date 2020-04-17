---
title: Créer un générateur de nombres aléatoires quantique
description: Générez un projet Q# qui démontre des concepts quantiques fondamentaux comme la superposition en créant un générateur de nombres aléatoires quantique.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: b9c8592b1296a7de1b9ad5d0538ad1972ec25e31
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906982"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Démarrage rapide : Implémenter un générateur de nombres aléatoires quantique en Q#
Un générateur de nombres aléatoires quantique est un exemple simple d’algorithme quantique écrit en Q#. Cet algorithme exploite la nature de la mécanique quantique pour produire un nombre aléatoire. 

## <a name="prerequisites"></a>Prérequis

- Le Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Créer un projet Q#](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Écrire une opération Q#

### <a name="q-operation-code"></a>Code d’opération Q#

1. Remplacez le contenu du fichier Operation.qs par le code suivant :

 :::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-14":::

Comme mentionné dans notre article intitulé [Qu’est-ce que l’informatique quantique ?](xref:microsoft.quantum.overview.what), un qubit est une unité d’information quantique qui peut être dans une superposition. Lorsqu’il est mesuré, un qubit peut uniquement avoir la valeur 0 ou 1. En revanche, pendant l’exécution, l’état du qubit représente la probabilité d’avoir la valeur 0 ou 1 avec une mesure. Cet état probabiliste est appelé superposition. Nous pouvons utiliser cette probabilité pour générer des nombres aléatoires.

Dans notre opération Q#, nous introduisons le type de données `Qubit`, natif en Q#. Nous pouvons uniquement allouer un `Qubit` avec une instruction `using`. Lorsqu’il est alloué, un qubit est toujours dans l’état `Zero`. 

À l’aide de l’opération `H`, nous pouvons placer notre `Qubit` dans une superposition. Pour mesurer un qubit et lire sa valeur, vous utilisez l’opération intrinsèque `M`.

En plaçant notre `Qubit` dans une superposition et en le mesurant, notre résultat est une valeur différente à chaque fois que le code est appelé. 

Quand un `Qubit` est désalloué, il doit être explicitement redéfini à l’état `Zero`. Sinon, le simulateur signale une erreur d’exécution. Un moyen simple d’y parvenir consiste à appeler `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Visualisation du code avec la sphère de Bloch

Dans la sphère de Bloch, le pôle nord représente la valeur classique **0** et le pôle sud représente la valeur classique **1**. Toute superposition peut être représentée par un point sur la sphère (représentée par une flèche). Plus l’extrémité de la flèche est proche d’un pôle, plus la probabilité est élevée que le qubit soit réduit à la valeur classique attribuée à ce pôle lors de la mesure. Par exemple, l’état du qubit représenté par la flèche rouge ci-dessous a une probabilité plus élevée de donner la valeur **0** si nous le mesurons.

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

Nous pouvons utiliser cette représentation pour visualiser ce que fait le code :

* Tout d’abord, nous commençons avec un qubit initialisé avec l’état **0** et nous appliquons `H` pour créer une superposition dans laquelle les probabilités d’obtenir **0** et **1** sont les mêmes.

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">


* Ensuite, nous mesurons le qubit et nous enregistrons la sortie :

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

Étant donné que le résultat de la mesure est complètement aléatoire, nous avons obtenu un bit aléatoire. Nous pouvons appeler cette opération plusieurs fois pour créer des entiers. Par exemple, si nous appelons l’opération trois fois pour obtenir trois bits aléatoires, nous pouvons générer des nombres de 3 bits aléatoires (c’est-à-dire un nombre aléatoire compris entre 0 et 7).

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a>Création d’un générateur de nombres aléatoires complet en utilisant un programme hôte

Maintenant que nous avons une opération Q# qui génère des bits aléatoires, nous pouvons l’utiliser pour créer un générateur de nombres aléatoires quantique complet avec un programme hôte.

 ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python avec Visual Studio Code ou la ligne de commande](#tab/tabid-python)
 
 Pour exécuter votre nouveau programme Q# à partir de Python, enregistrez le code suivant sous le nom `host.py` :
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 Vous pouvez ensuite exécuter votre programme hôte Python à partir de la ligne de commande :
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# avec Visual Studio Code ou la ligne de commande](#tab/tabid-csharp)
 
 Pour exécuter votre nouveau programme Q# à partir de C#, modifiez `Driver.cs` pour inclure le code C# suivant :
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 Vous pouvez ensuite exécuter votre programme hôte C# à partir de la ligne de commande :
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019"></a>[C# avec Visual Studio 2019](#tab/tabid-vs2019)

 Pour exécuter votre nouveau programme Q# à partir de C# dans Visual Studio, modifiez `Driver.cs` pour inclure le code C# suivant :

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 Appuyez ensuite sur F5, le programme démarre l’exécution et une nouvelle fenêtre s’affiche avec le nombre aléatoire généré : 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
