---
title: Explorer l’intrication avec Q#
description: Apprenez à écrire un programme quantique en Q#. Développez une application pour le traitement des états de Bell à l’aide du Quantum Development kit (QDK)
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 16c93b3dd17363c06602529cb34e8fc84aadc7a8
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415420"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Tutoriel : Explorer l’intrication avec Q\#

Dans ce tutoriel, nous vous montrons comment écrire un programme Q# qui manipule et mesure des qubits, puis montre les effets de la superposition et de l’intrication.

Vous allez écrire une application appelée Bell pour démontrer l’intrication quantique.
Le nom Bell fait référence aux états de Bell, à savoir les états quantiques spécifiques de deux qubits utilisés pour représenter les exemples les plus simples de superposition et d’intrication quantique.

## <a name="pre-requisites"></a>Conditions préalables

Si vous êtes prêt à commencer à programmer, suivez ces étapes préalables : 

* [Installez](xref:microsoft.quantum.install) le kit de développement quantique à l’aide de votre langue et de votre environnement de développement préférés.
* Si le QDK est déjà installé, assurez-vous que vous l’avez [mis à jour](xref:microsoft.quantum.update) avec la dernière version

Vous pouvez également suivre la narration sans installer le QDK, en examinant les vues d’ensemble du langage de programmation Q # et les premiers concepts de quantum computing.

## <a name="in-this-tutorial-youll-learn-how-to"></a>Ce didacticiel vous montre comment effectuer les opérations suivantes :

> [!div class="checklist"]
> * Créer et combiner des opérations dans Q\#
> * Créez des opérations pour placer les qubits dans la superposition, les préposer et les mesurer.
> * Démonstration de l’enchevêtrement quantique avec un programme Q # exécuté dans un simulateur. 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a>Démonstration du comportement de qubit avec QDK

Alors que les bits classiques contiennent une seule valeur binaire comme 0 ou 1, l’état d’un [qubit](xref:microsoft.quantum.glossary#qubit) peut se trouver dans une **superposition** de 0 et de 1.  D’un point de vue conceptuel, l’état d’un qubit peut être considéré comme une direction dans un espace abstrait (également appelé vecteur).  Un État qubit peut être dans n’importe quelle direction possible. Les deux **états classiques** sont les deux directions ; représentant 100 % des chances de mesurer 0 et 100 % des chances de mesurer 1.

L’acte de mesure produit un résultat binaire et modifie un l’état d’un qubit.
La mesure produit une valeur binaire, 0 ou 1.  Le qubit passe de la superposition (toute direction) à l’un des états classiques.  Par la suite, la répétition de la même mesure sans aucune opération intermédiaire produit le même résultat binaire.  

Plusieurs qubits peuvent être [**intriqués**](xref:microsoft.quantum.glossary#entanglement).  Quand nous mesurons un seul qubit intriqué, notre connaissance de l’état des autres qubits est également mise à jour.

Maintenant, nous sommes prêts à démontrer comment Q# exprime ce comportement.  Vous commencez avec le programme le plus simple possible, puis développez celui-ci pour démontrer la superposition quantique et l’intrication quantique.

## <a name="creating-a-q-project"></a>Création d’un projet Q #

La première chose à faire est de créer un projet Q #. Dans ce didacticiel, nous allons utiliser l’environnement basé sur des [applications en ligne de commande avec vs code](xref:microsoft.quantum.install.standalone).

Pour créer un nouveau projet, dans VS Code : 

1. Cliquez sur **Afficher**la  ->  **palette de commandes** et sélectionnez **Q # : créer un projet**.
2. Cliquez sur **application console autonome**.
3. Accédez à l’emplacement où enregistrer le projet, puis cliquez sur **créer un projet**.
4. Lorsque le projet est correctement créé, cliquez sur **ouvrir le nouveau projet...** dans le coin inférieur droit.

Dans le cas présent, nous avons appelé le projet `Bell` . Cela génère deux fichiers : `Bell.csproj` , le fichier projet et `Program.qs` , un modèle d’application Q # que nous allons utiliser pour écrire notre application. Le contenu de `Program.qs` doit être :

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a>Écrire l' \# application Q
 
Notre objectif est de préparer deux qubits dans un état quantique spécifique, en démontrant comment agir sur des qubits avec le langage Q# pour modifier leur état et ainsi montrer les effets de la superposition et de l’intrication. Nous allons créer ce composant pour introduire des États, opérations et mesures qubit.

### <a name="initialize-qubit-using-measurement"></a>Initialiser qubit à l’aide de mesures

Dans le premier code ci-dessous, nous vous montrons comment utiliser des qubits en Q#.  Nous allons introduire deux opérations [`M`](xref:microsoft.quantum.intrinsic.m) et [`X`](xref:microsoft.quantum.intrinsic.x) transformer l’état d’un qubit. Dans cet extrait de code, une opération `SetQubitState` est définie et prend comme paramètre un qubit et un autre paramètre, `desired`, qui représente l’état dans lequel nous aimerions que soit le qubit.  L’opération `SetQubitState` effectue une mesure sur le qubit à l’aide de l’opération `M`.  Dans Q #, une mesure qubit retourne toujours `Zero` ou `One` .  Si la mesure retourne une valeur qui n’est pas égale à la valeur souhaitée, `SetQubitState` « retourne » le qubit ; autrement dit, il exécute une `X` opération, qui fait passer l’état de qubit à un nouvel État dans lequel les probabilités d’une mesure retournent `Zero` et `One` sont inversées. De cette façon, `SetQubitState` place toujours le qubit cible à l’état souhaité.

Remplacez le contenu de `Program.qs` par le code suivant :


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

Cette opération peut maintenant être appelée pour définir un qubit dans un état classique, en retournant soit `Zero` dans 100 % des cas, soit `One` dans 100 % des cas.
`Zero` et `One` sont des constantes qui représentent les deux seuls résultats possibles d’une mesure de qubit.

L’opération `SetQubitState` mesure le qubit. Si le qubit est dans l’état souhaité, `SetQubitState` le laisse tranquille ; dans le cas contraire, en exécutant l’opération `X`, nous remplaçons l’état du qubit par l’état souhaité.

#### <a name="about-q-operations"></a>À propos des opérations Q#

Une opération Q# est une sous-routine quantique. Autrement dit, il s’agit d’une routine pouvant être appelée qui contient des appels à d’autres opérations de Quantum.

Les arguments pour une opération sont spécifiés sous forme de tuples, entre parenthèses.

Le type de retour de l’opération est spécifié après un signe deux points. Dans ce cas, l’opération `SetQubitState` ne reçoit pas de retour et est marquée comme renvoyant `Unit`. C’est l’équivalent Q# de `unit` en F#, analogue à `void` en C# et à un tuple vide (`Tuple[()]`) en Python.

Vous avez utilisé deux opérations quantiques dans votre première opération Q# :

* L' [`M`](xref:microsoft.quantum.intrinsic.m) opération, qui mesure l’état du qubit
* [`X`](xref:microsoft.quantum.intrinsic.x)Opération qui retourne l’état d’un qubit

Une opération quantique transforme l’état d’un qubit. Il arrive que les opérations quantiques soient appelées portes quantiques, par analogie avec les portes logiques classiques. Cette désignation remonte aux débuts de l’informatique quantique quand les algorithmes n’étaient qu’une construction théorique visualisée sous forme de schémas à l’instar des schémas électriques en informatique classique.

### <a name="counting-measurement-outcomes"></a>Comptage des résultats de mesure

Pour démontrer l’effet de l’opération de `SetQubitState`, une opération de `TestBellState` est ensuite ajoutée. Cette opération prend comme entrée un `Zero` ou un `One`, puis appelle l’opération `SetQubitState` un certain nombre de fois avec cette entrée, puis compte le nombre de fois où `Zero` a été retourné par la mesure du qubit et le nombre de fois où `One` a été retourné. Bien entendu, dans cette première simulation de l’opération `TestBellState`, nous nous attendons à ce que la sortie indique que toutes les mesures du qubit défini avec `Zero` comme entrée de paramètre retournent `Zero` et que toutes les mesures d’un qubit défini avec `One` comme entrée de paramètre retournent `One`. En outre, nous ajouterons du code à `TestBellState` pour illustrer la superposition et l’enchevêtrement.

Ajoutez l’opération suivante au fichier `Bell.qs`, à l’intérieur de l’espace de noms, une fois l’opération `SetQubitState` terminée :

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
Notez que nous avons ajouté une ligne avant le `return` pour imprimer un message explicatif dans la console avec la fonction ( `Message` ) [Microsoft. Quantum. Intrinsic. message]

Cette opération (`TestBellState`) effectuera une boucle de `count` itérations, définira une valeur `initial` spécifiée sur un qubit, puis mesurera (`M`) le résultat. Elle rassemblera des statistiques sur le nombre de zéros et de uns que nous aurons mesurés et les renverra à l’appelant. Elle effectue une autre opération nécessaire. Elle réinitialise le qubit dans un état connu (`Zero`) avant de le renvoyer pour permettre à d’autres de l’allouer dans un état connu. C’est ce qu’exige l’instruction `using`.

#### <a name="about-variables-in-q"></a>À propos des variables dans Q\#

Par défaut, les variables dans Q# sont immuables. Leur valeur ne peut plus être modifiée une fois qu’elles sont liées. Le mot clé `let` permet d’indiquer la liaison d’une variable immuable. Les arguments d’opération sont toujours immuables.

Si vous avez besoin d’une variable dont la valeur puisse changer, telle que `numOnes` dans l’exemple, vous pouvez la déclarer avec le mot clé `mutable`. Il est possible de modifier la valeur d’une variable muable à l’aide d’une instruction `setQubitState`.

Dans les deux cas, le type d’une variable est inféré par le compilateur. Q# ne nécessite ni annotations, ni variables.

#### <a name="about-using-statements-in-q"></a>À propos `using` des instructions dans Q\#

L’instruction `using` est également spéciale pour Q#. Elle permet d’allouer des qubits à utiliser dans un bloc de code. Dans Q#, tous les qubits sont alloués et libérés de manière dynamique, au lieu qu’ils soient des ressources fixes existant pendant toute la durée de vie d’un algorithme complexe. Une instruction `using` alloue un ensemble de qubits au début, puis libère ces qubits à la fin du bloc.

## <a name="execute-the-code-from-the-command-line"></a>Exécuter le code à partir de la ligne de commande

Pour exécuter le code, nous devons spécifier le compilateur *qui* peut être appelé pour s’exécuter quand nous fournissons la `dotnet run` commande. Pour ce faire, il suffit de modifier le fichier Q # en ajoutant une ligne qui `@EntryPoint()` précède directement l’appelable : l' `TestBellState` opération dans ce cas. Le code complet doit être :

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

Pour exécuter le programme, vous devez spécifier `count` les `initial` arguments et à partir de la ligne de commande. Nous allons choisir exemple `count = 1000` et `initial = One` . Entrez la commande suivante :

```dotnetcli
dotnet run --count 1000 --initial One
```

Et vous devez observer la sortie suivante :

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Si vous essayez avec, `initial = Zero` vous devez observer :

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a>Préparer la superposition

Voyons maintenant comment Q # exprime les façons de placer qubits en superposition.  Rappelez-vous que l’état d’un qubit peut être dans une superposition de 0 et de 1.  Nous allons utiliser l’opération `Hadamard` dans ce but. Si le qubit est dans l’un des états classiques (quand une mesure retourne toujours `Zero` ou toujours `One`), alors l’opération `Hadamard` ou `H` le place dans un état où une mesure du qubit retourne `Zero` dans 50 % des cas et `One` dans 50 % des cas.  D’un point de vue conceptuel, le qubit peut être considéré à mi-chemin entre `Zero` et `One`.  Maintenant, quand nous simulons l’opération `TestBellState`, nous voyons que les résultats retournent grosso modo un nombre égal de `Zero` et de `One` après la mesure.  

### <a name="x-flips-qubit-state"></a>`X`retourne l’État qubit

Nous allons d’abord nous contenter d’essayer d’inverser le qubit (si le qubit est à l’état `Zero`, il passe à `One` et vice versa). Pour cela, une opération `X` est nécessaire avant d’effectuer la mesure dans `TestBellState` :

```qsharp
X(qubit);
let res = M(qubit);
```

Désormais, les résultats sont inversés :

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

À présent, nous allons explorer les propriétés Quantum du qubits.

### <a name="h-prepares-superposition"></a>`H`prépare la superposition

Il nous suffit de remplacer l’opération `X` dans l’exécution précédente par une opération `H` ou Hadamard. Au lieu d’inverser entièrement le qubit de 0 à 1, nous allons ne l’inverser qu’à moitié. Les lignes remplacées dans `TestBellState` ressemblent maintenant à ce qui suit :

```qsharp
H(qubit);
let res = M(qubit);
```

Les résultats deviennent à présent plus intéressants :

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

Chaque fois que nous mesurons, nous demandons une valeur classique mais le qubit étant à mi-chemin entre 0 et 1, nous obtenons (statistiquement) 0 la moitié du temps et 1 l’autre moitié du temps.
C’est ce qu’on appelle une **superposition**, qui nous donne une première vue réelle d’un état quantique.

## <a name="prepare-entanglement"></a>Préparer l’intrication

Voyons maintenant comment Q# exprime les moyens d’intriquer des qubits.
Tout d’abord, nous définissons le premier qubit sur l’état initial, puis nous utilisons l’opération `H` pour le placer en superposition.  Ensuite, avant de mesurer le premier qubit, nous utilisons une nouvelle opération ( `CNOT` ), qui signifie contrôlé-not.  Le résultat de l’exécution de cette opération sur deux qubits consiste à inverser le second qubit si le premier correspond à `One`.  À présent, les deux qubits sont intriqués.  Nos statistiques pour le premier qubit n’ont pas changé (autant de `Zero` que de `One` après la mesure). En revanche, quand nous mesurons le second qubit, le résultat est __toujours__ identique à celui obtenu pour le premier. Notre `CNOT` a intriqué les deux qubits de sorte que ce qui arrive à l’un arrive également à l’autre. Si vous inversiez les mesures (deuxième qubit avant le premier), la même chose se produirait. La première mesure serait aléatoire et la seconde irait de pair avec la première.

La première chose à faire est d’allouer deux qubits au lieu d’un dans `TestBellState` :

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Cela nous permettra d’ajouter une nouvelle opération (`CNOT`) avant de mesurer (`M`) dans `TestBellState` :

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

Nous avons ajouté une autre opération `SetQubitState` pour initialiser le premier qubit afin de nous assurer qu’il est toujours à l’état `Zero` au démarrage.

Nous devons également réinitialiser le deuxième qubit avant de le libérer.

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

La routine complète ressemble maintenant à ceci :

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
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
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

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
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

La nouvelle valeur renvoyée (`agree`) conserve une trace de chaque fois que la mesure du premier qubit correspond à la mesure du deuxième.

Exécution du code que nous obtenons :

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

Comme indiqué dans la vue d’ensemble, nos statistiques pour le premier qubit n’ont pas changé (autant de 0 que de 1). En revanche, quand nous mesurons le second qubit, le résultat est __toujours__ identique à celui obtenu pour le premier, parce qu’ils sont intriqués.

## <a name="next-steps"></a>Étapes suivantes

Le tutoriel sur la [recherche de Grover](xref:microsoft.quantum.quickstarts.search) vous montre comment créer et exécuter une recherche de Grover, à savoir l’un des algorithmes les plus connus en informatique quantique, et propose un exemple de programme Q# pouvant servir à résoudre de vrais problèmes avec l’informatique quantique.  

[Bien démarrer avec le Quantum Development Kit](xref:microsoft.quantum.welcome) recommande d’autres moyens d’apprendre le langage Q# et la programmation quantique.
