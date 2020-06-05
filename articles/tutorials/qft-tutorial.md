---
title: 'Écrire et simuler des programmes de niveau qubit dans Q #'
description: Didacticiel pas à pas sur l’écriture et la simulation d’un programme Quantum fonctionnant au niveau qubit individuel
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
ms.openlocfilehash: 05d3292e1c6e3c8c1163c460f2aaa51c591aa1d5
ms.sourcegitcommit: 8d9d392bf5e114ae223e6f689ba80d25866ff586
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84422238"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a><span data-ttu-id="9b184-103">Didacticiel : écrire et simuler des programmes de niveau qubit dans Q\#</span><span class="sxs-lookup"><span data-stu-id="9b184-103">Tutorial: Write and simulate qubit-level programs in Q\#</span></span>

<span data-ttu-id="9b184-104">Bienvenue dans le didacticiel du kit de développement quantique sur l’écriture et la simulation d’un programme Quantum de base qui fonctionne sur des qubits individuels.</span><span class="sxs-lookup"><span data-stu-id="9b184-104">Welcome to the Quantum Development Kit tutorial on writing and simulating a basic quantum program that operates on individual qubits.</span></span> 

<span data-ttu-id="9b184-105">Même si Q # a été principalement créé en tant que langage de programmation de haut niveau pour les programmes quantiques à grande échelle, il peut tout aussi facilement être utilisé pour explorer le niveau inférieur de programmes Quantum : en traitant directement des qubits spécifiques.</span><span class="sxs-lookup"><span data-stu-id="9b184-105">Although Q# was primarily created as a high-level programming language for large-scale quantum programs, it can just as easily be used to explore the lower level of quantum programs: directly addressing specific qubits.</span></span>
<span data-ttu-id="9b184-106">La flexibilité de Q # permet aux utilisateurs d’aborder les systèmes quantiques à partir de n’importe quel niveau d’abstraction, et dans ce didacticiel, nous explorons les qubits eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="9b184-106">The flexibility of Q# allows users to approach quantum systems from any such level of abstraction, and in this tutorial we dive into the qubits themselves.</span></span>
<span data-ttu-id="9b184-107">Plus précisément, nous examinons le capot de la [transformation de Fourier quantique](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), une sous-routine qui fait partie intégrante de nombreux algorithmes quantiques plus volumineux.</span><span class="sxs-lookup"><span data-stu-id="9b184-107">Specifically, we take a look under the hood of the [quantum Fourier transform](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), a subroutine that is integral to many larger quantum algorithms.</span></span>

<span data-ttu-id="9b184-108">Notez que cette vue de bas niveau du traitement des informations de Quantum est souvent décrite en termes de «[circuits quantiques](xref:microsoft.quantum.concepts.circuits)», qui représentent l’application séquentielle des portes à des qubits spécifiques d’un système.</span><span class="sxs-lookup"><span data-stu-id="9b184-108">Note that this low-level view of quantum information processing is often described in terms of "[quantum circuits](xref:microsoft.quantum.concepts.circuits)," which represent the sequential application of gates to specific qubits of a system.</span></span>

<span data-ttu-id="9b184-109">Par conséquent, les opérations Single et qubit que nous appliquons séquentiellement peuvent être facilement représentées dans un « diagramme de circuit ».</span><span class="sxs-lookup"><span data-stu-id="9b184-109">Thus, the single- and multi-qubit operations we sequentially apply can be readily represented in a "circuit diagram."</span></span>
<span data-ttu-id="9b184-110">Dans notre cas, nous allons définir une opération Q # pour effectuer la transformation de Fourier quantique qubit complète, qui présente la représentation suivante sous la forme d’un circuit :</span><span class="sxs-lookup"><span data-stu-id="9b184-110">In our case, we will define a Q# operation to perform the full three-qubit quantum Fourier transform, which has the following representation as a circuit:</span></span>

<br/>
<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a><span data-ttu-id="9b184-111">Prérequis</span><span class="sxs-lookup"><span data-stu-id="9b184-111">Prerequisites</span></span>

* <span data-ttu-id="9b184-112">[Installez](xref:microsoft.quantum.install) le kit de développement quantique à l’aide de votre langue et de votre environnement de développement préférés.</span><span class="sxs-lookup"><span data-stu-id="9b184-112">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment.</span></span>
* <span data-ttu-id="9b184-113">Si le QDK est déjà installé, assurez-vous que vous l’avez [mis à jour](xref:microsoft.quantum.update) avec la dernière version</span><span class="sxs-lookup"><span data-stu-id="9b184-113">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>


## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="9b184-114">Ce didacticiel vous montre comment effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b184-114">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="9b184-115">Définir des opérations de Quantum dans Q #</span><span class="sxs-lookup"><span data-stu-id="9b184-115">Define quantum operations in Q#</span></span>
> * <span data-ttu-id="9b184-116">Appeler des opérations Q # directement à partir de la ligne de commande ou à l’aide d’un programme hôte classique</span><span class="sxs-lookup"><span data-stu-id="9b184-116">Call Q# operations directly from the command line or using a classical host program</span></span>
> * <span data-ttu-id="9b184-117">Simuler une opération de quantum de l’allocation qubit à la sortie de mesure</span><span class="sxs-lookup"><span data-stu-id="9b184-117">Simulate a quantum operation from qubit allocation to measurement output</span></span>
> * <span data-ttu-id="9b184-118">Observer la manière dont le wavefunction simulé du système Quantum évolue tout au long de l’opération</span><span class="sxs-lookup"><span data-stu-id="9b184-118">Observe how the quantum system's simulated wavefunction evolves throughout the operation</span></span>

<span data-ttu-id="9b184-119">L’exécution d’un programme Quantum avec le kit de développement Quantum de Microsoft se compose généralement de deux parties :</span><span class="sxs-lookup"><span data-stu-id="9b184-119">Running a quantum program with Microsoft's Quantum Development Kit typically consists of two parts:</span></span>
1. <span data-ttu-id="9b184-120">Le programme lui-même, qui est implémenté à l’aide du langage de programmation Q # Quantum, puis appelé pour s’exécuter sur un ordinateur Quantum ou un simulateur Quantum.</span><span class="sxs-lookup"><span data-stu-id="9b184-120">The program itself, which is implemented using the Q# quantum programming language, and then invoked to run on a quantum computer or quantum simulator.</span></span> <span data-ttu-id="9b184-121">Il s’agit de</span><span class="sxs-lookup"><span data-stu-id="9b184-121">These consist of</span></span> 
    - <span data-ttu-id="9b184-122">Opérations Q # : sous-routines agissant sur des registres quantiques et</span><span class="sxs-lookup"><span data-stu-id="9b184-122">Q# operations: subroutines acting on quantum registers, and</span></span> 
    - <span data-ttu-id="9b184-123">Fonctions Q # : sous-routines classiques utilisées dans l’algorithme Quantum.</span><span class="sxs-lookup"><span data-stu-id="9b184-123">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="9b184-124">Point d’entrée utilisé pour appeler le programme Quantum et spécifier l’ordinateur cible sur lequel il doit être exécuté.</span><span class="sxs-lookup"><span data-stu-id="9b184-124">The entry point used to call the quantum program and specify the target machine on which it should be run.</span></span>
    <span data-ttu-id="9b184-125">Cela peut être effectué directement à partir de la ligne de commande ou par le biais d’un programme hôte écrit dans un langage de programmation classique comme Python ou C#.</span><span class="sxs-lookup"><span data-stu-id="9b184-125">This can be done directly from the command line, or through a host program written in a classical programming language like Python or C#.</span></span>
    <span data-ttu-id="9b184-126">Ce didacticiel comprend des instructions sur la méthode que vous préférez.</span><span class="sxs-lookup"><span data-stu-id="9b184-126">This tutorial includes instructions for whichever method you prefer.</span></span>

## <a name="allocate-qubits-and-define-quantum-operations"></a><span data-ttu-id="9b184-127">Allouer des qubits et définir des opérations de Quantum</span><span class="sxs-lookup"><span data-stu-id="9b184-127">Allocate qubits and define quantum operations</span></span>

<span data-ttu-id="9b184-128">La première partie de ce didacticiel consiste à définir l’opération Q # `Perform3qubitQFT` , qui exécute la transformation de Fourier quantique sur trois qubits.</span><span class="sxs-lookup"><span data-stu-id="9b184-128">The first part of this tutorial consists of defining the Q# operation `Perform3qubitQFT`, which performs the quantum Fourier transform on three qubits.</span></span> 

<span data-ttu-id="9b184-129">En outre, nous allons utiliser la [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) fonction pour observer la façon dont la wavefunction simulée de nos trois systèmes qubit évolue au fil de l’opération.</span><span class="sxs-lookup"><span data-stu-id="9b184-129">In addition, we will use the [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) function to observe how the simulated wavefunction of our three qubit system evolves across the operation.</span></span>

<span data-ttu-id="9b184-130">La première étape consiste à créer votre projet et fichier Q #.</span><span class="sxs-lookup"><span data-stu-id="9b184-130">The first step is creating your Q# project and file.</span></span>
<span data-ttu-id="9b184-131">La procédure à suivre dépend de l’environnement que vous allez utiliser pour appeler le programme et vous pouvez trouver les détails dans les [guides d’installation](xref:microsoft.quantum.install)respectifs.</span><span class="sxs-lookup"><span data-stu-id="9b184-131">The steps for this depend on the environment you will use to call the program, and you can find the details in the respective [installation guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="9b184-132">Nous vous guiderons pas à pas dans les composants du fichier, mais le code est également disponible sous la forme d’un bloc complet ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9b184-132">We will walk you through the components of the file step-by-step, but the code is also available as a full block below.</span></span>

### <a name="namespaces-to-access-other-q-operations"></a><span data-ttu-id="9b184-133">Espaces de noms pour accéder aux autres opérations Q #</span><span class="sxs-lookup"><span data-stu-id="9b184-133">Namespaces to access other Q# operations</span></span>
<span data-ttu-id="9b184-134">Dans le fichier, nous commençons par définir l’espace de noms `NamespaceQFT` qui sera accessible par le compilateur.</span><span class="sxs-lookup"><span data-stu-id="9b184-134">Inside the file, we first define the namespace `NamespaceQFT` which will be accessed by the compiler.</span></span>
<span data-ttu-id="9b184-135">Pour que notre opération utilise des opérations Q # existantes, nous allons ouvrir les `Microsoft.Quantum.<>` espaces de noms appropriés.</span><span class="sxs-lookup"><span data-stu-id="9b184-135">For our operation to make use of existing Q# operations, we open the relevant `Microsoft.Quantum.<>` namespaces.</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a><span data-ttu-id="9b184-136">Définir des opérations avec des arguments et des retours</span><span class="sxs-lookup"><span data-stu-id="9b184-136">Define operations with arguments and returns</span></span>
<span data-ttu-id="9b184-137">Ensuite, nous définissons l' `Perform3qubitQFT` opération :</span><span class="sxs-lookup"><span data-stu-id="9b184-137">Next, we define the `Perform3qubitQFT` operation:</span></span>

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

<span data-ttu-id="9b184-138">Pour le moment, l’opération n’accepte aucun argument et ne retourne rien---dans ce cas, nous écrivons qu’elle retourne un `Unit` objet, qui est semblable à `void` en C# ou à un tuple vide, `Tuple[()]` , dans Python.</span><span class="sxs-lookup"><span data-stu-id="9b184-138">For now, the operation takes no arguments and does not return anything---in this case we write that it returns a `Unit` object, which is akin to `void` in C# or an empty tuple, `Tuple[()]`, in Python.</span></span>
<span data-ttu-id="9b184-139">Plus tard, nous la modifierons pour retourner un tableau de résultats de mesure, à partir duquel le point `Unit` sera remplacé par `Result[]` .</span><span class="sxs-lookup"><span data-stu-id="9b184-139">Later, we will modify it to return an array of measurement results, at which point `Unit` will be replaced by `Result[]`.</span></span> 

### <a name="allocate-qubits-with-using"></a><span data-ttu-id="9b184-140">Allouer qubits avec`using`</span><span class="sxs-lookup"><span data-stu-id="9b184-140">Allocate qubits with `using`</span></span>
<span data-ttu-id="9b184-141">Dans le cadre de notre opération Q #, nous allouez d’abord un registre de trois qubits à l’aide de l' `using` instruction :</span><span class="sxs-lookup"><span data-stu-id="9b184-141">Within our Q# operation, we first allocate a register of three qubits with the `using` statement:</span></span>

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

<span data-ttu-id="9b184-142">Avec `using` , les qubits sont automatiquement alloués dans l' {0} État $ \ket $.</span><span class="sxs-lookup"><span data-stu-id="9b184-142">With `using`, the qubits are automatically allocated in the $\ket{0}$ state.</span></span> <span data-ttu-id="9b184-143">Nous pouvons vérifier cela à l’aide de [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) et [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , qui impriment une chaîne et l’état actuel du système sur la console.</span><span class="sxs-lookup"><span data-stu-id="9b184-143">We can verify this by using [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) and [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine), which print a string and the system's current state to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="9b184-144">Les `Message(<string>)` `DumpMachine()` fonctions et (à partir de [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) et [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) , respectivement) s’impriment directement sur la console.</span><span class="sxs-lookup"><span data-stu-id="9b184-144">The `Message(<string>)` and `DumpMachine()` functions (from [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics), respectively) both print directly to the console.</span></span> <span data-ttu-id="9b184-145">Tout comme un véritable calcul Quantum, Q # ne nous permet pas d’accéder directement aux États qubit.</span><span class="sxs-lookup"><span data-stu-id="9b184-145">Just like a real quantum computation, Q# does not allow us to directly access qubit states.</span></span>
> <span data-ttu-id="9b184-146">Toutefois, comme `DumpMachine` imprime l’état actuel de l’ordinateur cible, il peut fournir des informations précieuses sur le débogage et l’apprentissage lorsqu’il est utilisé conjointement avec le simulateur d’état complet.</span><span class="sxs-lookup"><span data-stu-id="9b184-146">However, as `DumpMachine` prints the target machine's current state, it can provide valuable insight for debugging and learning when used in conjunction with the full state simulator.</span></span>


### <a name="applying-single-qubit-and-controlled-gates"></a><span data-ttu-id="9b184-147">Application de portes qubit et contrôlées</span><span class="sxs-lookup"><span data-stu-id="9b184-147">Applying single-qubit and controlled gates</span></span>

<span data-ttu-id="9b184-148">Ensuite, nous appliquons les portes qui composent l’opération elle-même.</span><span class="sxs-lookup"><span data-stu-id="9b184-148">Next, we apply the gates which comprise the operation itself.</span></span>
<span data-ttu-id="9b184-149">Q # contient déjà de nombreuses portes de quantum de base en tant qu’opérations dans l' [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) espace de noms, et il ne s’agit pas d’une exception.</span><span class="sxs-lookup"><span data-stu-id="9b184-149">Q# already contains many basic quantum gates as operations in the [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) namespace, and these are no exception.</span></span> 

<span data-ttu-id="9b184-150">Dans une opération Q #, les instructions qui appellent callables sont bien entendu exécutées dans un ordre séquentiel.</span><span class="sxs-lookup"><span data-stu-id="9b184-150">Within a Q# operation, the statements invoking callables will of course be executed in sequential order.</span></span>
<span data-ttu-id="9b184-151">Par conséquent, la première porte à appliquer est le [`H`](xref:microsoft.quantum.intrinsic.h) (hadarmard) au premier qubit :</span><span class="sxs-lookup"><span data-stu-id="9b184-151">Hence, the first gate to apply is the [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) to the first qubit:</span></span>

<br/>
<img src="./qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

<span data-ttu-id="9b184-152">Pour appliquer une opération à un qubit spécifique à partir d’un registre (c’est-à-dire un unique `Qubit` d’un tableau `Qubit[]` ), nous utilisons la notation d’index standard.</span><span class="sxs-lookup"><span data-stu-id="9b184-152">To apply an operation to a specific qubit from a register (i.e. a single `Qubit` from an array `Qubit[]`) we use standard index notation.</span></span>
<span data-ttu-id="9b184-153">Ainsi, l’application du [`H`](xref:microsoft.quantum.intrinsic.h) au premier qubit de notre Registre `qs` prend la forme suivante :</span><span class="sxs-lookup"><span data-stu-id="9b184-153">So, applying the [`H`](xref:microsoft.quantum.intrinsic.h) to the first qubit of our register `qs` takes the form:</span></span>

```qsharp
            H(qs[0]);
```

<span data-ttu-id="9b184-154">Outre l’application de la `H` porte (hadarmard) à des qubits individuels, le circuit QFT se compose principalement de [`R1`](xref:microsoft.quantum.intrinsic.r1) rotations contrôlées.</span><span class="sxs-lookup"><span data-stu-id="9b184-154">Besides applying the `H` (Hadamard) gate to individual qubits, the QFT circuit consists primarily of controlled [`R1`](xref:microsoft.quantum.intrinsic.r1) rotations.</span></span>
<span data-ttu-id="9b184-155">Une `R1(θ, <qubit>)` opération en général laisse le composant $ \ket {0} $ du qubit inchangé, tout en appliquant une rotation de $e ^ {i\theta} $ au composant $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="9b184-155">An `R1(θ, <qubit>)` operation in general leaves the $\ket{0}$ component of the qubit unchanged, while applying a rotation of $e^{i\theta}$ to the $\ket{1}$ component.</span></span>

#### <a name="controlled-operations"></a><span data-ttu-id="9b184-156">Opérations contrôlées</span><span class="sxs-lookup"><span data-stu-id="9b184-156">Controlled operations</span></span>

<span data-ttu-id="9b184-157">Q # rend très facile la condition de l’exécution d’une opération sur un ou plusieurs qubits de contrôle.</span><span class="sxs-lookup"><span data-stu-id="9b184-157">Q# makes it extremely easy to condition the execution of an operation upon one or multiple control qubits.</span></span>
<span data-ttu-id="9b184-158">En général, nous prévoyons simplement l’appel avec `Controlled` , et les arguments d’opération changent comme suit :</span><span class="sxs-lookup"><span data-stu-id="9b184-158">In general, we merely preface the call with `Controlled`, and the operation arguments change as:</span></span>

 <span data-ttu-id="9b184-159">`Op(<normal args>)`$ \To $ `Controlled Op([<control qubits>], (<normal args>))` .</span><span class="sxs-lookup"><span data-stu-id="9b184-159">`Op(<normal args>)` $\to$ `Controlled Op([<control qubits>], (<normal args>))`.</span></span>

<span data-ttu-id="9b184-160">Notez que le contrôle qubits doit être fourni sous la forme d’un tableau, même s’il s’agit d’un qubit unique.</span><span class="sxs-lookup"><span data-stu-id="9b184-160">Note that the control qubits must be provided as an array, even if it is a single qubit.</span></span>

<span data-ttu-id="9b184-161">Après `H` , nous voyons que les portes suivantes sont les `R1` portes agissant sur le premier qubit (et contrôlées par le deuxième/troisième) :</span><span class="sxs-lookup"><span data-stu-id="9b184-161">After the `H`, we see that the next gates are the `R1` gates acting on the first qubit (and controlled by the second/third):</span></span>

<br/>
<img src="./qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

<span data-ttu-id="9b184-162">Nous les appelons avec</span><span class="sxs-lookup"><span data-stu-id="9b184-162">We call these with</span></span>

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

<span data-ttu-id="9b184-163">Notez que nous utilisons la [`PI()`](xref:microsoft.quantum.math.pi) fonction à partir de l' [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) espace de noms pour définir les rotations en termes de pi radians.</span><span class="sxs-lookup"><span data-stu-id="9b184-163">Note that we use the [`PI()`](xref:microsoft.quantum.math.pi) function from the [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namespace to define the rotations in terms of pi radians.</span></span>
<span data-ttu-id="9b184-164">En outre, nous divisez par un `Double` (par exemple `2.0` ), car la division par un entier `2` lèvera une erreur de type.</span><span class="sxs-lookup"><span data-stu-id="9b184-164">Additionally, we divide by a `Double` (e.g. `2.0`) because dividing by an integer `2` would throw a type error.</span></span> 

> [!TIP]
> <span data-ttu-id="9b184-165">`R1(π/2)`et `R1(π/4)` sont équivalents aux `S` `T` opérations et (également dans `Microsoft.Quantum.Intrinsic` ).</span><span class="sxs-lookup"><span data-stu-id="9b184-165">`R1(π/2)` and `R1(π/4)` are equivalent to the `S` and `T` operations (also in `Microsoft.Quantum.Intrinsic`).</span></span>


<span data-ttu-id="9b184-166">Après avoir appliqué les `H` opérations pertinentes et les rotations contrôlées aux deuxième et troisième qubits :</span><span class="sxs-lookup"><span data-stu-id="9b184-166">After applying the relevant `H` operations and controlled rotations to the second and third qubits:</span></span>

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

<span data-ttu-id="9b184-167">Nous avons uniquement besoin d’appliquer une [`SWAP`](xref:microsoft.quantum.intrinsic.swap) porte pour terminer le circuit :</span><span class="sxs-lookup"><span data-stu-id="9b184-167">we need only apply a [`SWAP`](xref:microsoft.quantum.intrinsic.swap) gate to complete the circuit:</span></span>

```qsharp
            SWAP(qs[2], qs[0]);
```

<span data-ttu-id="9b184-168">Cela est nécessaire, car la nature de la transformation de Fourier quantique retourne le qubits dans l’ordre inverse, de sorte que les échanges permettent une intégration transparente de la sous-routine dans des algorithmes plus volumineux.</span><span class="sxs-lookup"><span data-stu-id="9b184-168">This is necessary because the nature of the quantum Fourier transform outputs the qubits in reverse order, so the swaps allow for seamless integration of the subroutine into larger algorithms.</span></span>

<span data-ttu-id="9b184-169">Nous avons donc fini d’écrire les opérations de niveau qubit de la transformation de Fourier quantique dans notre opération Q # :</span><span class="sxs-lookup"><span data-stu-id="9b184-169">Hence we have finished writing the qubit-level operations of the quantum Fourier transform into our Q# operation:</span></span>

<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

<span data-ttu-id="9b184-170">Toutefois, nous ne pouvons pas l’appeler une journée pour l’instant.</span><span class="sxs-lookup"><span data-stu-id="9b184-170">However, we can't call it a day just yet.</span></span>
<span data-ttu-id="9b184-171">Nos qubits étaient dans l’État $ \ket {0} $ lorsque nous les avons alloués, et comme dans la vie, en Q # nous devrions garder des choses de la même façon que nous les avons trouvées (ou mieux !).</span><span class="sxs-lookup"><span data-stu-id="9b184-171">Our qubits were in state $\ket{0}$ when we allocated them, and much like in life, in Q# we should leave things the same way we found them (or better!).</span></span>

### <a name="deallocate-qubits"></a><span data-ttu-id="9b184-172">Libérer qubits</span><span class="sxs-lookup"><span data-stu-id="9b184-172">Deallocate qubits</span></span>

<span data-ttu-id="9b184-173">Nous appelons à [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) nouveau pour voir l’état de la suite de l’opération. Enfin, s’applique [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) au registre qubit pour réinitialiser notre qubits à $ \ket {0} $ avant d’effectuer l’opération :</span><span class="sxs-lookup"><span data-stu-id="9b184-173">We call [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) again to see the post-operation state, and finally apply [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) to the qubit register to reset our qubits to $\ket{0}$ before completing the operation:</span></span>

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

<span data-ttu-id="9b184-174">Exiger que tous les qubits désalloués soient explicitement définis sur $ \ket {0} $ est une fonctionnalité de base de Q #, car il permet à d’autres opérations de connaître précisément leur état lorsqu’ils commencent à utiliser ces mêmes qubits (une ressource rare).</span><span class="sxs-lookup"><span data-stu-id="9b184-174">Requiring that all deallocated qubits be explicitly set to $\ket{0}$ is a basic feature of Q#, as it allows other operations to know their state precisely when they begin using those same qubits (a scarce resource).</span></span>
<span data-ttu-id="9b184-175">En outre, cela garantit qu’ils ne sont pas associés à d’autres qubits dans le système.</span><span class="sxs-lookup"><span data-stu-id="9b184-175">Additionally, this assures that they not be entangled with any other qubits in the system.</span></span>
<span data-ttu-id="9b184-176">Si la réinitialisation n’est pas effectuée à la fin d’un `using` bloc d’allocation, une erreur d’exécution est générée.</span><span class="sxs-lookup"><span data-stu-id="9b184-176">If the reset is not performed at the end of a `using` allocation block, a runtime error will be thrown.</span></span>

<span data-ttu-id="9b184-177">Votre fichier Q # complet doit maintenant ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="9b184-177">Your full Q# file should now look like this:</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


<span data-ttu-id="9b184-178">Une fois le fichier Q # et l’opération terminées, notre programme Quantum est prêt à être appelé et simulé.</span><span class="sxs-lookup"><span data-stu-id="9b184-178">With the Q# file and operation complete, our quantum program is ready to be called and simulated.</span></span>

## <a name="execute-the-program"></a><span data-ttu-id="9b184-179">Exécuter le programme</span><span class="sxs-lookup"><span data-stu-id="9b184-179">Execute the program</span></span>

<span data-ttu-id="9b184-180">Après avoir défini notre opération Q # dans un `.qs` fichier, nous devons maintenant appeler cette opération et observer toutes les données classiques retournées.</span><span class="sxs-lookup"><span data-stu-id="9b184-180">Having defined our Q# operation in a `.qs` file, we now need to call that operation and observe any returned classical data.</span></span>
<span data-ttu-id="9b184-181">Pour le moment, aucun résultat n’est renvoyé (Rappelez-vous que notre opération définie ci-dessus retourne `Unit` ), mais lorsque nous modifions ultérieurement l’opération Q # pour retourner un tableau de résultats de mesure ( `Result[]` ), nous allons résoudre ce point.</span><span class="sxs-lookup"><span data-stu-id="9b184-181">For now, there isn't anything returned (recall that our operation defined above returns `Unit`), but when we later modify the Q# operation to return an array of measurement results (`Result[]`), we will address this.</span></span>

<span data-ttu-id="9b184-182">Bien que le programme Q # soit omniprésent dans les environnements utilisés pour l’appeler, le mode de fonctionnement est bien sûr différent.</span><span class="sxs-lookup"><span data-stu-id="9b184-182">While the Q# program is ubiquitous across the environments used to call it, the manner of doing so will of course vary.</span></span> <span data-ttu-id="9b184-183">Par conséquent, suivez simplement les instructions de l’onglet correspondant à votre configuration : utilisation de l’application de ligne de commande Q # ou utilisation d’un programme hôte en Python ou C#.</span><span class="sxs-lookup"><span data-stu-id="9b184-183">As such, simply follow the instructions in the tab corresponding to your setup: working from the Q# command line application or using a host program in Python or C#.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="9b184-184">Ligne de commande</span><span class="sxs-lookup"><span data-stu-id="9b184-184">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="9b184-185">L’exécution du programme Q # à partir de la ligne de commande nécessite uniquement une petite modification du fichier Q #.</span><span class="sxs-lookup"><span data-stu-id="9b184-185">Running the Q# program from the command line requires only a small change to the Q# file.</span></span>

<span data-ttu-id="9b184-186">Ajoutez simplement `@EntryPoint()` à une ligne précédant la définition de l’opération :</span><span class="sxs-lookup"><span data-stu-id="9b184-186">Simply add `@EntryPoint()` to a line preceding the operation definition:</span></span>

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

<span data-ttu-id="9b184-187">Pour exécuter le programme, ouvrez le terminal dans le dossier de votre projet et entrez</span><span class="sxs-lookup"><span data-stu-id="9b184-187">To run the program, open the terminal in the folder of your project and enter</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="9b184-188">Lors de l’exécution, vous devez voir les `Message` `DumpMachine` sorties et ci-dessous imprimées dans votre console.</span><span class="sxs-lookup"><span data-stu-id="9b184-188">Upon execution, you should see the `Message` and `DumpMachine` outputs below printed in your console.</span></span>


#### <a name="python"></a>[<span data-ttu-id="9b184-189">Python</span><span class="sxs-lookup"><span data-stu-id="9b184-189">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="9b184-190">Créez un fichier d’hôte Python : `host.py` .</span><span class="sxs-lookup"><span data-stu-id="9b184-190">Create a Python host file: `host.py`.</span></span>

<span data-ttu-id="9b184-191">Le fichier hôte est construit comme suit :</span><span class="sxs-lookup"><span data-stu-id="9b184-191">The host file is constructed as follows:</span></span> 
1. <span data-ttu-id="9b184-192">Tout d’abord, nous importons le `qsharp` module, qui inscrit le chargeur de module pour l’interopérabilité Q #.</span><span class="sxs-lookup"><span data-stu-id="9b184-192">First, we import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="9b184-193">Cela permet d’afficher les espaces de noms Q # (par exemple `NamespaceQFT` , que nous avons définis dans notre fichier q #) comme des modules python, à partir desquels nous pouvons importer des opérations q #.</span><span class="sxs-lookup"><span data-stu-id="9b184-193">This allows Q# namespaces (e.g. the `NamespaceQFT` we defined in our Q# file) to appear as Python modules, from which we can import Q# operations.</span></span>
2. <span data-ttu-id="9b184-194">Ensuite, importez les opérations Q # que nous appellerons directement---dans ce cas, `Perform3qubitQFT` .</span><span class="sxs-lookup"><span data-stu-id="9b184-194">Then, import the Q# operations which we will directly invoke---in this case, `Perform3qubitQFT`.</span></span>
    <span data-ttu-id="9b184-195">Nous avons uniquement besoin d’importer le point d’entrée dans un programme Q # (c’est-à-dire _pas_ des opérations telles que `H` et `R1` , qui sont appelées par d’autres opérations q # mais jamais par l’hôte classique).</span><span class="sxs-lookup"><span data-stu-id="9b184-195">We need only import the entry point into a Q# program (i.e. _not_ operations like `H` and `R1`, which are called by other Q# operations but never by the classical host).</span></span>
3. <span data-ttu-id="9b184-196">Pour simuler des opérations ou des fonctions Q #, utilisez le formulaire `<Q#callable>.simulate(<args>)` pour les exécuter sur l' `QuantumSimulator()` ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="9b184-196">In simulating Q# operations or functions, use the form `<Q#callable>.simulate(<args>)` to run them on the `QuantumSimulator()` target machine.</span></span> 

> [!NOTE]
> <span data-ttu-id="9b184-197">Si nous voulions appeler l’opération sur un autre ordinateur, par exemple le `ResourceEstimator()` , nous utiliserions simplement `<Q#callable>.estimate_resources(<args>)` .</span><span class="sxs-lookup"><span data-stu-id="9b184-197">If we wanted to call the operation on a different machine, for example the `ResourceEstimator()`, we would simply use `<Q#callable>.estimate_resources(<args>)`.</span></span>
> <span data-ttu-id="9b184-198">En général, les opérations Q # sont indépendantes des ordinateurs sur lesquels elles sont exécutées, mais certaines fonctionnalités telles que `DumpMachine` peuvent se comporter différemment.</span><span class="sxs-lookup"><span data-stu-id="9b184-198">In general, Q# operations are agnostic to the machines on which they're run, but some features such as `DumpMachine` may behave differently.</span></span>

4. <span data-ttu-id="9b184-199">Lors de l’exécution de la simulation, l’appel d’opération retourne des valeurs telles que définies dans le fichier Q #.</span><span class="sxs-lookup"><span data-stu-id="9b184-199">Upon performing the simulation, the operation call will return values as defined in the Q# file.</span></span>
    <span data-ttu-id="9b184-200">Pour le moment, rien n’est retourné, mais plus tard, nous verrons un exemple d’affectation et de traitement de ces valeurs.</span><span class="sxs-lookup"><span data-stu-id="9b184-200">For now there is nothing returned, but later on we will see an example of assigning and processing these values.</span></span>
    <span data-ttu-id="9b184-201">Avec les données qui en résultent, nous pouvons faire tout ce que nous aimerions de faire.</span><span class="sxs-lookup"><span data-stu-id="9b184-201">With the resultant data in our hands and totally classical, we can do whatever we'd like with it.</span></span>

<span data-ttu-id="9b184-202">Le `host.py` fichier complet doit être le suivant :</span><span class="sxs-lookup"><span data-stu-id="9b184-202">Your full `host.py` file should be this:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

<span data-ttu-id="9b184-203">Exécutez le fichier Python, puis imprimez-le dans votre console. vous devez voir les `Message` `DumpMachine` sorties et ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9b184-203">Run the Python file, and printed in your console you should see the `Message` and `DumpMachine` outputs below.</span></span> 


#### <a name="c"></a>[<span data-ttu-id="9b184-204">C#</span><span class="sxs-lookup"><span data-stu-id="9b184-204">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="9b184-205">Suivez les mêmes instructions que dans le [Guide d’installation](xref:microsoft.quantum.install.cs), créez un fichier d’hôte C#, puis renommez-le `host.cs` .</span><span class="sxs-lookup"><span data-stu-id="9b184-205">Following the same instructions as in the [install guide](xref:microsoft.quantum.install.cs), create a C# host file, and rename it to `host.cs`.</span></span>

<span data-ttu-id="9b184-206">L’hôte C# se compose de quatre parties :</span><span class="sxs-lookup"><span data-stu-id="9b184-206">The C# host has four parts:</span></span>
1. <span data-ttu-id="9b184-207">Construire un simulateur quantique.</span><span class="sxs-lookup"><span data-stu-id="9b184-207">Construct a quantum simulator.</span></span>
    <span data-ttu-id="9b184-208">Dans le code ci-dessous, il s’agit de la variable `qsim` .</span><span class="sxs-lookup"><span data-stu-id="9b184-208">In the code below, this is the variable `qsim`.</span></span>
2. <span data-ttu-id="9b184-209">Calculer tous les arguments requis pour l’algorithme quantique.</span><span class="sxs-lookup"><span data-stu-id="9b184-209">Compute any arguments required for the quantum algorithm.</span></span>
    <span data-ttu-id="9b184-210">Il n’y en a aucun dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="9b184-210">There are none in this example.</span></span>
3. <span data-ttu-id="9b184-211">Exécuter l’algorithme quantique.</span><span class="sxs-lookup"><span data-stu-id="9b184-211">Run the quantum algorithm.</span></span> 
    <span data-ttu-id="9b184-212">Chaque opération Q# génère une classe C# du même nom.</span><span class="sxs-lookup"><span data-stu-id="9b184-212">Each Q# operation generates a C# class with the same name.</span></span> 
    <span data-ttu-id="9b184-213">Cette classe a une méthode `Run` qui exécute l’opération **de façon asynchrone** .</span><span class="sxs-lookup"><span data-stu-id="9b184-213">This class has a `Run` method that **asynchronously** executes the operation.</span></span>
    <span data-ttu-id="9b184-214">L’exécution est asynchrone parce que l’exécution sur du matériel réel sera asynchrone.</span><span class="sxs-lookup"><span data-stu-id="9b184-214">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> 
    <span data-ttu-id="9b184-215">Étant donné que la `Run` méthode est asynchrone, nous appelons la `Wait()` méthode, ce qui bloque l’exécution jusqu’à ce que la tâche se termine et retourne le résultat de façon synchrone.</span><span class="sxs-lookup"><span data-stu-id="9b184-215">Because the `Run` method is asynchronous, we call the `Wait()` method; this blocks execution until the task completes and returns the result synchronously.</span></span> 
4. <span data-ttu-id="9b184-216">Traitez le résultat retourné de l’opération.</span><span class="sxs-lookup"><span data-stu-id="9b184-216">Process the returned result of the operation.</span></span>
    <span data-ttu-id="9b184-217">Pour le moment, l’opération ne retourne rien.</span><span class="sxs-lookup"><span data-stu-id="9b184-217">For now, the operation returns nothing.</span></span>


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
<span data-ttu-id="9b184-218">Exécutez l’application et votre sortie doit correspondre à celle ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9b184-218">Run the application, and your output should match that below.</span></span>
<span data-ttu-id="9b184-219">Le programme se fermera sur l’action d’une touche.</span><span class="sxs-lookup"><span data-stu-id="9b184-219">The program will exit after you press a key.</span></span>
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

<span data-ttu-id="9b184-220">En cas d’appel sur le simulateur d’état complet, `DumpMachine()` fournit ces représentations multiples du wavefunction de l’état de Quantum.</span><span class="sxs-lookup"><span data-stu-id="9b184-220">When called on the full-state simulator, `DumpMachine()` provides these mutliple representations of the quantum state's wavefunction.</span></span> <span data-ttu-id="9b184-221">Les États possibles d’un système $n $-qubit peuvent être représentés par des États de base de $2 ^ n $, chacun avec un coefficient complexe correspondant (simplement une amplitude et une phase).</span><span class="sxs-lookup"><span data-stu-id="9b184-221">The possible states of an $n$-qubit system can be represented by $2^n$ computational basis states, each with a corresponding complex coefficient (simply an amplitude and a phase).</span></span>
<span data-ttu-id="9b184-222">Les États de base de calcul correspondent à toutes les chaînes binaires de longueur $n $---autrement dit, toutes les combinaisons possibles de qubit $ \ket {0} $ et $ \ket {1} $, où chaque chiffre binaire correspond à un qubit individuel.</span><span class="sxs-lookup"><span data-stu-id="9b184-222">The computational basis states correspond to all the possible binary strings of length $n$---that is, all the possible combinations of qubit states $\ket{0}$ and $\ket{1}$, where each binary digit corresponds to an individual qubit.</span></span>

<span data-ttu-id="9b184-223">La première ligne fournit un commentaire avec les ID des qubits correspondants dans leur ordre significatif.</span><span class="sxs-lookup"><span data-stu-id="9b184-223">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="9b184-224">Qubit `2` étant le « plus significatif » signifie simplement que dans la représentation binaire du vecteur d’état de base $ \ket{i} $, l’état de qubit `2` correspond au chiffre le plus à gauche.</span><span class="sxs-lookup"><span data-stu-id="9b184-224">Qubit `2` being the "most significant" simply means that in the binary representation of basis state vector $\ket{i}$, the state of qubit `2` corresponds to the left-most digit.</span></span> <span data-ttu-id="9b184-225">Par exemple, $ \ket {6} = \ket {110} $ comprend qubits `2` et `1` les deux dans $ \ket {1} $ et qubit `0` dans $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="9b184-225">For example, $\ket{6} = \ket{110}$ comprises qubits `2` and `1` both in $\ket{1}$ and qubit `0` in $\ket{0}$.</span></span>


<span data-ttu-id="9b184-226">Les autres lignes décrivent l’amplitude de probabilité de la mesure du vecteur d’état de base $ \ket{i} $ à la fois dans les formats cartésien et polaire.</span><span class="sxs-lookup"><span data-stu-id="9b184-226">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{i}$ in both Cartesian and polar formats.</span></span>
<span data-ttu-id="9b184-227">En détail pour la première ligne de notre état d’entrée $ \ket {000} $ :</span><span class="sxs-lookup"><span data-stu-id="9b184-227">In detail for the first row of our input state $\ket{000}$:</span></span>
* <span data-ttu-id="9b184-228">**`|0>:`** Cette ligne correspond à l' `0` État de la base de calcul (étant donné que notre état initial après allocation était de $ \ket {000} $, nous pensons qu’il s’agit du seul État avec une amplitude de probabilité à ce stade).</span><span class="sxs-lookup"><span data-stu-id="9b184-228">**`|0>:`** this row corresponds to the `0` computational basis state (given that our initial state post-allocation was $\ket{000}$, we would expect this to be the only state with probability amplitude at this point).</span></span>
* <span data-ttu-id="9b184-229">**`1.000000 +  0.000000 i`**: amplitude de probabilité au format cartésien.</span><span class="sxs-lookup"><span data-stu-id="9b184-229">**`1.000000 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="9b184-230">**` == `**: le `equal` signe sépare les deux représentations équivalentes.</span><span class="sxs-lookup"><span data-stu-id="9b184-230">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="9b184-231">**`********************`**: Représentation graphique de l’amplitude, le nombre de `*` est proportionnel à la probabilité de mesurer ce vecteur d’État.</span><span class="sxs-lookup"><span data-stu-id="9b184-231">**`********************`**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span> 
* <span data-ttu-id="9b184-232">**`[ 1.000000 ]`**: valeur numérique de l’amplitude</span><span class="sxs-lookup"><span data-stu-id="9b184-232">**`[ 1.000000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="9b184-233">**`    ---`**: Représentation graphique de la phase de l’amplitude.</span><span class="sxs-lookup"><span data-stu-id="9b184-233">**`    ---`**: A graphical representation of the amplitude's phase.</span></span>
* <span data-ttu-id="9b184-234">**`[ 0.0000 rad ]`**: valeur numérique de la phase (en radians).</span><span class="sxs-lookup"><span data-stu-id="9b184-234">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="9b184-235">L’amplitude et la phase sont toutes les deux affichées avec une représentation graphique.</span><span class="sxs-lookup"><span data-stu-id="9b184-235">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="9b184-236">La représentation magnitude est simple : elle affiche une barre de `*` et plus la probabilité est élevée, plus la barre est grande.</span><span class="sxs-lookup"><span data-stu-id="9b184-236">The magnitude representation is straightforward: it shows a bar of `*`, and the higher the probability, the larger the bar will be.</span></span> <span data-ttu-id="9b184-237">Pour la phase, consultez [test et débogage : fonctions de vidage](xref:microsoft.quantum.guide.testingdebugging#dump-functions) pour les représentations de symboles possibles en fonction des plages angulaires.</span><span class="sxs-lookup"><span data-stu-id="9b184-237">For the phase, see [Testing and debugging: dump functions](xref:microsoft.quantum.guide.testingdebugging#dump-functions) for the possible symbol representations based on angle ranges.</span></span>


<span data-ttu-id="9b184-238">La sortie imprimée illustre donc que nos portes programmées ont transformé notre état à partir de</span><span class="sxs-lookup"><span data-stu-id="9b184-238">So, the printed output is illustrating that our programmed gates transformed our state from</span></span>

<span data-ttu-id="9b184-239">$ $ \ket{\Psi} \_ {initial} = \ket {000} $ $</span><span class="sxs-lookup"><span data-stu-id="9b184-239">$$ \ket{\psi}\_{initial} = \ket{000} $$</span></span>

<span data-ttu-id="9b184-240">to</span><span class="sxs-lookup"><span data-stu-id="9b184-240">to</span></span> 

<span data-ttu-id="9b184-241">$ $ \begin{align} \ket{\Psi} \_ {final} &= \frac {1} {\sqrt {8} } \left (\ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="9b184-241">$$ \begin{align} \ket{\psi}\_{final} &= \frac{1}{\sqrt{8}} \left( \ket{000} + \ket{001} + \ket{010} + \ket{011} + \ket{100} + \ket{101} + \ket{110} + \ket{111}  \right) \\\\ &= \frac{1}{\sqrt{2^n}}\sum\_{j=0}^{2^n-1} \ket{j}, \end{align} $$</span></span>

<span data-ttu-id="9b184-242">qui est précisément le comportement de la transformation de Fourier 3-qubit.</span><span class="sxs-lookup"><span data-stu-id="9b184-242">which is precisely the behavior of the 3-qubit Fourier transform.</span></span> 

<span data-ttu-id="9b184-243">Si vous êtes curieux de savoir comment d’autres États d’entrée sont affectés, nous vous invitons à vous lancer avec l’application d’opérations qubit avant la transformation.</span><span class="sxs-lookup"><span data-stu-id="9b184-243">If you are curious about how other input states are affected, we encourage you to play around with applying qubit operations before the transform.</span></span>

## <a name="adding-measurements"></a><span data-ttu-id="9b184-244">Ajout de mesures</span><span class="sxs-lookup"><span data-stu-id="9b184-244">Adding measurements</span></span>

<span data-ttu-id="9b184-245">Malheureusement, une pierre angulaire de la mécanique de Quantum nous dit qu’un système Quantum réel ne peut pas avoir une telle `DumpMachine` fonction.</span><span class="sxs-lookup"><span data-stu-id="9b184-245">Unfortunately, a cornerstone of quantum mechanics tells us that a real quantum system cannot have such a `DumpMachine` function.</span></span> <span data-ttu-id="9b184-246">Au lieu de cela, nous sommes obligés d’extraire des informations par le biais de mesures, ce qui, en général, ne nous permet pas de fournir l’État quantum complet, mais peut également modifier radicalement le système lui-même.</span><span class="sxs-lookup"><span data-stu-id="9b184-246">Instead, we're forced to extract information through measurements, which in general not only fail to provide us the full quantum state, but can also drastically alter the system itself.</span></span>
<span data-ttu-id="9b184-247">Il existe de nombreux types de mesures de Quantum, mais nous allons nous concentrer sur les mesures projective sur une seule qubits.</span><span class="sxs-lookup"><span data-stu-id="9b184-247">There are many sorts of quantum measurements, but we will focus on the most basic: projective measurements on single qubits.</span></span>
<span data-ttu-id="9b184-248">En cas de mesure dans une base donnée (par exemple, la base de calcul $ \{ \ket {0} , \ket {1} \} $), l’État qubit est projeté sur tout état de base mesuré---détruisant ainsi la superposition entre les deux.</span><span class="sxs-lookup"><span data-stu-id="9b184-248">Upon measurement in a given basis (e.g. the computational basis $ \{ \ket{0}, \ket{1} \} $), the qubit state is projected onto whichever basis state was measured---hence destroying any superposition between the two.</span></span>

<span data-ttu-id="9b184-249">Pour implémenter des mesures dans un programme Q #, nous utilisons l' `M` opération (from `Microsoft.Quantum.Intrinsic` ), qui retourne un `Result` type.</span><span class="sxs-lookup"><span data-stu-id="9b184-249">To implement measurements within a Q# program, we use the `M` operation (from `Microsoft.Quantum.Intrinsic`), which returns a `Result` type.</span></span>

<span data-ttu-id="9b184-250">Tout d’abord, nous modifions notre `Perform3QubitQFT` opération pour retourner un tableau de résultats de mesure, `Result[]` , au lieu de `Unit` .</span><span class="sxs-lookup"><span data-stu-id="9b184-250">First, we modify our `Perform3QubitQFT` operation to return an array of measurement results, `Result[]`, instead of `Unit`.</span></span>

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a><span data-ttu-id="9b184-251">Définir et initialiser un `Result[]` tableau</span><span class="sxs-lookup"><span data-stu-id="9b184-251">Define and initialize `Result[]` array</span></span>

<span data-ttu-id="9b184-252">Avant même d’allouer des qubits (c’est-à-dire avant l' `using` instruction), nous déclarons et Lions ce tableau de longueur-3 (un `Result` pour chaque qubit) :</span><span class="sxs-lookup"><span data-stu-id="9b184-252">Before even allocating qubits (i.e. before the `using` statement), we declare and bind this length-3 array (one `Result` for each qubit):</span></span> 

```qsharp
        mutable resultArray = new Result[3];
```

<span data-ttu-id="9b184-253">Le `mutable` mot clé `resultArray` en regard permet à la variable d’être reliée plus tard dans le code---par exemple, lors de l’ajout de nos résultats de mesure.</span><span class="sxs-lookup"><span data-stu-id="9b184-253">The `mutable` keyword prefacing `resultArray` allows the variable to be rebound later in the code---for example, when adding our measurement results.</span></span>

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a><span data-ttu-id="9b184-254">Effectuer des mesures dans une `for` boucle et ajouter des résultats à un tableau</span><span class="sxs-lookup"><span data-stu-id="9b184-254">Perform measurements in a `for` loop and add results to array</span></span>

<span data-ttu-id="9b184-255">Après les opérations de transformation de Fourier à l’intérieur du `using` bloc, insérez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="9b184-255">After the Fourier transform operations inside the `using` block, insert the following code:</span></span>

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
<span data-ttu-id="9b184-256">La [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) fonction appelée sur un tableau (par exemple, notre tableau de qubits `qs` ) retourne une plage sur les index du tableau.</span><span class="sxs-lookup"><span data-stu-id="9b184-256">The [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) function called on an array (e.g. our array of qubits, `qs`) returns a range over the indices of the array.</span></span> <span data-ttu-id="9b184-257">Ici, nous l’utilisons dans notre `for` boucle pour mesurer séquentiellement chaque qubit à l’aide de l' `M(qs[i])` instruction.</span><span class="sxs-lookup"><span data-stu-id="9b184-257">Here, we use it in our `for` loop to sequentially measure each qubit using the `M(qs[i])` statement.</span></span>
<span data-ttu-id="9b184-258">Chaque `Result` type mesuré ( `Zero` ou `One` ) est ensuite ajouté à la position d’index correspondante dans `resultArray` avec une instruction Update-and-réassign.</span><span class="sxs-lookup"><span data-stu-id="9b184-258">Each measured `Result` type (either `Zero` or `One`) is then added to the corresponding index position in `resultArray` with an update-and-reassign statement.</span></span>

> [!NOTE]
> <span data-ttu-id="9b184-259">La syntaxe de cette instruction est propre à Q #, mais correspond à la réaffectation de variables similaires `resultArray[i] <- M(qs[i])` vue dans d’autres langages tels que F # et R.</span><span class="sxs-lookup"><span data-stu-id="9b184-259">The syntax of this statement is unique to Q#, but corresponds to the similar variable reassignment `resultArray[i] <- M(qs[i])` seen in other languages such as F# and R.</span></span>

<span data-ttu-id="9b184-260">Le mot clé `set` est toujours utilisé pour réassigner les variables liées à l’aide de `mutable` .</span><span class="sxs-lookup"><span data-stu-id="9b184-260">The keyword `set` is always used to reassign variables bound using `mutable`.</span></span>

#### <a name="return-resultarray"></a><span data-ttu-id="9b184-261">Renvoi`resultArray`</span><span class="sxs-lookup"><span data-stu-id="9b184-261">Return `resultArray`</span></span>

<span data-ttu-id="9b184-262">Avec les trois qubits mesurés et les résultats ajoutés à `resultArray` , nous sommes sûrs de réinitialiser et de libérer les qubits comme auparavant.</span><span class="sxs-lookup"><span data-stu-id="9b184-262">With all three qubits measured and the results added to `resultArray`, we are safe to reset and deallocate the qubits as before.</span></span>
<span data-ttu-id="9b184-263">Après la `using` fermeture du bloc, insérez</span><span class="sxs-lookup"><span data-stu-id="9b184-263">After the `using` block's close, insert</span></span>

```qsharp
        return resultArray;
```
<span data-ttu-id="9b184-264">pour retourner finalement la sortie de notre opération.</span><span class="sxs-lookup"><span data-stu-id="9b184-264">to ultimately return the output of our operation.</span></span> 

### <a name="understanding-the-effects-of-measurement"></a><span data-ttu-id="9b184-265">Comprendre les effets de la mesure</span><span class="sxs-lookup"><span data-stu-id="9b184-265">Understanding the effects of measurement</span></span>

<span data-ttu-id="9b184-266">Nous allons modifier le placement de nos `DumpMachine` fonctions pour sortir l’état avant et après les mesures.</span><span class="sxs-lookup"><span data-stu-id="9b184-266">Let's change the placement of our `DumpMachine` functions to output the state before and after the measurements.</span></span>
<span data-ttu-id="9b184-267">Le code d’opération final doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="9b184-267">The final operation code should look like:</span></span> 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

<span data-ttu-id="9b184-268">Si vous travaillez à partir de la ligne de commande, le tableau retourné sera simplement imprimé directement sur la console à la fin de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="9b184-268">If you are working from the command line, the returned array will simply be printed directly to the console at the end of the execution.</span></span>
<span data-ttu-id="9b184-269">Dans le cas contraire, mettez à jour votre programme hôte pour traiter le tableau retourné.</span><span class="sxs-lookup"><span data-stu-id="9b184-269">Otherwise, update your host program to process the returned array.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="9b184-270">Ligne de commande</span><span class="sxs-lookup"><span data-stu-id="9b184-270">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="9b184-271">Pour mieux comprendre le tableau retourné qui sera imprimé dans la console, nous pouvons ajouter un autre `Message` dans le fichier Q # juste avant l' `return` instruction :</span><span class="sxs-lookup"><span data-stu-id="9b184-271">To have more understanding of the returned array which will be printed in the console, we can add another `Message` in the Q# file just before the `return` statement:</span></span>

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

<span data-ttu-id="9b184-272">Exécutez le projet, et votre sortie doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="9b184-272">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[<span data-ttu-id="9b184-273">Python</span><span class="sxs-lookup"><span data-stu-id="9b184-273">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="9b184-274">Mettez à jour votre programme Python en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="9b184-274">Update your Python program to the following:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

<span data-ttu-id="9b184-275">Exécutez le fichier, et votre sortie doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="9b184-275">Run the file, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[<span data-ttu-id="9b184-276">C#</span><span class="sxs-lookup"><span data-stu-id="9b184-276">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="9b184-277">Maintenant que notre opération retourne un résultat, remplacez l’appel de méthode `Wait()` par l’extraction de la `Result` propriété.</span><span class="sxs-lookup"><span data-stu-id="9b184-277">Now that our operation is returning a result, replace the method call `Wait()` with fetching the `Result` property.</span></span> <span data-ttu-id="9b184-278">Cela accomplit toujours le même synchronicité que celui abordé précédemment, et nous pouvons lier directement cette valeur à la variable `measurementResult` .</span><span class="sxs-lookup"><span data-stu-id="9b184-278">This still accomplishes the same synchronicity discussed earlier, and we can directly bind this value to the variable `measurementResult`.</span></span>

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="9b184-279">Exécutez le projet, et votre sortie doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="9b184-279">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

<span data-ttu-id="9b184-280">Cette sortie illustre plusieurs choses :</span><span class="sxs-lookup"><span data-stu-id="9b184-280">This output illustrates a few different things:</span></span>
1. <span data-ttu-id="9b184-281">En comparant le résultat retourné à la pré-mesure `DumpMachine` , il n’illustre évidemment _pas_ la superposition QFT sur les États de base.</span><span class="sxs-lookup"><span data-stu-id="9b184-281">Comparing the returned result to the pre-measurement `DumpMachine`, it clearly does _not_ illustrate the post-QFT superposition over basis states.</span></span>
    <span data-ttu-id="9b184-282">Une mesure ne retourne qu’un seul État de base, avec une probabilité déterminée par l’amplitude de cet État dans le wavefunction du système.</span><span class="sxs-lookup"><span data-stu-id="9b184-282">A measurement only returns a single basis state, with a probability determined by the amplitude of that state in the system's wavefunction.</span></span>
2. <span data-ttu-id="9b184-283">À partir de l’après-mesure `DumpMachine` , nous voyons que la mesure _modifie_ l’État lui-même, en la projetant à partir de la superposition initiale sur les États de base jusqu’à l’état de base unique qui correspond à la valeur mesurée.</span><span class="sxs-lookup"><span data-stu-id="9b184-283">From the post-measurement `DumpMachine`, we see that measurement _changes_ the state itself, projecting it from the initial superposition over basis states to the single basis state that corresponds to the measured value.</span></span>

<span data-ttu-id="9b184-284">Si nous devions répéter cette opération plusieurs fois, nous verrions que les statistiques de résultat commencent à illustrer la superposition de l’État postérieur à la QFT qui donne lieu à un résultat aléatoire sur chaque capture.</span><span class="sxs-lookup"><span data-stu-id="9b184-284">If we were to repeat this operation many times, we would see the result statistics begin to illustrate the equally weighted superposition of the post-QFT state that gives rise to a random result on each shot.</span></span>
<span data-ttu-id="9b184-285">_Toutefois_, en plus d’être inefficace et toujours imparfait, cela ne reproduirait néanmoins que les amplitudes relatives des États de base, et non les phases relatives entre elles.</span><span class="sxs-lookup"><span data-stu-id="9b184-285">_However_, besides being inefficient and still imperfect, this would nevertheless only reproduce the relative amplitudes of the basis states, not the relative phases between them.</span></span>
<span data-ttu-id="9b184-286">Ce dernier n’est pas un problème dans cet exemple, mais nous verrions des phases relatives apparaître si une entrée plus complexe est donnée à QFT que $ \ket {000} $.</span><span class="sxs-lookup"><span data-stu-id="9b184-286">The latter is not an issue in this example, but we would see relative phases appear if given a more complex input to the QFT than $\ket{000}$.</span></span>

#### <a name="partial-measurements"></a><span data-ttu-id="9b184-287">Mesures partielles</span><span class="sxs-lookup"><span data-stu-id="9b184-287">Partial measurements</span></span> 
<span data-ttu-id="9b184-288">Pour découvrir comment mesurer uniquement certains qubits du Registre peut affecter l’état du système, essayez d’ajouter le code suivant à l’intérieur de la `for` boucle, après la ligne de mesure :</span><span class="sxs-lookup"><span data-stu-id="9b184-288">To explore how measuring only some qubits of the register can affect the system's state, try adding the following inside the `for` loop, after the measurement line:</span></span>
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

<span data-ttu-id="9b184-289">Notez que pour accéder à la `IntAsString` fonction, vous devez ajouter</span><span class="sxs-lookup"><span data-stu-id="9b184-289">Note that to access the `IntAsString` function you will have to add</span></span> 
```qsharp
    open Microsoft.Quantum.Convert;
```
<span data-ttu-id="9b184-290">avec les autres instructions d’espace de noms `open` .</span><span class="sxs-lookup"><span data-stu-id="9b184-290">with the rest of the namespace `open` statements.</span></span>

<span data-ttu-id="9b184-291">Dans le résultat obtenu, vous verrez la projection progressive dans des sous-espaces à mesure que chaque qubit est mesuré.</span><span class="sxs-lookup"><span data-stu-id="9b184-291">In the resulting output, you will see the gradual projection into subspaces as each qubit is measured.</span></span>


## <a name="use-the-q-libraries"></a><span data-ttu-id="9b184-292">Utiliser les bibliothèques Q #</span><span class="sxs-lookup"><span data-stu-id="9b184-292">Use the Q# libraries</span></span>
<span data-ttu-id="9b184-293">Comme nous l’avons mentionné dans l’introduction, la plupart des déplacements d’énergie de Q # dans le fait qu’il vous permet de faire abstraction des soucis liés à la gestion de qubits individuels.</span><span class="sxs-lookup"><span data-stu-id="9b184-293">As we mentioned in the introduction, much of Q#'s power rests in the fact that it allows you to abstract-away the worries of dealing with individual qubits.</span></span>
<span data-ttu-id="9b184-294">En effet, si vous souhaitez développer des programmes quantiques à grande échelle et applicables, vous vous inquiétez de savoir si une `H` opération doit être effectuée avant ou après une rotation particulière.</span><span class="sxs-lookup"><span data-stu-id="9b184-294">Indeed, if you want to develop full-scale, applicable quantum programs, worrying about whether an `H` operation goes before or after a particular rotation would only slow you down.</span></span> 

<span data-ttu-id="9b184-295">Les bibliothèques Q # contiennent l’opération [QFT](xref:microsoft.quantum.canon.qft) , que vous pouvez simplement prendre et demander pour un nombre quelconque de qubits.</span><span class="sxs-lookup"><span data-stu-id="9b184-295">The Q# libraries contain the [QFT](xref:microsoft.quantum.canon.qft) operation, which you can simply take and apply for any number of qubits.</span></span>
<span data-ttu-id="9b184-296">Pour essayer, définissez une nouvelle opération dans votre fichier Q # qui a le même contenu `Perform3QubitQFT` , mais avec tout ce qui est du premier `H` au `SWAP` remplacé par deux lignes simples :</span><span class="sxs-lookup"><span data-stu-id="9b184-296">To give it a try, define a new operation in your Q# file which has the same contents of `Perform3QubitQFT`, but with everything from the first `H` to the `SWAP` replaced by two easy lines:</span></span>
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
<span data-ttu-id="9b184-297">La première ligne crée simplement une [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expression du tableau alloué de qubits, `qs` , qui est ce que prend l’opération [QFT](xref:microsoft.quantum.canon.qft) comme argument.</span><span class="sxs-lookup"><span data-stu-id="9b184-297">The first line simply creates a [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expression of the allocated array of qubits, `qs`, which is what the [QFT](xref:microsoft.quantum.canon.qft) operation takes as an argument.</span></span>
<span data-ttu-id="9b184-298">Cela correspond à l’ordre des index des qubits dans le registre.</span><span class="sxs-lookup"><span data-stu-id="9b184-298">This corresponds to index ordering of the qubits in the register.</span></span>

<span data-ttu-id="9b184-299">Pour avoir accès à ces opérations, ajoutez `open` des instructions pour leurs espaces de noms respectifs au début du fichier Q # :</span><span class="sxs-lookup"><span data-stu-id="9b184-299">To have access to these operations, add `open` statements for their respective namespaces at the beginning of the Q# file:</span></span>
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

<span data-ttu-id="9b184-300">À présent, ajustez votre programme hôte pour appeler le nom de votre nouvelle opération (par exemple `PerformIntrinsicQFT` ,) et donnez-lui un essayons.</span><span class="sxs-lookup"><span data-stu-id="9b184-300">Now, adjust your host program to call the name of your new operation (e.g. `PerformIntrinsicQFT`), and give it a whirl.</span></span>

<span data-ttu-id="9b184-301">Pour voir l’avantage réel de l’utilisation des opérations de la bibliothèque Q #, modifiez le nombre de qubits à une valeur autre que `3` :</span><span class="sxs-lookup"><span data-stu-id="9b184-301">To see the real benefit of using the Q# library operations, change the number of qubits to something other than `3`:</span></span>
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
<span data-ttu-id="9b184-302">Vous pouvez ainsi appliquer le QFT approprié pour un nombre donné de qubits, sans avoir à vous soucier des nouvelles `H` opérations et des rotations sur chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="9b184-302">You can thus apply the proper QFT for any given number of qubits, without having to worry about the mess of new `H` operations and rotations on each qubit.</span></span>

<span data-ttu-id="9b184-303">Notez que le simulateur Quantum prend encore plus de temps pour s’exécuter au fur et à mesure que vous augmentez le nombre de qubits---précisément la raison pour laquelle nous sommes impatients de matériel Quantum réel !</span><span class="sxs-lookup"><span data-stu-id="9b184-303">Note that the quantum simulator takes exponentially more time to run as you increase the number of qubits---precisely why we look forward to real quantum hardware!</span></span>













