---
title: Simulateurs quantiques et applications hôtes | Microsoft Docs
description: 'Décrit comment utiliser les simulateurs quantiques avec un langage .NET de calcul classique, en général C# ou Q #.'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2020
ms.locfileid: "73442225"
---
# <a name="quantum-simulators-and-host-applications"></a><span data-ttu-id="e1373-103">Simulateurs quantiques et applications hôtes</span><span class="sxs-lookup"><span data-stu-id="e1373-103">Quantum simulators and host applications</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="e1373-104">Ce que vous allez apprendre</span><span class="sxs-lookup"><span data-stu-id="e1373-104">What You'll Learn</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="e1373-105">Mode d’exécution des algorithmes quantiques</span><span class="sxs-lookup"><span data-stu-id="e1373-105">How quantum algorithms are executed</span></span>
> * <span data-ttu-id="e1373-106">Les simulateurs quantiques inclus dans cette version</span><span class="sxs-lookup"><span data-stu-id="e1373-106">What quantum simulators are included in this release</span></span>
> * <span data-ttu-id="e1373-107">Comment écrire un pilote C# pour votre algorithme quantique</span><span class="sxs-lookup"><span data-stu-id="e1373-107">How to write a C# driver for your quantum algorithm</span></span>

## <a name="the-quantum-development-kit-execution-model"></a><span data-ttu-id="e1373-108">Modèle d’exécution du Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="e1373-108">The Quantum Development Kit Execution Model</span></span>

<span data-ttu-id="e1373-109">Dans [Écriture d’un programme quantique](xref:microsoft.quantum.write-program), nous avons exécuté notre algorithme quantique en passant un objet `QuantumSimulator` dans la méthode `Run` de la classe de l’algorithme.</span><span class="sxs-lookup"><span data-stu-id="e1373-109">In [Writing a quantum program](xref:microsoft.quantum.write-program), we executed our quantum algorithm by passing a `QuantumSimulator` object to the algorithm class's `Run` method.</span></span>
<span data-ttu-id="e1373-110">La classe `QuantumSimulator` exécute l’algorithme quantique en simulant complètement le vecteur d’état quantique, ce qui est parfait pour l’exécution et le test de `Teleport`.</span><span class="sxs-lookup"><span data-stu-id="e1373-110">The `QuantumSimulator` class executes the quantum algorithm by fully simulating the quantum state vector, which is perfect for running and testing `Teleport`.</span></span>
<span data-ttu-id="e1373-111">Pour plus d’informations sur les vecteurs d’état quantique, consultez le [guide des concepts](xref:microsoft.quantum.concepts.intro).</span><span class="sxs-lookup"><span data-stu-id="e1373-111">See the [Concepts guide](xref:microsoft.quantum.concepts.intro) for more on quantum state vectors.</span></span>

<span data-ttu-id="e1373-112">D’autres machines cibles peuvent être utilisées pour exécuter un algorithme quantique.</span><span class="sxs-lookup"><span data-stu-id="e1373-112">Other target machines may be used to run a quantum algorithm.</span></span>
<span data-ttu-id="e1373-113">La machine est chargée de fournir des implémentations de primitives quantiques pour l’algorithme.</span><span class="sxs-lookup"><span data-stu-id="e1373-113">The machine is responsible for providing implementations of quantum primitives for the algorithm.</span></span>
<span data-ttu-id="e1373-114">Cela comprend les opérations primitives telles que H, CNOT et Mesure, ainsi que la gestion et le suivi des qubits.</span><span class="sxs-lookup"><span data-stu-id="e1373-114">This includes primitive operations such as H, CNOT, and Measure, as well as qubit management and tracking.</span></span>
<span data-ttu-id="e1373-115">Différentes classes de machines quantiques représentent des modèles d’exécution différents pour le même algorithme quantique.</span><span class="sxs-lookup"><span data-stu-id="e1373-115">Different classes of quantum machines represent different execution models for the same quantum algorithm.</span></span>

<span data-ttu-id="e1373-116">Chaque type de machine quantique peut fournir des implémentations différentes de ces primitives.</span><span class="sxs-lookup"><span data-stu-id="e1373-116">Each type of quantum machine may provide different implementations of these primitives.</span></span>
<span data-ttu-id="e1373-117">Par exemple, le simulateur de traces d’ordinateur quantique inclus dans le kit de développement ne réalise aucune simulation.</span><span class="sxs-lookup"><span data-stu-id="e1373-117">For instance, the quantum computer trace simulator included in the development kit doesn't do any simulation at all.</span></span>
<span data-ttu-id="e1373-118">Au lieu de cela, il permet de suivre l’utilisation des portes, des qubits et d’autres ressources de l’algorithme.</span><span class="sxs-lookup"><span data-stu-id="e1373-118">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machines"></a><span data-ttu-id="e1373-119">Machines quantiques</span><span class="sxs-lookup"><span data-stu-id="e1373-119">Quantum Machines</span></span>

<span data-ttu-id="e1373-120">À l’avenir, nous définirons des classes de machines quantiques supplémentaires pour prendre en charge d’autres types de simulation et leur exécution sur des ordinateurs quantiques topologiques.</span><span class="sxs-lookup"><span data-stu-id="e1373-120">In the future, we will define additional quantum machine classes to support other types of simulation and to support execution on topological quantum computers.</span></span>
<span data-ttu-id="e1373-121">Permettre à l’algorithme de rester constant tout en modifiant l’implémentation de la machine sous-jacente facilite le test et le débogage d’un algorithme en simulation, puis son exécution sur du matériel réel avec la certitude que l’algorithme n’a pas changé.</span><span class="sxs-lookup"><span data-stu-id="e1373-121">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

### <a name="whats-included-in-this-release"></a><span data-ttu-id="e1373-122">Éléments inclus dans cette version</span><span class="sxs-lookup"><span data-stu-id="e1373-122">What's Included in this Release</span></span>

<span data-ttu-id="e1373-123">Cette version du kit de développement quantique comprend plusieurs classes de machines quantiques.</span><span class="sxs-lookup"><span data-stu-id="e1373-123">This release of the quantum developer kit includes several quantum machine classes.</span></span>
<span data-ttu-id="e1373-124">Toutes sont définies dans l’espace de noms `Microsoft.Quantum.Simulation.Simulators`.</span><span class="sxs-lookup"><span data-stu-id="e1373-124">All of them are defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

* <span data-ttu-id="e1373-125">Un [simulateur vectoriel d’état complet](xref:microsoft.quantum.machines.full-state-simulator), classe `QuantumSimulator`.</span><span class="sxs-lookup"><span data-stu-id="e1373-125">A [full state vector simulator](xref:microsoft.quantum.machines.full-state-simulator), the `QuantumSimulator` class.</span></span>
* <span data-ttu-id="e1373-126">Un [estimateur de ressources simple](xref:microsoft.quantum.machines.resources-estimator), classe `ResourcesEstimator`, qui permet une analyse de haut niveau des ressources nécessaires à l’exécution d’un algorithme quantique.</span><span class="sxs-lookup"><span data-stu-id="e1373-126">A [simple resources estimator](xref:microsoft.quantum.machines.resources-estimator), the `ResourcesEstimator` class, it allows a top level analysis of the resources needed to run a quantum algorithm.</span></span>
* <span data-ttu-id="e1373-127">Un [estimateur de ressources basé sur les traces](xref:microsoft.quantum.machines.qc-trace-simulator.intro), classe `QCTraceSimulator`, qui permet une analyse avancée des consommations de ressources pour l’ensemble du graphique d’appel de l’algorithme.</span><span class="sxs-lookup"><span data-stu-id="e1373-127">A [trace-based resource estimator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), the `QCTraceSimulator` class, it allows advanced analysis of resources consumptions for the algorithm's entire call-graph.</span></span>
* <span data-ttu-id="e1373-128">Un [simulateur Toffoli](xref:microsoft.quantum.machines.toffoli-simulator), classe `ToffoliSimulator`.</span><span class="sxs-lookup"><span data-stu-id="e1373-128">A [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator), the `ToffoliSimulator` class.</span></span>

## <a name="writing-a-host-application"></a><span data-ttu-id="e1373-129">Écriture d’une application hôte</span><span class="sxs-lookup"><span data-stu-id="e1373-129">Writing a host application</span></span>

<span data-ttu-id="e1373-130">Dans [Écriture d’un programme quantique](xref:microsoft.quantum.write-program), nous avons écrit un pilote en C# simple pour notre algorithme de téléportation.</span><span class="sxs-lookup"><span data-stu-id="e1373-130">In [Writing a quantum program](xref:microsoft.quantum.write-program), we wrote a simple C# driver for our teleport algorithm.</span></span> <span data-ttu-id="e1373-131">Un pilote en C# a quatre objectifs principaux :</span><span class="sxs-lookup"><span data-stu-id="e1373-131">A C# driver has 4 main purposes:</span></span>

* <span data-ttu-id="e1373-132">Construction de la machine cible</span><span class="sxs-lookup"><span data-stu-id="e1373-132">Constructing the target machine</span></span>
* <span data-ttu-id="e1373-133">Calcul de tous les arguments requis pour l’algorithme quantique</span><span class="sxs-lookup"><span data-stu-id="e1373-133">Computing any arguments required for the quantum algorithm</span></span>
* <span data-ttu-id="e1373-134">Exécution de l’algorithme quantique à l’aide du simulateur</span><span class="sxs-lookup"><span data-stu-id="e1373-134">Running the quantum algorithm using the simulator</span></span>
* <span data-ttu-id="e1373-135">Traitement du résultat de l’opération</span><span class="sxs-lookup"><span data-stu-id="e1373-135">Processing the result of the operation</span></span>

<span data-ttu-id="e1373-136">Ici, nous aborderons chaque étape plus en détail.</span><span class="sxs-lookup"><span data-stu-id="e1373-136">Here we'll discuss each step in more detail.</span></span>

### <a name="constructing-the-target-machine"></a><span data-ttu-id="e1373-137">Construction de la machine cible</span><span class="sxs-lookup"><span data-stu-id="e1373-137">Constructing the Target Machine</span></span>

<span data-ttu-id="e1373-138">Les machines quantiques sont des instances de classes .NET normales. Elles sont donc créées en invoquant leur constructeur, comme n’importe quelle classe .NET.</span><span class="sxs-lookup"><span data-stu-id="e1373-138">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span>
<span data-ttu-id="e1373-139">Certains simulateurs, y compris le `QuantumSimulator`, implémentent l’interface <xref:System.IDisposable?displayProperty=nameWithType> .NET et doivent donc être incluses dans une instruction `using` en C#.</span><span class="sxs-lookup"><span data-stu-id="e1373-139">Some simulators, including the `QuantumSimulator`, implement the .NET <xref:System.IDisposable?displayProperty=nameWithType> interface, and so should be wrapped in a C# `using` statement.</span></span>

### <a name="computing-arguments-for-the-algorithm"></a><span data-ttu-id="e1373-140">Calcul des arguments pour l’algorithme</span><span class="sxs-lookup"><span data-stu-id="e1373-140">Computing Arguments for the Algorithm</span></span>

<span data-ttu-id="e1373-141">Dans notre exemple `Teleport`, nous avons calculé quelques arguments relativement artificiels à transmettre à notre algorithme quantique.</span><span class="sxs-lookup"><span data-stu-id="e1373-141">In our `Teleport` example, we computed some relatively artificial arguments to pass to our quantum algorithm.</span></span>
<span data-ttu-id="e1373-142">Cependant, l’algorithme quantique requiert plus généralement des données significatives et il est plus facile de les fournir à partir du pilote classique.</span><span class="sxs-lookup"><span data-stu-id="e1373-142">More typically, however, there is significant data required by the quantum algorithm, and it is easiest to provide it from the classical driver.</span></span>

<span data-ttu-id="e1373-143">Par exemple, lors de simulations chimiques, l’algorithme quantique requiert une grande table d’intégrales d’interactions orbitales moléculaires.</span><span class="sxs-lookup"><span data-stu-id="e1373-143">For instance, when doing chemical simulations, the quantum algorithm requires a large table of molecular orbital interaction integrals.</span></span>
<span data-ttu-id="e1373-144">En général, elles sont lues à partir d’un fichier fourni lors de l’exécution de l’algorithme.</span><span class="sxs-lookup"><span data-stu-id="e1373-144">Generally these are read in from a file that is provided when running the algorithm.</span></span>
<span data-ttu-id="e1373-145">Comme Q# ne dispose pas d’un mécanisme permettant d’accéder au système de fichiers, la meilleure solution est que ce type de données soit collecté par le pilote classique, puis transmis à la méthode `Run` de l’algorithme quantique.</span><span class="sxs-lookup"><span data-stu-id="e1373-145">Since Q# does not have a mechanism for accessing the file system, this sort of data is best collected by the classical driver and then passed to the quantum algorithm's `Run` method.</span></span>

<span data-ttu-id="e1373-146">Le pilote classique joue également un rôle clé dans le cas des méthodes variationnelles.</span><span class="sxs-lookup"><span data-stu-id="e1373-146">Another case where the classical driver plays a key role is in variational methods.</span></span>
<span data-ttu-id="e1373-147">Dans cette classe d’algorithmes, un état quantique est préparé à partir de certains paramètres classiques, et cet état est utilisé pour calculer une valeur intéressante.</span><span class="sxs-lookup"><span data-stu-id="e1373-147">In this class of algorithms, a quantum state is prepared based on some classical parameters, and that state is used to compute some value of interest.</span></span>
<span data-ttu-id="e1373-148">Les paramètres sont ajustés en fonction d’un certain type d’algorithme d’escalade ou d’apprentissage automatique et l’algorithme quantique fonctionne à nouveau.</span><span class="sxs-lookup"><span data-stu-id="e1373-148">The parameters are adjusted based on some type of hill climbing or machine learning algorithm and the quantum algorithm run again.</span></span>
<span data-ttu-id="e1373-149">Pour ces algorithmes, l’algorithme d’escalade est le mieux implémenté comme fonction purement classique appelée par le pilote classique. Les résultats de l’escalade sont ensuite transmis à la prochaine exécution de l’algorithme quantique.</span><span class="sxs-lookup"><span data-stu-id="e1373-149">For such algorithms, the hill climbing algorithm itself is best implemented as a purely classical function that is called by the classical driver; the results of the hill climbing are then passed to the next execution of the quantum algorithm.</span></span>

### <a name="running-the-quantum-algorithm"></a><span data-ttu-id="e1373-150">Exécution de l’algorithme quantique</span><span class="sxs-lookup"><span data-stu-id="e1373-150">Running the Quantum Algorithm</span></span>

<span data-ttu-id="e1373-151">Cette partie est généralement très simple.</span><span class="sxs-lookup"><span data-stu-id="e1373-151">This part is generally very straightforward.</span></span>
<span data-ttu-id="e1373-152">Chaque opération Q# est compilée dans une classe qui fournit une méthode `Run` statique.</span><span class="sxs-lookup"><span data-stu-id="e1373-152">Each Q# operation is compiled into a class that provides a static `Run` method.</span></span>
<span data-ttu-id="e1373-153">Les arguments de cette méthode sont fournis par le tuple d’argument aplati de l’opération elle-même, plus un premier argument supplémentaire qui est le simulateur servant à l’exécution.</span><span class="sxs-lookup"><span data-stu-id="e1373-153">The arguments to this method are given by the flattened argument tuple of the operation itself, plus an additional first argument which is the simulator to execute with.</span></span> <span data-ttu-id="e1373-154">Pour une opération qui attend le tuple nommé de type `(a: String, (b: Double, c: Double))`, son équivalent aplati est de type `(String a, Double b, Double c)`.</span><span class="sxs-lookup"><span data-stu-id="e1373-154">For an operation that expects the named tuple of type `(a: String, (b: Double, c: Double))` its flattened counterpart is of type `(String a, Double b, Double c)`.</span></span>


<span data-ttu-id="e1373-155">Il existe quelques subtilités lors du passage d’arguments à une méthode `Run` :</span><span class="sxs-lookup"><span data-stu-id="e1373-155">There are some subtleties when passing arguments to a `Run` method:</span></span>

* <span data-ttu-id="e1373-156">Les tableaux doivent être inclus dans un objet `Microsoft.Quantum.Simulation.Core.QArray<T>`.</span><span class="sxs-lookup"><span data-stu-id="e1373-156">Arrays must be wrapped in a `Microsoft.Quantum.Simulation.Core.QArray<T>` object.</span></span>
    <span data-ttu-id="e1373-157">Une classe `QArray` a un constructeur qui peut prendre n’importe quelle collection ordonnée (`IEnumerable<T>`) d’objets appropriés.</span><span class="sxs-lookup"><span data-stu-id="e1373-157">A `QArray` class has a constructor that can take any ordered collection (`IEnumerable<T>`) of appropriate objects.</span></span>
* <span data-ttu-id="e1373-158">Le tuple vide, `()` en Q#, est représenté par `QVoid.Instance` en C#.</span><span class="sxs-lookup"><span data-stu-id="e1373-158">The empty tuple, `()` in Q#, is represented by `QVoid.Instance` in C#.</span></span>
* <span data-ttu-id="e1373-159">Les tuples non vides sont représentés sous forme d’instances `ValueTuple` .NET.</span><span class="sxs-lookup"><span data-stu-id="e1373-159">Non-empty tuples are represented as .NET `ValueTuple` instances.</span></span>
* <span data-ttu-id="e1373-160">Les types définis par l’utilisateur Q# sont passés comme type de base.</span><span class="sxs-lookup"><span data-stu-id="e1373-160">Q# user-defined types are passed as their base type.</span></span>
* <span data-ttu-id="e1373-161">Pour passer une opération ou une fonction à une méthode `Run`, vous devez obtenir une instance de la classe de l’opération ou de la fonction à l’aide de la méthode `Get<>` du simulateur.</span><span class="sxs-lookup"><span data-stu-id="e1373-161">To pass an operation or a function to a `Run` method, you have to obtain an   instance of the operation's or function's class, using the simulator's `Get<>` method.</span></span>

### <a name="processing-the-results"></a><span data-ttu-id="e1373-162">Traitement des résultats</span><span class="sxs-lookup"><span data-stu-id="e1373-162">Processing the Results</span></span>

<span data-ttu-id="e1373-163">Les résultats de l’algorithme quantique sont retournés à partir de la méthode `Run`.</span><span class="sxs-lookup"><span data-stu-id="e1373-163">The results of the quantum algorithm are returned from the `Run` method.</span></span>
<span data-ttu-id="e1373-164">La méthode `Run` s’exécute de façon asynchrone et retourne par conséquent une instance de <xref:System.Threading.Tasks.Task`1>.</span><span class="sxs-lookup"><span data-stu-id="e1373-164">The `Run` method executes asynchronously thus it returns an instance of <xref:System.Threading.Tasks.Task`1>.</span></span>
<span data-ttu-id="e1373-165">Il existe plusieurs façons d’obtenir les résultats de l’opération réelle.</span><span class="sxs-lookup"><span data-stu-id="e1373-165">There are multiple ways to get the actual operation's results.</span></span> <span data-ttu-id="e1373-166">La méthode la plus simple consiste à utiliser la [propriété `Result`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result) de `Task` :</span><span class="sxs-lookup"><span data-stu-id="e1373-166">The simplest is by using the `Task`'s [`Result` property](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span></span>

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
<span data-ttu-id="e1373-167">mais d’autres techniques, telles que l’utilisation de la [méthode `Wait`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait)ou du [mot clé `await`](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) en C#, fonctionnent également.</span><span class="sxs-lookup"><span data-stu-id="e1373-167">but other techniques, like using the [`Wait` method](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) or C# [`await` keyword](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) will also work.</span></span>

<span data-ttu-id="e1373-168">Comme avec les arguments, les tuples Q# sont représentés par des instances `ValueTuple` et les tableaux Q# sont représentés par des instances `QArray`.</span><span class="sxs-lookup"><span data-stu-id="e1373-168">As with arguments, Q# tuples are represented as `ValueTuple` instances and Q# arrays are represented as `QArray` instances.</span></span>
<span data-ttu-id="e1373-169">Les types définis par l’utilisateur sont retournés comme types de base.</span><span class="sxs-lookup"><span data-stu-id="e1373-169">User-defined types are returned as their base types.</span></span>
<span data-ttu-id="e1373-170">Le tuple vide, `()`, est retourné en tant qu’instance de la classe `QVoid`.</span><span class="sxs-lookup"><span data-stu-id="e1373-170">The empty tuple, `()`, is returned as an instance of the `QVoid` class.</span></span>

<span data-ttu-id="e1373-171">De nombreux algorithmes quantiques nécessitent un post-traitement important pour en extraire des réponses utiles.</span><span class="sxs-lookup"><span data-stu-id="e1373-171">Many quantum algorithms require substantial post-processing to derive useful answers.</span></span>
<span data-ttu-id="e1373-172">Par exemple, la partie quantique de l’algorithme de Shor n’est que le début d’un calcul qui recherche les facteurs d’un nombre.</span><span class="sxs-lookup"><span data-stu-id="e1373-172">For instance, the quantum part of Shor's algorithm is just the beginning of a computation that finds the factors of a number.</span></span>

<span data-ttu-id="e1373-173">Dans la plupart des cas, il est plus simple et plus facile d’effectuer ce type de post-traitement dans le pilote classique.</span><span class="sxs-lookup"><span data-stu-id="e1373-173">In most cases, it is simplest and easiest to do this sort of post-processing in the classical driver.</span></span>
<span data-ttu-id="e1373-174">Seul le pilote classique peut rapporter les résultats à l’utilisateur ou les écrire sur le disque.</span><span class="sxs-lookup"><span data-stu-id="e1373-174">Only the classical driver can report results to the user or write them to disk.</span></span>
<span data-ttu-id="e1373-175">Le pilote classique aura accès à des bibliothèques analytiques et à d’autres fonctions mathématiques qui ne sont pas exposées en Q#.</span><span class="sxs-lookup"><span data-stu-id="e1373-175">The classical driver will have access to analytical libraries and other mathematical functions that are not exposed in Q#.</span></span>


## <a name="failures"></a><span data-ttu-id="e1373-176">Échecs</span><span class="sxs-lookup"><span data-stu-id="e1373-176">Failures</span></span>

<span data-ttu-id="e1373-177">Lorsque l’instruction `fail` en Q# est atteinte pendant l’exécution d’une opération, une `ExecutionFailException` est levée.</span><span class="sxs-lookup"><span data-stu-id="e1373-177">When the Q# `fail` statement is reached during the execution of an operation, an `ExecutionFailException` is thrown.</span></span>

<span data-ttu-id="e1373-178">En raison de l’utilisation de `System.Task` dans la méthode `Run`, l’exception levée à la suite d’une instruction `fail` sera incluse dans une `System.AggregateException`.</span><span class="sxs-lookup"><span data-stu-id="e1373-178">Due to the use of `System.Task` in the `Run` method, the exception thrown as a result of a `fail` statement will be wrapped into a `System.AggregateException`.</span></span>
<span data-ttu-id="e1373-179">Pour trouver la raison réelle de l’échec, vous devez itérer dans le `AggregateException` 
`InnerExceptions`, par exemple :</span><span class="sxs-lookup"><span data-stu-id="e1373-179">To find the actual reason for the failure, you need to iterate into the `AggregateException` 
`InnerExceptions`, for example:</span></span>

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a><span data-ttu-id="e1373-180">Autres langages classiques de programmation</span><span class="sxs-lookup"><span data-stu-id="e1373-180">Other Classical Languages</span></span>

<span data-ttu-id="e1373-181">Bien que les exemples que nous avons fournis soient en C#, F# et Python, le Quantum Development Kit prend également en charge l’écriture de programmes hôtes classiques dans d’autres langages informatiques.</span><span class="sxs-lookup"><span data-stu-id="e1373-181">While the samples we have provided are in C#, F#, and Python, the Quantum Development Kit also supports writing classical host programs in other languages.</span></span>
<span data-ttu-id="e1373-182">Par exemple, si vous souhaitez écrire un programme hôte en Visual Basic, [il devrait parfaitement fonctionner](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span><span class="sxs-lookup"><span data-stu-id="e1373-182">For example, if you want to write a host program in Visual Basic, [it should work just fine](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span></span>
