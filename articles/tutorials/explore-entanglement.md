---
title: 'Explorez l’enchevêtrement avec Q#'
description: 'Découvrez comment écrire un programme Quantum dans Q# . Développez une application pour le traitement des états de Bell à l’aide du Quantum Development kit (QDK)'
author: geduardo
ms.author: v-edsanc
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 7a1a49e18ac9330ca6e3cc89b3e58c96eccb91db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691671"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="14338-104">Tutoriel : Explorer l’intrication avec Q\#</span><span class="sxs-lookup"><span data-stu-id="14338-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="14338-105">Dans ce didacticiel, nous vous montrons comment écrire un Q# programme qui manipule et mesure les qubits et montre les effets de la superposition et de l’enchevêtrement.</span><span class="sxs-lookup"><span data-stu-id="14338-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>

<span data-ttu-id="14338-106">Vous allez écrire une application appelée Bell pour démontrer l’intrication quantique.</span><span class="sxs-lookup"><span data-stu-id="14338-106">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="14338-107">Le nom Bell fait référence aux états de Bell, à savoir les états quantiques spécifiques de deux qubits utilisés pour représenter les exemples les plus simples de superposition et d’intrication quantique.</span><span class="sxs-lookup"><span data-stu-id="14338-107">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="14338-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="14338-108">Pre-requisites</span></span>

<span data-ttu-id="14338-109">Si vous êtes prêt à commencer à programmer, suivez ces étapes préalables :</span><span class="sxs-lookup"><span data-stu-id="14338-109">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="14338-110">[Installez](xref:microsoft.quantum.install) le kit de développement quantique à l’aide de votre langue et de votre environnement de développement préférés.</span><span class="sxs-lookup"><span data-stu-id="14338-110">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your  preferred language and development environment.</span></span>
* <span data-ttu-id="14338-111">Si le QDK est déjà installé, assurez-vous que vous l’avez [mis à jour](xref:microsoft.quantum.update) avec la dernière version</span><span class="sxs-lookup"><span data-stu-id="14338-111">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="14338-112">Vous pouvez également suivre la narration sans installer le QDK, en examinant les vues d’ensemble du Q# langage de programmation et les premiers concepts de quantum computing.</span><span class="sxs-lookup"><span data-stu-id="14338-112">You can also follow along with the narrative without installing the QDK, reviewing  the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="14338-113">Ce didacticiel vous montre comment effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="14338-113">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="14338-114">Créer et combiner des opérations dans Q\#</span><span class="sxs-lookup"><span data-stu-id="14338-114">Create and combine operations in Q\#</span></span>
> * <span data-ttu-id="14338-115">Créez des opérations pour placer les qubits dans la superposition, les préposer et les mesurer.</span><span class="sxs-lookup"><span data-stu-id="14338-115">Create operations to put qubits in superposition, entangle and measure them.</span></span>
> * <span data-ttu-id="14338-116">Démonstration de l’enchevêtrement quantique avec un Q# programme exécuté dans un simulateur.</span><span class="sxs-lookup"><span data-stu-id="14338-116">Demonstrate quantum entanglement with a Q# program run in a simulator.</span></span> 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a><span data-ttu-id="14338-117">Démonstration du comportement de qubit avec QDK</span><span class="sxs-lookup"><span data-stu-id="14338-117">Demonstrating qubit behavior with the QDK</span></span>

<span data-ttu-id="14338-118">Alors que les bits classiques contiennent une seule valeur binaire comme 0 ou 1, l’état d’un [qubit](xref:microsoft.quantum.glossary#qubit) peut se trouver dans une **superposition** de 0 et de 1.</span><span class="sxs-lookup"><span data-stu-id="14338-118">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="14338-119">D’un point de vue conceptuel, l’état d’un qubit peut être considéré comme une direction dans un espace abstrait (également appelé vecteur).</span><span class="sxs-lookup"><span data-stu-id="14338-119">Conceptually, the state of a qubit can be thought of as a direction in an abstract space (also known as a vector).</span></span>  <span data-ttu-id="14338-120">Un État qubit peut être dans n’importe quelle direction possible.</span><span class="sxs-lookup"><span data-stu-id="14338-120">A qubit state can be in any of the possible directions.</span></span> <span data-ttu-id="14338-121">Les deux **états classiques** sont les deux directions ; représentant 100 % des chances de mesurer 0 et 100 % des chances de mesurer 1.</span><span class="sxs-lookup"><span data-stu-id="14338-121">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>

<span data-ttu-id="14338-122">L’acte de mesure produit un résultat binaire et modifie un l’état d’un qubit.</span><span class="sxs-lookup"><span data-stu-id="14338-122">The act of measurement produces a binary result and changes a qubit state.</span></span>
<span data-ttu-id="14338-123">La mesure produit une valeur binaire, 0 ou 1.</span><span class="sxs-lookup"><span data-stu-id="14338-123">Measurement  produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="14338-124">Le qubit passe de la superposition (toute direction) à l’un des états classiques.</span><span class="sxs-lookup"><span data-stu-id="14338-124">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="14338-125">Par la suite, la répétition de la même mesure sans aucune opération intermédiaire produit le même résultat binaire.</span><span class="sxs-lookup"><span data-stu-id="14338-125">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="14338-126">Plusieurs qubits peuvent être [**intriqués**](xref:microsoft.quantum.glossary#entanglement).</span><span class="sxs-lookup"><span data-stu-id="14338-126">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span>  <span data-ttu-id="14338-127">Quand nous mesurons un seul qubit intriqué, notre connaissance de l’état des autres qubits est également mise à jour.</span><span class="sxs-lookup"><span data-stu-id="14338-127">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="14338-128">Maintenant, nous sommes prêts à montrer comment Q# exprime ce comportement.</span><span class="sxs-lookup"><span data-stu-id="14338-128">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="14338-129">Vous commencez avec le programme le plus simple possible, puis développez celui-ci pour démontrer la superposition quantique et l’intrication quantique.</span><span class="sxs-lookup"><span data-stu-id="14338-129">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="creating-a-no-locq-project"></a><span data-ttu-id="14338-130">Création d’un Q# projet</span><span class="sxs-lookup"><span data-stu-id="14338-130">Creating a Q# project</span></span>

<span data-ttu-id="14338-131">La première chose à faire est de créer un nouveau Q# projet.</span><span class="sxs-lookup"><span data-stu-id="14338-131">The first thing we have to do is to create a new Q# project.</span></span> <span data-ttu-id="14338-132">Dans ce didacticiel, nous allons utiliser l’environnement basé sur des [ Q# applications avec vs code](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="14338-132">In this tutorial we are going to use the environment based on [Q# applications with VS Code](xref:microsoft.quantum.install.standalone).</span></span>

<span data-ttu-id="14338-133">Pour créer un nouveau projet, dans VS Code :</span><span class="sxs-lookup"><span data-stu-id="14338-133">To create a new project, in VS Code:</span></span> 

1. <span data-ttu-id="14338-134">Cliquez sur **Affichage** -> **Palette de commandes** et sélectionnez **Q# : Créer un projet** .</span><span class="sxs-lookup"><span data-stu-id="14338-134">Click **View** -> **Command Palette** and select **Q#: Create New Project** .</span></span>
2. <span data-ttu-id="14338-135">Cliquez sur **Application console autonome** .</span><span class="sxs-lookup"><span data-stu-id="14338-135">Click **Standalone console application** .</span></span>
3. <span data-ttu-id="14338-136">Accédez à l’emplacement où vous souhaitez enregistrer le projet, puis cliquez sur **Créer le projet** .</span><span class="sxs-lookup"><span data-stu-id="14338-136">Navigate to the location to save the project and click **Create Project** .</span></span>
4. <span data-ttu-id="14338-137">Une fois le projet créé, cliquez sur **Ouvrir le nouveau projet...** dans le coin inférieur droit.</span><span class="sxs-lookup"><span data-stu-id="14338-137">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="14338-138">Dans le cas présent, nous avons appelé le projet `Bell` .</span><span class="sxs-lookup"><span data-stu-id="14338-138">In this case we called the project `Bell`.</span></span> <span data-ttu-id="14338-139">Cela génère deux fichiers : `Bell.csproj` , le fichier projet et `Program.qs` , un modèle d' Q# application que nous allons utiliser pour écrire notre application.</span><span class="sxs-lookup"><span data-stu-id="14338-139">This generates two files: `Bell.csproj`, the project file and `Program.qs`, a template of a Q# application that we will use to write our application.</span></span> <span data-ttu-id="14338-140">Le contenu de `Program.qs` doit être :</span><span class="sxs-lookup"><span data-stu-id="14338-140">The content of `Program.qs` should be:</span></span>

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a><span data-ttu-id="14338-141">Écrire l' \# application Q</span><span class="sxs-lookup"><span data-stu-id="14338-141">Write the Q\# application</span></span>
 
<span data-ttu-id="14338-142">Notre objectif est de préparer deux qubits dans un État Quantum spécifique, en montrant comment fonctionner sur qubits avec Q# pour modifier leur état et démontrer les effets de la superposition et de l’enchevêtrement.</span><span class="sxs-lookup"><span data-stu-id="14338-142">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="14338-143">Nous allons créer ce composant pour introduire des États, opérations et mesures qubit.</span><span class="sxs-lookup"><span data-stu-id="14338-143">We will build this up piece by piece to introduce qubit states, operations, and measurement.</span></span>

### <a name="initialize-qubit-using-measurement"></a><span data-ttu-id="14338-144">Initialiser qubit à l’aide de mesures</span><span class="sxs-lookup"><span data-stu-id="14338-144">Initialize qubit using measurement</span></span>

<span data-ttu-id="14338-145">Dans le premier extrait de code ci-dessous, nous vous montrons comment utiliser qubits dans Q# .</span><span class="sxs-lookup"><span data-stu-id="14338-145">In the first code snippet below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="14338-146">Nous allons introduire deux opérations [`M`](xref:Microsoft.Quantum.Intrinsic.m) et [`X`](xref:Microsoft.Quantum.Intrinsic.X) transformer l’état d’un qubit.</span><span class="sxs-lookup"><span data-stu-id="14338-146">We’ll introduce two operations, [`M`](xref:Microsoft.Quantum.Intrinsic.m) and [`X`](xref:Microsoft.Quantum.Intrinsic.X) that transform the state of a qubit.</span></span> <span data-ttu-id="14338-147">Dans cet extrait de code, une opération `SetQubitState` est définie et prend comme paramètre un qubit et un autre paramètre, `desired`, qui représente l’état dans lequel nous aimerions que soit le qubit.</span><span class="sxs-lookup"><span data-stu-id="14338-147">In this code snippet, an operation `SetQubitState` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="14338-148">L’opération `SetQubitState` effectue une mesure sur le qubit à l’aide de l’opération `M`.</span><span class="sxs-lookup"><span data-stu-id="14338-148">The operation `SetQubitState` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="14338-149">Dans Q# , une mesure qubit retourne toujours `Zero` ou `One` .</span><span class="sxs-lookup"><span data-stu-id="14338-149">In Q#, a qubit measurement always returns either `Zero` or `One`.</span></span>  <span data-ttu-id="14338-150">Si la mesure retourne une valeur qui n’est pas égale à la valeur souhaitée, `SetQubitState` « retourne » le qubit ; autrement dit, il exécute une `X` opération, qui fait passer l’état de qubit à un nouvel État dans lequel les probabilités d’une mesure retournent `Zero` et `One` sont inversées.</span><span class="sxs-lookup"><span data-stu-id="14338-150">If the measurement returns a value not equal to the desired value, `SetQubitState` “flips” the qubit; that is, it runs an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span> <span data-ttu-id="14338-151">De cette façon, `SetQubitState` place toujours le qubit cible à l’état souhaité.</span><span class="sxs-lookup"><span data-stu-id="14338-151">This way, `SetQubitState` always puts the target qubit in the desired state.</span></span>

<span data-ttu-id="14338-152">Remplacez le contenu de `Program.qs` par le code suivant :</span><span class="sxs-lookup"><span data-stu-id="14338-152">Replace the contents of `Program.qs` with the following code:</span></span>


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

<span data-ttu-id="14338-153">Cette opération peut maintenant être appelée pour définir un qubit dans un état classique, en retournant soit `Zero` dans 100 % des cas, soit `One` dans 100 % des cas.</span><span class="sxs-lookup"><span data-stu-id="14338-153">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>
<span data-ttu-id="14338-154">`Zero` et `One` sont des constantes qui représentent les deux seuls résultats possibles d’une mesure de qubit.</span><span class="sxs-lookup"><span data-stu-id="14338-154">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

<span data-ttu-id="14338-155">L’opération `SetQubitState` mesure le qubit.</span><span class="sxs-lookup"><span data-stu-id="14338-155">The operation `SetQubitState` measures the qubit.</span></span> <span data-ttu-id="14338-156">Si le qubit est dans l’état souhaité, le `SetQubitState` laisse seul ; sinon, en exécutant l' `X` opération, nous modifions l’état de qubit à l’état souhaité.</span><span class="sxs-lookup"><span data-stu-id="14338-156">If the qubit is in the state we want, `SetQubitState` leaves it alone; otherwise, by running the `X` operation, we change the qubit state to the desired state.</span></span>

#### <a name="about-no-locq-operations"></a><span data-ttu-id="14338-157">À propos des Q# opérations</span><span class="sxs-lookup"><span data-stu-id="14338-157">About Q# operations</span></span>

<span data-ttu-id="14338-158">Une Q# opération est une sous-routine Quantum.</span><span class="sxs-lookup"><span data-stu-id="14338-158">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="14338-159">Autrement dit, il s’agit d’une routine pouvant être appelée qui contient des appels à d’autres opérations de Quantum.</span><span class="sxs-lookup"><span data-stu-id="14338-159">That is, it is a callable routine that contains calls to other quantum operations.</span></span>

<span data-ttu-id="14338-160">Les arguments pour une opération sont spécifiés sous forme de tuples, entre parenthèses.</span><span class="sxs-lookup"><span data-stu-id="14338-160">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="14338-161">Le type de retour de l’opération est spécifié après un signe deux points.</span><span class="sxs-lookup"><span data-stu-id="14338-161">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="14338-162">Dans ce cas, l' `SetQubitState` opération n’a pas de type de retour, donc elle est marquée comme retournant `Unit` .</span><span class="sxs-lookup"><span data-stu-id="14338-162">In this case, the `SetQubitState` operation has no return type, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="14338-163">Il s’agit Q# de l’équivalent de `unit` en F #, qui est à peu près similaire à `void` en C#, et d’un tuple vide dans Python ( `()` , représenté par l’indicateur de type `Tuple[()]` ).</span><span class="sxs-lookup"><span data-stu-id="14338-163">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple in Python (`()`, represented by the type hint `Tuple[()]`).</span></span>

<span data-ttu-id="14338-164">Vous avez utilisé deux opérations de Quantum dans votre première Q# opération :</span><span class="sxs-lookup"><span data-stu-id="14338-164">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="14338-165">L' [`M`](xref:Microsoft.Quantum.Intrinsic.m) opération, qui mesure l’état du qubit</span><span class="sxs-lookup"><span data-stu-id="14338-165">The [`M`](xref:Microsoft.Quantum.Intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="14338-166">[`X`](xref:Microsoft.Quantum.Intrinsic.X)Opération qui retourne l’état d’un qubit</span><span class="sxs-lookup"><span data-stu-id="14338-166">The [`X`](xref:Microsoft.Quantum.Intrinsic.X) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="14338-167">Une opération quantique transforme l’état d’un qubit.</span><span class="sxs-lookup"><span data-stu-id="14338-167">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="14338-168">Il arrive que les opérations quantiques soient appelées portes quantiques, par analogie avec les portes logiques classiques.</span><span class="sxs-lookup"><span data-stu-id="14338-168">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="14338-169">Cette désignation remonte aux débuts de l’informatique quantique quand les algorithmes n’étaient qu’une construction théorique visualisée sous forme de schémas à l’instar des schémas électriques en informatique classique.</span><span class="sxs-lookup"><span data-stu-id="14338-169">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="counting-measurement-outcomes"></a><span data-ttu-id="14338-170">Comptage des résultats de mesure</span><span class="sxs-lookup"><span data-stu-id="14338-170">Counting measurement outcomes</span></span>

<span data-ttu-id="14338-171">Pour démontrer l’effet de l’opération de `SetQubitState`, une opération de `TestBellState` est ensuite ajoutée.</span><span class="sxs-lookup"><span data-stu-id="14338-171">To demonstrate the effect of the `SetQubitState` operation, a `TestBellState` operation is then added.</span></span> <span data-ttu-id="14338-172">Cette opération prend comme entrée un `Zero` ou un `One`, puis appelle l’opération `SetQubitState` un certain nombre de fois avec cette entrée, puis compte le nombre de fois où `Zero` a été retourné par la mesure du qubit et le nombre de fois où `One` a été retourné.</span><span class="sxs-lookup"><span data-stu-id="14338-172">This operation takes as input a `Zero` or `One`, and calls the `SetQubitState` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="14338-173">Bien entendu, dans cette première simulation de l’opération `TestBellState`, nous nous attendons à ce que la sortie indique que toutes les mesures du qubit défini avec `Zero` comme entrée de paramètre retournent `Zero` et que toutes les mesures d’un qubit défini avec `One` comme entrée de paramètre retournent `One`.</span><span class="sxs-lookup"><span data-stu-id="14338-173">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span> <span data-ttu-id="14338-174">En outre, nous ajouterons du code à `TestBellState` pour illustrer la superposition et l’enchevêtrement.</span><span class="sxs-lookup"><span data-stu-id="14338-174">Further on, we’ll add code to `TestBellState` to demonstrate superposition and entanglement.</span></span>

<span data-ttu-id="14338-175">Ajoutez l’opération suivante au fichier `Program.qs`, à l’intérieur de l’espace de noms, une fois l’opération `SetQubitState` terminée :</span><span class="sxs-lookup"><span data-stu-id="14338-175">Add the following operation to the `Program.qs` file, inside the namespace, after the end of the `SetQubitState` operation:</span></span>

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
<span data-ttu-id="14338-176">Notez que nous avons ajouté une ligne avant le `return` pour imprimer un message explicatif dans la console avec la fonction ( `Message` ) [Microsoft. Quantum. Intrinsic. message]</span><span class="sxs-lookup"><span data-stu-id="14338-176">Note that we added a line before the `return` to print an explanatory message in the console with the function (`Message`)[microsoft.quantum.intrinsic.message]</span></span>

<span data-ttu-id="14338-177">Cette opération (`TestBellState`) effectuera une boucle de `count` itérations, définira une valeur `initial` spécifiée sur un qubit, puis mesurera (`M`) le résultat.</span><span class="sxs-lookup"><span data-stu-id="14338-177">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="14338-178">Elle rassemblera des statistiques sur le nombre de zéros et de uns que nous aurons mesurés et les renverra à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="14338-178">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="14338-179">Elle effectue une autre opération nécessaire.</span><span class="sxs-lookup"><span data-stu-id="14338-179">It performs one other necessary operation.</span></span> <span data-ttu-id="14338-180">Elle réinitialise le qubit dans un état connu (`Zero`) avant de le renvoyer pour permettre à d’autres de l’allouer dans un état connu.</span><span class="sxs-lookup"><span data-stu-id="14338-180">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="14338-181">C’est ce qu’exige l’instruction `using`.</span><span class="sxs-lookup"><span data-stu-id="14338-181">This is required by the `using` statement.</span></span>

#### <a name="about-variables-in-q"></a><span data-ttu-id="14338-182">À propos des variables dans Q\#</span><span class="sxs-lookup"><span data-stu-id="14338-182">About variables in Q\#</span></span>

<span data-ttu-id="14338-183">Par défaut, les variables dans Q# sont immuables ; leur valeur ne peut pas être modifiée une fois qu’elles sont liées.</span><span class="sxs-lookup"><span data-stu-id="14338-183">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="14338-184">Le mot clé `let` permet d’indiquer la liaison d’une variable immuable.</span><span class="sxs-lookup"><span data-stu-id="14338-184">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="14338-185">Les arguments d’opération sont toujours immuables.</span><span class="sxs-lookup"><span data-stu-id="14338-185">Operation arguments are always immutable.</span></span>

<span data-ttu-id="14338-186">Si vous avez besoin d’une variable dont la valeur puisse changer, telle que `numOnes` dans l’exemple, vous pouvez la déclarer avec le mot clé `mutable`.</span><span class="sxs-lookup"><span data-stu-id="14338-186">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="14338-187">Il est possible de modifier la valeur d’une variable muable à l’aide d’une instruction `set`.</span><span class="sxs-lookup"><span data-stu-id="14338-187">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="14338-188">Dans les deux cas, le type d’une variable est inféré par le compilateur.</span><span class="sxs-lookup"><span data-stu-id="14338-188">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="14338-189">Q# ne requiert pas d’annotations de type pour les variables.</span><span class="sxs-lookup"><span data-stu-id="14338-189">Q# doesn't require any type annotations for variables.</span></span>

#### <a name="about-using-statements-in-q"></a><span data-ttu-id="14338-190">À propos `using` des instructions dans Q\#</span><span class="sxs-lookup"><span data-stu-id="14338-190">About `using` statements in Q\#</span></span>

<span data-ttu-id="14338-191">L' `using` instruction est également spéciale à Q# .</span><span class="sxs-lookup"><span data-stu-id="14338-191">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="14338-192">Elle permet d’allouer des qubits à utiliser dans un bloc de code.</span><span class="sxs-lookup"><span data-stu-id="14338-192">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="14338-193">Dans Q# , tous les qubits sont alloués et libérés dynamiquement, au lieu d’être des ressources fixes qui s’y trouvent pour toute la durée de vie d’un algorithme complexe.</span><span class="sxs-lookup"><span data-stu-id="14338-193">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="14338-194">Une instruction `using` alloue un ensemble de qubits au début, puis libère ces qubits à la fin du bloc.</span><span class="sxs-lookup"><span data-stu-id="14338-194">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="run-the-code-from-the-command-prompt"></a><span data-ttu-id="14338-195">Exécuter le code à partir de l’invite de commandes</span><span class="sxs-lookup"><span data-stu-id="14338-195">Run the code from the command prompt</span></span>

<span data-ttu-id="14338-196">Pour exécuter le code, nous devons indiquer au compilateur *qu'* il est peut être appelé à s’exécuter quand nous fournissons la `dotnet run` commande.</span><span class="sxs-lookup"><span data-stu-id="14338-196">In order to run the code we need to tell the compiler *which* callable to run when we provide the `dotnet run` command.</span></span> <span data-ttu-id="14338-197">Pour ce faire, il suffit de modifier le Q# fichier en ajoutant une ligne qui `@EntryPoint()` précède directement l’appelable : l' `TestBellState` opération dans ce cas.</span><span class="sxs-lookup"><span data-stu-id="14338-197">This is done with a simple change in the Q# file by adding a line with `@EntryPoint()` directly preceding the callable: the `TestBellState` operation in this case.</span></span> <span data-ttu-id="14338-198">Le code complet doit être :</span><span class="sxs-lookup"><span data-stu-id="14338-198">The full code should be:</span></span>

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

<span data-ttu-id="14338-199">Pour exécuter le programme, vous devez spécifier `count` les `initial` arguments et à partir de l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="14338-199">To run the program we need to specify `count` and `initial` arguments from the command prompt.</span></span> <span data-ttu-id="14338-200">Nous allons choisir exemple `count = 1000` et `initial = One` .</span><span class="sxs-lookup"><span data-stu-id="14338-200">Let's choose for example `count = 1000` and `initial = One`.</span></span> <span data-ttu-id="14338-201">Entrez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="14338-201">Enter the following command:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

<span data-ttu-id="14338-202">Et vous devez observer la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="14338-202">And you should observe the following output:</span></span>

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="14338-203">Si vous essayez avec, `initial = Zero` vous devez observer :</span><span class="sxs-lookup"><span data-stu-id="14338-203">If you try with `initial = Zero` you should observe:</span></span>

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a><span data-ttu-id="14338-204">Préparer la superposition</span><span class="sxs-lookup"><span data-stu-id="14338-204">Prepare superposition</span></span>

<span data-ttu-id="14338-205">Voyons maintenant comment Q# exprime les moyens de mettre qubits en superposition.</span><span class="sxs-lookup"><span data-stu-id="14338-205">Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="14338-206">Rappelez-vous que l’état d’un qubit peut être dans une superposition de 0 et de 1.</span><span class="sxs-lookup"><span data-stu-id="14338-206">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="14338-207">Nous allons utiliser l’opération `Hadamard` dans ce but.</span><span class="sxs-lookup"><span data-stu-id="14338-207">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="14338-208">Si le qubit est dans l’un des états classiques (quand une mesure retourne toujours `Zero` ou toujours `One`), alors l’opération `Hadamard` ou `H` le place dans un état où une mesure du qubit retourne `Zero` dans 50 % des cas et `One` dans 50 % des cas.</span><span class="sxs-lookup"><span data-stu-id="14338-208">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="14338-209">D’un point de vue conceptuel, le qubit peut être considéré à mi-chemin entre `Zero` et `One`.</span><span class="sxs-lookup"><span data-stu-id="14338-209">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="14338-210">Maintenant, quand nous simulons l’opération `TestBellState`, nous voyons que les résultats retournent grosso modo un nombre égal de `Zero` et de `One` après la mesure.</span><span class="sxs-lookup"><span data-stu-id="14338-210">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

### <a name="x-flips-qubit-state"></a><span data-ttu-id="14338-211">`X` retourne l’État qubit</span><span class="sxs-lookup"><span data-stu-id="14338-211">`X` flips qubit state</span></span>

<span data-ttu-id="14338-212">Tout d’abord, nous allons simplement essayer de retourner le qubit (si le qubit est dans l’État dans lequel `Zero` il se renverse `One` et vice versa).</span><span class="sxs-lookup"><span data-stu-id="14338-212">First we'll just try to flip the qubit (if the qubit is in `Zero` state it will flip to `One` and vice versa).</span></span> <span data-ttu-id="14338-213">Pour cela, une opération `X` est nécessaire avant d’effectuer la mesure dans `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="14338-213">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="14338-214">Désormais, les résultats sont inversés :</span><span class="sxs-lookup"><span data-stu-id="14338-214">Now the results are reversed:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="14338-215">À présent, nous allons explorer les propriétés Quantum du qubits.</span><span class="sxs-lookup"><span data-stu-id="14338-215">Now let's explore the quantum properties of the qubits.</span></span>

### <a name="h-prepares-superposition"></a><span data-ttu-id="14338-216">`H` prépare la superposition</span><span class="sxs-lookup"><span data-stu-id="14338-216">`H` prepares superposition</span></span>

<span data-ttu-id="14338-217">Il nous suffit de remplacer l’opération `X` dans l’exécution précédente par une opération `H` ou Hadamard.</span><span class="sxs-lookup"><span data-stu-id="14338-217">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="14338-218">Au lieu d’inverser entièrement le qubit de 0 à 1, nous allons ne l’inverser qu’à moitié.</span><span class="sxs-lookup"><span data-stu-id="14338-218">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="14338-219">Les lignes remplacées dans `TestBellState` ressemblent maintenant à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="14338-219">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="14338-220">Les résultats deviennent à présent plus intéressants :</span><span class="sxs-lookup"><span data-stu-id="14338-220">Now the results get more interesting:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

<span data-ttu-id="14338-221">Chaque fois que nous mesurons, nous demandons une valeur classique mais le qubit étant à mi-chemin entre 0 et 1, nous obtenons (statistiquement) 0 la moitié du temps et 1 l’autre moitié du temps.</span><span class="sxs-lookup"><span data-stu-id="14338-221">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span>
<span data-ttu-id="14338-222">C’est ce qu’on appelle une **superposition** , qui nous donne une première vue réelle d’un état quantique.</span><span class="sxs-lookup"><span data-stu-id="14338-222">This is known as **superposition** and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="14338-223">Préparer l’intrication</span><span class="sxs-lookup"><span data-stu-id="14338-223">Prepare entanglement</span></span>

<span data-ttu-id="14338-224">Voyons maintenant comment Q# exprime les méthodes de qubits.</span><span class="sxs-lookup"><span data-stu-id="14338-224">Now let’s look at how Q# expresses ways to entangle qubits.</span></span>
<span data-ttu-id="14338-225">Tout d’abord, nous définissons le premier qubit sur l’état initial, puis nous utilisons l’opération `H` pour le placer en superposition.</span><span class="sxs-lookup"><span data-stu-id="14338-225">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="14338-226">Ensuite, avant de mesurer le premier qubit, nous utilisons une nouvelle opération ( `CNOT` ), qui signifie *contrôlé-not* .</span><span class="sxs-lookup"><span data-stu-id="14338-226">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for *Controlled-NOT* .</span></span>  <span data-ttu-id="14338-227">Le résultat de l’exécution de cette opération sur deux qubits consiste à retourner le deuxième qubit si le premier qubit est `One` .</span><span class="sxs-lookup"><span data-stu-id="14338-227">The result of running this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="14338-228">À présent, les deux qubits sont intriqués.</span><span class="sxs-lookup"><span data-stu-id="14338-228">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="14338-229">Nos statistiques pour le premier qubit n’ont pas changé (autant de `Zero` que de `One` après la mesure). En revanche, quand nous mesurons le second qubit, le résultat est __toujours__ identique à celui obtenu pour le premier.</span><span class="sxs-lookup"><span data-stu-id="14338-229">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="14338-230">Notre `CNOT` a intriqué les deux qubits de sorte que ce qui arrive à l’un arrive également à l’autre.</span><span class="sxs-lookup"><span data-stu-id="14338-230">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="14338-231">Si vous inversiez les mesures (deuxième qubit avant le premier), la même chose se produirait.</span><span class="sxs-lookup"><span data-stu-id="14338-231">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="14338-232">La première mesure serait aléatoire et la seconde irait de pair avec la première.</span><span class="sxs-lookup"><span data-stu-id="14338-232">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="14338-233">La première chose à faire est d’allouer deux qubits au lieu d’un dans `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="14338-233">The first thing we'll need to do is allocate two qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="14338-234">Cela nous permettra d’ajouter une nouvelle opération (`CNOT`) avant de mesurer (`M`) dans `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="14338-234">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="14338-235">Nous avons ajouté une autre opération `SetQubitState` pour initialiser le premier qubit afin de nous assurer qu’il est toujours à l’état `Zero` au démarrage.</span><span class="sxs-lookup"><span data-stu-id="14338-235">We've added another `SetQubitState` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="14338-236">Nous devons également réinitialiser le deuxième qubit avant de le libérer.</span><span class="sxs-lookup"><span data-stu-id="14338-236">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

<span data-ttu-id="14338-237">La routine complète ressemble maintenant à ceci :</span><span class="sxs-lookup"><span data-stu-id="14338-237">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="14338-238">Si nous l’exécutons, nous obtiendrons exactement le même résultat 50/50 que celui obtenu auparavant.</span><span class="sxs-lookup"><span data-stu-id="14338-238">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="14338-239">Cependant, ce qui nous intéresse, c’est la réaction du deuxième qubit à la mesure du premier.</span><span class="sxs-lookup"><span data-stu-id="14338-239">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="14338-240">Nous ajouterons cette statistique avec une nouvelle version de l’opération `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="14338-240">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

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
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="14338-241">La nouvelle valeur renvoyée (`agree`) conserve une trace de chaque fois que la mesure du premier qubit correspond à la mesure du deuxième.</span><span class="sxs-lookup"><span data-stu-id="14338-241">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span>

<span data-ttu-id="14338-242">Exécution du code que nous obtenons :</span><span class="sxs-lookup"><span data-stu-id="14338-242">Running the code we obtain:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

<span data-ttu-id="14338-243">Comme indiqué dans la vue d’ensemble, nos statistiques pour le premier qubit n’ont pas changé (autant de 0 que de 1). En revanche, quand nous mesurons le second qubit, le résultat est __toujours__ identique à celui obtenu pour le premier, parce qu’ils sont intriqués.</span><span class="sxs-lookup"><span data-stu-id="14338-243">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

## <a name="next-steps"></a><span data-ttu-id="14338-244">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="14338-244">Next steps</span></span>

<span data-ttu-id="14338-245">La [recherche du didacticiel Grover](xref:microsoft.quantum.quickstarts.search) vous montre comment créer et exécuter Grover Search, l’un des algorithmes Quantum les plus populaires et offre un bon exemple de Q# programme qui peut être utilisé pour résoudre des problèmes réels avec quantum computing.</span><span class="sxs-lookup"><span data-stu-id="14338-245">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="14338-246">[La prise en main du kit de développement Quantum](xref:microsoft.quantum.welcome) vous recommande davantage de méthodes pour apprendre Q# et programmer la programmation.</span><span class="sxs-lookup"><span data-stu-id="14338-246">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
