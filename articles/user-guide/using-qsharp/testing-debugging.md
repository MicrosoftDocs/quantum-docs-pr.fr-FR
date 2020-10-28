---
title: Test et débogage
description: Découvrez comment utiliser des tests unitaires, des faits et des assertions, et des fonctions dump pour tester et déboguer des programmes quantiques.
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 5505086c5efac89f6940cde1ecae2ce629cfeda5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690966"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="34d9c-103">Test et débogage</span><span class="sxs-lookup"><span data-stu-id="34d9c-103">Testing and debugging</span></span>

<span data-ttu-id="34d9c-104">Comme pour la programmation classique, il est essentiel de pouvoir vérifier que les programmes de Quantum fonctionnent comme prévu et de pouvoir diagnostiquer un comportement incorrect.</span><span class="sxs-lookup"><span data-stu-id="34d9c-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="34d9c-105">Dans cette section, nous allons aborder les outils proposés par :::no-loc(Q#)::: pour le test et le débogage de programmes quantiques.</span><span class="sxs-lookup"><span data-stu-id="34d9c-105">In this section, we cover the tools offered by :::no-loc(Q#)::: for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="34d9c-106">Tests unitaires</span><span class="sxs-lookup"><span data-stu-id="34d9c-106">Unit Tests</span></span>

<span data-ttu-id="34d9c-107">Une approche courante du test des programmes classiques consiste à écrire de petits programmes appelés *tests unitaires* , qui exécutent le code dans une bibliothèque et à comparer la sortie à une sortie attendue.</span><span class="sxs-lookup"><span data-stu-id="34d9c-107">One common approach to testing classical programs is to write small programs called *unit tests* , which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="34d9c-108">Par exemple, vous pouvez vous assurer que `Square(2)` retourne, `4` car vous connaissez *un priori* de $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="34d9c-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="34d9c-109">:::no-loc(Q#)::: prend en charge la création de tests unitaires pour les programmes Quantum et peut s’exécuter en tant que tests dans l’infrastructure de tests unitaires [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="34d9c-109">:::no-loc(Q#)::: supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="34d9c-110">Création d’un projet de test</span><span class="sxs-lookup"><span data-stu-id="34d9c-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="34d9c-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="34d9c-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="34d9c-112">Ouvrez Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="34d9c-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="34d9c-113">Accédez au menu **fichier** et sélectionnez **nouveau > projet...** . Dans l’angle supérieur droit, recherchez `:::no-loc(Q#):::` et sélectionnez le modèle **:::no-loc(Q#)::: projet de test** .</span><span class="sxs-lookup"><span data-stu-id="34d9c-113">Go to the **File** menu and select **New > Project...** . In the upper right corner, search for `:::no-loc(Q#):::`, and select the **:::no-loc(Q#)::: Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="34d9c-114">Code de ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="34d9c-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="34d9c-115">À partir de votre ligne de commande favorite, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="34d9c-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang :::no-loc(Q#)::: -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="34d9c-116">Votre nouveau projet contient un seul fichier `Tests.qs` , qui fournit un emplacement pratique pour définir de nouveaux :::no-loc(Q#)::: tests unitaires.</span><span class="sxs-lookup"><span data-stu-id="34d9c-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new :::no-loc(Q#)::: unit tests.</span></span>
<span data-ttu-id="34d9c-117">Initialement, ce fichier contient un exemple de test unitaire `AllocateQubit` qui vérifie qu’un qubit nouvellement alloué est dans l’État $ \ket {0} $ et imprime un message :</span><span class="sxs-lookup"><span data-stu-id="34d9c-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="34d9c-118">Toute :::no-loc(Q#)::: opération ou fonction qui accepte un argument de type `Unit` et retourne `Unit` peut être marquée comme un test unitaire via l' `@Test("...")` attribut.</span><span class="sxs-lookup"><span data-stu-id="34d9c-118">Any :::no-loc(Q#)::: operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="34d9c-119">Dans l’exemple précédent, l’argument de cet attribut, `"QuantumSimulator"` , spécifie la cible sur laquelle le test s’exécute.</span><span class="sxs-lookup"><span data-stu-id="34d9c-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="34d9c-120">Un test unique peut s’exécuter sur plusieurs cibles.</span><span class="sxs-lookup"><span data-stu-id="34d9c-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="34d9c-121">Par exemple, ajoutez un attribut `@Test("ResourcesEstimator")` avant `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="34d9c-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="34d9c-122">Enregistrez le fichier et exécutez tous les tests.</span><span class="sxs-lookup"><span data-stu-id="34d9c-122">Save the file and run all tests.</span></span> <span data-ttu-id="34d9c-123">Il doit maintenant y avoir deux tests unitaires, un où `AllocateQubit` s’exécute sur le `QuantumSimulator` , et un autre où il s’exécute dans le `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="34d9c-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="34d9c-124">Le :::no-loc(Q#)::: compilateur reconnaît les cibles intégrées `"QuantumSimulator"` , `"ToffoliSimulator"` et `"ResourcesEstimator"` en tant que cibles d’exécution valides pour les tests unitaires.</span><span class="sxs-lookup"><span data-stu-id="34d9c-124">The :::no-loc(Q#)::: compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid run targets for unit tests.</span></span> <span data-ttu-id="34d9c-125">Il est également possible de spécifier un nom qualifié complet pour définir une cible d’exécution personnalisée.</span><span class="sxs-lookup"><span data-stu-id="34d9c-125">It is also possible to specify any fully qualified name to define a custom run target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="34d9c-126">Exécution de :::no-loc(Q#)::: tests unitaires</span><span class="sxs-lookup"><span data-stu-id="34d9c-126">Running :::no-loc(Q#)::: Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="34d9c-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="34d9c-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="34d9c-128">Dans le cadre d’une configuration par solution unique, accédez au menu **test** et sélectionnez **paramètres de test > architecture de processeur par défaut > x64** .</span><span class="sxs-lookup"><span data-stu-id="34d9c-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64** .</span></span>

> [!TIP]
> <span data-ttu-id="34d9c-129">Le paramètre d’architecture de processeur par défaut pour Visual Studio est stocké dans le fichier options de solution ( `.suo` ) de chaque solution.</span><span class="sxs-lookup"><span data-stu-id="34d9c-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="34d9c-130">Si vous supprimez ce fichier, vous devez à nouveau sélectionner **x64** comme architecture de processeur.</span><span class="sxs-lookup"><span data-stu-id="34d9c-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="34d9c-131">Générez le projet, ouvrez le menu **test** , puis sélectionnez **Windows >** de l’Explorateur de tests.</span><span class="sxs-lookup"><span data-stu-id="34d9c-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer** .</span></span> <span data-ttu-id="34d9c-132">**AllocateQubit** s’affiche dans la liste des tests dans le groupe **tests non exécutés** .</span><span class="sxs-lookup"><span data-stu-id="34d9c-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="34d9c-133">Sélectionnez **exécuter tout** ou exécuter ce test individuel.</span><span class="sxs-lookup"><span data-stu-id="34d9c-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="34d9c-134">Code de ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="34d9c-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="34d9c-135">Pour exécuter les tests, accédez au dossier du projet (le dossier qui contient `Tests.csproj` ), puis exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="34d9c-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="34d9c-136">La sortie doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="34d9c-136">You should get output similar to the following:</span></span>

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

<span data-ttu-id="34d9c-137">Les tests unitaires peuvent être filtrés en fonction de leur nom ou de la cible d’exécution :</span><span class="sxs-lookup"><span data-stu-id="34d9c-137">Unit tests can be filtered according to their name or the run target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


<span data-ttu-id="34d9c-138">\*\*_</span><span class="sxs-lookup"><span data-stu-id="34d9c-138">\*\*_</span></span>

<span data-ttu-id="34d9c-139">La fonction intrinsèque <xref:Microsoft.Quantum.Intrinsic.Message> a le type `(String -> Unit)` et permet la création de messages de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="34d9c-139">The intrinsic function <xref:Microsoft.Quantum.Intrinsic.Message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="34d9c-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="34d9c-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="34d9c-141">Après avoir exécuté un test dans l’Explorateur de tests et cliqué sur le test, un panneau s’affiche avec des informations sur la série de tests : état réussite/échec, temps écoulé et un lien vers la sortie.</span><span class="sxs-lookup"><span data-stu-id="34d9c-141">After you run a test in Test Explorer and click on the test, a panel displays with information about test run: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="34d9c-142">Cliquez sur _ *Output* \* pour ouvrir la sortie de test dans une nouvelle fenêtre.</span><span class="sxs-lookup"><span data-stu-id="34d9c-142">Click _ *Output* \* to open the test output in a new window.</span></span>

![sortie de test](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="34d9c-144">Code de ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="34d9c-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="34d9c-145">L’État réussite/échec de chaque test est imprimé sur la console par `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="34d9c-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="34d9c-146">Pour les tests ayant échoué, les sorties sont également imprimées sur la console pour faciliter le diagnostic de l’échec.</span><span class="sxs-lookup"><span data-stu-id="34d9c-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

<span data-ttu-id="34d9c-147">\*\*_</span><span class="sxs-lookup"><span data-stu-id="34d9c-147">\*\*_</span></span>

## <a name="facts-and-assertions"></a><span data-ttu-id="34d9c-148">Faits et assertions</span><span class="sxs-lookup"><span data-stu-id="34d9c-148">Facts and Assertions</span></span>

<span data-ttu-id="34d9c-149">Étant donné que les fonctions de n' :::no-loc(Q#)::: ont pas d’effets secondaires _logiques_ , vous ne pouvez jamais observer, à partir d’un :::no-loc(Q#)::: programme, tous les autres genres d’effets de l’exécution d’une fonction dont le type de sortie est le tuple vide `()` .</span><span class="sxs-lookup"><span data-stu-id="34d9c-149">Because functions in :::no-loc(Q#)::: have no _logical_ side effects, you can never observe, from within a :::no-loc(Q#)::: program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="34d9c-150">Autrement dit, un ordinateur cible peut choisir de ne pas exécuter une fonction qui retourne `()` avec la garantie que cette omission ne modifiera pas le comportement d’un :::no-loc(Q#)::: code suivant.</span><span class="sxs-lookup"><span data-stu-id="34d9c-150">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following :::no-loc(Q#)::: code.</span></span>
<span data-ttu-id="34d9c-151">Ce comportement rend les fonctions qui retournent `()` (comme `Unit` ) un outil utile pour incorporer des assertions et la logique de débogage dans des :::no-loc(Q#)::: programmes.</span><span class="sxs-lookup"><span data-stu-id="34d9c-151">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into :::no-loc(Q#)::: programs.</span></span> 

<span data-ttu-id="34d9c-152">Prenons un exemple simple :</span><span class="sxs-lookup"><span data-stu-id="34d9c-152">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="34d9c-153">Ici, le mot clé `fail` indique que le calcul ne doit pas continuer et lève une exception sur l’ordinateur cible qui exécute le :::no-loc(Q#)::: programme.</span><span class="sxs-lookup"><span data-stu-id="34d9c-153">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the :::no-loc(Q#)::: program.</span></span>
<span data-ttu-id="34d9c-154">Par définition, une défaillance de ce type ne peut pas être observée dans :::no-loc(Q#)::: , car l’ordinateur cible n’exécute plus le :::no-loc(Q#)::: code après avoir atteint une `fail` instruction.</span><span class="sxs-lookup"><span data-stu-id="34d9c-154">By definition, a failure of this kind cannot be observed from within :::no-loc(Q#):::, as the target machine no longer runs the :::no-loc(Q#)::: code after reaching a `fail` statement.</span></span>
<span data-ttu-id="34d9c-155">Par conséquent, si nous poursuivons un appel à `PositivityFact` , nous pouvons être assurés que son entrée était positive.</span><span class="sxs-lookup"><span data-stu-id="34d9c-155">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="34d9c-156">Notez que nous pouvons implémenter le même comportement que l' `PositivityFact` utilisation [`Fact`](xref:Microsoft.Quantum.Diagnostics.fact) de la fonction à partir de l' <xref:Microsoft.Quantum.Diagnostics> espace de noms :</span><span class="sxs-lookup"><span data-stu-id="34d9c-156">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:Microsoft.Quantum.Diagnostics.fact) function from the <xref:Microsoft.Quantum.Diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="34d9c-157">_Assertions \*, en revanche, sont utilisés de la même façon que les faits, mais peuvent dépendre de l’état de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="34d9c-157">_Assertions\*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="34d9c-158">En conséquence, ils sont définis en tant qu’opérations, tandis que les faits sont définis en tant que fonctions (comme dans l’exemple précédent).</span><span class="sxs-lookup"><span data-stu-id="34d9c-158">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="34d9c-159">Pour comprendre la distinction, considérez l’utilisation suivante d’un fait au sein d’une assertion :</span><span class="sxs-lookup"><span data-stu-id="34d9c-159">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="34d9c-160">Ici, nous utilisons l’opération <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> pour retourner le nombre de qubits disponibles à utiliser.</span><span class="sxs-lookup"><span data-stu-id="34d9c-160">Here, we are using the operation <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="34d9c-161">Comme cela dépend de l’état global du programme et de son environnement d’exécution, notre définition de `AssertQubitsAreAvailable` doit également être une opération.</span><span class="sxs-lookup"><span data-stu-id="34d9c-161">As this depends on the global state of the program and its run environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="34d9c-162">Toutefois, nous pouvons utiliser cet état global pour donner une `Bool` valeur simple comme entrée à la `Fact` fonction.</span><span class="sxs-lookup"><span data-stu-id="34d9c-162">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="34d9c-163">[Préambule destiné à](xref:microsoft.quantum.libraries.standard.prelude), en s’appuyant sur ces idées, offre deux assertions particulièrement utiles, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> et <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> les deux modèles en tant qu’opérations sur `()` .</span><span class="sxs-lookup"><span data-stu-id="34d9c-163">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> and <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="34d9c-164">Ces assertions prennent chacune un opérateur Pauli décrivant une mesure particulière d’intérêt, un registre quantique sur lequel une mesure est effectuée et un résultat hypothétique.</span><span class="sxs-lookup"><span data-stu-id="34d9c-164">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="34d9c-165">Les machines cibles qui fonctionnent par simulation ne sont pas liées par le registre de [non-clonage](https://en.wikipedia.org/wiki/No-cloning_theorem), et peuvent effectuer des mesures de ce type sans perturber le Registre qui passe à ces assertions.</span><span class="sxs-lookup"><span data-stu-id="34d9c-165">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="34d9c-166">Un simulateur peut ensuite, à l’instar de la `PositivityFact` fonction précédente, arrêter le calcul si le résultat hypothétique n’est pas observé dans la pratique :</span><span class="sxs-lookup"><span data-stu-id="34d9c-166">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in :::no-loc(Q#):::,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="34d9c-167">Sur le matériel Quantum physique, où le niveau de stockage de non-clonage empêche l’examen d’un État Quantum, les `AssertMeasurement` `AssertMeasurementProbability` opérations et ne retournent simplement `()` aucun autre effet.</span><span class="sxs-lookup"><span data-stu-id="34d9c-167">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="34d9c-168">L' <xref:Microsoft.Quantum.Diagnostics> espace de noms fournit plusieurs autres fonctions de la `Assert` famille, avec lesquelles vous pouvez vérifier des conditions plus avancées.</span><span class="sxs-lookup"><span data-stu-id="34d9c-168">The <xref:Microsoft.Quantum.Diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="34d9c-169">Fonctions dump</span><span class="sxs-lookup"><span data-stu-id="34d9c-169">Dump Functions</span></span>

<span data-ttu-id="34d9c-170">Pour aider à résoudre les problèmes liés aux programmes Quantum, l' <xref:Microsoft.Quantum.Diagnostics> espace de noms offre deux fonctions qui peuvent faire un dump dans un fichier de l’état actuel de l’ordinateur cible : <xref:Microsoft.Quantum.Diagnostics.DumpMachine> et <xref:Microsoft.Quantum.Diagnostics.DumpRegister> .</span><span class="sxs-lookup"><span data-stu-id="34d9c-170">To help troubleshooting quantum programs, the <xref:Microsoft.Quantum.Diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> and <xref:Microsoft.Quantum.Diagnostics.DumpRegister>.</span></span> <span data-ttu-id="34d9c-171">La sortie générée de chaque dépend de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="34d9c-171">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="34d9c-172">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="34d9c-172">DumpMachine</span></span>

<span data-ttu-id="34d9c-173">Le simulateur quantum complet distribué dans le cadre du kit de développement quantique écrit dans le fichier la [fonction Wave](https://en.wikipedia.org/wiki/Wave_function) de l’ensemble du système Quantum, sous la forme d’un tableau unidimensionnel de nombres complexes, dans lequel chaque élément représente l’amplitude de la probabilité de mesure de l’état de la base de calcul $ \ket{n} $, où $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ pour bits $ \{ b_i \} $.</span><span class="sxs-lookup"><span data-stu-id="34d9c-173">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="34d9c-174">Par exemple, sur un ordinateur avec seulement deux qubits alloués et dans l’État Quantum $ $ \begin{align} \ket{\Psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ Calling <xref:Microsoft.Quantum.Diagnostics.DumpMachine> génère cette sortie :</span><span class="sxs-lookup"><span data-stu-id="34d9c-174">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpMachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="34d9c-175">La première ligne fournit un commentaire avec les ID des qubits correspondants dans leur ordre significatif.</span><span class="sxs-lookup"><span data-stu-id="34d9c-175">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="34d9c-176">Les autres lignes décrivent l’amplitude de probabilité de la mesure du vecteur d’état de base $ \ket{n} $ à la fois dans les formats cartésien et polaire.</span><span class="sxs-lookup"><span data-stu-id="34d9c-176">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="34d9c-177">En détail pour la première ligne :</span><span class="sxs-lookup"><span data-stu-id="34d9c-177">In detail for the first row:</span></span>

* <span data-ttu-id="34d9c-178">**`∣0❭:`** Cette ligne correspond à l' `0` État de la base de calcul</span><span class="sxs-lookup"><span data-stu-id="34d9c-178">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="34d9c-179">**`0.707107 +  0.000000 i`** : amplitude de probabilité au format cartésien.</span><span class="sxs-lookup"><span data-stu-id="34d9c-179">**`0.707107 +  0.000000 i`** : the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="34d9c-180">**` == `** : le `equal` signe sépare les deux représentations équivalentes.</span><span class="sxs-lookup"><span data-stu-id="34d9c-180">**` == `** : the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="34d9c-181">**`**********  `** : Représentation graphique de l’amplitude, le nombre de `*` est proportionnel à la probabilité de mesurer ce vecteur d’État.</span><span class="sxs-lookup"><span data-stu-id="34d9c-181">**`**********  `** : A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="34d9c-182">**`[ 0.500000 ]`** : valeur numérique de l’amplitude</span><span class="sxs-lookup"><span data-stu-id="34d9c-182">**`[ 0.500000 ]`** : the numeric value of the magnitude</span></span>
* <span data-ttu-id="34d9c-183">**`    ---`** : Représentation graphique de la phase de l’amplitude (voir la sortie suivante).</span><span class="sxs-lookup"><span data-stu-id="34d9c-183">**`    ---`** : A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="34d9c-184">**`[ 0.0000 rad ]`** : valeur numérique de la phase (en radians).</span><span class="sxs-lookup"><span data-stu-id="34d9c-184">**`[ 0.0000 rad ]`** : the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="34d9c-185">L’amplitude et la phase sont toutes les deux affichées avec une représentation graphique.</span><span class="sxs-lookup"><span data-stu-id="34d9c-185">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="34d9c-186">La représentation magnitude est simple : elle affiche une barre de, plus la probabilité de la barre est importante `*` .</span><span class="sxs-lookup"><span data-stu-id="34d9c-186">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="34d9c-187">Pour la phase, nous affichons les symboles suivants pour représenter l’angle en fonction des plages :</span><span class="sxs-lookup"><span data-stu-id="34d9c-187">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="34d9c-188">Les exemples suivants illustrent `DumpMachine` certains États courants :</span><span class="sxs-lookup"><span data-stu-id="34d9c-188">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="34d9c-189">L’ID d’un qubit est assigné au moment de l’exécution et n’est pas nécessairement aligné avec l’ordre dans lequel le qubit a été alloué ou sa position dans un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="34d9c-189">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="34d9c-190">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="34d9c-190">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="34d9c-191">Vous pouvez localiser un ID qubit dans Visual Studio en plaçant un point d’arrêt dans votre code et en inspectant la valeur d’une variable qubit, par exemple :</span><span class="sxs-lookup"><span data-stu-id="34d9c-191">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![afficher l’ID qubit dans Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="34d9c-193">le qubit avec l’index `0` sur `register2` a l’ID = `3` , le qubit avec l’index `1` a l’ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="34d9c-193">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="34d9c-194">Code de ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="34d9c-194">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="34d9c-195">Vous pouvez localiser un ID qubit à l’aide de la <xref:Microsoft.Quantum.Intrinsic.Message> fonction et en passant la variable qubit dans le message, par exemple :</span><span class="sxs-lookup"><span data-stu-id="34d9c-195">You can locate a qubit id by using the <xref:Microsoft.Quantum.Intrinsic.Message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="34d9c-196">qui peut générer cette sortie :</span><span class="sxs-lookup"><span data-stu-id="34d9c-196">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="34d9c-197">ce qui signifie que le qubit avec l’index `0` sur `register2` a `3` l’ID =, le qubit avec l’index `1` a l’ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="34d9c-197">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


<span data-ttu-id="34d9c-198">\*\*_</span><span class="sxs-lookup"><span data-stu-id="34d9c-198">\*\*_</span></span>

<span data-ttu-id="34d9c-199">Étant donné que <xref:Microsoft.Quantum.Diagnostics.DumpMachine> fait partie de l'  <xref:Microsoft.Quantum.Diagnostics> espace de noms, vous devez ajouter une `open` instruction pour y accéder :</span><span class="sxs-lookup"><span data-stu-id="34d9c-199">Since <xref:Microsoft.Quantum.Diagnostics.DumpMachine> is part of the  <xref:Microsoft.Quantum.Diagnostics> namespace, you must add an `open` statement to access it:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="34d9c-200">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="34d9c-200">DumpRegister</span></span>

<span data-ttu-id="34d9c-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> fonctionne comme <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , mais il prend également un tableau de qubits pour limiter la quantité d’informations à ce qui concerne uniquement les qubits correspondants.</span><span class="sxs-lookup"><span data-stu-id="34d9c-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> works like <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="34d9c-202">Comme avec <xref:Microsoft.Quantum.Diagnostics.DumpMachine> , les informations générées par <xref:Microsoft.Quantum.Diagnostics.DumpRegister> dépendent de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="34d9c-202">As with <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, the information generated by <xref:Microsoft.Quantum.Diagnostics.DumpRegister> depends on the target machine.</span></span> <span data-ttu-id="34d9c-203">Pour le simulateur Quantum à état complet, il écrit dans le fichier la fonction Wave jusqu’à une phase globale du sous-système Quantum généré par le qubits fourni dans le même format que <xref:Microsoft.Quantum.Diagnostics.DumpMachine> .</span><span class="sxs-lookup"><span data-stu-id="34d9c-203">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:Microsoft.Quantum.Diagnostics.DumpMachine>.</span></span>  <span data-ttu-id="34d9c-204">Par exemple, reprenez un ordinateur avec seulement deux qubits alloués et dans l’État Quantum $ $ \begin{align} \ket{\Psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ pi/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ). l’appel de \end{align} $ $ <xref:Microsoft.Quantum.Diagnostics.DumpRegister> pour `qubit[0]` génère la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="34d9c-204">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     _******************* [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="34d9c-205">et <xref:Microsoft.Quantum.Diagnostics.DumpRegister> l’appel de pour `qubit[1]` génère cette sortie :</span><span class="sxs-lookup"><span data-stu-id="34d9c-205">and calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="34d9c-206">En général, l’état d’un registre qui est enchevêtré avec un autre registre est un État mixte plutôt qu’un état pur.</span><span class="sxs-lookup"><span data-stu-id="34d9c-206">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="34d9c-207">Dans ce cas, <xref:Microsoft.Quantum.Diagnostics.DumpRegister> génère le message suivant :</span><span class="sxs-lookup"><span data-stu-id="34d9c-207">In this case, <xref:Microsoft.Quantum.Diagnostics.DumpRegister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="34d9c-208">L’exemple suivant montre comment vous pouvez utiliser <xref:Microsoft.Quantum.Diagnostics.DumpRegister> et <xref:Microsoft.Quantum.Diagnostics.DumpMachine> dans votre :::no-loc(Q#)::: Code :</span><span class="sxs-lookup"><span data-stu-id="34d9c-208">The following example shows you how you can use both <xref:Microsoft.Quantum.Diagnostics.DumpRegister> and <xref:Microsoft.Quantum.Diagnostics.DumpMachine> in your :::no-loc(Q#)::: code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="34d9c-209">Débogage</span><span class="sxs-lookup"><span data-stu-id="34d9c-209">Debugging</span></span>

<span data-ttu-id="34d9c-210">En plus de `Assert` et des `Dump` fonctions et opérations :::no-loc(Q#)::: , prend en charge un sous-ensemble de fonctionnalités de débogage Visual Studio standard : la [définition de points d’arrêt de ligne](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), le parcours du [code à l’aide de F10 et l'](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) [inspection des valeurs des variables classiques](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) sont toutes possibles lors de l’exécution de votre code sur le simulateur.</span><span class="sxs-lookup"><span data-stu-id="34d9c-210">On top of `Assert` and `Dump` functions and operations, :::no-loc(Q#)::: supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible when running your code on the simulator.</span></span>

<span data-ttu-id="34d9c-211">Le débogage dans Visual Studio Code s’appuie sur les fonctionnalités de débogage fournies par l’extension C# pour Visual Studio Code équipée de OmniSharp et nécessite l’installation de la [version la plus récente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="34d9c-211">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
