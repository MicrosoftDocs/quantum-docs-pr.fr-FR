---
title: Explorer l’intrication avec Q#
description: Apprenez à écrire un programme quantique en Q#. Développez une application pour le traitement des états de Bell à l’aide du Quantum Development kit (QDK)
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 294366b884da93f11c60cfdbdce9b40cf5202b0d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274760"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Tutoriel : Explorer l’intrication avec Q\#

Dans ce tutoriel, nous vous montrons comment écrire un programme Q# qui manipule et mesure des qubits, puis montre les effets de la superposition et de l’intrication.
Vous êtes ainsi accompagné tout au long de l’installation du QDK, de la génération du programme et de son exécution sur un simulateur quantique.  

Vous allez écrire une application appelée Bell pour démontrer l’intrication quantique.
Le nom Bell fait référence aux états de Bell, à savoir les états quantiques spécifiques de deux qubits utilisés pour représenter les exemples les plus simples de superposition et d’intrication quantique.

## <a name="prerequisites"></a>Prérequis

Si vous êtes prêt à commencer à programmer, suivez ces étapes préalables : 

* Installez le kit de développement Quantum pour [Python](xref:microsoft.quantum.install.python) ou [.NET](xref:microsoft.quantum.install.cs).
* Si le QDK est déjà installé, assurez-vous que vous l’avez [mis à jour](xref:microsoft.quantum.update) avec la dernière version

Vous pouvez également suivre la narration sans installer le QDK, en consultant les vues d’ensemble du langage de programmation Q# et les premiers concepts de l’informatique quantique.

## <a name="demonstrating-qubit-behavior-with-q"></a>Démonstration du comportement des qubits avec Q#

Souvenez-vous de notre simple [définition d’un qubit](xref:microsoft.quantum.overview.understanding).  Alors que les bits classiques contiennent une seule valeur binaire comme 0 ou 1, l’état d’un [qubit](xref:microsoft.quantum.glossary#qubit) peut se trouver dans une **superposition** de 0 et de 1.  D’un point de vue conceptuel, un qubit peut être considéré comme une direction dans l’espace (également appelée vecteur).  Un qubit peut être dans n’importe quelle direction possible. Les deux **états classiques** sont les deux directions ; représentant 100 % des chances de mesurer 0 et 100 % des chances de mesurer 1.  Cette représentation se visualise aussi de façon plus formelle par la [sphère de Bloch](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

L’acte de mesure produit un résultat binaire et modifie un l’état d’un qubit. La mesure produit une valeur binaire, 0 ou 1.  Le qubit passe de la superposition (toute direction) à l’un des états classiques.  Par la suite, la répétition de la même mesure sans aucune opération intermédiaire produit le même résultat binaire.  

Plusieurs qubits peuvent être [**intriqués**](xref:microsoft.quantum.glossary#entanglement). Quand nous mesurons un seul qubit intriqué, notre connaissance de l’état des autres qubits est également mise à jour.

Maintenant, nous sommes prêts à démontrer comment Q# exprime ce comportement.  Vous commencez avec le programme le plus simple possible, puis développez celui-ci pour démontrer la superposition quantique et l’intrication quantique.

## <a name="setup"></a>Programme d’installation

Ce tutoriel utilise un programme hôte et se compose de deux parties :

1. Une série d’algorithmes quantiques, implémentés avec le langage de programmation quantique Q#.
1. Un programme hôte, implémenté en Python ou C#, qui sert de point d’entrée principal et appelle des opérations Q# pour exécuter les algorithmes quantiques.

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Choisissez un emplacement pour votre application

1. Création d’un fichier appelé `Bell.qs`. Ce fichier contiendra votre code Q#.

1. Création d’un fichier appelé `host.py`. Ce fichier contiendra votre code d’hôte Python.

#### <a name="c-command-line"></a>[Ligne de commande C#](#tab/tabid-csharp)

1. Créez un projet Q# :

    ```
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    Vous devriez voir un fichier `.csproj`, un fichier Q# nommé `Operations.qs` et un fichier de programme hôte nommé`Driver.cs`

1. Renommez le fichier Q#

    ```
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. Création d'un projet

   * Ouvrez Visual Studio.
   * Ouvrez le menu **Fichier**, puis sélectionnez **Nouveau** -> **Projet...** .
   * Dans l’explorateur de modèles de projet, tapez `Q#` dans le champ de recherche et sélectionnez le modèle `Q# Application`
   * Nommez votre projet `Bell`

1. Renommez le fichier Q#

   * Accédez à l’**Explorateur de solutions**
   * Cliquez avec le bouton droit sur le fichier `Operations.qs`
   * Renommez-le `Bell.qs`

* * *

## <a name="write-a-q-operation"></a>Écrire une opération Q#

Notre objectif est de préparer deux qubits dans un état quantique spécifique, en démontrant comment agir sur des qubits avec le langage Q# pour modifier leur état et ainsi montrer les effets de la superposition et de l’intrication. Nous allons élaborer cela pièce par pièce pour démontrer les états, les opérations et les mesures de qubit.

**Vue d’ensemble :**  Dans le premier code ci-dessous, nous vous montrons comment utiliser des qubits en Q#.  Nous allons introduire deux opérations, `M` et `X` qui transforment l’état d’un qubit. 

Dans cet extrait de code, une opération `Set` est définie et prend comme paramètre un qubit et un autre paramètre, `desired`, qui représente l’état dans lequel nous aimerions que soit le qubit.  L’opération `Set` effectue une mesure sur le qubit à l’aide de l’opération `M`.  En Q#, une mesure de qubit retourne toujours `Zero` ou `One`.  Si la mesure retourne une valeur qui n’est pas égale à une valeur souhaitée, Set « inverse » le qubit ; autrement dit, Set exécute une opération `X`, qui remplace l’état du qubit par un nouvel état dans lequel les probabilités qu’une mesure retourne `Zero` et `One` sont inversées.  Pour démontrer l’effet de l’opération de `Set`, une opération de `TestBellState` est ensuite ajoutée.  Cette opération prend comme entrée un `Zero` ou un `One`, puis appelle l’opération `Set` un certain nombre de fois avec cette entrée, puis compte le nombre de fois où `Zero` a été retourné par la mesure du qubit et le nombre de fois où `One` a été retourné. Bien entendu, dans cette première simulation de l’opération `TestBellState`, nous nous attendons à ce que la sortie indique que toutes les mesures du qubit défini avec `Zero` comme entrée de paramètre retournent `Zero` et que toutes les mesures d’un qubit défini avec `One` comme entrée de paramètre retournent `One`.  De plus, nous allons ajouter du code à `TestBellState` pour démontrer la superposition et l’intrication.


### <a name="q-operation-code"></a>Code d’opération Q#

1. Remplacez le contenu du fichier Bell.qs par le code suivant :

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    Cette opération peut maintenant être appelée pour définir un qubit dans un état classique, en retournant soit `Zero` dans 100 % des cas, soit `One` dans 100 % des cas.  `Zero` et `One` sont des constantes qui représentent les deux seuls résultats possibles d’une mesure de qubit.

    L’opération `Set` mesure le qubit.
    Si le qubit est dans l’état souhaité, `Set` le laisse tranquille ; dans le cas contraire, en exécutant l’opération `X`, nous remplaçons l’état du qubit par l’état souhaité.

### <a name="about-q-operations"></a>À propos des opérations Q#

Une opération Q# est une sous-routine quantique. Autrement dit, il s’agit d’une routine appelable qui contient des opérations quantiques.

Les arguments pour une opération sont spécifiés sous forme de tuples, entre parenthèses.

Le type de retour de l’opération est spécifié après un signe deux points. Dans ce cas, l’opération `Set` ne reçoit pas de retour et est marquée comme renvoyant `Unit`. C’est l’équivalent Q# de `unit` en F#, analogue à `void` en C# et à un tuple vide (`Tuple[()]`) en Python.

Vous avez utilisé deux opérations quantiques dans votre première opération Q# :

* L’opération [M](xref:microsoft.quantum.intrinsic.m), qui mesure l’état du qubit
* L’opération [X](xref:microsoft.quantum.intrinsic.x), qui inverse l’état d’un qubit

Une opération quantique transforme l’état d’un qubit. Il arrive que les opérations quantiques soient appelées portes quantiques, par analogie avec les portes logiques classiques. Cette désignation remonte aux débuts de l’informatique quantique quand les algorithmes n’étaient qu’une construction théorique visualisée sous forme de schémas à l’instar des schémas électriques en informatique classique.

### <a name="add-q-test-code"></a>Ajouter un code de test Q#

1. Ajoutez l’opération suivante au fichier `Bell.qs`, à l’intérieur de l’espace de noms, une fois l’opération `Set` terminée :

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    Cette opération (`TestBellState`) effectuera une boucle de `count` itérations, définira une valeur `initial` spécifiée sur un qubit, puis mesurera (`M`) le résultat. Elle rassemblera des statistiques sur le nombre de zéros et de uns que nous aurons mesurés et les renverra à l’appelant. Elle effectue une autre opération nécessaire. Elle réinitialise le qubit dans un état connu (`Zero`) avant de le renvoyer pour permettre à d’autres de l’allouer dans un état connu. C’est ce qu’exige l’instruction `using`.

### <a name="about-variables-in-q"></a>À propos des variables dans Q#

Par défaut, les variables dans Q# sont immuables. Leur valeur ne peut plus être modifiée une fois qu’elles sont liées. Le mot clé `let` permet d’indiquer la liaison d’une variable immuable. Les arguments d’opération sont toujours immuables.

Si vous avez besoin d’une variable dont la valeur puisse changer, telle que `numOnes` dans l’exemple, vous pouvez la déclarer avec le mot clé `mutable`. Il est possible de modifier la valeur d’une variable muable à l’aide d’une instruction `set`.

Dans les deux cas, le type d’une variable est inféré par le compilateur. Q# ne nécessite ni annotations, ni variables.

### <a name="about-using-statements-in-q"></a>À propos des instructions `using` dans Q#

L’instruction `using` est également spéciale pour Q#. Elle permet d’allouer des qubits à utiliser dans un bloc de code. Dans Q#, tous les qubits sont alloués et libérés de manière dynamique, au lieu qu’ils soient des ressources fixes existant pendant toute la durée de vie d’un algorithme complexe. Une instruction `using` alloue un ensemble de qubits au début, puis libère ces qubits à la fin du bloc.

## <a name="create-the-host-application-code"></a>Créer le code de l’application hôte

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Ouvrez le fichier`host.py` et ajoutez le code suivant :

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

1. Remplacez le contenu du fichier `Driver.cs` par le code suivant :

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a>À propos du code de l’application hôte

#### <a name="python"></a>[Python](#tab/tabid-python)

L’application hôte Python a trois facettes :

* Calculer tous les arguments requis pour l’algorithme quantique. Dans l’exemple, `count` est fixé à 1000 et `initial` est la valeur initiale du qubit.
* Exécuter l’algorithme quantique en appelant la méthode `simulate()` de l’opération Q# importée.
* Traiter le résultat de l’opération. Dans l’exemple, `res` reçoit le résultat de l’opération. Ici, le résultat est un tuple du nombre de zéros (`num_zeros`) et de uns (`num_ones`) mesurés par le simulateur. Nous déconstruisons le tuple pour obtenir les deux champs, puis imprimons les résultats.

#### <a name="c"></a>[C#](#tab/tabid-csharp)

L’application hôte C# comporte quatre volets :

* Construire un simulateur quantique. Dans l’exemple, `qsim` est le simulateur.
* Calculer tous les arguments requis pour l’algorithme quantique. Dans l’exemple, `count` est fixé à 1000 et `initial` est la valeur initiale du qubit.
* Exécuter l’algorithme quantique. Chaque opération Q# génère une classe C# du même nom. Cette classe a une méthode `Run` qui exécute l’opération **de façon asynchrone** . L’exécution est asynchrone parce que l’exécution sur du matériel réel sera asynchrone. La méthode `Run` étant asynchrone, nous récupérons la propriété `Result`. Cela a pour effet de bloquer l’exécution jusqu’à ce que la tâche s’achève et renvoie le résultat de manière synchrone.
* Traiter le résultat de l’opération. Dans l’exemple, `res` reçoit le résultat de l’opération. Ici, le résultat est un tuple du nombre de zéros (`numZeros`) et de uns (`numOnes`) mesurés par le simulateur. Il est retourné en tant que ValueTuple en C#. Nous déconstruisons le tuple pour obtenir les deux champs, imprimons les résultats, puis attendons une action de touche.

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a>Créer et exécuter

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Exécutez la commande suivante sur votre terminal :

    ```
    python host.py
    ```

    Cette commande exécute l’application hôte qui simule l’opération Q#.

Les résultats devraient être les suivants :

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[Code de ligne de commande/Visual Studio Code](#tab/tabid-csharp)

1. Exécutez ce qui suit sur votre terminal :

    ```dotnetcli
    dotnet run
    ```

    Cette commande téléchargera automatiquement tous les packages requis, générera l’application, puis l’exécutera à partir de la ligne de commande.

1. Vous pouvez également appuyer sur **F1** pour ouvrir la palette de commandes et sélectionner **Débogage : Démarrer sans débogage.**
Vous serez peut-être invité à créer un nouveau fichier ``launch.json`` décrivant comment démarrer le programme.
La valeur par défaut ``launch.json`` devrait convenir pour la plupart des applications.

Les résultats devraient être les suivants :

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. Appuyez simplement sur `F5`. Cela devrait avoir pour effet de générer et d’exécuter votre programme.

Les résultats devraient être les suivants :

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

Le programme se fermera sur l’action d’une touche.

* * *

## <a name="prepare-superposition"></a>Préparer la superposition

**Vue d’ensemble** Intéressons-nous maintenant à la manière dont le langage Q# exprime les moyens de mettre des qubits en superposition.  Rappelez-vous que l’état d’un qubit peut être dans une superposition de 0 et de 1.  Nous allons utiliser l’opération `Hadamard` dans ce but. Si le qubit est dans l’un des états classiques (quand une mesure retourne toujours `Zero` ou toujours `One`), alors l’opération `Hadamard` ou `H` le place dans un état où une mesure du qubit retourne `Zero` dans 50 % des cas et `One` dans 50 % des cas.  D’un point de vue conceptuel, le qubit peut être considéré à mi-chemin entre `Zero` et `One`.  Maintenant, quand nous simulons l’opération `TestBellState`, nous voyons que les résultats retournent grosso modo un nombre égal de `Zero` et de `One` après la mesure.  

Nous allons d’abord nous contenter d’essayer d’inverser le qubit (si le qubit est à l’état `Zero`, il passe à `One` et vice versa). Pour cela, une opération `X` est nécessaire avant d’effectuer la mesure dans `TestBellState` :

```qsharp
X(qubit);
let res = M(qubit);
```

À présent, les résultats (après avoir appuyé sur `F5`) sont inversés :

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

Cependant, tout ce que nous avons vu jusqu’à présent est classique. Obtenons un résultat quantique. Il nous suffit de remplacer l’opération `X` dans l’exécution précédente par une opération `H` ou Hadamard. Au lieu d’inverser entièrement le qubit de 0 à 1, nous allons ne l’inverser qu’à moitié. Les lignes remplacées dans `TestBellState` ressemblent maintenant à ce qui suit :

```qsharp
H(qubit);
let res = M(qubit);
```

Les résultats deviennent à présent plus intéressants :

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

Chaque fois que nous mesurons, nous demandons une valeur classique mais le qubit étant à mi-chemin entre 0 et 1, nous obtenons (statistiquement) 0 la moitié du temps et 1 l’autre moitié du temps. C’est ce qu’on appelle une __superposition__, qui nous donne une première vue réelle d’un état quantique.

## <a name="prepare-entanglement"></a>Préparer l’intrication

**Vue d’ensemble :**  Voyons maintenant comment Q# exprime les moyens d’intriquer des qubits.  Tout d’abord, nous définissons le premier qubit sur l’état initial, puis nous utilisons l’opération `H` pour le placer en superposition.  Ensuite, avant de mesurer le premier qubit, nous utilisons une nouvelle opération, `CNOT` (Controlled-Not).  Le résultat de l’exécution de cette opération sur deux qubits consiste à inverser le second qubit si le premier correspond à `One`.  À présent, les deux qubits sont intriqués.  Nos statistiques pour le premier qubit n’ont pas changé (autant de `Zero` que de `One` après la mesure). En revanche, quand nous mesurons le second qubit, le résultat est __toujours__ identique à celui obtenu pour le premier. Notre `CNOT` a intriqué les deux qubits de sorte que ce qui arrive à l’un arrive également à l’autre. Si vous inversiez les mesures (deuxième qubit avant le premier), la même chose se produirait. La première mesure serait aléatoire et la seconde irait de pair avec la première.

La première chose à faire est d’allouer 2 qubits au lieu d’un dans `TestBellState` :

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Cela nous permettra d’ajouter une nouvelle opération (`CNOT`) avant de mesurer (`M`) dans `TestBellState` :

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

Nous avons ajouté une autre opération `Set` pour initialiser le premier qubit afin de nous assurer qu’il est toujours à l’état `Zero` au démarrage.

Nous devons également réinitialiser le deuxième qubit avant de le libérer.

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

La routine complète ressemble maintenant à ceci :

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

Si nous l’exécutons, nous obtiendrons exactement le même résultat 50/50 que celui obtenu auparavant. Cependant, ce qui nous intéresse, c’est la réaction du deuxième qubit à la mesure du premier. Nous ajouterons cette statistique avec une nouvelle version de l’opération `TestBellState` :

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

La nouvelle valeur renvoyée (`agree`) conserve une trace de chaque fois que la mesure du premier qubit correspond à la mesure du deuxième. Nous devons également mettre à jour l’application hôte en conséquence :

#### <a name="python"></a>[Python](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

Maintenant, après exécution, nous obtenons un résultat assez extraordinaire :

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

Comme indiqué dans la vue d’ensemble, nos statistiques pour le premier qubit n’ont pas changé (autant de 0 que de 1). En revanche, quand nous mesurons le second qubit, le résultat est __toujours__ identique à celui obtenu pour le premier, parce qu’ils sont intriqués.

Félicitations, vous avez écrit votre premier programme quantique.

## <a name="next-steps"></a>Étapes suivantes

Le tutoriel sur la [recherche de Grover](xref:microsoft.quantum.quickstarts.search) vous montre comment créer et exécuter une recherche de Grover, à savoir l’un des algorithmes les plus connus en informatique quantique, et propose un exemple de programme Q# pouvant servir à résoudre de vrais problèmes avec l’informatique quantique.  

[Bien démarrer avec le Quantum Development Kit](xref:microsoft.quantum.welcome) recommande d’autres moyens d’apprendre le langage Q# et la programmation quantique.
