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
# <a name="testing-and-debugging"></a>Test et débogage

Comme pour la programmation classique, il est essentiel de pouvoir vérifier que les programmes de Quantum fonctionnent comme prévu, et de pouvoir diagnostiquer un programme Quantum qui est incorrect.
Dans cette section, nous allons aborder les outils proposés par Q # pour le test et le débogage de programmes quantiques.

## <a name="unit-tests"></a>Tests unitaires

Une approche courante du test des programmes classiques consiste à écrire de petits programmes appelés *tests unitaires* , qui exécutent du code dans une bibliothèque et à comparer la sortie à une sortie attendue.
Par exemple, nous pouvons nous assurer que `Square(2)` retourne `4`, puisque nous savons *un a priori* que $2 ^ 2 = $4.

Q # prend en charge la création de tests unitaires pour les programmes Quantum, et qui peuvent être exécutés en tant que tests dans le Framework de tests unitaires [xUnit](https://xunit.github.io/) .

### <a name="creating-a-test-project"></a>Création d’un projet de test

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Ouvrez Visual Studio 2019. Accédez au menu `File` et sélectionnez `New` > `Project...`.
Dans l’Explorateur de modèles de projet, sous `Installed` > `Visual C#`, sélectionnez le modèle `Q# Test Project`.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Ligne de commande/Visual Studio Code](#tab/tabid-vscode)

À partir de votre ligne de commande favorite, exécutez la commande suivante :
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Dans les deux cas, deux fichiers sont ouverts sur votre nouveau projet.
Le premier fichier, `Tests.qs`, offre un emplacement pratique pour définir de nouveaux tests unitaires Q #.
Initialement, ce fichier contient un exemple de test unitaire `AllocateQubitTest` qui vérifie qu’un qubit nouvellement alloué se trouve dans l’État $ \ket{0}$ et imprime un message :

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

Toute opération Q # compatible avec le type `(Unit => Unit)` ou la fonction compatible avec `(Unit -> Unit)` peut être exécutée en tant que test unitaire. 

Le deuxième fichier, `TestSuiteRunner.cs` contient une méthode qui découvre et exécute les tests unitaires Q #. Il s’agit de la méthode `TestTarget` annotée avec `OperationDriver` attribut.
L’attribut `OperationDriver` fait partie de la bibliothèque d’extensions xUnit Microsoft. Quantum. simulation. xUnit.
Le Framework de tests unitaires appelle `TestTarget` méthode pour chaque test unitaire Q # qu’il a découvert.
L’infrastructure passe la description de test unitaire à la méthode via `op` argument. La ligne de code suivante :
```csharp
op.TestOperationRunner(sim);
```
exécute le test unitaire sur `QuantumSimulator`.

Par défaut, le mécanisme de détection de tests unitaires recherche toutes les fonctions Q # ou les opérations de type compatible qui répondent aux propriétés suivantes :
* Situé dans le même assembly que la méthode annotée avec l’attribut `OperationDriver`.
* Situé dans le même espace de noms que la méthode annotée avec l’attribut `OperationDriver`.
* A un nom se terminant par `Test`.

Un assembly, un espace de noms et un suffixe pour les fonctions et les opérations de test unitaire peuvent être définis à l’aide de paramètres facultatifs de l’attribut `OperationDriver` :
* `AssemblyName` paramètre définit le nom de l’assembly dans lequel les tests sont recherchés.
* `TestNamespace` paramètre définit le nom de l’espace de noms dans lequel les tests sont recherchés.
* `Suffix` définit le suffixe des noms d’opération ou de fonction qui sont considérés comme des tests unitaires.

En outre, le `TestCasePrefix` paramètre facultatif vous permet de définir un préfixe pour le nom du cas de test. Le préfixe devant le nom de l’opération s’affiche dans la liste des cas de test. Par exemple, `TestCasePrefix = "QSim:"` entraîne l’affichage de `AllocateQubitTest` comme `QSim:AllocateQubitTest` dans la liste des tests trouvés. Cela peut être utile pour indiquer, par exemple, le simulateur utilisé pour exécuter un test.

### <a name="running-q-unit-tests"></a>Exécution de tests unitaires Q #

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Dans le cadre d’une configuration par solution unique, accédez au menu `Test`, puis sélectionnez `Test Settings` > `Default Processor Architecture` > `X64`.

> [!TIP]
> Le paramètre d’architecture de processeur par défaut de Visual Studio est stocké dans le fichier d’options de solution (`.suo`) pour chaque solution.
> Si vous supprimez ce fichier, vous devez sélectionner `X64` à nouveau en tant qu’architecture de processeur.

Générez le projet, accédez au menu `Test` et sélectionnez `Windows` > `Test Explorer`. `AllocateQubitTest` s’affiche dans la liste des tests du groupe `Not Run Tests`. Sélectionnez `Run All` ou exécutez ce test individuel, et il doit réussir.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Ligne de commande/Visual Studio Code](#tab/tabid-vscode)

Pour exécuter les tests, accédez au dossier du projet (le dossier qui contient `Tests.csproj`) et exécutez la commande :

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

***

## <a name="logging-and-assertions"></a>Journalisation et assertions

Une conséquence importante du fait que les fonctions dans Q # n’ont pas d’effets secondaires, c’est que tous les effets de l’exécution d’une fonction dont le type de sortie est le tuple vide `()` ne peuvent jamais être observés dans un programme Q #.
Autrement dit, un ordinateur cible peut choisir de ne pas exécuter de fonction qui retourne `()` avec la garantie que cette omission ne modifiera pas le comportement d’un code Q # suivant.
Cela rend les fonctions qui retournent `()` un outil utile pour incorporer des assertions et la logique de débogage dans des programmes Q #. 

### <a name="logging"></a>Journalisation

La fonction intrinsèque <xref:microsoft.quantum.intrinsic.message> a le type `(String -> Unit)` et permet la création de messages de diagnostic.

L’action `onLog` de `QuantumSimulator` peut être utilisée pour définir des actions exécutées lorsque le code Q # appelle `Message`. Par défaut, les messages enregistrés sont imprimés dans la sortie standard.

Lors de la définition d’une suite de tests unitaires, les messages journalisés peuvent être dirigés vers la sortie du test. Quand un projet est créé à partir du modèle de projet de test Q #, cette redirection est préconfigurée pour la suite et créée par défaut comme suit :

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Après avoir exécuté un test dans l’Explorateur de tests et cliqué sur le test, un panneau s’affiche avec des informations sur l’exécution des tests : état réussite/échec, temps écoulé et lien de sortie. Si vous cliquez sur le lien « sortie », la sortie de test s’ouvre dans une nouvelle fenêtre.

![sortie de test](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Ligne de commande/Visual Studio Code](#tab/tabid-vscode)

L’État réussite/échec de chaque test est imprimé sur la console par `dotnet test`.
Pour les tests ayant échoué, les sorties enregistrées à la suite de l’appel de `output.WriteLine(msg)` ci-dessus sont également imprimées sur la console pour aider à diagnostiquer l’échec.

***

### <a name="assertions"></a>Assertions

La même logique peut être appliquée à l’implémentation des assertions. Prenons un exemple simple :

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Ici, le mot clé `fail` indique que le calcul ne doit pas continuer, déclenchant une exception sur l’ordinateur cible exécutant le programme Q #.
Par définition, une défaillance de ce type ne peut pas être observée dans Q #, car aucun code Q # supplémentaire n’est exécuté après qu’une instruction `fail` a été atteinte.
Par conséquent, si nous poursuivons un appel à `AssertPositive`, nous pouvons être sûrs que son entrée était positive.

En s’appuyant sur ces idées, [préambule destiné à](xref:microsoft.quantum.libraries.standard.prelude) propose deux assertions particulièrement utiles, <xref:microsoft.quantum.intrinsic.assert> et <xref:microsoft.quantum.intrinsic.assertprob> modelées comme des opérations sur `()`. Ces assertions prennent chacune un opérateur Pauli décrivant une mesure particulière d’intérêt, un registre quantique sur lequel une mesure doit être effectuée et un résultat hypothétique.
Sur les machines cibles qui fonctionnent par simulation, nous ne sommes pas liés par le niveau de travail de [non-clonage](https://en.wikipedia.org/wiki/No-cloning_theorem)et peuvent effectuer ces mesures sans perturber le registre passé à ces assertions.
Un simulateur peut ensuite, à l’instar de la fonction `AssertPositive` ci-dessus, abandonner le calcul si le résultat hypothétique n’est pas respecté dans la pratique :

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

Sur le matériel Quantum physique, où le niveau de stockage de non-clonage empêche l’examen de l’État Quantum, les opérations de `Assert` et de `AssertProb` renvoient simplement `()` sans autre effet.

L’espace de noms <xref:microsoft.quantum.diagnostics> fournit plusieurs autres fonctions de la famille `Assert` qui nous permettent de vérifier des conditions plus avancées. 

## <a name="dump-functions"></a>Fonctions dump

Pour vous aider à résoudre les problèmes liés aux programmes Quantum, l’espace de noms <xref:microsoft.quantum.diagnostics> offre deux fonctions qui peuvent vider dans un fichier l’état actuel de l’ordinateur cible : <xref:microsoft.quantum.diagnostics.dumpmachine> et <xref:microsoft.quantum.diagnostics.dumpregister>. La sortie générée de chaque dépend de l’ordinateur cible.

### <a name="dumpmachine"></a>DumpMachine

Le simulateur quantum complet distribué dans le cadre du kit de développement Quantum écrit dans le fichier la [fonction Wave](https://en.wikipedia.org/wiki/Wave_function) de l’ensemble du système Quantum, sous la forme d’un tableau unidimensionnel de nombres complexes, dans lequel chaque élément représente l’amplitude du probabilité de mesure de l’état de la base de calcul $ \ket{n} $, où $ \ket{n} = \ket{b_{n-1}... b_1b_0} $ pour bits $\{b_i\}$. Par exemple, sur un ordinateur avec seulement deux qubits alloués et dans l’État Quantum $ $ \begin{align} \ket{\Psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10}, \end{align} $ $ appelant <xref:microsoft.quantum.diagnostics.dumpmachine> génère cette sortie :

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

La première ligne fournit un commentaire avec les ID des qubits correspondants dans leur ordre significatif.
Les autres lignes décrivent l’amplitude de probabilité de la mesure du vecteur d’état de base $ \ket{n} $ à la fois dans les formats cartésien et polaire. En détail pour la première ligne :

* **`∣0❭:`** cette ligne correspond à l’état de la base de calcul `0`
* **`0.707107 +  0.000000 i`** : amplitude de probabilité au format cartésien.
* **` == `** : le signe `equal` sépare les deux représentations équivalentes.
* **`**********  `** : représentation graphique de l’amplitude, le nombre de `*` est proportionnel à la probabilité de mesurer ce vecteur d’État.
* **`[ 0.500000 ]`** : valeur numérique de l’amplitude
* **`    ---`** : représentation graphique de la phase de l’amplitude (voir ci-dessous).
* **`[ 0.0000 rad ]`** : valeur numérique de la phase (en radians).

L’amplitude et la phase sont toutes les deux affichées avec une représentation graphique. La représentation magnitude est simple : elle affiche une barre de `*`, plus la probabilité de la barre est importante. Pour la phase, nous affichons les symboles suivants pour représenter l’angle en fonction des plages :

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

Les exemples suivants montrent `DumpMachine` pour certains États courants :

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


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Vous pouvez déterminer un ID qubit dans Visual Studio en plaçant un point d’arrêt dans votre code et en inspectant la valeur d’une variable qubit, par exemple :
  > 
  > ![afficher l’ID qubit dans Visual Studio](~/media/qubit_id.png)
  >
  > le qubit avec l’index `0` sur `register2` possède l’ID =`3`, le qubit avec l’index `1` possède l’ID =`2`.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Ligne de commande/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Vous pouvez déterminer un ID qubit à l’aide de la fonction <xref:microsoft.quantum.intrinsic.message> et en passant la variable qubit dans le message, par exemple :
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > qui peut générer cette sortie :
  >```
  > 0=q:3; 1=q:2
  >```
  > ce qui signifie que le qubit avec l’index `0` sur `register2` a l’ID =`3`, le qubit avec l’index `1` possède l’ID =`2`.


***

<xref:microsoft.quantum.diagnostics.dumpmachine> fait partie de l’espace de noms <xref:microsoft.quantum.diagnostics>, afin de pouvoir l’utiliser, vous devez ajouter une instruction `open` :

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

<xref:microsoft.quantum.diagnostics.dumpregister> fonctionne comme <xref:microsoft.quantum.diagnostics.dumpmachine>, sauf qu’il prend également un tableau de qubits pour limiter la quantité d’informations à ce qui concerne uniquement les qubits correspondants.

Comme avec <xref:microsoft.quantum.diagnostics.dumpmachine>, les informations générées par <xref:microsoft.quantum.diagnostics.dumpregister> dépendent de l’ordinateur cible. Pour le simulateur Quantum à état complet, il écrit dans le fichier la fonction Wave jusqu’à une phase globale du sous-système Quantum généré par le qubits fourni dans le même format que <xref:microsoft.quantum.diagnostics.dumpmachine>.  Par exemple, reprenez un ordinateur avec seulement deux qubits alloués et dans l’État Quantum $ $ \begin{align} \ket{\Psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ pi/4} ((\frac{1}{\sqrt{2}} \ Ket{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + i)} {\sqrt{2}} \ket{0}), \end{align} $ $ appelant <xref:microsoft.quantum.diagnostics.dumpregister> pour `qubit[0]` génère cette sortie :

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

et l’appel de <xref:microsoft.quantum.diagnostics.dumpregister> pour `qubit[1]` génère cette sortie :

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

En général, l’état d’un registre qui est enchevêtré avec un autre registre est un État mixte plutôt qu’un état pur. Dans ce cas, <xref:microsoft.quantum.diagnostics.dumpregister> génère le message suivant :

```
Qubits provided (0;) are entangled with some other qubit.
```

L’exemple suivant montre comment vous pouvez utiliser à la fois <xref:microsoft.quantum.diagnostics.dumpregister> et <xref:microsoft.quantum.diagnostics.dumpmachine> dans votre code Q # :

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

En plus des fonctions et opérations d' `Assert` et de `Dump`, Q # prend en charge un sous-ensemble de fonctionnalités de débogage Visual Studio standard : [définition de points d’arrêt de ligne](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [exécution pas à pas du code à l’aide de F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) et [inspection des valeurs des variables classiques ](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)sont tous possibles au cours de l’exécution du code sur le simulateur.

Le débogage dans Visual Studio Code n’est pas encore pris en charge.

