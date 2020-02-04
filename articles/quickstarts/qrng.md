---
title: Créer un générateur de nombres aléatoires quantique
description: Générez un projet Q# qui démontre des concepts quantiques fondamentaux comme la superposition en créant un générateur de nombres aléatoires quantique.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 134617455b720cc755b9ee9fb68fb59e624d3f1a
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820908"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="7b16c-103">Démarrage rapide : Implémenter un générateur de nombres aléatoires quantique en Q#</span><span class="sxs-lookup"><span data-stu-id="7b16c-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="7b16c-104">Un générateur de nombres aléatoires quantique est un exemple simple d’algorithme quantique écrit en Q#.</span><span class="sxs-lookup"><span data-stu-id="7b16c-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="7b16c-105">Cet algorithme exploite la nature de la mécanique quantique pour produire un nombre aléatoire.</span><span class="sxs-lookup"><span data-stu-id="7b16c-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="7b16c-106">Conditions préalables requises</span><span class="sxs-lookup"><span data-stu-id="7b16c-106">Prerequisites</span></span>

- <span data-ttu-id="7b16c-107">Le Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="7b16c-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="7b16c-108">Créer un projet Q#</span><span class="sxs-lookup"><span data-stu-id="7b16c-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="7b16c-109">Écrire une opération Q#</span><span class="sxs-lookup"><span data-stu-id="7b16c-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="7b16c-110">Code d’opération Q#</span><span class="sxs-lookup"><span data-stu-id="7b16c-110">Q# operation code</span></span>

1. <span data-ttu-id="7b16c-111">Remplacez le contenu du fichier Operation.qs par le code suivant :</span><span class="sxs-lookup"><span data-stu-id="7b16c-111">Replace the contents of the Operation.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(qubit = Qubit())  { // Allocate a qubit.
                H(qubit);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(v);     // Measure the qubit value.
                Reset(qubit);
                return r;
            }
        }
    }
    ```

<span data-ttu-id="7b16c-112">Comme mentionné dans notre article intitulé [Qu’est-ce que l’informatique quantique ?](xref:microsoft.quantum.overview.what), un qubit est une unité d’information quantique qui peut être dans une superposition.</span><span class="sxs-lookup"><span data-stu-id="7b16c-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="7b16c-113">Lorsqu’il est mesuré, un qubit peut uniquement avoir la valeur 0 ou 1.</span><span class="sxs-lookup"><span data-stu-id="7b16c-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="7b16c-114">En revanche, pendant l’exécution, l’état du qubit représente la probabilité d’avoir la valeur 0 ou 1 avec une mesure.</span><span class="sxs-lookup"><span data-stu-id="7b16c-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="7b16c-115">Cet état probabiliste est appelé superposition.</span><span class="sxs-lookup"><span data-stu-id="7b16c-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="7b16c-116">Nous pouvons utiliser cette probabilité pour générer des nombres aléatoires.</span><span class="sxs-lookup"><span data-stu-id="7b16c-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="7b16c-117">Dans notre opération Q#, nous introduisons le type de données `Qubit`, natif en Q#.</span><span class="sxs-lookup"><span data-stu-id="7b16c-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="7b16c-118">Nous pouvons uniquement allouer un `Qubit` avec une instruction `using`.</span><span class="sxs-lookup"><span data-stu-id="7b16c-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="7b16c-119">Lorsqu’il est alloué, un qubit est toujours dans l’état `Zero`.</span><span class="sxs-lookup"><span data-stu-id="7b16c-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="7b16c-120">À l’aide de l’opération `H`, nous pouvons placer notre `Qubit` dans une superposition.</span><span class="sxs-lookup"><span data-stu-id="7b16c-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="7b16c-121">Pour mesurer un qubit et lire sa valeur, vous utilisez l’opération intrinsèque `M`.</span><span class="sxs-lookup"><span data-stu-id="7b16c-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="7b16c-122">En plaçant notre `Qubit` dans une superposition et en le mesurant, notre résultat est une valeur différente à chaque fois que le code est appelé.</span><span class="sxs-lookup"><span data-stu-id="7b16c-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="7b16c-123">Quand un `Qubit` est désalloué, il doit être explicitement redéfini à l’état `Zero`. Sinon, le simulateur signale une erreur d’exécution.</span><span class="sxs-lookup"><span data-stu-id="7b16c-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="7b16c-124">Un moyen simple d’y parvenir consiste à appeler `Reset`.</span><span class="sxs-lookup"><span data-stu-id="7b16c-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="7b16c-125">Visualisation du code avec la sphère de Bloch</span><span class="sxs-lookup"><span data-stu-id="7b16c-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="7b16c-126">Dans la sphère de Bloch, le pôle nord représente la valeur classique **0** et le pôle sud représente la valeur classique **1**.</span><span class="sxs-lookup"><span data-stu-id="7b16c-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="7b16c-127">Toute superposition peut être représentée par un point sur la sphère (représentée par une flèche).</span><span class="sxs-lookup"><span data-stu-id="7b16c-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="7b16c-128">Plus l’extrémité de la flèche est proche d’un pôle, plus la probabilité est élevée que le qubit soit réduit à la valeur classique attribuée à ce pôle lors de la mesure.</span><span class="sxs-lookup"><span data-stu-id="7b16c-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="7b16c-129">Par exemple, l’état du qubit représenté par la flèche rouge ci-dessous a une probabilité plus élevée de donner la valeur **0** si nous le mesurons.</span><span class="sxs-lookup"><span data-stu-id="7b16c-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175">

<span data-ttu-id="7b16c-130">Nous pouvons utiliser cette représentation pour visualiser ce que fait le code :</span><span class="sxs-lookup"><span data-stu-id="7b16c-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="7b16c-131">Tout d’abord, nous commençons avec un qubit à l’état initial de **0** et nous appliquons `H` pour créer une superposition dans laquelle les probabilités d’obtenir **0** et **1** sont les mêmes.</span><span class="sxs-lookup"><span data-stu-id="7b16c-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450">

* <span data-ttu-id="7b16c-132">Ensuite, nous mesurons le qubit et nous enregistrons la sortie :</span><span class="sxs-lookup"><span data-stu-id="7b16c-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450">

<span data-ttu-id="7b16c-133">Étant donné que le résultat de la mesure est complètement aléatoire, nous avons obtenu un bit aléatoire.</span><span class="sxs-lookup"><span data-stu-id="7b16c-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="7b16c-134">Nous pouvons appeler cette opération plusieurs fois pour créer des entiers.</span><span class="sxs-lookup"><span data-stu-id="7b16c-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="7b16c-135">Par exemple, si nous appelons l’opération trois fois pour obtenir trois bits aléatoires, nous pouvons générer des nombres de 3 bits aléatoires (c’est-à-dire un nombre aléatoire compris entre 0 et 7).</span><span class="sxs-lookup"><span data-stu-id="7b16c-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a><span data-ttu-id="7b16c-136">Création d’un générateur de nombres aléatoires complet en utilisant un programme hôte</span><span class="sxs-lookup"><span data-stu-id="7b16c-136">Creating a complete random number generator using a host program</span></span>

<span data-ttu-id="7b16c-137">Maintenant que nous avons une opération Q# qui génère des bits aléatoires, nous pouvons l’utiliser pour créer un générateur de nombres aléatoires quantique complet avec un programme hôte.</span><span class="sxs-lookup"><span data-stu-id="7b16c-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator with a host program.</span></span>

 ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[<span data-ttu-id="7b16c-138">Python avec Visual Studio Code ou la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="7b16c-138">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)
 
 <span data-ttu-id="7b16c-139">Pour exécuter votre nouveau programme Q# à partir de Python, enregistrez le code suivant sous le nom `host.py` :</span><span class="sxs-lookup"><span data-stu-id="7b16c-139">To run your new Q# program from Python, save the following code as `host.py`:</span></span>
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 <span data-ttu-id="7b16c-140">Vous pouvez ensuite exécuter votre programme hôte Python à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="7b16c-140">You can then run your Python host program from the command line:</span></span>
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[<span data-ttu-id="7b16c-141">C# avec Visual Studio Code ou la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="7b16c-141">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)
 
 <span data-ttu-id="7b16c-142">Pour exécuter votre nouveau programme Q# à partir de C#, modifiez `Driver.cs` pour inclure le code C# suivant :</span><span class="sxs-lookup"><span data-stu-id="7b16c-142">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 <span data-ttu-id="7b16c-143">Vous pouvez ensuite exécuter votre programme hôte C# à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="7b16c-143">You can then run your C# host program from the command line:</span></span>
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="7b16c-144">C# avec Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="7b16c-144">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

 <span data-ttu-id="7b16c-145">Pour exécuter votre nouveau programme Q# à partir de C# dans Visual Studio, modifiez `Driver.cs` pour inclure le code C# suivant :</span><span class="sxs-lookup"><span data-stu-id="7b16c-145">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 <span data-ttu-id="7b16c-146">Appuyez ensuite sur F5, le programme démarre l’exécution et une nouvelle fenêtre s’affiche avec le nombre aléatoire généré :</span><span class="sxs-lookup"><span data-stu-id="7b16c-146">Then press F5, the program will start execution and a new window will pop up with the random number generated:</span></span> 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
