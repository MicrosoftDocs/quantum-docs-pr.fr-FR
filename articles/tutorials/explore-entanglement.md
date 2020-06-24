---
title: Explorer l’intrication avec Q#
description: Apprenez à écrire un programme quantique en Q#. Développez une application pour le traitement des états de Bell à l’aide du Quantum Development kit (QDK)
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 294366b884da93f11c60cfdbdce9b40cf5202b0d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274760"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="0a508-104">Tutoriel : Explorer l’intrication avec Q\#</span><span class="sxs-lookup"><span data-stu-id="0a508-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="0a508-105">Dans ce tutoriel, nous vous montrons comment écrire un programme Q# qui manipule et mesure des qubits, puis montre les effets de la superposition et de l’intrication.</span><span class="sxs-lookup"><span data-stu-id="0a508-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>
<span data-ttu-id="0a508-106">Vous êtes ainsi accompagné tout au long de l’installation du QDK, de la génération du programme et de son exécution sur un simulateur quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-106">This guides you on installing the QDK, building the program and executing that program on a quantum simulator.</span></span>  

<span data-ttu-id="0a508-107">Vous allez écrire une application appelée Bell pour démontrer l’intrication quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-107">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="0a508-108">Le nom Bell fait référence aux états de Bell, à savoir les états quantiques spécifiques de deux qubits utilisés pour représenter les exemples les plus simples de superposition et d’intrication quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-108">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0a508-109">Prérequis</span><span class="sxs-lookup"><span data-stu-id="0a508-109">Prerequisites</span></span>

<span data-ttu-id="0a508-110">Si vous êtes prêt à commencer à programmer, suivez ces étapes préalables :</span><span class="sxs-lookup"><span data-stu-id="0a508-110">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="0a508-111">Installez le kit de développement Quantum pour [Python](xref:microsoft.quantum.install.python) ou [.NET](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="0a508-111">Install the Quantum Development Kit for [Python](xref:microsoft.quantum.install.python) or [.NET](xref:microsoft.quantum.install.cs).</span></span>
* <span data-ttu-id="0a508-112">Si le QDK est déjà installé, assurez-vous que vous l’avez [mis à jour](xref:microsoft.quantum.update) avec la dernière version</span><span class="sxs-lookup"><span data-stu-id="0a508-112">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="0a508-113">Vous pouvez également suivre la narration sans installer le QDK, en consultant les vues d’ensemble du langage de programmation Q# et les premiers concepts de l’informatique quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-113">You can also follow along with the narrative without installing the QDK, reviewing the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="demonstrating-qubit-behavior-with-q"></a><span data-ttu-id="0a508-114">Démonstration du comportement des qubits avec Q#</span><span class="sxs-lookup"><span data-stu-id="0a508-114">Demonstrating qubit behavior with Q#</span></span>

<span data-ttu-id="0a508-115">Souvenez-vous de notre simple [définition d’un qubit](xref:microsoft.quantum.overview.understanding).</span><span class="sxs-lookup"><span data-stu-id="0a508-115">Recall our simple [definition of a qubit](xref:microsoft.quantum.overview.understanding).</span></span>  <span data-ttu-id="0a508-116">Alors que les bits classiques contiennent une seule valeur binaire comme 0 ou 1, l’état d’un [qubit](xref:microsoft.quantum.glossary#qubit) peut se trouver dans une **superposition** de 0 et de 1.</span><span class="sxs-lookup"><span data-stu-id="0a508-116">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="0a508-117">D’un point de vue conceptuel, un qubit peut être considéré comme une direction dans l’espace (également appelée vecteur).</span><span class="sxs-lookup"><span data-stu-id="0a508-117">Conceptually, a qubit can be thought of as a direction in space (also known as a vector).</span></span>  <span data-ttu-id="0a508-118">Un qubit peut être dans n’importe quelle direction possible.</span><span class="sxs-lookup"><span data-stu-id="0a508-118">A qubit can be in any of the possible directions.</span></span> <span data-ttu-id="0a508-119">Les deux **états classiques** sont les deux directions ; représentant 100 % des chances de mesurer 0 et 100 % des chances de mesurer 1.</span><span class="sxs-lookup"><span data-stu-id="0a508-119">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>  <span data-ttu-id="0a508-120">Cette représentation se visualise aussi de façon plus formelle par la [sphère de Bloch](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="0a508-120">This representation is also more formally visualized by the [bloch sphere](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

<span data-ttu-id="0a508-121">L’acte de mesure produit un résultat binaire et modifie un l’état d’un qubit.</span><span class="sxs-lookup"><span data-stu-id="0a508-121">The act of measurement produces a binary result and changes a qubit state.</span></span> <span data-ttu-id="0a508-122">La mesure produit une valeur binaire, 0 ou 1.</span><span class="sxs-lookup"><span data-stu-id="0a508-122">Measurement produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="0a508-123">Le qubit passe de la superposition (toute direction) à l’un des états classiques.</span><span class="sxs-lookup"><span data-stu-id="0a508-123">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="0a508-124">Par la suite, la répétition de la même mesure sans aucune opération intermédiaire produit le même résultat binaire.</span><span class="sxs-lookup"><span data-stu-id="0a508-124">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="0a508-125">Plusieurs qubits peuvent être [**intriqués**](xref:microsoft.quantum.glossary#entanglement).</span><span class="sxs-lookup"><span data-stu-id="0a508-125">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span> <span data-ttu-id="0a508-126">Quand nous mesurons un seul qubit intriqué, notre connaissance de l’état des autres qubits est également mise à jour.</span><span class="sxs-lookup"><span data-stu-id="0a508-126">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="0a508-127">Maintenant, nous sommes prêts à démontrer comment Q# exprime ce comportement.</span><span class="sxs-lookup"><span data-stu-id="0a508-127">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="0a508-128">Vous commencez avec le programme le plus simple possible, puis développez celui-ci pour démontrer la superposition quantique et l’intrication quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-128">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="setup"></a><span data-ttu-id="0a508-129">Programme d’installation</span><span class="sxs-lookup"><span data-stu-id="0a508-129">Setup</span></span>

<span data-ttu-id="0a508-130">Ce tutoriel utilise un programme hôte et se compose de deux parties :</span><span class="sxs-lookup"><span data-stu-id="0a508-130">This tutorial uses a host programs and consists of two parts:</span></span>

1. <span data-ttu-id="0a508-131">Une série d’algorithmes quantiques, implémentés avec le langage de programmation quantique Q#.</span><span class="sxs-lookup"><span data-stu-id="0a508-131">A series of quantum algorithms, implemented using the Q# quantum programming language.</span></span>
1. <span data-ttu-id="0a508-132">Un programme hôte, implémenté en Python ou C#, qui sert de point d’entrée principal et appelle des opérations Q# pour exécuter les algorithmes quantiques.</span><span class="sxs-lookup"><span data-stu-id="0a508-132">A host program, implemented in either Python or C#, that serves as the main entry point and invokes Q# operations to execute the quantum algorithms.</span></span>

#### <a name="python"></a>[<span data-ttu-id="0a508-133">Python</span><span class="sxs-lookup"><span data-stu-id="0a508-133">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="0a508-134">Choisissez un emplacement pour votre application</span><span class="sxs-lookup"><span data-stu-id="0a508-134">Choose a location for your application</span></span>

1. <span data-ttu-id="0a508-135">Création d’un fichier appelé `Bell.qs`.</span><span class="sxs-lookup"><span data-stu-id="0a508-135">Create a file called `Bell.qs`.</span></span> <span data-ttu-id="0a508-136">Ce fichier contiendra votre code Q#.</span><span class="sxs-lookup"><span data-stu-id="0a508-136">This file will contain your Q# code.</span></span>

1. <span data-ttu-id="0a508-137">Création d’un fichier appelé `host.py`.</span><span class="sxs-lookup"><span data-stu-id="0a508-137">Create a file called `host.py`.</span></span> <span data-ttu-id="0a508-138">Ce fichier contiendra votre code d’hôte Python.</span><span class="sxs-lookup"><span data-stu-id="0a508-138">This file will contain your Python host code.</span></span>

#### <a name="c-command-line"></a>[<span data-ttu-id="0a508-139">Ligne de commande C#</span><span class="sxs-lookup"><span data-stu-id="0a508-139">C# Command Line</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="0a508-140">Créez un projet Q# :</span><span class="sxs-lookup"><span data-stu-id="0a508-140">Create a new Q# project:</span></span>

    ```
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    <span data-ttu-id="0a508-141">Vous devriez voir un fichier `.csproj`, un fichier Q# nommé `Operations.qs` et un fichier de programme hôte nommé`Driver.cs`</span><span class="sxs-lookup"><span data-stu-id="0a508-141">You should see a `.csproj` file, a Q# file called `Operations.qs`, and a host program file called `Driver.cs`</span></span>

1. <span data-ttu-id="0a508-142">Renommez le fichier Q#</span><span class="sxs-lookup"><span data-stu-id="0a508-142">Rename the Q# file</span></span>

    ```
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[<span data-ttu-id="0a508-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0a508-143">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="0a508-144">Création d'un projet</span><span class="sxs-lookup"><span data-stu-id="0a508-144">Create a new project</span></span>

   * <span data-ttu-id="0a508-145">Ouvrez Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0a508-145">Open Visual Studio</span></span>
   * <span data-ttu-id="0a508-146">Ouvrez le menu **Fichier**, puis sélectionnez **Nouveau** -> **Projet...** .</span><span class="sxs-lookup"><span data-stu-id="0a508-146">Go to the **File** menu and select **New** -> **Project...**</span></span>
   * <span data-ttu-id="0a508-147">Dans l’explorateur de modèles de projet, tapez `Q#` dans le champ de recherche et sélectionnez le modèle `Q# Application`</span><span class="sxs-lookup"><span data-stu-id="0a508-147">In the project template explorer, type `Q#` into the search field and select the `Q# Application` template</span></span>
   * <span data-ttu-id="0a508-148">Nommez votre projet `Bell`</span><span class="sxs-lookup"><span data-stu-id="0a508-148">Give your project the name `Bell`</span></span>

1. <span data-ttu-id="0a508-149">Renommez le fichier Q#</span><span class="sxs-lookup"><span data-stu-id="0a508-149">Rename the Q# file</span></span>

   * <span data-ttu-id="0a508-150">Accédez à l’**Explorateur de solutions**</span><span class="sxs-lookup"><span data-stu-id="0a508-150">Navigate to the **Solution Explorer**</span></span>
   * <span data-ttu-id="0a508-151">Cliquez avec le bouton droit sur le fichier `Operations.qs`</span><span class="sxs-lookup"><span data-stu-id="0a508-151">Right click on the `Operations.qs` file</span></span>
   * <span data-ttu-id="0a508-152">Renommez-le `Bell.qs`</span><span class="sxs-lookup"><span data-stu-id="0a508-152">Rename it to `Bell.qs`</span></span>

* * *

## <a name="write-a-q-operation"></a><span data-ttu-id="0a508-153">Écrire une opération Q#</span><span class="sxs-lookup"><span data-stu-id="0a508-153">Write a Q# operation</span></span>

<span data-ttu-id="0a508-154">Notre objectif est de préparer deux qubits dans un état quantique spécifique, en démontrant comment agir sur des qubits avec le langage Q# pour modifier leur état et ainsi montrer les effets de la superposition et de l’intrication.</span><span class="sxs-lookup"><span data-stu-id="0a508-154">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="0a508-155">Nous allons élaborer cela pièce par pièce pour démontrer les états, les opérations et les mesures de qubit.</span><span class="sxs-lookup"><span data-stu-id="0a508-155">We will build this up piece by piece to demonstrate qubit states, operations, and measurement.</span></span>

<span data-ttu-id="0a508-156">**Vue d’ensemble :**  Dans le premier code ci-dessous, nous vous montrons comment utiliser des qubits en Q#.</span><span class="sxs-lookup"><span data-stu-id="0a508-156">**Overview:**  In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="0a508-157">Nous allons introduire deux opérations, `M` et `X` qui transforment l’état d’un qubit.</span><span class="sxs-lookup"><span data-stu-id="0a508-157">We’ll introduce two operations, `M` and `X` that transform the state of a qubit.</span></span> 

<span data-ttu-id="0a508-158">Dans cet extrait de code, une opération `Set` est définie et prend comme paramètre un qubit et un autre paramètre, `desired`, qui représente l’état dans lequel nous aimerions que soit le qubit.</span><span class="sxs-lookup"><span data-stu-id="0a508-158">In this code snippet, an operation `Set` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="0a508-159">L’opération `Set` effectue une mesure sur le qubit à l’aide de l’opération `M`.</span><span class="sxs-lookup"><span data-stu-id="0a508-159">The operation `Set` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="0a508-160">En Q#, une mesure de qubit retourne toujours `Zero` ou `One`.</span><span class="sxs-lookup"><span data-stu-id="0a508-160">In Q#, a qubit measurement always returns either  `Zero` or `One`.</span></span>  <span data-ttu-id="0a508-161">Si la mesure retourne une valeur qui n’est pas égale à une valeur souhaitée, Set « inverse » le qubit ; autrement dit, Set exécute une opération `X`, qui remplace l’état du qubit par un nouvel état dans lequel les probabilités qu’une mesure retourne `Zero` et `One` sont inversées.</span><span class="sxs-lookup"><span data-stu-id="0a508-161">If the measurement returns a value not equal to a desired value, Set “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span>  <span data-ttu-id="0a508-162">Pour démontrer l’effet de l’opération de `Set`, une opération de `TestBellState` est ensuite ajoutée.</span><span class="sxs-lookup"><span data-stu-id="0a508-162">To demonstrate the effect of the `Set` operation, a `TestBellState` operation is then added.</span></span>  <span data-ttu-id="0a508-163">Cette opération prend comme entrée un `Zero` ou un `One`, puis appelle l’opération `Set` un certain nombre de fois avec cette entrée, puis compte le nombre de fois où `Zero` a été retourné par la mesure du qubit et le nombre de fois où `One` a été retourné.</span><span class="sxs-lookup"><span data-stu-id="0a508-163">This operation takes as input a `Zero` or `One`, and calls the `Set` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="0a508-164">Bien entendu, dans cette première simulation de l’opération `TestBellState`, nous nous attendons à ce que la sortie indique que toutes les mesures du qubit défini avec `Zero` comme entrée de paramètre retournent `Zero` et que toutes les mesures d’un qubit défini avec `One` comme entrée de paramètre retournent `One`.</span><span class="sxs-lookup"><span data-stu-id="0a508-164">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span>  <span data-ttu-id="0a508-165">De plus, nous allons ajouter du code à `TestBellState` pour démontrer la superposition et l’intrication.</span><span class="sxs-lookup"><span data-stu-id="0a508-165">Further on, we’ll add code to `TestBellState` to demonstrating superposition and entanglement.</span></span>


### <a name="q-operation-code"></a><span data-ttu-id="0a508-166">Code d’opération Q#</span><span class="sxs-lookup"><span data-stu-id="0a508-166">Q# operation code</span></span>

1. <span data-ttu-id="0a508-167">Remplacez le contenu du fichier Bell.qs par le code suivant :</span><span class="sxs-lookup"><span data-stu-id="0a508-167">Replace the contents of the Bell.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    <span data-ttu-id="0a508-168">Cette opération peut maintenant être appelée pour définir un qubit dans un état classique, en retournant soit `Zero` dans 100 % des cas, soit `One` dans 100 % des cas.</span><span class="sxs-lookup"><span data-stu-id="0a508-168">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>  <span data-ttu-id="0a508-169">`Zero` et `One` sont des constantes qui représentent les deux seuls résultats possibles d’une mesure de qubit.</span><span class="sxs-lookup"><span data-stu-id="0a508-169">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

    <span data-ttu-id="0a508-170">L’opération `Set` mesure le qubit.</span><span class="sxs-lookup"><span data-stu-id="0a508-170">The operation `Set` measures the qubit.</span></span>
    <span data-ttu-id="0a508-171">Si le qubit est dans l’état souhaité, `Set` le laisse tranquille ; dans le cas contraire, en exécutant l’opération `X`, nous remplaçons l’état du qubit par l’état souhaité.</span><span class="sxs-lookup"><span data-stu-id="0a508-171">If the qubit is in the state we want, `Set` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

### <a name="about-q-operations"></a><span data-ttu-id="0a508-172">À propos des opérations Q#</span><span class="sxs-lookup"><span data-stu-id="0a508-172">About Q# operations</span></span>

<span data-ttu-id="0a508-173">Une opération Q# est une sous-routine quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-173">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="0a508-174">Autrement dit, il s’agit d’une routine appelable qui contient des opérations quantiques.</span><span class="sxs-lookup"><span data-stu-id="0a508-174">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="0a508-175">Les arguments pour une opération sont spécifiés sous forme de tuples, entre parenthèses.</span><span class="sxs-lookup"><span data-stu-id="0a508-175">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="0a508-176">Le type de retour de l’opération est spécifié après un signe deux points.</span><span class="sxs-lookup"><span data-stu-id="0a508-176">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="0a508-177">Dans ce cas, l’opération `Set` ne reçoit pas de retour et est marquée comme renvoyant `Unit`.</span><span class="sxs-lookup"><span data-stu-id="0a508-177">In this case, the `Set` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="0a508-178">C’est l’équivalent Q# de `unit` en F#, analogue à `void` en C# et à un tuple vide (`Tuple[()]`) en Python.</span><span class="sxs-lookup"><span data-stu-id="0a508-178">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="0a508-179">Vous avez utilisé deux opérations quantiques dans votre première opération Q# :</span><span class="sxs-lookup"><span data-stu-id="0a508-179">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="0a508-180">L’opération [M](xref:microsoft.quantum.intrinsic.m), qui mesure l’état du qubit</span><span class="sxs-lookup"><span data-stu-id="0a508-180">The [M](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="0a508-181">L’opération [X](xref:microsoft.quantum.intrinsic.x), qui inverse l’état d’un qubit</span><span class="sxs-lookup"><span data-stu-id="0a508-181">The [X](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="0a508-182">Une opération quantique transforme l’état d’un qubit.</span><span class="sxs-lookup"><span data-stu-id="0a508-182">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="0a508-183">Il arrive que les opérations quantiques soient appelées portes quantiques, par analogie avec les portes logiques classiques.</span><span class="sxs-lookup"><span data-stu-id="0a508-183">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="0a508-184">Cette désignation remonte aux débuts de l’informatique quantique quand les algorithmes n’étaient qu’une construction théorique visualisée sous forme de schémas à l’instar des schémas électriques en informatique classique.</span><span class="sxs-lookup"><span data-stu-id="0a508-184">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="add-q-test-code"></a><span data-ttu-id="0a508-185">Ajouter un code de test Q#</span><span class="sxs-lookup"><span data-stu-id="0a508-185">Add Q# test code</span></span>

1. <span data-ttu-id="0a508-186">Ajoutez l’opération suivante au fichier `Bell.qs`, à l’intérieur de l’espace de noms, une fois l’opération `Set` terminée :</span><span class="sxs-lookup"><span data-stu-id="0a508-186">Add the following operation to the `Bell.qs` file, inside the namespace, after the end of the `Set` operation:</span></span>

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    <span data-ttu-id="0a508-187">Cette opération (`TestBellState`) effectuera une boucle de `count` itérations, définira une valeur `initial` spécifiée sur un qubit, puis mesurera (`M`) le résultat.</span><span class="sxs-lookup"><span data-stu-id="0a508-187">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="0a508-188">Elle rassemblera des statistiques sur le nombre de zéros et de uns que nous aurons mesurés et les renverra à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="0a508-188">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="0a508-189">Elle effectue une autre opération nécessaire.</span><span class="sxs-lookup"><span data-stu-id="0a508-189">It performs one other necessary operation.</span></span> <span data-ttu-id="0a508-190">Elle réinitialise le qubit dans un état connu (`Zero`) avant de le renvoyer pour permettre à d’autres de l’allouer dans un état connu.</span><span class="sxs-lookup"><span data-stu-id="0a508-190">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="0a508-191">C’est ce qu’exige l’instruction `using`.</span><span class="sxs-lookup"><span data-stu-id="0a508-191">This is required by the `using` statement.</span></span>

### <a name="about-variables-in-q"></a><span data-ttu-id="0a508-192">À propos des variables dans Q#</span><span class="sxs-lookup"><span data-stu-id="0a508-192">About variables in Q#</span></span>

<span data-ttu-id="0a508-193">Par défaut, les variables dans Q# sont immuables. Leur valeur ne peut plus être modifiée une fois qu’elles sont liées.</span><span class="sxs-lookup"><span data-stu-id="0a508-193">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="0a508-194">Le mot clé `let` permet d’indiquer la liaison d’une variable immuable.</span><span class="sxs-lookup"><span data-stu-id="0a508-194">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="0a508-195">Les arguments d’opération sont toujours immuables.</span><span class="sxs-lookup"><span data-stu-id="0a508-195">Operation arguments are always immutable.</span></span>

<span data-ttu-id="0a508-196">Si vous avez besoin d’une variable dont la valeur puisse changer, telle que `numOnes` dans l’exemple, vous pouvez la déclarer avec le mot clé `mutable`.</span><span class="sxs-lookup"><span data-stu-id="0a508-196">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="0a508-197">Il est possible de modifier la valeur d’une variable muable à l’aide d’une instruction `set`.</span><span class="sxs-lookup"><span data-stu-id="0a508-197">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="0a508-198">Dans les deux cas, le type d’une variable est inféré par le compilateur.</span><span class="sxs-lookup"><span data-stu-id="0a508-198">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="0a508-199">Q# ne nécessite ni annotations, ni variables.</span><span class="sxs-lookup"><span data-stu-id="0a508-199">Q# doesn't require any type annotations for variables.</span></span>

### <a name="about-using-statements-in-q"></a><span data-ttu-id="0a508-200">À propos des instructions `using` dans Q#</span><span class="sxs-lookup"><span data-stu-id="0a508-200">About `using` statements in Q#</span></span>

<span data-ttu-id="0a508-201">L’instruction `using` est également spéciale pour Q#.</span><span class="sxs-lookup"><span data-stu-id="0a508-201">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="0a508-202">Elle permet d’allouer des qubits à utiliser dans un bloc de code.</span><span class="sxs-lookup"><span data-stu-id="0a508-202">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="0a508-203">Dans Q#, tous les qubits sont alloués et libérés de manière dynamique, au lieu qu’ils soient des ressources fixes existant pendant toute la durée de vie d’un algorithme complexe.</span><span class="sxs-lookup"><span data-stu-id="0a508-203">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="0a508-204">Une instruction `using` alloue un ensemble de qubits au début, puis libère ces qubits à la fin du bloc.</span><span class="sxs-lookup"><span data-stu-id="0a508-204">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="create-the-host-application-code"></a><span data-ttu-id="0a508-205">Créer le code de l’application hôte</span><span class="sxs-lookup"><span data-stu-id="0a508-205">Create the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="0a508-206">Python</span><span class="sxs-lookup"><span data-stu-id="0a508-206">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="0a508-207">Ouvrez le fichier`host.py` et ajoutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="0a508-207">Open the `host.py` file and add the following code:</span></span>

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[<span data-ttu-id="0a508-208">C#</span><span class="sxs-lookup"><span data-stu-id="0a508-208">C#</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="0a508-209">Remplacez le contenu du fichier `Driver.cs` par le code suivant :</span><span class="sxs-lookup"><span data-stu-id="0a508-209">Replace the contents of the `Driver.cs` file with the following code:</span></span>

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a><span data-ttu-id="0a508-210">À propos du code de l’application hôte</span><span class="sxs-lookup"><span data-stu-id="0a508-210">About the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="0a508-211">Python</span><span class="sxs-lookup"><span data-stu-id="0a508-211">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="0a508-212">L’application hôte Python a trois facettes :</span><span class="sxs-lookup"><span data-stu-id="0a508-212">The Python host application has three parts:</span></span>

* <span data-ttu-id="0a508-213">Calculer tous les arguments requis pour l’algorithme quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-213">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="0a508-214">Dans l’exemple, `count` est fixé à 1000 et `initial` est la valeur initiale du qubit.</span><span class="sxs-lookup"><span data-stu-id="0a508-214">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="0a508-215">Exécuter l’algorithme quantique en appelant la méthode `simulate()` de l’opération Q# importée.</span><span class="sxs-lookup"><span data-stu-id="0a508-215">Run the quantum algorithm by calling the `simulate()` method of the imported Q# operation.</span></span>
* <span data-ttu-id="0a508-216">Traiter le résultat de l’opération.</span><span class="sxs-lookup"><span data-stu-id="0a508-216">Process the result of the operation.</span></span> <span data-ttu-id="0a508-217">Dans l’exemple, `res` reçoit le résultat de l’opération.</span><span class="sxs-lookup"><span data-stu-id="0a508-217">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="0a508-218">Ici, le résultat est un tuple du nombre de zéros (`num_zeros`) et de uns (`num_ones`) mesurés par le simulateur.</span><span class="sxs-lookup"><span data-stu-id="0a508-218">Here the result is a tuple of the number of zeros (`num_zeros`) and number of ones (`num_ones`) measured by the simulator.</span></span> <span data-ttu-id="0a508-219">Nous déconstruisons le tuple pour obtenir les deux champs, puis imprimons les résultats.</span><span class="sxs-lookup"><span data-stu-id="0a508-219">We deconstruct the tuple to get the two fields, and print the results.</span></span>

#### <a name="c"></a>[<span data-ttu-id="0a508-220">C#</span><span class="sxs-lookup"><span data-stu-id="0a508-220">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="0a508-221">L’application hôte C# comporte quatre volets :</span><span class="sxs-lookup"><span data-stu-id="0a508-221">The C# host application has four parts:</span></span>

* <span data-ttu-id="0a508-222">Construire un simulateur quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-222">Construct a quantum simulator.</span></span> <span data-ttu-id="0a508-223">Dans l’exemple, `qsim` est le simulateur.</span><span class="sxs-lookup"><span data-stu-id="0a508-223">In the example, `qsim` is the simulator.</span></span>
* <span data-ttu-id="0a508-224">Calculer tous les arguments requis pour l’algorithme quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-224">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="0a508-225">Dans l’exemple, `count` est fixé à 1000 et `initial` est la valeur initiale du qubit.</span><span class="sxs-lookup"><span data-stu-id="0a508-225">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="0a508-226">Exécuter l’algorithme quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-226">Run the quantum algorithm.</span></span> <span data-ttu-id="0a508-227">Chaque opération Q# génère une classe C# du même nom.</span><span class="sxs-lookup"><span data-stu-id="0a508-227">Each Q# operation generates a C# class with the same name.</span></span> <span data-ttu-id="0a508-228">Cette classe a une méthode `Run` qui exécute l’opération **de façon asynchrone** .</span><span class="sxs-lookup"><span data-stu-id="0a508-228">This class has a `Run` method that **asynchronously** executes the operation.</span></span> <span data-ttu-id="0a508-229">L’exécution est asynchrone parce que l’exécution sur du matériel réel sera asynchrone.</span><span class="sxs-lookup"><span data-stu-id="0a508-229">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> <span data-ttu-id="0a508-230">La méthode `Run` étant asynchrone, nous récupérons la propriété `Result`. Cela a pour effet de bloquer l’exécution jusqu’à ce que la tâche s’achève et renvoie le résultat de manière synchrone.</span><span class="sxs-lookup"><span data-stu-id="0a508-230">Because the `Run` method is asynchronous, we fetch the `Result` property; this blocks execution until the task completes and returns the result synchronously.</span></span>
* <span data-ttu-id="0a508-231">Traiter le résultat de l’opération.</span><span class="sxs-lookup"><span data-stu-id="0a508-231">Process the result of the operation.</span></span> <span data-ttu-id="0a508-232">Dans l’exemple, `res` reçoit le résultat de l’opération.</span><span class="sxs-lookup"><span data-stu-id="0a508-232">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="0a508-233">Ici, le résultat est un tuple du nombre de zéros (`numZeros`) et de uns (`numOnes`) mesurés par le simulateur.</span><span class="sxs-lookup"><span data-stu-id="0a508-233">Here the result is a tuple of the number of zeros (`numZeros`) and number of ones (`numOnes`) measured by the simulator.</span></span> <span data-ttu-id="0a508-234">Il est retourné en tant que ValueTuple en C#.</span><span class="sxs-lookup"><span data-stu-id="0a508-234">This is returned as a ValueTuple in C#.</span></span> <span data-ttu-id="0a508-235">Nous déconstruisons le tuple pour obtenir les deux champs, imprimons les résultats, puis attendons une action de touche.</span><span class="sxs-lookup"><span data-stu-id="0a508-235">We deconstruct the tuple to get the two fields, print the results, and wait for a keypress.</span></span>

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a><span data-ttu-id="0a508-236">Créer et exécuter</span><span class="sxs-lookup"><span data-stu-id="0a508-236">Build and run</span></span>

#### <a name="python"></a>[<span data-ttu-id="0a508-237">Python</span><span class="sxs-lookup"><span data-stu-id="0a508-237">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="0a508-238">Exécutez la commande suivante sur votre terminal :</span><span class="sxs-lookup"><span data-stu-id="0a508-238">Run the following command at your terminal:</span></span>

    ```
    python host.py
    ```

    <span data-ttu-id="0a508-239">Cette commande exécute l’application hôte qui simule l’opération Q#.</span><span class="sxs-lookup"><span data-stu-id="0a508-239">This command runs the host application, which simulates the Q# operation.</span></span>

<span data-ttu-id="0a508-240">Les résultats devraient être les suivants :</span><span class="sxs-lookup"><span data-stu-id="0a508-240">The results should be:</span></span>

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="0a508-241">Code de ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0a508-241">Command Line / Visual Studio Code</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="0a508-242">Exécutez ce qui suit sur votre terminal :</span><span class="sxs-lookup"><span data-stu-id="0a508-242">Run the following at your terminal:</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="0a508-243">Cette commande téléchargera automatiquement tous les packages requis, générera l’application, puis l’exécutera à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="0a508-243">This command will automatically download all required packages, build the application, then run it at the command line.</span></span>

1. <span data-ttu-id="0a508-244">Vous pouvez également appuyer sur **F1** pour ouvrir la palette de commandes et sélectionner **Débogage : Démarrer sans débogage.**</span><span class="sxs-lookup"><span data-stu-id="0a508-244">Alternatively, press **F1** to open the Command Palette and select **Debug: Start Without Debugging.**</span></span>
<span data-ttu-id="0a508-245">Vous serez peut-être invité à créer un nouveau fichier ``launch.json`` décrivant comment démarrer le programme.</span><span class="sxs-lookup"><span data-stu-id="0a508-245">You may be prompted to create a new ``launch.json`` file describing how to start the program.</span></span>
<span data-ttu-id="0a508-246">La valeur par défaut ``launch.json`` devrait convenir pour la plupart des applications.</span><span class="sxs-lookup"><span data-stu-id="0a508-246">The default ``launch.json`` should work well for most applications.</span></span>

<span data-ttu-id="0a508-247">Les résultats devraient être les suivants :</span><span class="sxs-lookup"><span data-stu-id="0a508-247">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[<span data-ttu-id="0a508-248">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0a508-248">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="0a508-249">Appuyez simplement sur `F5`. Cela devrait avoir pour effet de générer et d’exécuter votre programme.</span><span class="sxs-lookup"><span data-stu-id="0a508-249">Just hit `F5`, and your program should build and run!</span></span>

<span data-ttu-id="0a508-250">Les résultats devraient être les suivants :</span><span class="sxs-lookup"><span data-stu-id="0a508-250">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

<span data-ttu-id="0a508-251">Le programme se fermera sur l’action d’une touche.</span><span class="sxs-lookup"><span data-stu-id="0a508-251">The program will exit after you press a key.</span></span>

* * *

## <a name="prepare-superposition"></a><span data-ttu-id="0a508-252">Préparer la superposition</span><span class="sxs-lookup"><span data-stu-id="0a508-252">Prepare superposition</span></span>

<span data-ttu-id="0a508-253">**Vue d’ensemble** Intéressons-nous maintenant à la manière dont le langage Q# exprime les moyens de mettre des qubits en superposition.</span><span class="sxs-lookup"><span data-stu-id="0a508-253">**Overview** Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="0a508-254">Rappelez-vous que l’état d’un qubit peut être dans une superposition de 0 et de 1.</span><span class="sxs-lookup"><span data-stu-id="0a508-254">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="0a508-255">Nous allons utiliser l’opération `Hadamard` dans ce but.</span><span class="sxs-lookup"><span data-stu-id="0a508-255">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="0a508-256">Si le qubit est dans l’un des états classiques (quand une mesure retourne toujours `Zero` ou toujours `One`), alors l’opération `Hadamard` ou `H` le place dans un état où une mesure du qubit retourne `Zero` dans 50 % des cas et `One` dans 50 % des cas.</span><span class="sxs-lookup"><span data-stu-id="0a508-256">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="0a508-257">D’un point de vue conceptuel, le qubit peut être considéré à mi-chemin entre `Zero` et `One`.</span><span class="sxs-lookup"><span data-stu-id="0a508-257">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="0a508-258">Maintenant, quand nous simulons l’opération `TestBellState`, nous voyons que les résultats retournent grosso modo un nombre égal de `Zero` et de `One` après la mesure.</span><span class="sxs-lookup"><span data-stu-id="0a508-258">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

<span data-ttu-id="0a508-259">Nous allons d’abord nous contenter d’essayer d’inverser le qubit (si le qubit est à l’état `Zero`, il passe à `One` et vice versa).</span><span class="sxs-lookup"><span data-stu-id="0a508-259">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="0a508-260">Pour cela, une opération `X` est nécessaire avant d’effectuer la mesure dans `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="0a508-260">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="0a508-261">À présent, les résultats (après avoir appuyé sur `F5`) sont inversés :</span><span class="sxs-lookup"><span data-stu-id="0a508-261">Now the results (after pressing `F5`) are reversed:</span></span>

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

<span data-ttu-id="0a508-262">Cependant, tout ce que nous avons vu jusqu’à présent est classique.</span><span class="sxs-lookup"><span data-stu-id="0a508-262">However, everything we've seen so far is classical.</span></span> <span data-ttu-id="0a508-263">Obtenons un résultat quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-263">Let's get a quantum result.</span></span> <span data-ttu-id="0a508-264">Il nous suffit de remplacer l’opération `X` dans l’exécution précédente par une opération `H` ou Hadamard.</span><span class="sxs-lookup"><span data-stu-id="0a508-264">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="0a508-265">Au lieu d’inverser entièrement le qubit de 0 à 1, nous allons ne l’inverser qu’à moitié.</span><span class="sxs-lookup"><span data-stu-id="0a508-265">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="0a508-266">Les lignes remplacées dans `TestBellState` ressemblent maintenant à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0a508-266">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="0a508-267">Les résultats deviennent à présent plus intéressants :</span><span class="sxs-lookup"><span data-stu-id="0a508-267">Now the results get more interesting:</span></span>

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

<span data-ttu-id="0a508-268">Chaque fois que nous mesurons, nous demandons une valeur classique mais le qubit étant à mi-chemin entre 0 et 1, nous obtenons (statistiquement) 0 la moitié du temps et 1 l’autre moitié du temps.</span><span class="sxs-lookup"><span data-stu-id="0a508-268">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span> <span data-ttu-id="0a508-269">C’est ce qu’on appelle une __superposition__, qui nous donne une première vue réelle d’un état quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-269">This is known as __superposition__ and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="0a508-270">Préparer l’intrication</span><span class="sxs-lookup"><span data-stu-id="0a508-270">Prepare entanglement</span></span>

<span data-ttu-id="0a508-271">**Vue d’ensemble :**  Voyons maintenant comment Q# exprime les moyens d’intriquer des qubits.</span><span class="sxs-lookup"><span data-stu-id="0a508-271">**Overview:**  Now let’s look at how Q# expresses ways to entangle qubits.</span></span>  <span data-ttu-id="0a508-272">Tout d’abord, nous définissons le premier qubit sur l’état initial, puis nous utilisons l’opération `H` pour le placer en superposition.</span><span class="sxs-lookup"><span data-stu-id="0a508-272">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="0a508-273">Ensuite, avant de mesurer le premier qubit, nous utilisons une nouvelle opération, `CNOT` (Controlled-Not).</span><span class="sxs-lookup"><span data-stu-id="0a508-273">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-Not.</span></span>  <span data-ttu-id="0a508-274">Le résultat de l’exécution de cette opération sur deux qubits consiste à inverser le second qubit si le premier correspond à `One`.</span><span class="sxs-lookup"><span data-stu-id="0a508-274">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="0a508-275">À présent, les deux qubits sont intriqués.</span><span class="sxs-lookup"><span data-stu-id="0a508-275">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="0a508-276">Nos statistiques pour le premier qubit n’ont pas changé (autant de `Zero` que de `One` après la mesure). En revanche, quand nous mesurons le second qubit, le résultat est __toujours__ identique à celui obtenu pour le premier.</span><span class="sxs-lookup"><span data-stu-id="0a508-276">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="0a508-277">Notre `CNOT` a intriqué les deux qubits de sorte que ce qui arrive à l’un arrive également à l’autre.</span><span class="sxs-lookup"><span data-stu-id="0a508-277">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="0a508-278">Si vous inversiez les mesures (deuxième qubit avant le premier), la même chose se produirait.</span><span class="sxs-lookup"><span data-stu-id="0a508-278">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="0a508-279">La première mesure serait aléatoire et la seconde irait de pair avec la première.</span><span class="sxs-lookup"><span data-stu-id="0a508-279">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="0a508-280">La première chose à faire est d’allouer 2 qubits au lieu d’un dans `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="0a508-280">The first thing we'll need to do is allocate 2 qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="0a508-281">Cela nous permettra d’ajouter une nouvelle opération (`CNOT`) avant de mesurer (`M`) dans `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="0a508-281">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="0a508-282">Nous avons ajouté une autre opération `Set` pour initialiser le premier qubit afin de nous assurer qu’il est toujours à l’état `Zero` au démarrage.</span><span class="sxs-lookup"><span data-stu-id="0a508-282">We've added another `Set` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="0a508-283">Nous devons également réinitialiser le deuxième qubit avant de le libérer.</span><span class="sxs-lookup"><span data-stu-id="0a508-283">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

<span data-ttu-id="0a508-284">La routine complète ressemble maintenant à ceci :</span><span class="sxs-lookup"><span data-stu-id="0a508-284">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="0a508-285">Si nous l’exécutons, nous obtiendrons exactement le même résultat 50/50 que celui obtenu auparavant.</span><span class="sxs-lookup"><span data-stu-id="0a508-285">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="0a508-286">Cependant, ce qui nous intéresse, c’est la réaction du deuxième qubit à la mesure du premier.</span><span class="sxs-lookup"><span data-stu-id="0a508-286">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="0a508-287">Nous ajouterons cette statistique avec une nouvelle version de l’opération `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="0a508-287">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="0a508-288">La nouvelle valeur renvoyée (`agree`) conserve une trace de chaque fois que la mesure du premier qubit correspond à la mesure du deuxième.</span><span class="sxs-lookup"><span data-stu-id="0a508-288">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span> <span data-ttu-id="0a508-289">Nous devons également mettre à jour l’application hôte en conséquence :</span><span class="sxs-lookup"><span data-stu-id="0a508-289">We also have to update the host application accordingly:</span></span>

#### <a name="python"></a>[<span data-ttu-id="0a508-290">Python</span><span class="sxs-lookup"><span data-stu-id="0a508-290">Python</span></span>](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[<span data-ttu-id="0a508-291">C#</span><span class="sxs-lookup"><span data-stu-id="0a508-291">C#</span></span>](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

<span data-ttu-id="0a508-292">Maintenant, après exécution, nous obtenons un résultat assez extraordinaire :</span><span class="sxs-lookup"><span data-stu-id="0a508-292">Now when we run, we get something pretty amazing:</span></span>

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

<span data-ttu-id="0a508-293">Comme indiqué dans la vue d’ensemble, nos statistiques pour le premier qubit n’ont pas changé (autant de 0 que de 1). En revanche, quand nous mesurons le second qubit, le résultat est __toujours__ identique à celui obtenu pour le premier, parce qu’ils sont intriqués.</span><span class="sxs-lookup"><span data-stu-id="0a508-293">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

<span data-ttu-id="0a508-294">Félicitations, vous avez écrit votre premier programme quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-294">Congratulations, you've written your first quantum program!</span></span>

## <a name="next-steps"></a><span data-ttu-id="0a508-295">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="0a508-295">Next steps</span></span>

<span data-ttu-id="0a508-296">Le tutoriel sur la [recherche de Grover](xref:microsoft.quantum.quickstarts.search) vous montre comment créer et exécuter une recherche de Grover, à savoir l’un des algorithmes les plus connus en informatique quantique, et propose un exemple de programme Q# pouvant servir à résoudre de vrais problèmes avec l’informatique quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-296">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="0a508-297">[Bien démarrer avec le Quantum Development Kit](xref:microsoft.quantum.welcome) recommande d’autres moyens d’apprendre le langage Q# et la programmation quantique.</span><span class="sxs-lookup"><span data-stu-id="0a508-297">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
