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
# <a name="testing-and-debugging"></a>Test et débogage

Comme pour la programmation classique, il est essentiel de pouvoir vérifier que les programmes quantiques agissent comme prévu, et d’être en mesure de diagnostiquer un programme quantique qui est incorrect.
Dans cette section, nous couvrons les outils offerts par QMD pour tester et débogage des programmes quantiques.

## <a name="unit-tests"></a>Tests unitaires

Une approche courante pour tester les programmes classiques est d’écrire de petits programmes appelés *tests unitaires* qui exécutent du code dans une bibliothèque et de comparer sa production à une certaine sortie prévue.
Par exemple, nous pouvons `Square(2)` vouloir `4`nous assurer que les retours , puisque nous savons *a priori* que 2 $ - 4 $.

QMD prend en charge la création de tests unitaires pour les programmes quantiques, et qui peuvent être exécutés sous forme de tests dans le cadre de test de [l’unité xUnit.](https://xunit.github.io/)

### <a name="creating-a-test-project"></a>Création d’un projet d’essai

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Ouvrez Visual Studio 2019. Aller au `File` menu `New`  >  `Project...`et sélectionner .
Dans le coin supérieur `Q#`droit, recherchez et sélectionnez le `Q# Test Project` modèle.

#### <a name="command-line--visual-studio-code"></a>[Code de ligne de commande/Visual Studio Code](#tab/tabid-vscode)

De votre ligne de commande préférée, exécutez la commande suivante :
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Votre nouveau projet aura `Tests.qs`un seul fichier, qui fournit un endroit pratique pour définir les nouveaux tests unitaires Q.
Initialement, ce fichier contient `AllocateQubit` un test unitaire échantillon qui vérifie qu’un qubit nouvellement alloué est dans l’état de $ket{0}$ et imprime un message:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:nouveau : Toute opération ou fonction QMD `Unit` qui `Unit` prend un argument de `@Test("...")` type et de retours peut être marquée comme un test unitaire via l’attribut. L’argument à `"QuantumSimulator"` cet attribut, ci-dessus, spécifie la cible sur laquelle le test est exécuté. Un seul test peut être exécuté sur plusieurs cibles. Par exemple, ajoutez `@Test("ResourcesEstimator")` `AllocateQubit`un attribut ci-dessus . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Enregistrer le fichier et exécuter tous les tests. Il devrait maintenant y avoir deux tests unitaires, l’un où AllocateQubit est exécuté sur le QuantumSimulator, et l’autre où il est exécuté dans le ResourceEstimator. 

Le compilateur Qmd reconnaît les cibles intégrées « QuantumSimulator », « ToffoliSimulator » et « ResourcesEstimator » comme cibles d’exécution valides pour les tests unitaires. Il est également possible de spécifier un nom entièrement qualifié pour définir une cible d’exécution personnalisée. 

### <a name="running-q-unit-tests"></a>Exécution des tests d’unité Q

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

En tant que configuration par solution `Test` unique, `Test Settings`  >  `Default Processor Architecture`  > allez au menu et sélectionnez. `X64`

> [!TIP]
> Le paramètre d’architecture de processeur par`.suo`défaut pour Visual Studio est stocké dans le fichier options de solution () pour chaque solution.
> Si vous supprimez ce fichier, `X64` alors vous devrez sélectionner comme architecture de processeur à nouveau.

Construire le projet, `Test` aller au `Windows`  >  `Test Explorer`menu et sélectionner . `AllocateQubit`s’affichera dans la liste `Not Run Tests` des tests dans le groupe. Sélectionnez `Run All` ou exécutez ce test individuel, et il devrait passer!

#### <a name="command-line--visual-studio-code"></a>[Code de ligne de commande/Visual Studio Code](#tab/tabid-vscode)

Pour exécuter des tests, naviguez vers le `Tests.csproj`dossier du projet (le dossier qui contient), et exécutez la commande :

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

Les tests unitaires peuvent être filtrés en fonction de leur nom et/ou de la cible d’exécution :

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

La fonction <xref:microsoft.quantum.intrinsic.message> intrinsèque `(String -> Unit)` a le type et permet la création de messages diagnostiques.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Après avoir exécuté un test dans Test Explorer et cliquer sur le test, un panneau apparaîtra avec des informations sur l’exécution du test: Statut passé/échec, temps écoulé et un lien "Sortie". Si vous cliquez sur le lien "Output", la sortie du test s’ouvrira dans une nouvelle fenêtre.

![sortie de test](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Code de ligne de commande/Visual Studio Code](#tab/tabid-vscode)

Le statut de passage/échec pour chaque test `dotnet test`est imprimé sur la console par .
Pour les tests défaillants, les sorties sont également imprimées sur la console pour aider à diagnostiquer l’échec.

***

## <a name="facts-and-assertions"></a>Faits et affirmations

Étant donné que les fonctions dans Q N’ont pas d’effets secondaires _logiques,_ tout _autre type_ d’effets de l’exécution d’une fonction dont le type de sortie est le tuple `()` vide ne peut jamais être observé à partir d’un programme Q.
Autrement dit, une machine cible peut choisir `()` de ne pas exécuter toute fonction qui revient avec la garantie que cette omission ne modifiera pas le comportement de tout code Q ' suivant.
Cela rend le `()` retour des `Unit`fonctions (c.-à-d. ) un outil utile pour intégrer les affirmations et déboguer la logique dans les programmes Q. 

Prenons un exemple simple :

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Ici, le `fail` mot clé indique que le calcul ne doit pas se poursuivre, ce qui soulève une exception dans la machine cible exécutant le programme Q.
Par définition, un échec de ce type ne peut pas être observé à `fail` partir de Q, car aucun autre code Q est exécuté après qu’une déclaration est atteinte.
Ainsi, si nous passons au-delà d’un appel à `PositivityFact`, nous pouvons être assurés par que son apport était positif.

Notez que nous pouvons `PositivityFact` implémenter le même comportement que l’utilisation de la [`Fact`](xref:microsoft.quantum.diagnostics.fact) fonction de l’espace <xref:microsoft.quantum.diagnostics> nom:

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

*Les affirmations,* d’autre part, sont utilisées de la même façon que les faits, mais peuvent dépendre de l’état de la machine cible. En conséquence, ils sont définis comme des opérations, tandis que les faits sont définis comme des fonctions (comme ci-dessus).
Pour comprendre la distinction, considérez l’utilisation suivante d’un fait dans une affirmation :

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Ici, nous utilisons <xref:microsoft.quantum.environment.getqubitsavailabletouse> l’opération pour retourner le nombre de qubits disponibles à l’utilisation.
Comme cela dépend clairement de l’état global du programme `AssertQubitsAreAvailable` et de son environnement d’exécution, notre définition de doit être une opération ainsi.
Cependant, nous pouvons utiliser cet état `Bool` mondial pour `Fact` donner une valeur simple comme entrée à la fonction.

S’appuyant sur ces idées, [le prélude](xref:microsoft.quantum.libraries.standard.prelude) <xref:microsoft.quantum.intrinsic.assertprob> offre deux affirmations `()`particulièrement utiles, <xref:microsoft.quantum.intrinsic.assert> et les deux modélisé comme des opérations sur . Ces affirmations prennent chacune un opérateur Pauli décrivant une mesure particulière de l’intérêt, un registre quantique sur lequel une mesure doit être effectuée, et un résultat hypothétique.
Sur les machines cibles qui fonctionnent par simulation, nous ne sommes pas liés par [le théorème de non-clonage](https://en.wikipedia.org/wiki/No-cloning_theorem), et peut effectuer de telles mesures sans perturber le registre passé à de telles affirmations.
Un simulateur peut alors, `PositivityFact` semblable à la fonction ci-dessus, interrompre le calcul si le résultat hypothétique ne serait pas observé dans la pratique :

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

Sur le matériel quantique physique, où le théorème sans `Assert` clonage empêche l’examen de l’état quantique, les opérations et `AssertProb` les opérations reviennent `()` tout simplement sans autre effet.

L’espace <xref:microsoft.quantum.diagnostics> de nom fournit `Assert` plusieurs autres fonctions de la famille qui nous permettent de vérifier les conditions plus avancées. 

## <a name="dump-functions"></a>Fonctions de décharge

Pour aider à dépanner <xref:microsoft.quantum.diagnostics> les programmes quantiques, l’espace nom offre deux fonctions qui peuvent jeter dans un fichier l’état actuel de la machine cible: <xref:microsoft.quantum.diagnostics.dumpmachine> et <xref:microsoft.quantum.diagnostics.dumpregister>. La sortie générée de chacun dépend de la machine cible.

### <a name="dumpmachine"></a>DumpMachine

Le simulateur quantique à plein état distribué dans le cadre de la trousse de développement quantique écrit dans le fichier la [fonction d’onde](https://en.wikipedia.org/wiki/Wave_function) de l’ensemble du système quantique, comme une gamme unidimensionnelle de nombres complexes, dans lequel chaque élément représente l’amplitude de la probabilité de mesurer l’état de base de calcul $ket 'n$, où $ket 'n ' ' 'b_ 'n-1 '... b_1b_0$ pour les morceaux\{b_i\}$. Par exemple, sur une machine avec seulement deux qubits alloués et dans l’état quantique $ ${1}$ ${2}'begin 'align' ''ket 'psi ' 'frac 'sqrt ' 'ket{00} ' 'frac '(1 'i)'{2} 'ket{10}, 'end 'align' $$ appelant <xref:microsoft.quantum.diagnostics.dumpmachine> génère cette sortie:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

La première rangée fournit un commentaire avec les cartes d’ID des qubits correspondants dans leur ordre significatif.
Le reste des lignes décrit l’amplitude de probabilité de mesurer le vecteur de l’état de base $ 'n'$ dans les formats cartésiens et polaires. Dans le détail pour la première rangée:

* **`∣0❭:`** cette ligne correspond `0` à l’état de base de calcul
* **`0.707107 +  0.000000 i`**: l’amplitude de probabilité en format cartésien.
* **` == `**: `equal` le signe sépécie les deux représentations équivalentes.
* **`**********  `**: Représentation graphique de l’ampleur, `*` le nombre de est proportionnel à la probabilité de mesurer ce vecteur d’état.
* **`[ 0.500000 ]`**: la valeur numérique de l’ampleur
* **`    ---`**: Représentation graphique de la phase de l’amplitude (voir ci-dessous).
* **`[ 0.0000 rad ]`**: la valeur numérique de la phase (en radians).

L’ampleur et la phase sont affichées avec une représentation graphique. La représentation de magnitude est simple: `*`il montre une barre de , plus la probabilité plus la barre sera grande. Pour la phase, nous montrons les symboles suivants pour représenter l’angle en fonction des plages :

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

Les exemples `DumpMachine` suivants montrent pour certains États communs :

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
  > L’id d’un qubit est attribué au moment de l’exécution et il n’est pas nécessairement aligné avec l’ordre dans lequel le qubit a été attribué ou sa position dans un registre de qubit.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Vous pouvez trouver un identifiant qubit dans Visual Studio en mettant un point d’arrêt dans votre code et en inspectant la valeur d’une variable qubit, par exemple :
  > 
  > ![afficher qubit id dans Visual Studio](~/media/qubit_id.png)
  >
  > le qubit `0` avec `register2` index`3`sur a id `1` , le`2`qubit avec l’indice a id .

#### <a name="command-line--visual-studio-code"></a>[Code de ligne de commande/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Vous pouvez trouver un id qubit en utilisant la <xref:microsoft.quantum.intrinsic.message> fonction et en passant la variable de qubit dans le message, par exemple:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > qui pourrait générer cette production:
  >```
  > 0=q:3; 1=q:2
  >```
  > ce qui signifie que `0` le `register2` qubit`3`avec indice sur `1` a`2`id , le qubit avec l’indice a id .


***

<xref:microsoft.quantum.diagnostics.dumpmachine>fait partie <xref:microsoft.quantum.diagnostics> de l’espace de nom, donc `open` pour l’utiliser, vous devez ajouter une déclaration:

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

<xref:microsoft.quantum.diagnostics.dumpregister>fonctionne <xref:microsoft.quantum.diagnostics.dumpmachine>comme , sauf qu’il faut également un tableau de qubits pour limiter la quantité d’informations à seulement celle pertinente pour les qubits correspondants.

Comme <xref:microsoft.quantum.diagnostics.dumpmachine>avec , les <xref:microsoft.quantum.diagnostics.dumpregister> informations générées par dépend de la machine cible. Pour le simulateur quantique à plein état, il écrit dans le fichier la fonction d’onde jusqu’à une <xref:microsoft.quantum.diagnostics.dumpmachine>phase globale du sous-système quantique généré par les qubits fournis dans le même format que .  Par exemple, prendre à nouveau une machine avec seulement deux qubits alloués et dans l’état quantique ${1}$ ${2}$ ${00} ' begin 'align' 'ket{2} 'psi ' 'frac 'sqrt ' 'ket ' 'frac '(1 'i) ' ' ' ' ' ' ' ' '{10} ' ' ' ' ' ' ' '{0} ' ' ' ' ' <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[0]` ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ( (frac{1}'sqrt{2}{0} ' 'ket ' 'frac '(1 'i)'{2} 'ket{1} ) 'otimes 'frac'-(1 'i)'sqrt{2}' 'ket ', 'end’align' $$ calling for generates this output:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

et <xref:microsoft.quantum.diagnostics.dumpregister> appeler `qubit[1]` à générer cette production:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

En général, l’état d’un registre qui est empêtré dans un autre registre est un état mixte plutôt qu’un état pur. Dans ce <xref:microsoft.quantum.diagnostics.dumpregister> cas, les sorties du message suivant:

```
Qubits provided (0;) are entangled with some other qubit.
```

L’exemple suivant vous montre <xref:microsoft.quantum.diagnostics.dumpregister> comment <xref:microsoft.quantum.diagnostics.dumpmachine> vous pouvez utiliser à la fois et dans votre code Q :

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

En plus `Assert` `Dump` des fonctions et des opérations, Q' prend en charge un sous-ensemble de capacités standard de débogage Visual Studio : réglage des points de rupture de [ligne,](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints) [passage au code à l’aide de F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) et [l’inspection des valeurs des variables classiques](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) sont possibles lors de l’exécution du code sur le simulateur.

Debugging dans Visual Studio Code tire parti des capacités de débogage fournies par l’extension C 'pour Visual Studio Code alimenté par OmniSharp et nécessite l’installation de la [dernière version](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp). 
