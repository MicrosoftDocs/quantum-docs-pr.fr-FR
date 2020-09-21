---
title: Test et débogage
description: Découvrez comment utiliser des tests unitaires, des faits et des assertions, et des fonctions dump pour tester et déboguer des programmes quantiques.
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2f2181d388a59c1c6c5a0f13c9aa49d5fa1e51ae
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833182"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="f598a-103">Test et débogage</span><span class="sxs-lookup"><span data-stu-id="f598a-103">Testing and debugging</span></span>

<span data-ttu-id="f598a-104">Comme pour la programmation classique, il est essentiel de pouvoir vérifier que les programmes de Quantum fonctionnent comme prévu et de pouvoir diagnostiquer un comportement incorrect.</span><span class="sxs-lookup"><span data-stu-id="f598a-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="f598a-105">Dans cette section, nous allons aborder les outils proposés par Q# pour le test et le débogage de programmes quantiques.</span><span class="sxs-lookup"><span data-stu-id="f598a-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="f598a-106">Tests unitaires</span><span class="sxs-lookup"><span data-stu-id="f598a-106">Unit Tests</span></span>

<span data-ttu-id="f598a-107">Une approche courante du test des programmes classiques consiste à écrire de petits programmes appelés *tests unitaires*, qui exécutent le code dans une bibliothèque et à comparer la sortie à une sortie attendue.</span><span class="sxs-lookup"><span data-stu-id="f598a-107">One common approach to testing classical programs is to write small programs called *unit tests*, which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="f598a-108">Par exemple, vous pouvez vous assurer que `Square(2)` retourne, `4` car vous connaissez *un priori* de $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="f598a-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="f598a-109">Q# prend en charge la création de tests unitaires pour les programmes Quantum et peut s’exécuter en tant que tests dans l’infrastructure de tests unitaires [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="f598a-109">Q# supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="f598a-110">Création d’un projet de test</span><span class="sxs-lookup"><span data-stu-id="f598a-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="f598a-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f598a-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f598a-112">Ouvrez Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="f598a-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="f598a-113">Accédez au menu **fichier** et sélectionnez **nouveau > projet...**. Dans l’angle supérieur droit, recherchez `Q#` et sélectionnez le modèle \*\* Q# projet de test\*\* .</span><span class="sxs-lookup"><span data-stu-id="f598a-113">Go to the **File** menu and select **New > Project...**. In the upper right corner, search for `Q#`, and select the **Q# Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="f598a-114">Code de ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f598a-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f598a-115">À partir de votre ligne de commande favorite, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f598a-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="f598a-116">Votre nouveau projet contient un seul fichier `Tests.qs` , qui fournit un emplacement pratique pour définir de nouveaux Q# tests unitaires.</span><span class="sxs-lookup"><span data-stu-id="f598a-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="f598a-117">Initialement, ce fichier contient un exemple de test unitaire `AllocateQubit` qui vérifie qu’un qubit nouvellement alloué est dans l’État $ \ket {0} $ et imprime un message :</span><span class="sxs-lookup"><span data-stu-id="f598a-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="f598a-118">Toute Q# opération ou fonction qui accepte un argument de type `Unit` et retourne `Unit` peut être marquée comme un test unitaire via l' `@Test("...")` attribut.</span><span class="sxs-lookup"><span data-stu-id="f598a-118">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="f598a-119">Dans l’exemple précédent, l’argument de cet attribut, `"QuantumSimulator"` , spécifie la cible sur laquelle le test s’exécute.</span><span class="sxs-lookup"><span data-stu-id="f598a-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="f598a-120">Un test unique peut s’exécuter sur plusieurs cibles.</span><span class="sxs-lookup"><span data-stu-id="f598a-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="f598a-121">Par exemple, ajoutez un attribut `@Test("ResourcesEstimator")` avant `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="f598a-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="f598a-122">Enregistrez le fichier et exécutez tous les tests.</span><span class="sxs-lookup"><span data-stu-id="f598a-122">Save the file and run all tests.</span></span> <span data-ttu-id="f598a-123">Il doit maintenant y avoir deux tests unitaires, un où `AllocateQubit` s’exécute sur le `QuantumSimulator` , et un autre où il s’exécute dans le `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="f598a-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="f598a-124">Le Q# compilateur reconnaît les cibles intégrées `"QuantumSimulator"` , `"ToffoliSimulator"` et `"ResourcesEstimator"` en tant que cibles d’exécution valides pour les tests unitaires.</span><span class="sxs-lookup"><span data-stu-id="f598a-124">The Q# compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid run targets for unit tests.</span></span> <span data-ttu-id="f598a-125">Il est également possible de spécifier un nom qualifié complet pour définir une cible d’exécution personnalisée.</span><span class="sxs-lookup"><span data-stu-id="f598a-125">It is also possible to specify any fully qualified name to define a custom run target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="f598a-126">Exécution de Q# tests unitaires</span><span class="sxs-lookup"><span data-stu-id="f598a-126">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="f598a-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f598a-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f598a-128">Dans le cadre d’une configuration par solution unique, accédez au menu **test** et sélectionnez **paramètres de test > architecture de processeur par défaut > x64**.</span><span class="sxs-lookup"><span data-stu-id="f598a-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64**.</span></span>

> [!TIP]
> <span data-ttu-id="f598a-129">Le paramètre d’architecture de processeur par défaut pour Visual Studio est stocké dans le fichier options de solution ( `.suo` ) de chaque solution.</span><span class="sxs-lookup"><span data-stu-id="f598a-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="f598a-130">Si vous supprimez ce fichier, vous devez à nouveau sélectionner **x64** comme architecture de processeur.</span><span class="sxs-lookup"><span data-stu-id="f598a-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="f598a-131">Générez le projet, ouvrez le menu **test** , puis sélectionnez **Windows >** de l’Explorateur de tests.</span><span class="sxs-lookup"><span data-stu-id="f598a-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer**.</span></span> <span data-ttu-id="f598a-132">**AllocateQubit** s’affiche dans la liste des tests dans le groupe **tests non exécutés** .</span><span class="sxs-lookup"><span data-stu-id="f598a-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="f598a-133">Sélectionnez **exécuter tout** ou exécuter ce test individuel.</span><span class="sxs-lookup"><span data-stu-id="f598a-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="f598a-134">Code de ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f598a-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f598a-135">Pour exécuter les tests, accédez au dossier du projet (le dossier qui contient `Tests.csproj` ), puis exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="f598a-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="f598a-136">La sortie doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f598a-136">You should get output similar to the following:</span></span>

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

<span data-ttu-id="f598a-137">Les tests unitaires peuvent être filtrés en fonction de leur nom ou de la cible d’exécution :</span><span class="sxs-lookup"><span data-stu-id="f598a-137">Unit tests can be filtered according to their name or the run target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="f598a-138">La fonction intrinsèque <xref:microsoft.quantum.intrinsic.message> a le type `(String -> Unit)` et permet la création de messages de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="f598a-138">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="f598a-139">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f598a-139">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f598a-140">Après avoir exécuté un test dans l’Explorateur de tests et cliqué sur le test, un panneau s’affiche avec des informations sur la série de tests : état réussite/échec, temps écoulé et un lien vers la sortie.</span><span class="sxs-lookup"><span data-stu-id="f598a-140">After you run a test in Test Explorer and click on the test, a panel displays with information about test run: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="f598a-141">Cliquez sur **sortie** pour ouvrir la sortie de test dans une nouvelle fenêtre.</span><span class="sxs-lookup"><span data-stu-id="f598a-141">Click **Output** to open the test output in a new window.</span></span>

![sortie de test](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="f598a-143">Code de ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f598a-143">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f598a-144">L’État réussite/échec de chaque test est imprimé sur la console par `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="f598a-144">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="f598a-145">Pour les tests ayant échoué, les sorties sont également imprimées sur la console pour faciliter le diagnostic de l’échec.</span><span class="sxs-lookup"><span data-stu-id="f598a-145">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="f598a-146">Faits et assertions</span><span class="sxs-lookup"><span data-stu-id="f598a-146">Facts and Assertions</span></span>

<span data-ttu-id="f598a-147">Étant donné que les fonctions de n' Q# ont pas d’effets secondaires _logiques_ , vous ne pouvez jamais observer, à partir d’un Q# programme, tous les autres genres d’effets de l’exécution d’une fonction dont le type de sortie est le tuple vide `()` .</span><span class="sxs-lookup"><span data-stu-id="f598a-147">Because functions in Q# have no _logical_ side effects, you can never observe, from within a Q# program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="f598a-148">Autrement dit, un ordinateur cible peut choisir de ne pas exécuter une fonction qui retourne `()` avec la garantie que cette omission ne modifiera pas le comportement d’un Q# code suivant.</span><span class="sxs-lookup"><span data-stu-id="f598a-148">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="f598a-149">Ce comportement rend les fonctions qui retournent `()` (comme `Unit` ) un outil utile pour incorporer des assertions et la logique de débogage dans des Q# programmes.</span><span class="sxs-lookup"><span data-stu-id="f598a-149">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="f598a-150">Prenons un exemple simple :</span><span class="sxs-lookup"><span data-stu-id="f598a-150">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="f598a-151">Ici, le mot clé `fail` indique que le calcul ne doit pas continuer et lève une exception sur l’ordinateur cible qui exécute le Q# programme.</span><span class="sxs-lookup"><span data-stu-id="f598a-151">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="f598a-152">Par définition, une défaillance de ce type ne peut pas être observée dans Q# , car l’ordinateur cible n’exécute plus le Q# code après avoir atteint une `fail` instruction.</span><span class="sxs-lookup"><span data-stu-id="f598a-152">By definition, a failure of this kind cannot be observed from within Q#, as the target machine no longer runs the Q# code after reaching a `fail` statement.</span></span>
<span data-ttu-id="f598a-153">Par conséquent, si nous poursuivons un appel à `PositivityFact` , nous pouvons être assurés que son entrée était positive.</span><span class="sxs-lookup"><span data-stu-id="f598a-153">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="f598a-154">Notez que nous pouvons implémenter le même comportement que l' `PositivityFact` utilisation [`Fact`](xref:microsoft.quantum.diagnostics.fact) de la fonction à partir de l' <xref:microsoft.quantum.diagnostics> espace de noms :</span><span class="sxs-lookup"><span data-stu-id="f598a-154">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="f598a-155">En revanche, les *assertions*sont utilisées de la même façon que les faits, mais peuvent dépendre de l’état de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="f598a-155">*Assertions*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="f598a-156">En conséquence, ils sont définis en tant qu’opérations, tandis que les faits sont définis en tant que fonctions (comme dans l’exemple précédent).</span><span class="sxs-lookup"><span data-stu-id="f598a-156">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="f598a-157">Pour comprendre la distinction, considérez l’utilisation suivante d’un fait au sein d’une assertion :</span><span class="sxs-lookup"><span data-stu-id="f598a-157">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="f598a-158">Ici, nous utilisons l’opération <xref:microsoft.quantum.environment.getqubitsavailabletouse> pour retourner le nombre de qubits disponibles à utiliser.</span><span class="sxs-lookup"><span data-stu-id="f598a-158">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="f598a-159">Comme cela dépend de l’état global du programme et de son environnement d’exécution, notre définition de `AssertQubitsAreAvailable` doit également être une opération.</span><span class="sxs-lookup"><span data-stu-id="f598a-159">As this depends on the global state of the program and its run environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="f598a-160">Toutefois, nous pouvons utiliser cet état global pour donner une `Bool` valeur simple comme entrée à la `Fact` fonction.</span><span class="sxs-lookup"><span data-stu-id="f598a-160">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="f598a-161">[Préambule destiné à](xref:microsoft.quantum.libraries.standard.prelude), en s’appuyant sur ces idées, offre deux assertions particulièrement utiles, <xref:microsoft.quantum.diagnostics.assertmeasurement> et <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> les deux modèles en tant qu’opérations sur `()` .</span><span class="sxs-lookup"><span data-stu-id="f598a-161">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:microsoft.quantum.diagnostics.assertmeasurement> and <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="f598a-162">Ces assertions prennent chacune un opérateur Pauli décrivant une mesure particulière d’intérêt, un registre quantique sur lequel une mesure est effectuée et un résultat hypothétique.</span><span class="sxs-lookup"><span data-stu-id="f598a-162">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="f598a-163">Les machines cibles qui fonctionnent par simulation ne sont pas liées par le registre de [non-clonage](https://en.wikipedia.org/wiki/No-cloning_theorem), et peuvent effectuer des mesures de ce type sans perturber le Registre qui passe à ces assertions.</span><span class="sxs-lookup"><span data-stu-id="f598a-163">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="f598a-164">Un simulateur peut ensuite, à l’instar de la `PositivityFact` fonction précédente, arrêter le calcul si le résultat hypothétique n’est pas observé dans la pratique :</span><span class="sxs-lookup"><span data-stu-id="f598a-164">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="f598a-165">Sur le matériel Quantum physique, où le niveau de stockage de non-clonage empêche l’examen d’un État Quantum, les `AssertMeasurement` `AssertMeasurementProbability` opérations et ne retournent simplement `()` aucun autre effet.</span><span class="sxs-lookup"><span data-stu-id="f598a-165">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="f598a-166">L' <xref:microsoft.quantum.diagnostics> espace de noms fournit plusieurs autres fonctions de la `Assert` famille, avec lesquelles vous pouvez vérifier des conditions plus avancées.</span><span class="sxs-lookup"><span data-stu-id="f598a-166">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="f598a-167">Fonctions dump</span><span class="sxs-lookup"><span data-stu-id="f598a-167">Dump Functions</span></span>

<span data-ttu-id="f598a-168">Pour aider à résoudre les problèmes liés aux programmes Quantum, l' <xref:microsoft.quantum.diagnostics> espace de noms offre deux fonctions qui peuvent faire un dump dans un fichier de l’état actuel de l’ordinateur cible : <xref:microsoft.quantum.diagnostics.dumpmachine> et <xref:microsoft.quantum.diagnostics.dumpregister> .</span><span class="sxs-lookup"><span data-stu-id="f598a-168">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="f598a-169">La sortie générée de chaque dépend de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="f598a-169">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="f598a-170">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="f598a-170">DumpMachine</span></span>

<span data-ttu-id="f598a-171">Le simulateur quantum complet distribué dans le cadre du kit de développement quantique écrit dans le fichier la [fonction Wave](https://en.wikipedia.org/wiki/Wave_function) de l’ensemble du système Quantum, sous la forme d’un tableau unidimensionnel de nombres complexes, dans lequel chaque élément représente l’amplitude de la probabilité de mesure de l’état de la base de calcul $ \ket{n} $, où $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ pour bits $ \{ b_i \} $.</span><span class="sxs-lookup"><span data-stu-id="f598a-171">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="f598a-172">Par exemple, sur un ordinateur avec seulement deux qubits alloués et dans l’État Quantum $ $ \begin{align} \ket{\Psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ Calling <xref:microsoft.quantum.diagnostics.dumpmachine> génère cette sortie :</span><span class="sxs-lookup"><span data-stu-id="f598a-172">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="f598a-173">La première ligne fournit un commentaire avec les ID des qubits correspondants dans leur ordre significatif.</span><span class="sxs-lookup"><span data-stu-id="f598a-173">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="f598a-174">Les autres lignes décrivent l’amplitude de probabilité de la mesure du vecteur d’état de base $ \ket{n} $ à la fois dans les formats cartésien et polaire.</span><span class="sxs-lookup"><span data-stu-id="f598a-174">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="f598a-175">En détail pour la première ligne :</span><span class="sxs-lookup"><span data-stu-id="f598a-175">In detail for the first row:</span></span>

* <span data-ttu-id="f598a-176">**`∣0❭:`** Cette ligne correspond à l' `0` État de la base de calcul</span><span class="sxs-lookup"><span data-stu-id="f598a-176">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="f598a-177">**`0.707107 +  0.000000 i`**: amplitude de probabilité au format cartésien.</span><span class="sxs-lookup"><span data-stu-id="f598a-177">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="f598a-178">**` == `**: le `equal` signe sépare les deux représentations équivalentes.</span><span class="sxs-lookup"><span data-stu-id="f598a-178">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="f598a-179">**`**********  `**: Représentation graphique de l’amplitude, le nombre de `*` est proportionnel à la probabilité de mesurer ce vecteur d’État.</span><span class="sxs-lookup"><span data-stu-id="f598a-179">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="f598a-180">**`[ 0.500000 ]`**: valeur numérique de l’amplitude</span><span class="sxs-lookup"><span data-stu-id="f598a-180">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="f598a-181">**`    ---`**: Représentation graphique de la phase de l’amplitude (voir la sortie suivante).</span><span class="sxs-lookup"><span data-stu-id="f598a-181">**`    ---`**: A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="f598a-182">**`[ 0.0000 rad ]`**: valeur numérique de la phase (en radians).</span><span class="sxs-lookup"><span data-stu-id="f598a-182">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="f598a-183">L’amplitude et la phase sont toutes les deux affichées avec une représentation graphique.</span><span class="sxs-lookup"><span data-stu-id="f598a-183">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="f598a-184">La représentation magnitude est simple : elle affiche une barre de, plus la probabilité de la barre est importante `*` .</span><span class="sxs-lookup"><span data-stu-id="f598a-184">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="f598a-185">Pour la phase, nous affichons les symboles suivants pour représenter l’angle en fonction des plages :</span><span class="sxs-lookup"><span data-stu-id="f598a-185">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="f598a-186">Les exemples suivants illustrent `DumpMachine` certains États courants :</span><span class="sxs-lookup"><span data-stu-id="f598a-186">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="f598a-187">L’ID d’un qubit est assigné au moment de l’exécution et n’est pas nécessairement aligné avec l’ordre dans lequel le qubit a été alloué ou sa position dans un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="f598a-187">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="f598a-188">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f598a-188">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="f598a-189">Vous pouvez localiser un ID qubit dans Visual Studio en plaçant un point d’arrêt dans votre code et en inspectant la valeur d’une variable qubit, par exemple :</span><span class="sxs-lookup"><span data-stu-id="f598a-189">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![afficher l’ID qubit dans Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="f598a-191">le qubit avec l’index `0` sur `register2` a l’ID = `3` , le qubit avec l’index `1` a l’ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="f598a-191">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="f598a-192">Code de ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f598a-192">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="f598a-193">Vous pouvez localiser un ID qubit à l’aide de la <xref:microsoft.quantum.intrinsic.message> fonction et en passant la variable qubit dans le message, par exemple :</span><span class="sxs-lookup"><span data-stu-id="f598a-193">You can locate a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="f598a-194">qui peut générer cette sortie :</span><span class="sxs-lookup"><span data-stu-id="f598a-194">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="f598a-195">ce qui signifie que le qubit avec l’index `0` sur `register2` a `3` l’ID =, le qubit avec l’index `1` a l’ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="f598a-195">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="f598a-196">Étant donné que <xref:microsoft.quantum.diagnostics.dumpmachine> fait partie de l'  <xref:microsoft.quantum.diagnostics> espace de noms, vous devez ajouter une `open` instruction pour y accéder :</span><span class="sxs-lookup"><span data-stu-id="f598a-196">Since <xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, you must add an `open` statement to access it:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="f598a-197">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="f598a-197">DumpRegister</span></span>

<span data-ttu-id="f598a-198"><xref:microsoft.quantum.diagnostics.dumpregister> fonctionne comme <xref:microsoft.quantum.diagnostics.dumpmachine> , mais il prend également un tableau de qubits pour limiter la quantité d’informations à ce qui concerne uniquement les qubits correspondants.</span><span class="sxs-lookup"><span data-stu-id="f598a-198"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="f598a-199">Comme avec <xref:microsoft.quantum.diagnostics.dumpmachine> , les informations générées par <xref:microsoft.quantum.diagnostics.dumpregister> dépendent de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="f598a-199">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="f598a-200">Pour le simulateur Quantum à état complet, il écrit dans le fichier la fonction Wave jusqu’à une phase globale du sous-système Quantum généré par le qubits fourni dans le même format que <xref:microsoft.quantum.diagnostics.dumpmachine> .</span><span class="sxs-lookup"><span data-stu-id="f598a-200">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="f598a-201">Par exemple, reprenez un ordinateur avec seulement deux qubits alloués et dans l’État Quantum $ $ \begin{align} \ket{\Psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ pi/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ). l’appel de \end{align} $ $ <xref:microsoft.quantum.diagnostics.dumpregister> pour `qubit[0]` génère la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="f598a-201">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="f598a-202">et <xref:microsoft.quantum.diagnostics.dumpregister> l’appel de pour `qubit[1]` génère cette sortie :</span><span class="sxs-lookup"><span data-stu-id="f598a-202">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="f598a-203">En général, l’état d’un registre qui est enchevêtré avec un autre registre est un État mixte plutôt qu’un état pur.</span><span class="sxs-lookup"><span data-stu-id="f598a-203">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="f598a-204">Dans ce cas, <xref:microsoft.quantum.diagnostics.dumpregister> génère le message suivant :</span><span class="sxs-lookup"><span data-stu-id="f598a-204">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="f598a-205">L’exemple suivant montre comment vous pouvez utiliser <xref:microsoft.quantum.diagnostics.dumpregister> et <xref:microsoft.quantum.diagnostics.dumpmachine> dans votre Q# Code :</span><span class="sxs-lookup"><span data-stu-id="f598a-205">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="f598a-206">Débogage</span><span class="sxs-lookup"><span data-stu-id="f598a-206">Debugging</span></span>

<span data-ttu-id="f598a-207">En plus de `Assert` et des `Dump` fonctions et opérations Q# , prend en charge un sous-ensemble de fonctionnalités de débogage Visual Studio standard : la [définition de points d’arrêt de ligne](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), le parcours du [code à l’aide de F10 et l'](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) [inspection des valeurs des variables classiques](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) sont toutes possibles lors de l’exécution de votre code sur le simulateur.</span><span class="sxs-lookup"><span data-stu-id="f598a-207">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible when running your code on the simulator.</span></span>

<span data-ttu-id="f598a-208">Le débogage dans Visual Studio Code s’appuie sur les fonctionnalités de débogage fournies par l’extension C# pour Visual Studio Code équipée de OmniSharp et nécessite l’installation de la [version la plus récente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="f598a-208">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
