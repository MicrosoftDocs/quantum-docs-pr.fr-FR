---
title: Créer un générateur de nombres aléatoires quantique
description: Générez un Q# projet qui illustre les concepts de Quantum fondamentaux comme les superpositions en créant un générateur de nombres aléatoires quantiques.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8db892091794cb1166e41744572d8938d975abf2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869764"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="dc6b1-103">Tutoriel : Implémenter un générateur de nombres aléatoires quantique en Q\#</span><span class="sxs-lookup"><span data-stu-id="dc6b1-103">Tutorial: Implement a Quantum Random Number Generator in Q\#</span></span>

<span data-ttu-id="dc6b1-104">Un exemple simple d’algorithme Quantum écrit dans Q# est un générateur de nombres aléatoires quantiques.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="dc6b1-105">Cet algorithme exploite la nature de la mécanique quantique pour produire un nombre aléatoire.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dc6b1-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="dc6b1-106">Prerequisites</span></span>

- <span data-ttu-id="dc6b1-107">Le Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="dc6b1-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="dc6b1-108">Créez un Q# projet à [l’aide Q# de à partir de la ligne de commande](xref:microsoft.quantum.install.standalone), ou avec un [programme hôte python](xref:microsoft.quantum.install.python) ou un [programme hôte C#](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="dc6b1-108">Create a Q# project for either [using Q# from the command line](xref:microsoft.quantum.install.standalone), or with a [Python host program](xref:microsoft.quantum.install.python) or [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="write-a-no-locq-operation"></a><span data-ttu-id="dc6b1-109">Écrire une Q# opération</span><span class="sxs-lookup"><span data-stu-id="dc6b1-109">Write a Q# operation</span></span>

### <a name="no-locq-operation-code"></a><span data-ttu-id="dc6b1-110">Q#code d’opération</span><span class="sxs-lookup"><span data-stu-id="dc6b1-110">Q# operation code</span></span>

1. <span data-ttu-id="dc6b1-111">Remplacez le contenu du fichier Program.qs par le code suivant :</span><span class="sxs-lookup"><span data-stu-id="dc6b1-111">Replace the contents of the Program.qs file with the following code:</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

<span data-ttu-id="dc6b1-112">Comme mentionné dans notre article intitulé [Fonctionnement de l’informatique quantique](xref:microsoft.quantum.overview.understanding), un qubit est une unité d’information quantique qui peut être dans une superposition.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-112">As mentioned in our [Understanding quantum computing](xref:microsoft.quantum.overview.understanding) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="dc6b1-113">Lorsqu’il est mesuré, un qubit peut uniquement avoir la valeur 0 ou 1.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="dc6b1-114">En revanche, pendant l’exécution, l’état du qubit représente la probabilité d’avoir la valeur 0 ou 1 avec une mesure.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="dc6b1-115">Cet état probabiliste est appelé superposition.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="dc6b1-116">Nous pouvons utiliser cette probabilité pour générer des nombres aléatoires.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="dc6b1-117">Dans le cadre de notre Q# opération, nous présentons le `Qubit` type de données, Native à Q# .</span><span class="sxs-lookup"><span data-stu-id="dc6b1-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="dc6b1-118">Nous pouvons uniquement allouer un `Qubit` avec une instruction `using`.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="dc6b1-119">Lorsqu’il est alloué, un qubit est toujours dans l’état `Zero`.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="dc6b1-120">À l’aide de l’opération `H`, nous pouvons placer notre `Qubit` dans une superposition.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="dc6b1-121">Pour mesurer un qubit et lire sa valeur, vous utilisez l’opération intrinsèque `M`.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="dc6b1-122">En plaçant notre `Qubit` dans une superposition et en le mesurant, notre résultat est une valeur différente à chaque fois que le code est appelé.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span>

<span data-ttu-id="dc6b1-123">Quand un `Qubit` est désalloué, il doit être explicitement redéfini à l’état `Zero`. Sinon, le simulateur signale une erreur d’exécution.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-123">When a `Qubit` is deallocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="dc6b1-124">Un moyen simple d’y parvenir consiste à appeler `Reset`.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="dc6b1-125">Visualisation du code avec la sphère de Bloch</span><span class="sxs-lookup"><span data-stu-id="dc6b1-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="dc6b1-126">Dans la sphère de Bloch, le pôle nord représente la valeur classique **0** et le pôle sud représente la valeur classique **1**.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="dc6b1-127">Toute superposition peut être représentée par un point sur la sphère (représentée par une flèche).</span><span class="sxs-lookup"><span data-stu-id="dc6b1-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="dc6b1-128">Plus l’extrémité de la flèche est proche d’un pôle, plus la probabilité est élevée que le qubit soit réduit à la valeur classique attribuée à ce pôle lors de la mesure.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="dc6b1-129">Par exemple, l’état du qubit représenté par la flèche rouge ci-dessous a une probabilité plus élevée de donner la valeur **0** si nous le mesurons.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="dc6b1-130">Nous pouvons utiliser cette représentation pour visualiser ce que fait le code :</span><span class="sxs-lookup"><span data-stu-id="dc6b1-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="dc6b1-131">Tout d’abord, nous commençons avec un qubit initialisé avec l’état **0** et nous appliquons `H` pour créer une superposition dans laquelle les probabilités d’obtenir **0** et **1** sont les mêmes.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* <span data-ttu-id="dc6b1-132">Ensuite, nous mesurons le qubit et nous enregistrons la sortie :</span><span class="sxs-lookup"><span data-stu-id="dc6b1-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="dc6b1-133">Étant donné que le résultat de la mesure est complètement aléatoire, nous avons obtenu un bit aléatoire.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="dc6b1-134">Nous pouvons appeler cette opération plusieurs fois pour créer des entiers.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="dc6b1-135">Par exemple, si nous appelons l’opération trois fois pour obtenir trois bits aléatoires, nous pouvons générer des nombres de 3 bits aléatoires (c’est-à-dire un nombre aléatoire compris entre 0 et 7).</span><span class="sxs-lookup"><span data-stu-id="dc6b1-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>


## <a name="creating-a-complete-random-number-generator"></a><span data-ttu-id="dc6b1-136">Création d’un générateur de nombres aléatoires complet</span><span class="sxs-lookup"><span data-stu-id="dc6b1-136">Creating a complete random number generator</span></span>

<span data-ttu-id="dc6b1-137">Maintenant que nous avons une Q# opération qui génère des bits aléatoires, nous pouvons l’utiliser pour générer un générateur de nombres aléatoires quantum complet.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator.</span></span> <span data-ttu-id="dc6b1-138">Nous pouvons utiliser les Q# applications en ligne de commande ou utiliser un programme hôte.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-138">We can use the Q# command line applications or use a host program.</span></span>



### <a name="no-locq-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[<span data-ttu-id="dc6b1-139">Q#applications en ligne de commande avec Visual Studio ou Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="dc6b1-139">Q# command line applications with Visual Studio or Visual Studio Code</span></span>](#tab/tabid-qsharp)

<span data-ttu-id="dc6b1-140">Pour créer l' Q# application en ligne de commande complète, ajoutez le point d’entrée suivant à votre Q# programme :</span><span class="sxs-lookup"><span data-stu-id="dc6b1-140">To create the full Q# command line application, add the following entry point to your Q# program:</span></span> 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

<span data-ttu-id="dc6b1-141">L’exécutable exécute l’opération ou la fonction marquée avec l’attribut `@EntryPoint()` sur un simulateur ou un estimateur de ressources, en fonction de la configuration du projet et des options de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-141">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

<span data-ttu-id="dc6b1-142">Dans Visual Studio, appuyez simplement sur CTRL + F5 pour exécuter le script.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-142">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="dc6b1-143">Dans VS Code, générez le Programme.qs pour la première fois en tapant le texte ci-dessous dans le terminal :</span><span class="sxs-lookup"><span data-stu-id="dc6b1-143">In VS Code, build the Program.qs the first time by typing the below in the terminal:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="dc6b1-144">Pour les exécutions suivantes, il n’est pas nécessaire de le regénérer.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-144">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="dc6b1-145">Pour l’exécuter, tapez la commande suivante et appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="dc6b1-145">To run it, type the following command and press enter:</span></span>

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="dc6b1-146">Python avec Visual Studio Code ou la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="dc6b1-146">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

<span data-ttu-id="dc6b1-147">Pour exécuter votre nouveau Q# programme à partir de Python, enregistrez le code suivant en tant que `host.py` :</span><span class="sxs-lookup"><span data-stu-id="dc6b1-147">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

<span data-ttu-id="dc6b1-148">Vous pouvez ensuite exécuter votre programme hôte Python à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="dc6b1-148">You can then run your Python host program from the command line:</span></span>

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[<span data-ttu-id="dc6b1-149">C# avec Visual Studio Code ou Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dc6b1-149">C# with Visual Studio Code or Visual Studio</span></span>](#tab/tabid-csharp)

<span data-ttu-id="dc6b1-150">Pour exécuter votre nouveau Q# programme à partir de C#, modifiez `Driver.cs` pour inclure le code C# suivant :</span><span class="sxs-lookup"><span data-stu-id="dc6b1-150">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

<span data-ttu-id="dc6b1-151">Vous pouvez ensuite exécuter votre programme hôte C# à partir de la ligne de commande (dans Visual Studio, vous devez appuyer sur F5) :</span><span class="sxs-lookup"><span data-stu-id="dc6b1-151">You can then run your C# host program from the command line (in Visual Studio you should press F5):</span></span>

```bash
$ dotnet run
The random number generated is 42
```

***
