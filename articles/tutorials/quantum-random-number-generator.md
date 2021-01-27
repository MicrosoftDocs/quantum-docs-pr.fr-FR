---
title: Créer un générateur de nombres aléatoires quantique
description: Générez un Q# projet qui illustre les concepts de Quantum fondamentaux comme les superpositions en créant un générateur de nombres aléatoires quantiques.
author: bromeg
ms.author: megbrow
ms.date: 10/25/2019
ms.topic: tutorial
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: f36db426a8f0479580117cce44a67ad3a053d5de
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856364"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>Tutoriel : Implémenter un générateur de nombres aléatoires quantique en Q\#

Un exemple simple d’algorithme Quantum écrit dans Q# est un générateur de nombres aléatoires quantiques. Cet algorithme exploite la nature de la mécanique quantique pour produire un nombre aléatoire.

## <a name="prerequisites"></a>Prérequis

- Le Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Créez un Q# projet pour une [ Q# application](xref:microsoft.quantum.install.standalone), avec un [programme hôte python](xref:microsoft.quantum.install.python)ou un [programme hôte C#](xref:microsoft.quantum.install.cs).

## <a name="write-a-no-locq-operation"></a>Écrire une Q# opération

### <a name="no-locq-operation-code"></a>Q# code d’opération

1. Remplacez le contenu du fichier Program.qs par le code suivant :

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

Comme mentionné dans notre article intitulé [Fonctionnement de l’informatique quantique](xref:microsoft.quantum.overview.understanding), un qubit est une unité d’information quantique qui peut être dans une superposition. Lorsqu’il est mesuré, un qubit peut uniquement avoir la valeur 0 ou 1. Toutefois, avant la mesure, l’état du qubit représente la probabilité de lire un 0 ou un 1 avec une mesure. Cet état probabiliste est appelé superposition. Nous pouvons utiliser cette probabilité pour générer des nombres aléatoires.

Dans le cadre de notre Q# opération, nous présentons le `Qubit` type de données, Native à Q# . Nous pouvons uniquement allouer un `Qubit` avec une instruction `using`. Lorsqu’il est alloué, un qubit est toujours dans l’état `Zero`. 

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


## <a name="creating-a-complete-random-number-generator"></a>Création d’un générateur de nombres aléatoires complet

Maintenant que nous avons une Q# opération qui génère des bits aléatoires, nous pouvons l’utiliser pour générer un générateur de nombres aléatoires quantum complet. Nous pouvons utiliser une Q# application ou un programme hôte.



### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>[Q# applications avec Visual Studio ou Visual Studio Code](#tab/tabid-qsharp)

Pour créer l' Q# application complète, ajoutez le point d’entrée suivant à votre Q# programme : 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

Le programme exécutera l’opération ou la fonction marquée avec l' `@EntryPoint()` attribut sur un simulateur ou un estimateur de ressources, en fonction de la configuration du projet et des options de ligne de commande.

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

Dans Visual Studio, appuyez simplement sur CTRL + F5 pour exécuter le script.

Dans VS Code, générez le Programme.qs pour la première fois en tapant le texte ci-dessous dans le terminal :

```dotnetcli
dotnet build
```

Pour les exécutions suivantes, il n’est pas nécessaire de le regénérer. Pour l’exécuter, tapez la commande suivante et appuyez sur Entrée :

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-prompt"></a>[Python avec Visual Studio Code ou l’invite de commandes](#tab/tabid-python)

Pour exécuter votre nouveau Q# programme à partir de Python, enregistrez le code suivant en tant que `host.py` :

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

Vous pouvez ensuite exécuter votre programme hôte Python à partir de l’invite de commandes :

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[C# avec Visual Studio Code ou Visual Studio](#tab/tabid-csharp)

Pour exécuter votre nouveau Q# programme à partir de C#, modifiez `Driver.cs` pour inclure le code C# suivant :

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

Vous pouvez ensuite exécuter votre programme hôte C# à partir de l’invite de commandes (dans Visual Studio, vous devez appuyer sur F5) :

```bash
$ dotnet run
The random number generated is 42
```

***
