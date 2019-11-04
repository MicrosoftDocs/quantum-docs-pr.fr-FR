---
title: 'Q # techniques-test et débogage | Microsoft Docs'
description: 'Techniques Q #-test et débogage'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183486"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="2b7d3-103">Test et débogage</span><span class="sxs-lookup"><span data-stu-id="2b7d3-103">Testing and Debugging</span></span>

<span data-ttu-id="2b7d3-104">Comme pour la programmation classique, il est essentiel de pouvoir vérifier que les programmes de Quantum fonctionnent comme prévu, et de pouvoir diagnostiquer un programme Quantum qui est incorrect.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="2b7d3-105">Dans cette section, nous allons aborder les outils proposés par Q # pour le test et le débogage de programmes quantiques.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="2b7d3-106">Tests unitaires</span><span class="sxs-lookup"><span data-stu-id="2b7d3-106">Unit Tests</span></span>

<span data-ttu-id="2b7d3-107">Une approche courante du test des programmes classiques consiste à écrire de petits programmes appelés *tests unitaires* , qui exécutent du code dans une bibliothèque et à comparer la sortie à une sortie attendue.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="2b7d3-108">Par exemple, nous pouvons nous assurer que `Square(2)` retourne `4`, puisque nous savons *un a priori* que $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="2b7d3-109">Q # prend en charge la création de tests unitaires pour les programmes Quantum, et qui peuvent être exécutés en tant que tests dans le Framework de tests unitaires [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="2b7d3-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="2b7d3-110">Création d’un projet de test</span><span class="sxs-lookup"><span data-stu-id="2b7d3-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="2b7d3-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2b7d3-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="2b7d3-112">Ouvrez Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="2b7d3-113">Accédez au menu `File` et sélectionnez `New` > `Project...`.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="2b7d3-114">Dans l’Explorateur de modèles de projet, sous `Installed` > `Visual C#`, sélectionnez le modèle `Q# Test Project`.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-114">In the project template explorer, under `Installed` > `Visual C#`, select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="2b7d3-115">Ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2b7d3-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="2b7d3-116">À partir de votre ligne de commande favorite, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="2b7d3-117">Dans les deux cas, deux fichiers sont ouverts sur votre nouveau projet.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-117">In either case, your new project will have two files open.</span></span>
<span data-ttu-id="2b7d3-118">Le premier fichier, `Tests.qs`, offre un emplacement pratique pour définir de nouveaux tests unitaires Q #.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-118">The first file, `Tests.qs`, provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="2b7d3-119">Initialement, ce fichier contient un exemple de test unitaire `AllocateQubitTest` qui vérifie qu’un qubit nouvellement alloué se trouve dans l’État $ \ket{0}$ et imprime un message :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-119">Initially this file contains one sample unit test `AllocateQubitTest` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="2b7d3-120">Toute opération Q # compatible avec le type `(Unit => Unit)` ou la fonction compatible avec `(Unit -> Unit)` peut être exécutée en tant que test unitaire.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-120">Any Q# operation compatible with the type `(Unit => Unit)` or function compatible with `(Unit -> Unit)` can be executed as a unit test.</span></span> 

<span data-ttu-id="2b7d3-121">Le deuxième fichier, `TestSuiteRunner.cs` contient une méthode qui découvre et exécute les tests unitaires Q #.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-121">The second file, `TestSuiteRunner.cs` contains a method that discovers and runs Q# unit tests.</span></span> <span data-ttu-id="2b7d3-122">Il s’agit de la méthode `TestTarget` annotée avec `OperationDriver` attribut.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-122">This is the method `TestTarget` annotated with `OperationDriver` attribute.</span></span>
<span data-ttu-id="2b7d3-123">L’attribut `OperationDriver` fait partie de la bibliothèque d’extensions xUnit Microsoft. Quantum. simulation. xUnit.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-123">The `OperationDriver` attribute is a part of the Xunit extension library Microsoft.Quantum.Simulation.Xunit.</span></span>
<span data-ttu-id="2b7d3-124">Le Framework de tests unitaires appelle `TestTarget` méthode pour chaque test unitaire Q # qu’il a découvert.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-124">The unit testing framework calls `TestTarget` method for every Q# unit test it has discovered.</span></span>
<span data-ttu-id="2b7d3-125">L’infrastructure passe la description de test unitaire à la méthode via `op` argument.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-125">The framework passes the unit test description to the method through `op` argument.</span></span> <span data-ttu-id="2b7d3-126">La ligne de code suivante :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-126">The following line of code:</span></span>
```csharp
op.TestOperationRunner(sim);
```
<span data-ttu-id="2b7d3-127">exécute le test unitaire sur `QuantumSimulator`.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-127">executes the unit test on `QuantumSimulator`.</span></span>

<span data-ttu-id="2b7d3-128">Par défaut, le mécanisme de détection de tests unitaires recherche toutes les fonctions Q # ou les opérations de type compatible qui répondent aux propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-128">By default, the unit test discovery mechanism looks for all Q# functions or operations of compatible type that satisfy the following properties:</span></span>
* <span data-ttu-id="2b7d3-129">Situé dans le même assembly que la méthode annotée avec l’attribut `OperationDriver`.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-129">Located in the same assembly as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="2b7d3-130">Situé dans le même espace de noms que la méthode annotée avec l’attribut `OperationDriver`.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-130">Located in the same namespace as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="2b7d3-131">A un nom se terminant par `Test`.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-131">Has a name ending with `Test`.</span></span>

<span data-ttu-id="2b7d3-132">Un assembly, un espace de noms et un suffixe pour les fonctions et les opérations de test unitaire peuvent être définis à l’aide de paramètres facultatifs de l’attribut `OperationDriver` :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-132">An assembly, a namespace, and a suffix for unit test functions and operations can be set using optional parameters of the `OperationDriver` attribute:</span></span>
* <span data-ttu-id="2b7d3-133">`AssemblyName` paramètre définit le nom de l’assembly dans lequel les tests sont recherchés.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-133">`AssemblyName` parameter sets the name of the assembly which is being searched for tests.</span></span>
* <span data-ttu-id="2b7d3-134">`TestNamespace` paramètre définit le nom de l’espace de noms dans lequel les tests sont recherchés.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-134">`TestNamespace` parameter sets the name of the namespace which is being searched for tests.</span></span>
* <span data-ttu-id="2b7d3-135">`Suffix` définit le suffixe des noms d’opération ou de fonction qui sont considérés comme des tests unitaires.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-135">`Suffix` sets the suffix of operation or function names that are considered to be unit tests.</span></span>

<span data-ttu-id="2b7d3-136">En outre, le `TestCasePrefix` paramètre facultatif vous permet de définir un préfixe pour le nom du cas de test.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-136">In addition, the `TestCasePrefix` optional parameter lets you set a prefix for the name of the test case.</span></span> <span data-ttu-id="2b7d3-137">Le préfixe devant le nom de l’opération s’affiche dans la liste des cas de test.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-137">The prefix in front of the operation name will appear in the list of test cases.</span></span> <span data-ttu-id="2b7d3-138">Par exemple, `TestCasePrefix = "QSim:"` entraîne l’affichage de `AllocateQubitTest` comme `QSim:AllocateQubitTest` dans la liste des tests trouvés.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-138">For example, `TestCasePrefix = "QSim:"` will cause `AllocateQubitTest` to appear as `QSim:AllocateQubitTest` in the list of found tests.</span></span> <span data-ttu-id="2b7d3-139">Cela peut être utile pour indiquer, par exemple, le simulateur utilisé pour exécuter un test.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-139">This can be useful to indicate, for instance, which simulator is used to run a test.</span></span>

### <a name="running-q-unit-tests"></a><span data-ttu-id="2b7d3-140">Exécution de tests unitaires Q #</span><span class="sxs-lookup"><span data-stu-id="2b7d3-140">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="2b7d3-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2b7d3-141">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="2b7d3-142">Dans le cadre d’une configuration par solution unique, accédez au menu `Test`, puis sélectionnez `Test Settings` > `Default Processor Architecture` > `X64`.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-142">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="2b7d3-143">Le paramètre d’architecture de processeur par défaut de Visual Studio est stocké dans le fichier d’options de solution (`.suo`) pour chaque solution.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-143">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="2b7d3-144">Si vous supprimez ce fichier, vous devez sélectionner `X64` à nouveau en tant qu’architecture de processeur.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-144">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="2b7d3-145">Générez le projet, accédez au menu `Test` et sélectionnez `Windows` > `Test Explorer`.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-145">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="2b7d3-146">`AllocateQubitTest` s’affiche dans la liste des tests du groupe `Not Run Tests`.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-146">`AllocateQubitTest` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="2b7d3-147">Sélectionnez `Run All` ou exécutez ce test individuel, et il doit réussir.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-147">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="2b7d3-148">Ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2b7d3-148">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="2b7d3-149">Pour exécuter les tests, accédez au dossier du projet (le dossier qui contient `Tests.csproj`) et exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-149">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="2b7d3-150">La sortie doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-150">You should get output similar to the following:</span></span>

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

***

## <a name="logging-and-assertions"></a><span data-ttu-id="2b7d3-151">Journalisation et assertions</span><span class="sxs-lookup"><span data-stu-id="2b7d3-151">Logging and Assertions</span></span>

<span data-ttu-id="2b7d3-152">Une conséquence importante du fait que les fonctions dans Q # n’ont pas d’effets secondaires, c’est que tous les effets de l’exécution d’une fonction dont le type de sortie est le tuple vide `()` ne peuvent jamais être observés dans un programme Q #.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-152">One important consequence of the fact that functions in Q# have no side effects is that any effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="2b7d3-153">Autrement dit, un ordinateur cible peut choisir de ne pas exécuter de fonction qui retourne `()` avec la garantie que cette omission ne modifiera pas le comportement d’un code Q # suivant.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-153">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="2b7d3-154">Cela rend les fonctions qui retournent `()` un outil utile pour incorporer des assertions et la logique de débogage dans des programmes Q #.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-154">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

### <a name="logging"></a><span data-ttu-id="2b7d3-155">Journalisation</span><span class="sxs-lookup"><span data-stu-id="2b7d3-155">Logging</span></span>

<span data-ttu-id="2b7d3-156">La fonction intrinsèque <xref:microsoft.quantum.intrinsic.message> a le type `(String -> Unit)` et permet la création de messages de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-156">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

<span data-ttu-id="2b7d3-157">L’action `onLog` de `QuantumSimulator` peut être utilisée pour définir des actions exécutées lorsque le code Q # appelle `Message`.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-157">The `onLog` action of `QuantumSimulator` can be used to define actions performed when Q# code calls `Message`.</span></span> <span data-ttu-id="2b7d3-158">Par défaut, les messages enregistrés sont imprimés dans la sortie standard.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-158">By default logged messages are printed to standard output.</span></span>

<span data-ttu-id="2b7d3-159">Lors de la définition d’une suite de tests unitaires, les messages journalisés peuvent être dirigés vers la sortie du test.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-159">When defining a unit test suite, the logged messages can be directed to the test output.</span></span> <span data-ttu-id="2b7d3-160">Quand un projet est créé à partir du modèle de projet de test Q #, cette redirection est préconfigurée pour la suite et créée par défaut comme suit :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-160">When a project is created from Q# Test Project template, this redirection is pre-configured for the suite and created by default as follows:</span></span>

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="2b7d3-161">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2b7d3-161">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="2b7d3-162">Après avoir exécuté un test dans l’Explorateur de tests et cliqué sur le test, un panneau s’affiche avec des informations sur l’exécution des tests : état réussite/échec, temps écoulé et lien de sortie.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-162">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="2b7d3-163">Si vous cliquez sur le lien « sortie », la sortie de test s’ouvre dans une nouvelle fenêtre.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-163">If you click the "Output" link, test output will open in a new window.</span></span>

![sortie de test](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="2b7d3-165">Ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2b7d3-165">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="2b7d3-166">L’État réussite/échec de chaque test est imprimé sur la console par `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-166">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="2b7d3-167">Pour les tests ayant échoué, les sorties enregistrées à la suite de l’appel de `output.WriteLine(msg)` ci-dessus sont également imprimées sur la console pour aider à diagnostiquer l’échec.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-167">For failing tests, the outputs logged as a result of the `output.WriteLine(msg)` call above are also printed to the console to help diagnose the failure.</span></span>

***

### <a name="assertions"></a><span data-ttu-id="2b7d3-168">Assertions</span><span class="sxs-lookup"><span data-stu-id="2b7d3-168">Assertions</span></span>

<span data-ttu-id="2b7d3-169">La même logique peut être appliquée à l’implémentation des assertions.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-169">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="2b7d3-170">Prenons un exemple simple :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-170">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="2b7d3-171">Ici, le mot clé `fail` indique que le calcul ne doit pas continuer, déclenchant une exception sur l’ordinateur cible exécutant le programme Q #.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-171">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="2b7d3-172">Par définition, une défaillance de ce type ne peut pas être observée dans Q #, car aucun code Q # supplémentaire n’est exécuté après qu’une instruction `fail` a été atteinte.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-172">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="2b7d3-173">Par conséquent, si nous poursuivons un appel à `AssertPositive`, nous pouvons être sûrs que son entrée était positive.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-173">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="2b7d3-174">En s’appuyant sur ces idées, [préambule destiné à](xref:microsoft.quantum.libraries.standard.prelude) propose deux assertions particulièrement utiles, <xref:microsoft.quantum.intrinsic.assert> et <xref:microsoft.quantum.intrinsic.assertprob> modelées comme des opérations sur `()`.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-174">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="2b7d3-175">Ces assertions prennent chacune un opérateur Pauli décrivant une mesure particulière d’intérêt, un registre quantique sur lequel une mesure doit être effectuée et un résultat hypothétique.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-175">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="2b7d3-176">Sur les machines cibles qui fonctionnent par simulation, nous ne sommes pas liés par le niveau de travail de [non-clonage](https://en.wikipedia.org/wiki/No-cloning_theorem)et peuvent effectuer ces mesures sans perturber le registre passé à ces assertions.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-176">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="2b7d3-177">Un simulateur peut ensuite, à l’instar de la fonction `AssertPositive` ci-dessus, abandonner le calcul si le résultat hypothétique n’est pas respecté dans la pratique :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-177">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="2b7d3-178">Sur le matériel Quantum physique, où le niveau de stockage de non-clonage empêche l’examen de l’État Quantum, les opérations de `Assert` et de `AssertProb` renvoient simplement `()` sans autre effet.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-178">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="2b7d3-179">L’espace de noms <xref:microsoft.quantum.diagnostics> fournit plusieurs autres fonctions de la famille `Assert` qui nous permettent de vérifier des conditions plus avancées.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-179">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="2b7d3-180">Fonctions dump</span><span class="sxs-lookup"><span data-stu-id="2b7d3-180">Dump Functions</span></span>

<span data-ttu-id="2b7d3-181">Pour vous aider à résoudre les problèmes liés aux programmes Quantum, l’espace de noms <xref:microsoft.quantum.diagnostics> offre deux fonctions qui peuvent vider dans un fichier l’état actuel de l’ordinateur cible : <xref:microsoft.quantum.diagnostics.dumpmachine> et <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-181">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="2b7d3-182">La sortie générée de chaque dépend de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-182">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="2b7d3-183">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="2b7d3-183">DumpMachine</span></span>

<span data-ttu-id="2b7d3-184">Le simulateur quantum complet distribué dans le cadre du kit de développement Quantum écrit dans le fichier la [fonction Wave](https://en.wikipedia.org/wiki/Wave_function) de l’ensemble du système Quantum, sous la forme d’un tableau unidimensionnel de nombres complexes, dans lequel chaque élément représente l’amplitude du probabilité de mesure de l’état de la base de calcul $ \ket{n} $, où $ \ket{n} = \ket{b_{n-1}... b_1b_0} $ pour bits $\{b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-184">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="2b7d3-185">Par exemple, sur un ordinateur avec seulement deux qubits alloués et dans l’État Quantum $ $ \begin{align} \ket{\Psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ appelant <xref:microsoft.quantum.diagnostics.dumpmachine> génère cette sortie :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-185">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="2b7d3-186">La première ligne fournit un commentaire avec les ID des qubits correspondants dans leur ordre significatif.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-186">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="2b7d3-187">Les autres lignes décrivent l’amplitude de probabilité de la mesure du vecteur d’état de base $ \ket{n} $ à la fois dans les formats cartésien et polaire.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-187">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="2b7d3-188">En détail pour la première ligne :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-188">In detail for the first row:</span></span>

* <span data-ttu-id="2b7d3-189">**`∣0❭:`** cette ligne correspond à l’état de la base de calcul `0`</span><span class="sxs-lookup"><span data-stu-id="2b7d3-189">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="2b7d3-190">**`0.707107 +  0.000000 i`** : amplitude de probabilité au format cartésien.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-190">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="2b7d3-191">**` == `** : le signe `equal` sépare les deux représentations équivalentes.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-191">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="2b7d3-192">**`**********  `** : représentation graphique de l’amplitude, le nombre de `*` est proportionnel à la probabilité de mesurer ce vecteur d’État.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-192">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="2b7d3-193">**`[ 0.500000 ]`** : valeur numérique de l’amplitude</span><span class="sxs-lookup"><span data-stu-id="2b7d3-193">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="2b7d3-194">**`    ---`** : représentation graphique de la phase de l’amplitude (voir ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="2b7d3-194">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="2b7d3-195">**`[ 0.0000 rad ]`** : valeur numérique de la phase (en radians).</span><span class="sxs-lookup"><span data-stu-id="2b7d3-195">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="2b7d3-196">L’amplitude et la phase sont toutes les deux affichées avec une représentation graphique.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-196">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="2b7d3-197">La représentation magnitude est simple : elle affiche une barre de `*`, plus la probabilité de la barre est importante.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-197">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="2b7d3-198">Pour la phase, nous affichons les symboles suivants pour représenter l’angle en fonction des plages :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-198">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

<span data-ttu-id="2b7d3-199">Les exemples suivants montrent `DumpMachine` pour certains États courants :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-199">The following examples show `DumpMachine` for some common states:</span></span>

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > <span data-ttu-id="2b7d3-200">L’ID d’un qubit est assigné au moment de l’exécution et n’est pas nécessairement aligné avec l’ordre dans lequel le qubit a été alloué ou sa position dans un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-200">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="2b7d3-201">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2b7d3-201">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="2b7d3-202">Vous pouvez déterminer un ID qubit dans Visual Studio en plaçant un point d’arrêt dans votre code et en inspectant la valeur d’une variable qubit, par exemple :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-202">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![afficher l’ID qubit dans Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="2b7d3-204">le qubit avec l’index `0` sur `register2` possède l’ID =`3`, le qubit avec l’index `1` possède l’ID =`2`.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-204">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="2b7d3-205">Ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2b7d3-205">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="2b7d3-206">Vous pouvez déterminer un ID qubit à l’aide de la fonction <xref:microsoft.quantum.intrinsic.message> et en passant la variable qubit dans le message, par exemple :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-206">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="2b7d3-207">qui peut générer cette sortie :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-207">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="2b7d3-208">ce qui signifie que le qubit avec l’index `0` sur `register2` a l’ID =`3`, le qubit avec l’index `1` possède l’ID =`2`.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-208">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="2b7d3-209"><xref:microsoft.quantum.diagnostics.dumpmachine> fait partie de l’espace de noms <xref:microsoft.quantum.diagnostics>, afin de pouvoir l’utiliser, vous devez ajouter une instruction `open` :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-209"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a><span data-ttu-id="2b7d3-210">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="2b7d3-210">DumpRegister</span></span>

<span data-ttu-id="2b7d3-211"><xref:microsoft.quantum.diagnostics.dumpregister> fonctionne comme <xref:microsoft.quantum.diagnostics.dumpmachine>, sauf qu’il prend également un tableau de qubits pour limiter la quantité d’informations à ce qui concerne uniquement les qubits correspondants.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-211"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="2b7d3-212">Comme avec <xref:microsoft.quantum.diagnostics.dumpmachine>, les informations générées par <xref:microsoft.quantum.diagnostics.dumpregister> dépendent de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-212">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="2b7d3-213">Pour le simulateur Quantum à état complet, il écrit dans le fichier la fonction Wave jusqu’à une phase globale du sous-système Quantum généré par le qubits fourni dans le même format que <xref:microsoft.quantum.diagnostics.dumpmachine>.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-213">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="2b7d3-214">Par exemple, reprenez un ordinateur avec seulement deux qubits alloués et dans l’État Quantum $ $ \begin{align} \ket{\Psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ pi/4} ((\frac{1}{\sqrt{2}} \ Ket{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ appelant <xref:microsoft.quantum.diagnostics.dumpregister> pour `qubit[0]` génère cette sortie :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-214">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="2b7d3-215">et l’appel de <xref:microsoft.quantum.diagnostics.dumpregister> pour `qubit[1]` génère cette sortie :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-215">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="2b7d3-216">En général, l’état d’un registre qui est enchevêtré avec un autre registre est un État mixte plutôt qu’un état pur.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-216">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="2b7d3-217">Dans ce cas, <xref:microsoft.quantum.diagnostics.dumpregister> génère le message suivant :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-217">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="2b7d3-218">L’exemple suivant montre comment vous pouvez utiliser à la fois <xref:microsoft.quantum.diagnostics.dumpregister> et <xref:microsoft.quantum.diagnostics.dumpmachine> dans votre code Q # :</span><span class="sxs-lookup"><span data-stu-id="2b7d3-218">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a><span data-ttu-id="2b7d3-219">Débogage</span><span class="sxs-lookup"><span data-stu-id="2b7d3-219">Debugging</span></span>

<span data-ttu-id="2b7d3-220">En plus des fonctions et opérations d' `Assert` et de `Dump`, Q # prend en charge un sous-ensemble de fonctionnalités de débogage Visual Studio standard : [définition de points d’arrêt de ligne](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [exécution pas à pas du code à l’aide de F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) et [inspection des valeurs des variables classiques ](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)sont tous possibles au cours de l’exécution du code sur le simulateur.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-220">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="2b7d3-221">Le débogage dans Visual Studio Code n’est pas encore pris en charge.</span><span class="sxs-lookup"><span data-stu-id="2b7d3-221">Debugging in Visual Studio Code is not yet supported.</span></span>

