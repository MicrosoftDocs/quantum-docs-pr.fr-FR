---
title: Test et débogage
description: Découvrez comment utiliser des tests unitaires, des faits et des assertions, et des fonctions dump pour tester et déboguer des programmes quantiques.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: 374ac42255ab6b2c5eff8ab7879b3a5103181f7f
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430915"
---
# <a name="testing-and-debugging"></a>Test et débogage

Comme pour la programmation classique, il est essentiel de pouvoir vérifier que les programmes de Quantum fonctionnent comme prévu, et de pouvoir diagnostiquer un programme Quantum qui est incorrect.
Dans cette section, nous allons aborder les outils proposés par Q # pour le test et le débogage de programmes quantiques.

## <a name="unit-tests"></a>Tests unitaires

Une approche courante du test des programmes classiques consiste à écrire de petits programmes appelés *tests unitaires* , qui exécutent du code dans une bibliothèque et à comparer la sortie à une sortie attendue.
Par exemple, nous pouvons vous assurer que `Square(2)` retourne `4` , puisque nous savons *un priori* que $2 ^ 2 = $4.

Q # prend en charge la création de tests unitaires pour les programmes Quantum, et qui peuvent être exécutés en tant que tests dans le Framework de tests unitaires [xUnit](https://xunit.github.io/) .

### <a name="creating-a-test-project"></a>Création d’un projet de test

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Ouvrez Visual Studio 2019. Accédez au `File` menu et sélectionnez `New`  >  `Project...` .
Dans l’angle supérieur droit, recherchez `Q#` et sélectionnez le `Q# Test Project` modèle.

#### <a name="command-line--visual-studio-code"></a>[Code de ligne de commande/Visual Studio Code](#tab/tabid-vscode)

À partir de votre ligne de commande favorite, exécutez la commande suivante :
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Votre nouveau projet aura un seul fichier `Tests.qs` , qui fournit un emplacement pratique pour définir de nouveaux tests unitaires Q #.
Initialement, ce fichier contient un exemple de test unitaire `AllocateQubit` qui vérifie qu’un qubit nouvellement alloué est dans l' {0} État $ \ket $ et imprime un message :

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

: nouveau : toute opération ou fonction Q # qui accepte un argument de type `Unit` et retourne `Unit` peut être marquée comme un test unitaire via l' `@Test("...")` attribut. L’argument de cet attribut, `"QuantumSimulator"` ci-dessus, spécifie la cible sur laquelle le test est exécuté. Un seul test peut être exécuté sur plusieurs cibles. Par exemple, ajoutez un attribut `@Test("ResourcesEstimator")` ci-dessus `AllocateQubit` . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Enregistrez le fichier et exécutez tous les tests. Il doit maintenant y avoir deux tests unitaires, l’un où AllocateQubit est exécuté sur le QuantumSimulator, et l’autre où il est exécuté dans le ResourceEstimator. 

Le compilateur Q # reconnaît les cibles intégrées « QuantumSimulator », « ToffoliSimulator » et « ResourcesEstimator » comme cibles d’exécution valides pour les tests unitaires. Il est également possible de spécifier un nom qualifié complet pour définir une cible d’exécution personnalisée. 

### <a name="running-q-unit-tests"></a>Exécution de tests unitaires Q #

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Dans le cadre d’une configuration par solution unique, accédez au `Test` menu, puis sélectionnez `Test Settings`  >  `Default Processor Architecture`  >  `X64` .

> [!TIP]
> Le paramètre d’architecture de processeur par défaut pour Visual Studio est stocké dans le fichier options de solution ( `.suo` ) de chaque solution.
> Si vous supprimez ce fichier, vous devrez à nouveau sélectionner `X64` en tant qu’architecture de processeur.

Générez le projet, accédez au `Test` menu et sélectionnez `Windows`  >  `Test Explorer` . `AllocateQubit`s’affiche dans la liste des tests du `Not Run Tests` groupe. Sélectionnez `Run All` ou exécutez ce test individuel, et il doit réussir !

#### <a name="command-line--visual-studio-code"></a>[Code de ligne de commande/Visual Studio Code](#tab/tabid-vscode)

Pour exécuter les tests, accédez au dossier du projet (le dossier qui contient `Tests.csproj` ) et exécutez la commande :

```bash
$ dotnet restore
$ dotnet test
```

La sortie doit ressembler à ce qui suit :

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

Les tests unitaires peuvent être filtrés en fonction de leur nom et/ou de la cible d’exécution :

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

La fonction intrinsèque <xref:microsoft.quantum.intrinsic.message> a le type `(String -> Unit)` et permet la création de messages de diagnostic.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Après avoir exécuté un test dans l’Explorateur de tests et cliqué sur le test, un panneau s’affiche avec des informations sur l’exécution des tests : état réussite/échec, temps écoulé et lien de sortie. Si vous cliquez sur le lien « sortie », la sortie de test s’ouvre dans une nouvelle fenêtre.

![sortie de test](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Code de ligne de commande/Visual Studio Code](#tab/tabid-vscode)

L’État réussite/échec de chaque test est imprimé sur la console par `dotnet test` .
Pour les tests ayant échoué, les sorties sont également imprimées sur la console pour faciliter le diagnostic de l’échec.

***

## <a name="facts-and-assertions"></a>Faits et assertions

Étant donné que les fonctions dans Q # n’ont pas d’effets secondaires _logiques_ , tous les _autres genres_ d’effets de l’exécution d’une fonction dont le type de sortie est le tuple vide ne `()` peuvent jamais être observés dans un programme Q #.
Autrement dit, un ordinateur cible peut choisir de ne pas exécuter une fonction qui retourne `()` avec la garantie que cette omission ne modifiera pas le comportement d’un code Q # suivant.
Cela rend les fonctions qui retournent `()` (c’est-à-dire `Unit` ) un outil utile pour incorporer des assertions et la logique de débogage dans des programmes Q #. 

Prenons un exemple simple :

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Ici, le mot clé `fail` indique que le calcul ne doit pas continuer, déclenchant une exception sur l’ordinateur cible exécutant le programme Q #.
Par définition, une défaillance de ce type ne peut pas être observée dans Q #, car aucun code Q # supplémentaire n’est exécuté une fois qu’une `fail` instruction a été atteinte.
Par conséquent, si nous poursuivons un appel à `PositivityFact` , nous pouvons être sûrs que son entrée était positive.

Notez que nous pouvons implémenter le même comportement que l' `PositivityFact` utilisation [`Fact`](xref:microsoft.quantum.diagnostics.fact) de la fonction à partir de l' <xref:microsoft.quantum.diagnostics> espace de noms :

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

Les *assertions*, en revanche, sont utilisées de la même façon que les faits, mais peuvent dépendre de l’état de l’ordinateur cible. En conséquence, ils sont définis comme des opérations, tandis que les faits sont définis en tant que fonctions (comme indiqué ci-dessus).
Pour comprendre la distinction, considérez l’utilisation suivante d’un fait au sein d’une assertion :

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Ici, nous utilisons l’opération <xref:microsoft.quantum.environment.getqubitsavailabletouse> pour retourner le nombre de qubits disponibles à utiliser.
Comme cela dépend clairement de l’état global du programme et de son environnement d’exécution, notre définition de `AssertQubitsAreAvailable` doit également être une opération.
Toutefois, nous pouvons utiliser cet état global pour donner une `Bool` valeur simple comme entrée à la `Fact` fonction.

En s’appuyant sur ces idées, [préambule destiné à](xref:microsoft.quantum.libraries.standard.prelude) propose deux assertions particulièrement utiles, <xref:microsoft.quantum.intrinsic.assert> et <xref:microsoft.quantum.intrinsic.assertprob> les deux modèles en tant qu’opérations sur `()` . Ces assertions prennent chacune un opérateur Pauli décrivant une mesure particulière d’intérêt, un registre quantique sur lequel une mesure doit être effectuée et un résultat hypothétique.
Sur les machines cibles qui fonctionnent par simulation, nous ne sommes pas liés par le niveau de travail de [non-clonage](https://en.wikipedia.org/wiki/No-cloning_theorem)et peuvent effectuer ces mesures sans perturber le registre passé à ces assertions.
Un simulateur peut ensuite, à l’instar de la `PositivityFact` fonction ci-dessus, abandonner le calcul si le résultat hypothétique n’est pas respecté dans la pratique :

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

Sur le matériel Quantum physique, où le niveau de stockage de non-clonage empêche l’examen de l’État Quantum, les `Assert` `AssertProb` opérations et ne retournent simplement `()` aucun autre effet.

L' <xref:microsoft.quantum.diagnostics> espace de noms fournit plusieurs autres fonctions de la `Assert` famille qui nous permettent de vérifier des conditions plus avancées. 

## <a name="dump-functions"></a>Fonctions dump

Pour aider à résoudre les problèmes liés aux programmes Quantum, l' <xref:microsoft.quantum.diagnostics> espace de noms offre deux fonctions qui peuvent faire un dump dans un fichier de l’état actuel de l’ordinateur cible : <xref:microsoft.quantum.diagnostics.dumpmachine> et <xref:microsoft.quantum.diagnostics.dumpregister> . La sortie générée de chaque dépend de l’ordinateur cible.

### <a name="dumpmachine"></a>DumpMachine

Le simulateur quantum complet distribué dans le cadre du kit de développement quantique écrit dans le fichier la [fonction Wave](https://en.wikipedia.org/wiki/Wave_function) de l’ensemble du système Quantum, sous la forme d’un tableau unidimensionnel de nombres complexes, dans lequel chaque élément représente l’amplitude de la probabilité de mesure de l’état de la base de calcul $ \ket{n} $, où $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ pour bits $ \{ b_i \} $. Par exemple, sur un ordinateur avec seulement deux qubits alloués et dans l’État Quantum $ $ \begin{align} \ket{\Psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ Calling <xref:microsoft.quantum.diagnostics.dumpmachine> génère cette sortie :

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

La première ligne fournit un commentaire avec les ID des qubits correspondants dans leur ordre significatif.
Les autres lignes décrivent l’amplitude de probabilité de la mesure du vecteur d’état de base $ \ket{n} $ à la fois dans les formats cartésien et polaire. En détail pour la première ligne :

* **`∣0❭:`** Cette ligne correspond à l' `0` État de la base de calcul
* **`0.707107 +  0.000000 i`**: amplitude de probabilité au format cartésien.
* **` == `**: le `equal` signe sépare les deux représentations équivalentes.
* **`**********  `**: Représentation graphique de l’amplitude, le nombre de `*` est proportionnel à la probabilité de mesurer ce vecteur d’État.
* **`[ 0.500000 ]`**: valeur numérique de l’amplitude
* **`    ---`**: Représentation graphique de la phase de l’amplitude (voir ci-dessous).
* **`[ 0.0000 rad ]`**: valeur numérique de la phase (en radians).

L’amplitude et la phase sont toutes les deux affichées avec une représentation graphique. La représentation magnitude est simple : elle affiche une barre de, plus la probabilité de la barre est importante `*` . Pour la phase, nous affichons les symboles suivants pour représenter l’angle en fonction des plages :

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

Les exemples suivants illustrent `DumpMachine` certains États courants :

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
  > L’ID d’un qubit est assigné au moment de l’exécution et n’est pas nécessairement aligné avec l’ordre dans lequel le qubit a été alloué ou sa position dans un registre qubit.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Vous pouvez déterminer un ID qubit dans Visual Studio en plaçant un point d’arrêt dans votre code et en inspectant la valeur d’une variable qubit, par exemple :
  > 
  > ![afficher l’ID qubit dans Visual Studio](~/media/qubit_id.png)
  >
  > le qubit avec l’index `0` sur `register2` a l’ID = `3` , le qubit avec l’index `1` a l’ID = `2` .

#### <a name="command-line--visual-studio-code"></a>[Code de ligne de commande/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Vous pouvez déterminer un ID qubit à l’aide de la <xref:microsoft.quantum.intrinsic.message> fonction et en passant la variable qubit dans le message, par exemple :
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > qui peut générer cette sortie :
  >```
  > 0=q:3; 1=q:2
  >```
  > ce qui signifie que le qubit avec l’index `0` sur `register2` a `3` l’ID =, le qubit avec l’index `1` a l’ID = `2` .


***

<xref:microsoft.quantum.diagnostics.dumpmachine>faisant partie de l' <xref:microsoft.quantum.diagnostics> espace de noms, pour pouvoir l’utiliser, vous devez ajouter une `open` instruction :

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


### <a name="dumpregister"></a>DumpRegister

<xref:microsoft.quantum.diagnostics.dumpregister>fonctionne comme <xref:microsoft.quantum.diagnostics.dumpmachine> , sauf qu’il prend également un tableau de qubits pour limiter la quantité d’informations à uniquement celles qui s’appliquent au qubits correspondant.

Comme avec <xref:microsoft.quantum.diagnostics.dumpmachine> , les informations générées par <xref:microsoft.quantum.diagnostics.dumpregister> dépendent de l’ordinateur cible. Pour le simulateur Quantum à état complet, il écrit dans le fichier la fonction Wave jusqu’à une phase globale du sous-système Quantum généré par le qubits fourni dans le même format que <xref:microsoft.quantum.diagnostics.dumpmachine> .  Par exemple, reprenez un ordinateur avec seulement deux qubits alloués et dans l’État Quantum $ $ \begin{align} \ket{\Psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ pi/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ). l’appel de \end{align} $ $ <xref:microsoft.quantum.diagnostics.dumpregister> pour `qubit[0]` génère la sortie suivante :

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

et <xref:microsoft.quantum.diagnostics.dumpregister> l’appel de pour `qubit[1]` génère cette sortie :

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

En général, l’état d’un registre qui est enchevêtré avec un autre registre est un État mixte plutôt qu’un état pur. Dans ce cas, <xref:microsoft.quantum.diagnostics.dumpregister> génère le message suivant :

```
Qubits provided (0;) are entangled with some other qubit.
```

L’exemple suivant montre comment vous pouvez utiliser <xref:microsoft.quantum.diagnostics.dumpregister> et <xref:microsoft.quantum.diagnostics.dumpmachine> dans votre code Q # :

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

## <a name="debugging"></a>Débogage

Sur `Assert` et fonctions et `Dump` opérations, Q # prend en charge un sous-ensemble de fonctionnalités de débogage Visual Studio standard : la [définition de points d’arrêt de ligne](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), le parcours du [code à l’aide de F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) et l' [inspection des valeurs des variables classiques](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) sont tous possibles lors de l’exécution du code sur le simulateur.

Le débogage dans Visual Studio Code s’appuie sur les fonctionnalités de débogage fournies par l’extension C# pour Visual Studio Code équipée de OmniSharp et nécessite l’installation de la [version la plus récente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp). 