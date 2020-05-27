---
title: Créer un générateur de nombres aléatoires quantique
description: Générez un projet Q# qui démontre des concepts quantiques fondamentaux comme la superposition en créant un générateur de nombres aléatoires quantique.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 3e109553adc4d724733834e3660bfe7789052bcf
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426816"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="8f192-103">Tutoriel : Implémenter un générateur de nombres aléatoires quantique en Q\#</span><span class="sxs-lookup"><span data-stu-id="8f192-103">Tutorial: Implement a Quantum Random Number Generator in Q\#</span></span>

<span data-ttu-id="8f192-104">Un générateur de nombres aléatoires quantique est un exemple simple d’algorithme quantique écrit en Q#.</span><span class="sxs-lookup"><span data-stu-id="8f192-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="8f192-105">Cet algorithme exploite la nature de la mécanique quantique pour produire un nombre aléatoire.</span><span class="sxs-lookup"><span data-stu-id="8f192-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8f192-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="8f192-106">Prerequisites</span></span>

- <span data-ttu-id="8f192-107">Le Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="8f192-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="8f192-108">Créer un projet Q#</span><span class="sxs-lookup"><span data-stu-id="8f192-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)

## <a name="write-a-q-operation"></a><span data-ttu-id="8f192-109">Écrire une opération Q#</span><span class="sxs-lookup"><span data-stu-id="8f192-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="8f192-110">Code d’opération Q#</span><span class="sxs-lookup"><span data-stu-id="8f192-110">Q# operation code</span></span>

1. <span data-ttu-id="8f192-111">Remplacez le contenu du fichier Program.qs par le code suivant :</span><span class="sxs-lookup"><span data-stu-id="8f192-111">Replace the contents of the Program.qs file with the following code:</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

<span data-ttu-id="8f192-112">Comme mentionné dans notre article intitulé [Fonctionnement de l’informatique quantique](xref:microsoft.quantum.overview.understanding), un qubit est une unité d’information quantique qui peut être dans une superposition.</span><span class="sxs-lookup"><span data-stu-id="8f192-112">As mentioned in our [Understanding quantum computing](xref:microsoft.quantum.overview.understanding) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="8f192-113">Lorsqu’il est mesuré, un qubit peut uniquement avoir la valeur 0 ou 1.</span><span class="sxs-lookup"><span data-stu-id="8f192-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="8f192-114">En revanche, pendant l’exécution, l’état du qubit représente la probabilité d’avoir la valeur 0 ou 1 avec une mesure.</span><span class="sxs-lookup"><span data-stu-id="8f192-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="8f192-115">Cet état probabiliste est appelé superposition.</span><span class="sxs-lookup"><span data-stu-id="8f192-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="8f192-116">Nous pouvons utiliser cette probabilité pour générer des nombres aléatoires.</span><span class="sxs-lookup"><span data-stu-id="8f192-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="8f192-117">Dans notre opération Q#, nous introduisons le type de données `Qubit`, natif en Q#.</span><span class="sxs-lookup"><span data-stu-id="8f192-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="8f192-118">Nous pouvons uniquement allouer un `Qubit` avec une instruction `using`.</span><span class="sxs-lookup"><span data-stu-id="8f192-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="8f192-119">Lorsqu’il est alloué, un qubit est toujours dans l’état `Zero`.</span><span class="sxs-lookup"><span data-stu-id="8f192-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="8f192-120">À l’aide de l’opération `H`, nous pouvons placer notre `Qubit` dans une superposition.</span><span class="sxs-lookup"><span data-stu-id="8f192-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="8f192-121">Pour mesurer un qubit et lire sa valeur, vous utilisez l’opération intrinsèque `M`.</span><span class="sxs-lookup"><span data-stu-id="8f192-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="8f192-122">En plaçant notre `Qubit` dans une superposition et en le mesurant, notre résultat est une valeur différente à chaque fois que le code est appelé.</span><span class="sxs-lookup"><span data-stu-id="8f192-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span>

<span data-ttu-id="8f192-123">Quand un `Qubit` est désalloué, il doit être explicitement redéfini à l’état `Zero`. Sinon, le simulateur signale une erreur d’exécution.</span><span class="sxs-lookup"><span data-stu-id="8f192-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="8f192-124">Un moyen simple d’y parvenir consiste à appeler `Reset`.</span><span class="sxs-lookup"><span data-stu-id="8f192-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="8f192-125">Visualisation du code avec la sphère de Bloch</span><span class="sxs-lookup"><span data-stu-id="8f192-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="8f192-126">Dans la sphère de Bloch, le pôle nord représente la valeur classique **0** et le pôle sud représente la valeur classique **1**.</span><span class="sxs-lookup"><span data-stu-id="8f192-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="8f192-127">Toute superposition peut être représentée par un point sur la sphère (représentée par une flèche).</span><span class="sxs-lookup"><span data-stu-id="8f192-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="8f192-128">Plus l’extrémité de la flèche est proche d’un pôle, plus la probabilité est élevée que le qubit soit réduit à la valeur classique attribuée à ce pôle lors de la mesure.</span><span class="sxs-lookup"><span data-stu-id="8f192-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="8f192-129">Par exemple, l’état du qubit représenté par la flèche rouge ci-dessous a une probabilité plus élevée de donner la valeur **0** si nous le mesurons.</span><span class="sxs-lookup"><span data-stu-id="8f192-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="8f192-130">Nous pouvons utiliser cette représentation pour visualiser ce que fait le code :</span><span class="sxs-lookup"><span data-stu-id="8f192-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="8f192-131">Tout d’abord, nous commençons avec un qubit initialisé avec l’état **0** et nous appliquons `H` pour créer une superposition dans laquelle les probabilités d’obtenir **0** et **1** sont les mêmes.</span><span class="sxs-lookup"><span data-stu-id="8f192-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* <span data-ttu-id="8f192-132">Ensuite, nous mesurons le qubit et nous enregistrons la sortie :</span><span class="sxs-lookup"><span data-stu-id="8f192-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="8f192-133">Étant donné que le résultat de la mesure est complètement aléatoire, nous avons obtenu un bit aléatoire.</span><span class="sxs-lookup"><span data-stu-id="8f192-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="8f192-134">Nous pouvons appeler cette opération plusieurs fois pour créer des entiers.</span><span class="sxs-lookup"><span data-stu-id="8f192-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="8f192-135">Par exemple, si nous appelons l’opération trois fois pour obtenir trois bits aléatoires, nous pouvons générer des nombres de 3 bits aléatoires (c’est-à-dire un nombre aléatoire compris entre 0 et 7).</span><span class="sxs-lookup"><span data-stu-id="8f192-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>


## <a name="creating-a-complete-random-number-generator"></a><span data-ttu-id="8f192-136">Création d’un générateur de nombres aléatoires complet</span><span class="sxs-lookup"><span data-stu-id="8f192-136">Creating a complete random number generator</span></span>

<span data-ttu-id="8f192-137">Maintenant que nous avons une opération Q# qui génère des bits aléatoires, nous pouvons l’utiliser pour créer un générateur de nombres aléatoires quantique complet.</span><span class="sxs-lookup"><span data-stu-id="8f192-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator.</span></span> <span data-ttu-id="8f192-138">Nous pouvons utiliser les applications de ligne de commande Q# ou utiliser un programme hôte.</span><span class="sxs-lookup"><span data-stu-id="8f192-138">We can use the Q# command line applications or use a host program.</span></span>



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[<span data-ttu-id="8f192-139">Applications de ligne de commande Q# avec Visual Studio ou Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8f192-139">Q# command line applications with Visual Studio or Visual Studio Code</span></span>](#tab/tabid-qsharp)

<span data-ttu-id="8f192-140">Pour créer l’application de ligne de commande Q# complète, ajoutez le point d’entrée suivant à votre programme Q# :</span><span class="sxs-lookup"><span data-stu-id="8f192-140">To create the full Q# command line application, add the following entry point to your Q# program:</span></span> 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

<span data-ttu-id="8f192-141">L’exécutable exécute l’opération ou la fonction marquée avec l’attribut `@EntryPoint()` sur un simulateur ou un estimateur de ressources, en fonction de la configuration du projet et des options de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="8f192-141">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

<span data-ttu-id="8f192-142">Dans Visual Studio, appuyez simplement sur CTRL + F5 pour exécuter le script.</span><span class="sxs-lookup"><span data-stu-id="8f192-142">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="8f192-143">Dans VS Code, générez le Programme.qs pour la première fois en tapant le texte ci-dessous dans le terminal :</span><span class="sxs-lookup"><span data-stu-id="8f192-143">In VS Code, build the Program.qs the first time by typing the below in the terminal:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="8f192-144">Pour les exécutions suivantes, il n’est pas nécessaire de le regénérer.</span><span class="sxs-lookup"><span data-stu-id="8f192-144">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="8f192-145">Pour l’exécuter, tapez la commande suivante et appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="8f192-145">To run it, type the following command and press enter:</span></span>

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="8f192-146">Python avec Visual Studio Code ou la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="8f192-146">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

<span data-ttu-id="8f192-147">Pour exécuter votre nouveau programme Q# à partir de Python, enregistrez le code suivant sous le nom `host.py` :</span><span class="sxs-lookup"><span data-stu-id="8f192-147">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

<span data-ttu-id="8f192-148">Vous pouvez ensuite exécuter votre programme hôte Python à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="8f192-148">You can then run your Python host program from the command line:</span></span>

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[<span data-ttu-id="8f192-149">C# avec Visual Studio Code ou Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8f192-149">C# with Visual Studio Code or Visual Studio</span></span>](#tab/tabid-csharp)

<span data-ttu-id="8f192-150">Pour exécuter votre nouveau programme Q# à partir de C#, modifiez `Driver.cs` pour inclure le code C# suivant :</span><span class="sxs-lookup"><span data-stu-id="8f192-150">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

<span data-ttu-id="8f192-151">Vous pouvez ensuite exécuter votre programme hôte C# à partir de la ligne de commande (dans Visual Studio, vous devez appuyer sur F5) :</span><span class="sxs-lookup"><span data-stu-id="8f192-151">You can then run your C# host program from the command line (in Visual Studio you should press F5):</span></span>

```bash
$ dotnet run
The random number generated is 42
```

***
