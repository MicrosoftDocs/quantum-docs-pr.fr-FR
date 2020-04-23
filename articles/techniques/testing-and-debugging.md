---
title: Tester et déboguer les programmes QMD
description: Apprenez à utiliser des tests unitaires, des faits et des affirmations, et déchargez des fonctions pour tester et déboguer les programmes quantiques.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030580"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="ee60d-103">Test et débogage</span><span class="sxs-lookup"><span data-stu-id="ee60d-103">Testing and Debugging</span></span>

<span data-ttu-id="ee60d-104">Comme pour la programmation classique, il est essentiel de pouvoir vérifier que les programmes quantiques agissent comme prévu, et d’être en mesure de diagnostiquer un programme quantique qui est incorrect.</span><span class="sxs-lookup"><span data-stu-id="ee60d-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="ee60d-105">Dans cette section, nous couvrons les outils offerts par QMD pour tester et débogage des programmes quantiques.</span><span class="sxs-lookup"><span data-stu-id="ee60d-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="ee60d-106">Tests unitaires</span><span class="sxs-lookup"><span data-stu-id="ee60d-106">Unit Tests</span></span>

<span data-ttu-id="ee60d-107">Une approche courante pour tester les programmes classiques est d’écrire de petits programmes appelés *tests unitaires* qui exécutent du code dans une bibliothèque et de comparer sa production à une certaine sortie prévue.</span><span class="sxs-lookup"><span data-stu-id="ee60d-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="ee60d-108">Par exemple, nous pouvons `Square(2)` vouloir `4`nous assurer que les retours , puisque nous savons *a priori* que 2 $ - 4 $.</span><span class="sxs-lookup"><span data-stu-id="ee60d-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="ee60d-109">QMD prend en charge la création de tests unitaires pour les programmes quantiques, et qui peuvent être exécutés sous forme de tests dans le cadre de test de [l’unité xUnit.](https://xunit.github.io/)</span><span class="sxs-lookup"><span data-stu-id="ee60d-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="ee60d-110">Création d’un projet d’essai</span><span class="sxs-lookup"><span data-stu-id="ee60d-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="ee60d-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="ee60d-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="ee60d-112">Ouvrez Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="ee60d-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="ee60d-113">Aller au `File` menu `New`  >  `Project...`et sélectionner .</span><span class="sxs-lookup"><span data-stu-id="ee60d-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="ee60d-114">Dans le coin supérieur `Q#`droit, recherchez et sélectionnez le `Q# Test Project` modèle.</span><span class="sxs-lookup"><span data-stu-id="ee60d-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="ee60d-115">Code de ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ee60d-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="ee60d-116">De votre ligne de commande préférée, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ee60d-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="ee60d-117">Votre nouveau projet aura `Tests.qs`un seul fichier, qui fournit un endroit pratique pour définir les nouveaux tests unitaires Q.</span><span class="sxs-lookup"><span data-stu-id="ee60d-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="ee60d-118">Initialement, ce fichier contient `AllocateQubit` un test unitaire échantillon qui vérifie qu’un qubit nouvellement alloué est dans l’état de $ket{0}$ et imprime un message:</span><span class="sxs-lookup"><span data-stu-id="ee60d-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="ee60d-119">:nouveau : Toute opération ou fonction QMD `Unit` qui `Unit` prend un argument de `@Test("...")` type et de retours peut être marquée comme un test unitaire via l’attribut.</span><span class="sxs-lookup"><span data-stu-id="ee60d-119">:new: Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="ee60d-120">L’argument à `"QuantumSimulator"` cet attribut, ci-dessus, spécifie la cible sur laquelle le test est exécuté.</span><span class="sxs-lookup"><span data-stu-id="ee60d-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="ee60d-121">Un seul test peut être exécuté sur plusieurs cibles.</span><span class="sxs-lookup"><span data-stu-id="ee60d-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="ee60d-122">Par exemple, ajoutez `@Test("ResourcesEstimator")` `AllocateQubit`un attribut ci-dessus .</span><span class="sxs-lookup"><span data-stu-id="ee60d-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="ee60d-123">Enregistrer le fichier et exécuter tous les tests.</span><span class="sxs-lookup"><span data-stu-id="ee60d-123">Save the file and execute all tests.</span></span> <span data-ttu-id="ee60d-124">Il devrait maintenant y avoir deux tests unitaires, l’un où AllocateQubit est exécuté sur le QuantumSimulator, et l’autre où il est exécuté dans le ResourceEstimator.</span><span class="sxs-lookup"><span data-stu-id="ee60d-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="ee60d-125">Le compilateur Qmd reconnaît les cibles intégrées « QuantumSimulator », « ToffoliSimulator » et « ResourcesEstimator » comme cibles d’exécution valides pour les tests unitaires.</span><span class="sxs-lookup"><span data-stu-id="ee60d-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="ee60d-126">Il est également possible de spécifier un nom entièrement qualifié pour définir une cible d’exécution personnalisée.</span><span class="sxs-lookup"><span data-stu-id="ee60d-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="ee60d-127">Exécution des tests d’unité Q</span><span class="sxs-lookup"><span data-stu-id="ee60d-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="ee60d-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="ee60d-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="ee60d-129">En tant que configuration par solution `Test` unique, `Test Settings`  >  `Default Processor Architecture`  > allez au menu et sélectionnez. `X64`</span><span class="sxs-lookup"><span data-stu-id="ee60d-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="ee60d-130">Le paramètre d’architecture de processeur par`.suo`défaut pour Visual Studio est stocké dans le fichier options de solution () pour chaque solution.</span><span class="sxs-lookup"><span data-stu-id="ee60d-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="ee60d-131">Si vous supprimez ce fichier, `X64` alors vous devrez sélectionner comme architecture de processeur à nouveau.</span><span class="sxs-lookup"><span data-stu-id="ee60d-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="ee60d-132">Construire le projet, `Test` aller au `Windows`  >  `Test Explorer`menu et sélectionner .</span><span class="sxs-lookup"><span data-stu-id="ee60d-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="ee60d-133">`AllocateQubit`s’affichera dans la liste `Not Run Tests` des tests dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="ee60d-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="ee60d-134">Sélectionnez `Run All` ou exécutez ce test individuel, et il devrait passer!</span><span class="sxs-lookup"><span data-stu-id="ee60d-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="ee60d-135">Code de ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ee60d-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="ee60d-136">Pour exécuter des tests, naviguez vers le `Tests.csproj`dossier du projet (le dossier qui contient), et exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="ee60d-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="ee60d-137">La sortie doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="ee60d-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="ee60d-138">Les tests unitaires peuvent être filtrés en fonction de leur nom et/ou de la cible d’exécution :</span><span class="sxs-lookup"><span data-stu-id="ee60d-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="ee60d-139">La fonction <xref:microsoft.quantum.intrinsic.message> intrinsèque `(String -> Unit)` a le type et permet la création de messages diagnostiques.</span><span class="sxs-lookup"><span data-stu-id="ee60d-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="ee60d-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="ee60d-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="ee60d-141">Après avoir exécuté un test dans Test Explorer et cliquer sur le test, un panneau apparaîtra avec des informations sur l’exécution du test: Statut passé/échec, temps écoulé et un lien "Sortie".</span><span class="sxs-lookup"><span data-stu-id="ee60d-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="ee60d-142">Si vous cliquez sur le lien "Output", la sortie du test s’ouvrira dans une nouvelle fenêtre.</span><span class="sxs-lookup"><span data-stu-id="ee60d-142">If you click the "Output" link, test output will open in a new window.</span></span>

![sortie de test](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="ee60d-144">Code de ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ee60d-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="ee60d-145">Le statut de passage/échec pour chaque test `dotnet test`est imprimé sur la console par .</span><span class="sxs-lookup"><span data-stu-id="ee60d-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="ee60d-146">Pour les tests défaillants, les sorties sont également imprimées sur la console pour aider à diagnostiquer l’échec.</span><span class="sxs-lookup"><span data-stu-id="ee60d-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="ee60d-147">Faits et affirmations</span><span class="sxs-lookup"><span data-stu-id="ee60d-147">Facts and Assertions</span></span>

<span data-ttu-id="ee60d-148">Étant donné que les fonctions dans Q N’ont pas d’effets secondaires _logiques,_ tout _autre type_ d’effets de l’exécution d’une fonction dont le type de sortie est le tuple `()` vide ne peut jamais être observé à partir d’un programme Q.</span><span class="sxs-lookup"><span data-stu-id="ee60d-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="ee60d-149">Autrement dit, une machine cible peut choisir `()` de ne pas exécuter toute fonction qui revient avec la garantie que cette omission ne modifiera pas le comportement de tout code Q ' suivant.</span><span class="sxs-lookup"><span data-stu-id="ee60d-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="ee60d-150">Cela rend le `()` retour des `Unit`fonctions (c.-à-d. ) un outil utile pour intégrer les affirmations et déboguer la logique dans les programmes Q.</span><span class="sxs-lookup"><span data-stu-id="ee60d-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="ee60d-151">Prenons un exemple simple :</span><span class="sxs-lookup"><span data-stu-id="ee60d-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="ee60d-152">Ici, le `fail` mot clé indique que le calcul ne doit pas se poursuivre, ce qui soulève une exception dans la machine cible exécutant le programme Q.</span><span class="sxs-lookup"><span data-stu-id="ee60d-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="ee60d-153">Par définition, un échec de ce type ne peut pas être observé à `fail` partir de Q, car aucun autre code Q est exécuté après qu’une déclaration est atteinte.</span><span class="sxs-lookup"><span data-stu-id="ee60d-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="ee60d-154">Ainsi, si nous passons au-delà d’un appel à `PositivityFact`, nous pouvons être assurés par que son apport était positif.</span><span class="sxs-lookup"><span data-stu-id="ee60d-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="ee60d-155">Notez que nous pouvons `PositivityFact` implémenter le même comportement que l’utilisation de la [`Fact`](xref:microsoft.quantum.diagnostics.fact) fonction de l’espace <xref:microsoft.quantum.diagnostics> nom:</span><span class="sxs-lookup"><span data-stu-id="ee60d-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="ee60d-156">*Les affirmations,* d’autre part, sont utilisées de la même façon que les faits, mais peuvent dépendre de l’état de la machine cible.</span><span class="sxs-lookup"><span data-stu-id="ee60d-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="ee60d-157">En conséquence, ils sont définis comme des opérations, tandis que les faits sont définis comme des fonctions (comme ci-dessus).</span><span class="sxs-lookup"><span data-stu-id="ee60d-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="ee60d-158">Pour comprendre la distinction, considérez l’utilisation suivante d’un fait dans une affirmation :</span><span class="sxs-lookup"><span data-stu-id="ee60d-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="ee60d-159">Ici, nous utilisons <xref:microsoft.quantum.environment.getqubitsavailabletouse> l’opération pour retourner le nombre de qubits disponibles à l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="ee60d-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="ee60d-160">Comme cela dépend clairement de l’état global du programme `AssertQubitsAreAvailable` et de son environnement d’exécution, notre définition de doit être une opération ainsi.</span><span class="sxs-lookup"><span data-stu-id="ee60d-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="ee60d-161">Cependant, nous pouvons utiliser cet état `Bool` mondial pour `Fact` donner une valeur simple comme entrée à la fonction.</span><span class="sxs-lookup"><span data-stu-id="ee60d-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="ee60d-162">S’appuyant sur ces idées, [le prélude](xref:microsoft.quantum.libraries.standard.prelude) <xref:microsoft.quantum.intrinsic.assertprob> offre deux affirmations `()`particulièrement utiles, <xref:microsoft.quantum.intrinsic.assert> et les deux modélisé comme des opérations sur .</span><span class="sxs-lookup"><span data-stu-id="ee60d-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="ee60d-163">Ces affirmations prennent chacune un opérateur Pauli décrivant une mesure particulière de l’intérêt, un registre quantique sur lequel une mesure doit être effectuée, et un résultat hypothétique.</span><span class="sxs-lookup"><span data-stu-id="ee60d-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="ee60d-164">Sur les machines cibles qui fonctionnent par simulation, nous ne sommes pas liés par [le théorème de non-clonage](https://en.wikipedia.org/wiki/No-cloning_theorem), et peut effectuer de telles mesures sans perturber le registre passé à de telles affirmations.</span><span class="sxs-lookup"><span data-stu-id="ee60d-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="ee60d-165">Un simulateur peut alors, `PositivityFact` semblable à la fonction ci-dessus, interrompre le calcul si le résultat hypothétique ne serait pas observé dans la pratique :</span><span class="sxs-lookup"><span data-stu-id="ee60d-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="ee60d-166">Sur le matériel quantique physique, où le théorème sans `Assert` clonage empêche l’examen de l’état quantique, les opérations et `AssertProb` les opérations reviennent `()` tout simplement sans autre effet.</span><span class="sxs-lookup"><span data-stu-id="ee60d-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="ee60d-167">L’espace <xref:microsoft.quantum.diagnostics> de nom fournit `Assert` plusieurs autres fonctions de la famille qui nous permettent de vérifier les conditions plus avancées.</span><span class="sxs-lookup"><span data-stu-id="ee60d-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="ee60d-168">Fonctions de décharge</span><span class="sxs-lookup"><span data-stu-id="ee60d-168">Dump Functions</span></span>

<span data-ttu-id="ee60d-169">Pour aider à dépanner <xref:microsoft.quantum.diagnostics> les programmes quantiques, l’espace nom offre deux fonctions qui peuvent jeter dans un fichier l’état actuel de la machine cible: <xref:microsoft.quantum.diagnostics.dumpmachine> et <xref:microsoft.quantum.diagnostics.dumpregister>.</span><span class="sxs-lookup"><span data-stu-id="ee60d-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="ee60d-170">La sortie générée de chacun dépend de la machine cible.</span><span class="sxs-lookup"><span data-stu-id="ee60d-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="ee60d-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="ee60d-171">DumpMachine</span></span>

<span data-ttu-id="ee60d-172">Le simulateur quantique à plein état distribué dans le cadre de la trousse de développement quantique écrit dans le fichier la [fonction d’onde](https://en.wikipedia.org/wiki/Wave_function) de l’ensemble du système quantique, comme une gamme unidimensionnelle de nombres complexes, dans lequel chaque élément représente l’amplitude de la probabilité de mesurer l’état de base de calcul $ket 'n$, où $ket 'n ' ' 'b_ 'n-1 '... b_1b_0$ pour les morceaux\{b_i\}$.</span><span class="sxs-lookup"><span data-stu-id="ee60d-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="ee60d-173">Par exemple, sur une machine avec seulement deux qubits alloués et dans l’état quantique $ ${1}$ ${2}'begin 'align' ''ket 'psi ' 'frac 'sqrt ' 'ket{00} ' 'frac '(1 'i)'{2} 'ket{10}, 'end 'align' $$ appelant <xref:microsoft.quantum.diagnostics.dumpmachine> génère cette sortie:</span><span class="sxs-lookup"><span data-stu-id="ee60d-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="ee60d-174">La première rangée fournit un commentaire avec les cartes d’ID des qubits correspondants dans leur ordre significatif.</span><span class="sxs-lookup"><span data-stu-id="ee60d-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="ee60d-175">Le reste des lignes décrit l’amplitude de probabilité de mesurer le vecteur de l’état de base $ 'n'$ dans les formats cartésiens et polaires.</span><span class="sxs-lookup"><span data-stu-id="ee60d-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="ee60d-176">Dans le détail pour la première rangée:</span><span class="sxs-lookup"><span data-stu-id="ee60d-176">In detail for the first row:</span></span>

* <span data-ttu-id="ee60d-177">**`∣0❭:`** cette ligne correspond `0` à l’état de base de calcul</span><span class="sxs-lookup"><span data-stu-id="ee60d-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="ee60d-178">**`0.707107 +  0.000000 i`**: l’amplitude de probabilité en format cartésien.</span><span class="sxs-lookup"><span data-stu-id="ee60d-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="ee60d-179">**` == `**: `equal` le signe sépécie les deux représentations équivalentes.</span><span class="sxs-lookup"><span data-stu-id="ee60d-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="ee60d-180">**`**********  `**: Représentation graphique de l’ampleur, `*` le nombre de est proportionnel à la probabilité de mesurer ce vecteur d’état.</span><span class="sxs-lookup"><span data-stu-id="ee60d-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="ee60d-181">**`[ 0.500000 ]`**: la valeur numérique de l’ampleur</span><span class="sxs-lookup"><span data-stu-id="ee60d-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="ee60d-182">**`    ---`**: Représentation graphique de la phase de l’amplitude (voir ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="ee60d-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="ee60d-183">**`[ 0.0000 rad ]`**: la valeur numérique de la phase (en radians).</span><span class="sxs-lookup"><span data-stu-id="ee60d-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="ee60d-184">L’ampleur et la phase sont affichées avec une représentation graphique.</span><span class="sxs-lookup"><span data-stu-id="ee60d-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="ee60d-185">La représentation de magnitude est simple: `*`il montre une barre de , plus la probabilité plus la barre sera grande.</span><span class="sxs-lookup"><span data-stu-id="ee60d-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="ee60d-186">Pour la phase, nous montrons les symboles suivants pour représenter l’angle en fonction des plages :</span><span class="sxs-lookup"><span data-stu-id="ee60d-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="ee60d-187">Les exemples `DumpMachine` suivants montrent pour certains États communs :</span><span class="sxs-lookup"><span data-stu-id="ee60d-187">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="ee60d-188">L’id d’un qubit est attribué au moment de l’exécution et il n’est pas nécessairement aligné avec l’ordre dans lequel le qubit a été attribué ou sa position dans un registre de qubit.</span><span class="sxs-lookup"><span data-stu-id="ee60d-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="ee60d-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="ee60d-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="ee60d-190">Vous pouvez trouver un identifiant qubit dans Visual Studio en mettant un point d’arrêt dans votre code et en inspectant la valeur d’une variable qubit, par exemple :</span><span class="sxs-lookup"><span data-stu-id="ee60d-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![afficher qubit id dans Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="ee60d-192">le qubit `0` avec `register2` index`3`sur a id `1` , le`2`qubit avec l’indice a id .</span><span class="sxs-lookup"><span data-stu-id="ee60d-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="ee60d-193">Code de ligne de commande/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ee60d-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="ee60d-194">Vous pouvez trouver un id qubit en utilisant la <xref:microsoft.quantum.intrinsic.message> fonction et en passant la variable de qubit dans le message, par exemple:</span><span class="sxs-lookup"><span data-stu-id="ee60d-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="ee60d-195">qui pourrait générer cette production:</span><span class="sxs-lookup"><span data-stu-id="ee60d-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="ee60d-196">ce qui signifie que `0` le `register2` qubit`3`avec indice sur `1` a`2`id , le qubit avec l’indice a id .</span><span class="sxs-lookup"><span data-stu-id="ee60d-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="ee60d-197"><xref:microsoft.quantum.diagnostics.dumpmachine>fait partie <xref:microsoft.quantum.diagnostics> de l’espace de nom, donc `open` pour l’utiliser, vous devez ajouter une déclaration:</span><span class="sxs-lookup"><span data-stu-id="ee60d-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="ee60d-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="ee60d-198">DumpRegister</span></span>

<span data-ttu-id="ee60d-199"><xref:microsoft.quantum.diagnostics.dumpregister>fonctionne <xref:microsoft.quantum.diagnostics.dumpmachine>comme , sauf qu’il faut également un tableau de qubits pour limiter la quantité d’informations à seulement celle pertinente pour les qubits correspondants.</span><span class="sxs-lookup"><span data-stu-id="ee60d-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="ee60d-200">Comme <xref:microsoft.quantum.diagnostics.dumpmachine>avec , les <xref:microsoft.quantum.diagnostics.dumpregister> informations générées par dépend de la machine cible.</span><span class="sxs-lookup"><span data-stu-id="ee60d-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="ee60d-201">Pour le simulateur quantique à plein état, il écrit dans le fichier la fonction d’onde jusqu’à une <xref:microsoft.quantum.diagnostics.dumpmachine>phase globale du sous-système quantique généré par les qubits fournis dans le même format que .</span><span class="sxs-lookup"><span data-stu-id="ee60d-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="ee60d-202">Par exemple, prendre à nouveau une machine avec seulement deux qubits alloués et dans l’état quantique ${1}$ ${2}$ ${00} ' begin 'align' 'ket{2} 'psi ' 'frac 'sqrt ' 'ket ' 'frac '(1 'i) ' ' ' ' ' ' ' ' '{10} ' ' ' ' ' ' ' '{0} ' ' ' ' ' <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[0]` ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ( (frac{1}'sqrt{2}{0} ' 'ket ' 'frac '(1 'i)'{2} 'ket{1} ) 'otimes 'frac'-(1 'i)'sqrt{2}' 'ket ', 'end’align' $$ calling for generates this output:</span><span class="sxs-lookup"><span data-stu-id="ee60d-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="ee60d-203">et <xref:microsoft.quantum.diagnostics.dumpregister> appeler `qubit[1]` à générer cette production:</span><span class="sxs-lookup"><span data-stu-id="ee60d-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="ee60d-204">En général, l’état d’un registre qui est empêtré dans un autre registre est un état mixte plutôt qu’un état pur.</span><span class="sxs-lookup"><span data-stu-id="ee60d-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="ee60d-205">Dans ce <xref:microsoft.quantum.diagnostics.dumpregister> cas, les sorties du message suivant:</span><span class="sxs-lookup"><span data-stu-id="ee60d-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="ee60d-206">L’exemple suivant vous montre <xref:microsoft.quantum.diagnostics.dumpregister> comment <xref:microsoft.quantum.diagnostics.dumpmachine> vous pouvez utiliser à la fois et dans votre code Q :</span><span class="sxs-lookup"><span data-stu-id="ee60d-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="ee60d-207">Débogage</span><span class="sxs-lookup"><span data-stu-id="ee60d-207">Debugging</span></span>

<span data-ttu-id="ee60d-208">En plus `Assert` `Dump` des fonctions et des opérations, Q' prend en charge un sous-ensemble de capacités standard de débogage Visual Studio : réglage des points de rupture de [ligne,](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints) [passage au code à l’aide de F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) et [l’inspection des valeurs des variables classiques](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) sont possibles lors de l’exécution du code sur le simulateur.</span><span class="sxs-lookup"><span data-stu-id="ee60d-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="ee60d-209">Debugging dans Visual Studio Code tire parti des capacités de débogage fournies par l’extension C 'pour Visual Studio Code alimenté par OmniSharp et nécessite l’installation de la [dernière version](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="ee60d-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span> 
