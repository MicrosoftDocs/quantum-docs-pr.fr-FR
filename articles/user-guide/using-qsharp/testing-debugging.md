---
title: Test et débogage
description: Découvrez comment utiliser des tests unitaires, des faits et des assertions, et des fonctions dump pour tester et déboguer des programmes quantiques.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2b5276da594ba263177d435c1153f6d96e29c4e8
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867911"
---
# <a name="testing-and-debugging"></a>Test et débogage

Comme pour la programmation classique, il est essentiel de pouvoir vérifier que les programmes de Quantum fonctionnent comme prévu et de pouvoir diagnostiquer un comportement incorrect.
Dans cette section, nous allons aborder les outils proposés par Q# pour le test et le débogage de programmes quantiques.

## <a name="unit-tests"></a>Tests unitaires

Une approche courante du test des programmes classiques consiste à écrire de petits programmes appelés *tests unitaires*, qui exécutent le code dans une bibliothèque et à comparer la sortie à une sortie attendue.
Par exemple, vous pouvez vous assurer que `Square(2)` retourne, `4` car vous connaissez *un priori* de $2 ^ 2 = $4.

Q#prend en charge la création de tests unitaires pour les programmes Quantum et peut s’exécuter en tant que tests dans l’infrastructure de tests unitaires [xUnit](https://xunit.github.io/) .

### <a name="creating-a-test-project"></a>Création d’un projet de test

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Ouvrez Visual Studio 2019. Accédez au menu **fichier** et sélectionnez **nouveau > projet...**. Dans l’angle supérieur droit, recherchez `Q#` et sélectionnez le modèle ** Q# projet de test** .

#### <a name="command-line--visual-studio-code"></a>[Code de ligne de commande/Visual Studio Code](#tab/tabid-vscode)

À partir de votre ligne de commande favorite, exécutez la commande suivante :
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Votre nouveau projet contient un seul fichier `Tests.qs` , qui fournit un emplacement pratique pour définir de nouveaux Q# tests unitaires.
Initialement, ce fichier contient un exemple de test unitaire `AllocateQubit` qui vérifie qu’un qubit nouvellement alloué est dans l’État $ \ket {0} $ et imprime un message :

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

Toute Q# opération ou fonction qui accepte un argument de type `Unit` et retourne `Unit` peut être marquée comme un test unitaire via l' `@Test("...")` attribut. Dans l’exemple précédent, l’argument de cet attribut, `"QuantumSimulator"` , spécifie la cible sur laquelle le test s’exécute. Un test unique peut s’exécuter sur plusieurs cibles. Par exemple, ajoutez un attribut `@Test("ResourcesEstimator")` avant `AllocateQubit` . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Enregistrez le fichier et exécutez tous les tests. Il doit maintenant y avoir deux tests unitaires, un où `AllocateQubit` s’exécute sur le `QuantumSimulator` , et un autre où il s’exécute dans le `ResourcesEstimator` . 

Le Q# compilateur reconnaît les cibles intégrées `"QuantumSimulator"` , `"ToffoliSimulator"` et `"ResourcesEstimator"` en tant que cibles d’exécution valides pour les tests unitaires. Il est également possible de spécifier un nom qualifié complet pour définir une cible d’exécution personnalisée. 

### <a name="running-no-locq-unit-tests"></a>Exécution de Q# tests unitaires

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Dans le cadre d’une configuration par solution unique, accédez au menu **test** et sélectionnez **paramètres de test > architecture de processeur par défaut > x64**.

> [!TIP]
> Le paramètre d’architecture de processeur par défaut pour Visual Studio est stocké dans le fichier options de solution ( `.suo` ) de chaque solution.
> Si vous supprimez ce fichier, vous devez à nouveau sélectionner **x64** comme architecture de processeur.

Générez le projet, ouvrez le menu **test** , puis sélectionnez **Windows >** de l’Explorateur de tests. **AllocateQubit** s’affiche dans la liste des tests dans le groupe **tests non exécutés** . Sélectionnez **exécuter tout** ou exécuter ce test individuel.

#### <a name="command-line--visual-studio-code"></a>[Code de ligne de commande/Visual Studio Code](#tab/tabid-vscode)

Pour exécuter les tests, accédez au dossier du projet (le dossier qui contient `Tests.csproj` ), puis exécutez la commande :

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

Les tests unitaires peuvent être filtrés en fonction de leur nom ou de la cible d’exécution :

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

La fonction intrinsèque <xref:microsoft.quantum.intrinsic.message> a le type `(String -> Unit)` et permet la création de messages de diagnostic.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Après avoir exécuté un test dans l’Explorateur de tests et cliqué sur le test, un panneau s’affiche avec des informations sur l’exécution des tests : état réussite/échec, temps écoulé et un lien vers la sortie. Cliquez sur **sortie** pour ouvrir la sortie de test dans une nouvelle fenêtre.

![sortie de test](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Code de ligne de commande/Visual Studio Code](#tab/tabid-vscode)

L’État réussite/échec de chaque test est imprimé sur la console par `dotnet test` .
Pour les tests ayant échoué, les sorties sont également imprimées sur la console pour faciliter le diagnostic de l’échec.

***

## <a name="facts-and-assertions"></a>Faits et assertions

Étant donné que les fonctions de n' Q# ont pas d’effets secondaires _logiques_ , vous ne pouvez jamais observer, à partir d’un Q# programme, tous les autres genres d’effets de l’exécution d’une fonction dont le type de sortie est le tuple vide `()` .
Autrement dit, un ordinateur cible peut choisir de ne pas exécuter une fonction qui retourne `()` avec la garantie que cette omission ne modifiera pas le comportement d’un Q# code suivant.
Ce comportement rend les fonctions qui retournent `()` (comme `Unit` ) un outil utile pour incorporer des assertions et la logique de débogage dans des Q# programmes. 

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

Ici, le mot clé `fail` indique que le calcul ne doit pas continuer et lève une exception sur l’ordinateur cible qui exécute le Q# programme.
Par définition, une défaillance de ce type ne peut pas être observée dans Q# , car l’ordinateur cible n’exécute plus le Q# code après avoir atteint une `fail` instruction.
Par conséquent, si nous poursuivons un appel à `PositivityFact` , nous pouvons être assurés que son entrée était positive.

Notez que nous pouvons implémenter le même comportement que l' `PositivityFact` utilisation [`Fact`](xref:microsoft.quantum.diagnostics.fact) de la fonction à partir de l' <xref:microsoft.quantum.diagnostics> espace de noms :

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

En revanche, les *assertions*sont utilisées de la même façon que les faits, mais peuvent dépendre de l’état de l’ordinateur cible. En conséquence, ils sont définis en tant qu’opérations, tandis que les faits sont définis en tant que fonctions (comme dans l’exemple précédent).
Pour comprendre la distinction, considérez l’utilisation suivante d’un fait au sein d’une assertion :

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Ici, nous utilisons l’opération <xref:microsoft.quantum.environment.getqubitsavailabletouse> pour retourner le nombre de qubits disponibles à utiliser.
Comme cela dépend de l’état global du programme et de son environnement d’exécution, notre définition de `AssertQubitsAreAvailable` doit également être une opération.
Toutefois, nous pouvons utiliser cet état global pour donner une `Bool` valeur simple comme entrée à la `Fact` fonction.

[Préambule destiné à](xref:microsoft.quantum.libraries.standard.prelude), en s’appuyant sur ces idées, offre deux assertions particulièrement utiles, <xref:microsoft.quantum.diagnostics.assertmeasurement> et <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> les deux modèles en tant qu’opérations sur `()` . Ces assertions prennent chacune un opérateur Pauli décrivant une mesure particulière d’intérêt, un registre quantique sur lequel une mesure est effectuée et un résultat hypothétique.
Les machines cibles qui fonctionnent par simulation ne sont pas liées par le registre de [non-clonage](https://en.wikipedia.org/wiki/No-cloning_theorem), et peuvent effectuer des mesures de ce type sans perturber le Registre qui passe à ces assertions.
Un simulateur peut ensuite, à l’instar de la `PositivityFact` fonction précédente, arrêter le calcul si le résultat hypothétique n’est pas observé dans la pratique :

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

Sur le matériel Quantum physique, où le niveau de stockage de non-clonage empêche l’examen d’un État Quantum, les `AssertMeasurement` `AssertMeasurementProbability` opérations et ne retournent simplement `()` aucun autre effet.

L' <xref:microsoft.quantum.diagnostics> espace de noms fournit plusieurs autres fonctions de la `Assert` famille, avec lesquelles vous pouvez vérifier des conditions plus avancées. 

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
* **`    ---`**: Représentation graphique de la phase de l’amplitude (voir la sortie suivante).
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
  > Vous pouvez localiser un ID qubit dans Visual Studio en plaçant un point d’arrêt dans votre code et en inspectant la valeur d’une variable qubit, par exemple :
  > 
  > ![afficher l’ID qubit dans Visual Studio](~/media/qubit_id.png)
  >
  > le qubit avec l’index `0` sur `register2` a l’ID = `3` , le qubit avec l’index `1` a l’ID = `2` .

#### <a name="command-line--visual-studio-code"></a>[Code de ligne de commande/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Vous pouvez localiser un ID qubit à l’aide de la <xref:microsoft.quantum.intrinsic.message> fonction et en passant la variable qubit dans le message, par exemple :
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

Étant donné que <xref:microsoft.quantum.diagnostics.dumpmachine> fait partie de l' <xref:microsoft.quantum.diagnostics> espace de noms, vous devez ajouter une `open` instruction pour y accéder :

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

<xref:microsoft.quantum.diagnostics.dumpregister>fonctionne comme <xref:microsoft.quantum.diagnostics.dumpmachine> , mais il prend également un tableau de qubits pour limiter la quantité d’informations à ce qui concerne uniquement les qubits correspondants.

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

L’exemple suivant montre comment vous pouvez utiliser <xref:microsoft.quantum.diagnostics.dumpregister> et <xref:microsoft.quantum.diagnostics.dumpmachine> dans votre Q# Code :

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

En plus de `Assert` et des `Dump` fonctions et opérations Q# , prend en charge un sous-ensemble de fonctionnalités de débogage Visual Studio standard : la [définition de points d’arrêt de ligne](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), le parcours du [code à l’aide de F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)et l' [inspection des valeurs des variables classiques](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) sont toutes possibles lors de l’exécution du code sur le simulateur.

Le débogage dans Visual Studio Code s’appuie sur les fonctionnalités de débogage fournies par l’extension C# pour Visual Studio Code équipée de OmniSharp et nécessite l’installation de la [version la plus récente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp). 
