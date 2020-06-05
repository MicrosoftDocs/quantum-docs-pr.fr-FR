---
title: 'Écrire et simuler des programmes de niveau qubit dans Q #'
description: Didacticiel pas à pas sur l’écriture et la simulation d’un programme Quantum fonctionnant au niveau qubit individuel
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
ms.openlocfilehash: 05d3292e1c6e3c8c1163c460f2aaa51c591aa1d5
ms.sourcegitcommit: 8d9d392bf5e114ae223e6f689ba80d25866ff586
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84422238"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a>Didacticiel : écrire et simuler des programmes de niveau qubit dans Q\#

Bienvenue dans le didacticiel du kit de développement quantique sur l’écriture et la simulation d’un programme Quantum de base qui fonctionne sur des qubits individuels. 

Même si Q # a été principalement créé en tant que langage de programmation de haut niveau pour les programmes quantiques à grande échelle, il peut tout aussi facilement être utilisé pour explorer le niveau inférieur de programmes Quantum : en traitant directement des qubits spécifiques.
La flexibilité de Q # permet aux utilisateurs d’aborder les systèmes quantiques à partir de n’importe quel niveau d’abstraction, et dans ce didacticiel, nous explorons les qubits eux-mêmes.
Plus précisément, nous examinons le capot de la [transformation de Fourier quantique](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), une sous-routine qui fait partie intégrante de nombreux algorithmes quantiques plus volumineux.

Notez que cette vue de bas niveau du traitement des informations de Quantum est souvent décrite en termes de «[circuits quantiques](xref:microsoft.quantum.concepts.circuits)», qui représentent l’application séquentielle des portes à des qubits spécifiques d’un système.

Par conséquent, les opérations Single et qubit que nous appliquons séquentiellement peuvent être facilement représentées dans un « diagramme de circuit ».
Dans notre cas, nous allons définir une opération Q # pour effectuer la transformation de Fourier quantique qubit complète, qui présente la représentation suivante sous la forme d’un circuit :

<br/>
<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a>Prérequis

* [Installez](xref:microsoft.quantum.install) le kit de développement quantique à l’aide de votre langue et de votre environnement de développement préférés.
* Si le QDK est déjà installé, assurez-vous que vous l’avez [mis à jour](xref:microsoft.quantum.update) avec la dernière version


## <a name="in-this-tutorial-youll-learn-how-to"></a>Ce didacticiel vous montre comment effectuer les opérations suivantes :

> [!div class="checklist"]
> * Définir des opérations de Quantum dans Q #
> * Appeler des opérations Q # directement à partir de la ligne de commande ou à l’aide d’un programme hôte classique
> * Simuler une opération de quantum de l’allocation qubit à la sortie de mesure
> * Observer la manière dont le wavefunction simulé du système Quantum évolue tout au long de l’opération

L’exécution d’un programme Quantum avec le kit de développement Quantum de Microsoft se compose généralement de deux parties :
1. Le programme lui-même, qui est implémenté à l’aide du langage de programmation Q # Quantum, puis appelé pour s’exécuter sur un ordinateur Quantum ou un simulateur Quantum. Il s’agit de 
    - Opérations Q # : sous-routines agissant sur des registres quantiques et 
    - Fonctions Q # : sous-routines classiques utilisées dans l’algorithme Quantum.
2. Point d’entrée utilisé pour appeler le programme Quantum et spécifier l’ordinateur cible sur lequel il doit être exécuté.
    Cela peut être effectué directement à partir de la ligne de commande ou par le biais d’un programme hôte écrit dans un langage de programmation classique comme Python ou C#.
    Ce didacticiel comprend des instructions sur la méthode que vous préférez.

## <a name="allocate-qubits-and-define-quantum-operations"></a>Allouer des qubits et définir des opérations de Quantum

La première partie de ce didacticiel consiste à définir l’opération Q # `Perform3qubitQFT` , qui exécute la transformation de Fourier quantique sur trois qubits. 

En outre, nous allons utiliser la [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) fonction pour observer la façon dont la wavefunction simulée de nos trois systèmes qubit évolue au fil de l’opération.

La première étape consiste à créer votre projet et fichier Q #.
La procédure à suivre dépend de l’environnement que vous allez utiliser pour appeler le programme et vous pouvez trouver les détails dans les [guides d’installation](xref:microsoft.quantum.install)respectifs.

Nous vous guiderons pas à pas dans les composants du fichier, mais le code est également disponible sous la forme d’un bloc complet ci-dessous.

### <a name="namespaces-to-access-other-q-operations"></a>Espaces de noms pour accéder aux autres opérations Q #
Dans le fichier, nous commençons par définir l’espace de noms `NamespaceQFT` qui sera accessible par le compilateur.
Pour que notre opération utilise des opérations Q # existantes, nous allons ouvrir les `Microsoft.Quantum.<>` espaces de noms appropriés.

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a>Définir des opérations avec des arguments et des retours
Ensuite, nous définissons l' `Perform3qubitQFT` opération :

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

Pour le moment, l’opération n’accepte aucun argument et ne retourne rien---dans ce cas, nous écrivons qu’elle retourne un `Unit` objet, qui est semblable à `void` en C# ou à un tuple vide, `Tuple[()]` , dans Python.
Plus tard, nous la modifierons pour retourner un tableau de résultats de mesure, à partir duquel le point `Unit` sera remplacé par `Result[]` . 

### <a name="allocate-qubits-with-using"></a>Allouer qubits avec`using`
Dans le cadre de notre opération Q #, nous allouez d’abord un registre de trois qubits à l’aide de l' `using` instruction :

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

Avec `using` , les qubits sont automatiquement alloués dans l' {0} État $ \ket $. Nous pouvons vérifier cela à l’aide de [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) et [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , qui impriment une chaîne et l’état actuel du système sur la console.

> [!NOTE]
> Les `Message(<string>)` `DumpMachine()` fonctions et (à partir de [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) et [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) , respectivement) s’impriment directement sur la console. Tout comme un véritable calcul Quantum, Q # ne nous permet pas d’accéder directement aux États qubit.
> Toutefois, comme `DumpMachine` imprime l’état actuel de l’ordinateur cible, il peut fournir des informations précieuses sur le débogage et l’apprentissage lorsqu’il est utilisé conjointement avec le simulateur d’état complet.


### <a name="applying-single-qubit-and-controlled-gates"></a>Application de portes qubit et contrôlées

Ensuite, nous appliquons les portes qui composent l’opération elle-même.
Q # contient déjà de nombreuses portes de quantum de base en tant qu’opérations dans l' [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) espace de noms, et il ne s’agit pas d’une exception. 

Dans une opération Q #, les instructions qui appellent callables sont bien entendu exécutées dans un ordre séquentiel.
Par conséquent, la première porte à appliquer est le [`H`](xref:microsoft.quantum.intrinsic.h) (hadarmard) au premier qubit :

<br/>
<img src="./qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

Pour appliquer une opération à un qubit spécifique à partir d’un registre (c’est-à-dire un unique `Qubit` d’un tableau `Qubit[]` ), nous utilisons la notation d’index standard.
Ainsi, l’application du [`H`](xref:microsoft.quantum.intrinsic.h) au premier qubit de notre Registre `qs` prend la forme suivante :

```qsharp
            H(qs[0]);
```

Outre l’application de la `H` porte (hadarmard) à des qubits individuels, le circuit QFT se compose principalement de [`R1`](xref:microsoft.quantum.intrinsic.r1) rotations contrôlées.
Une `R1(θ, <qubit>)` opération en général laisse le composant $ \ket {0} $ du qubit inchangé, tout en appliquant une rotation de $e ^ {i\theta} $ au composant $ \ket {1} $.

#### <a name="controlled-operations"></a>Opérations contrôlées

Q # rend très facile la condition de l’exécution d’une opération sur un ou plusieurs qubits de contrôle.
En général, nous prévoyons simplement l’appel avec `Controlled` , et les arguments d’opération changent comme suit :

 `Op(<normal args>)`$ \To $ `Controlled Op([<control qubits>], (<normal args>))` .

Notez que le contrôle qubits doit être fourni sous la forme d’un tableau, même s’il s’agit d’un qubit unique.

Après `H` , nous voyons que les portes suivantes sont les `R1` portes agissant sur le premier qubit (et contrôlées par le deuxième/troisième) :

<br/>
<img src="./qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

Nous les appelons avec

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

Notez que nous utilisons la [`PI()`](xref:microsoft.quantum.math.pi) fonction à partir de l' [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) espace de noms pour définir les rotations en termes de pi radians.
En outre, nous divisez par un `Double` (par exemple `2.0` ), car la division par un entier `2` lèvera une erreur de type. 

> [!TIP]
> `R1(π/2)`et `R1(π/4)` sont équivalents aux `S` `T` opérations et (également dans `Microsoft.Quantum.Intrinsic` ).


Après avoir appliqué les `H` opérations pertinentes et les rotations contrôlées aux deuxième et troisième qubits :

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

Nous avons uniquement besoin d’appliquer une [`SWAP`](xref:microsoft.quantum.intrinsic.swap) porte pour terminer le circuit :

```qsharp
            SWAP(qs[2], qs[0]);
```

Cela est nécessaire, car la nature de la transformation de Fourier quantique retourne le qubits dans l’ordre inverse, de sorte que les échanges permettent une intégration transparente de la sous-routine dans des algorithmes plus volumineux.

Nous avons donc fini d’écrire les opérations de niveau qubit de la transformation de Fourier quantique dans notre opération Q # :

<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

Toutefois, nous ne pouvons pas l’appeler une journée pour l’instant.
Nos qubits étaient dans l’État $ \ket {0} $ lorsque nous les avons alloués, et comme dans la vie, en Q # nous devrions garder des choses de la même façon que nous les avons trouvées (ou mieux !).

### <a name="deallocate-qubits"></a>Libérer qubits

Nous appelons à [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) nouveau pour voir l’état de la suite de l’opération. Enfin, s’applique [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) au registre qubit pour réinitialiser notre qubits à $ \ket {0} $ avant d’effectuer l’opération :

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

Exiger que tous les qubits désalloués soient explicitement définis sur $ \ket {0} $ est une fonctionnalité de base de Q #, car il permet à d’autres opérations de connaître précisément leur état lorsqu’ils commencent à utiliser ces mêmes qubits (une ressource rare).
En outre, cela garantit qu’ils ne sont pas associés à d’autres qubits dans le système.
Si la réinitialisation n’est pas effectuée à la fin d’un `using` bloc d’allocation, une erreur d’exécution est générée.

Votre fichier Q # complet doit maintenant ressembler à ceci :

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


Une fois le fichier Q # et l’opération terminées, notre programme Quantum est prêt à être appelé et simulé.

## <a name="execute-the-program"></a>Exécuter le programme

Après avoir défini notre opération Q # dans un `.qs` fichier, nous devons maintenant appeler cette opération et observer toutes les données classiques retournées.
Pour le moment, aucun résultat n’est renvoyé (Rappelez-vous que notre opération définie ci-dessus retourne `Unit` ), mais lorsque nous modifions ultérieurement l’opération Q # pour retourner un tableau de résultats de mesure ( `Result[]` ), nous allons résoudre ce point.

Bien que le programme Q # soit omniprésent dans les environnements utilisés pour l’appeler, le mode de fonctionnement est bien sûr différent. Par conséquent, suivez simplement les instructions de l’onglet correspondant à votre configuration : utilisation de l’application de ligne de commande Q # ou utilisation d’un programme hôte en Python ou C#.

#### <a name="command-line"></a>[Ligne de commande](#tab/tabid-cmdline)

L’exécution du programme Q # à partir de la ligne de commande nécessite uniquement une petite modification du fichier Q #.

Ajoutez simplement `@EntryPoint()` à une ligne précédant la définition de l’opération :

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

Pour exécuter le programme, ouvrez le terminal dans le dossier de votre projet et entrez

```dotnetcli
dotnet run
```

Lors de l’exécution, vous devez voir les `Message` `DumpMachine` sorties et ci-dessous imprimées dans votre console.


#### <a name="python"></a>[Python](#tab/tabid-python)

Créez un fichier d’hôte Python : `host.py` .

Le fichier hôte est construit comme suit : 
1. Tout d’abord, nous importons le `qsharp` module, qui inscrit le chargeur de module pour l’interopérabilité Q #. 
    Cela permet d’afficher les espaces de noms Q # (par exemple `NamespaceQFT` , que nous avons définis dans notre fichier q #) comme des modules python, à partir desquels nous pouvons importer des opérations q #.
2. Ensuite, importez les opérations Q # que nous appellerons directement---dans ce cas, `Perform3qubitQFT` .
    Nous avons uniquement besoin d’importer le point d’entrée dans un programme Q # (c’est-à-dire _pas_ des opérations telles que `H` et `R1` , qui sont appelées par d’autres opérations q # mais jamais par l’hôte classique).
3. Pour simuler des opérations ou des fonctions Q #, utilisez le formulaire `<Q#callable>.simulate(<args>)` pour les exécuter sur l' `QuantumSimulator()` ordinateur cible. 

> [!NOTE]
> Si nous voulions appeler l’opération sur un autre ordinateur, par exemple le `ResourceEstimator()` , nous utiliserions simplement `<Q#callable>.estimate_resources(<args>)` .
> En général, les opérations Q # sont indépendantes des ordinateurs sur lesquels elles sont exécutées, mais certaines fonctionnalités telles que `DumpMachine` peuvent se comporter différemment.

4. Lors de l’exécution de la simulation, l’appel d’opération retourne des valeurs telles que définies dans le fichier Q #.
    Pour le moment, rien n’est retourné, mais plus tard, nous verrons un exemple d’affectation et de traitement de ces valeurs.
    Avec les données qui en résultent, nous pouvons faire tout ce que nous aimerions de faire.

Le `host.py` fichier complet doit être le suivant :

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

Exécutez le fichier Python, puis imprimez-le dans votre console. vous devez voir les `Message` `DumpMachine` sorties et ci-dessous. 


#### <a name="c"></a>[C#](#tab/tabid-csharp)

Suivez les mêmes instructions que dans le [Guide d’installation](xref:microsoft.quantum.install.cs), créez un fichier d’hôte C#, puis renommez-le `host.cs` .

L’hôte C# se compose de quatre parties :
1. Construire un simulateur quantique.
    Dans le code ci-dessous, il s’agit de la variable `qsim` .
2. Calculer tous les arguments requis pour l’algorithme quantique.
    Il n’y en a aucun dans cet exemple.
3. Exécuter l’algorithme quantique. 
    Chaque opération Q# génère une classe C# du même nom. 
    Cette classe a une méthode `Run` qui exécute l’opération **de façon asynchrone** .
    L’exécution est asynchrone parce que l’exécution sur du matériel réel sera asynchrone. 
    Étant donné que la `Run` méthode est asynchrone, nous appelons la `Wait()` méthode, ce qui bloque l’exécution jusqu’à ce que la tâche se termine et retourne le résultat de façon synchrone. 
4. Traitez le résultat retourné de l’opération.
    Pour le moment, l’opération ne retourne rien.


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
Exécutez l’application et votre sortie doit correspondre à celle ci-dessous.
Le programme se fermera sur l’action d’une touche.
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

En cas d’appel sur le simulateur d’état complet, `DumpMachine()` fournit ces représentations multiples du wavefunction de l’état de Quantum. Les États possibles d’un système $n $-qubit peuvent être représentés par des États de base de $2 ^ n $, chacun avec un coefficient complexe correspondant (simplement une amplitude et une phase).
Les États de base de calcul correspondent à toutes les chaînes binaires de longueur $n $---autrement dit, toutes les combinaisons possibles de qubit $ \ket {0} $ et $ \ket {1} $, où chaque chiffre binaire correspond à un qubit individuel.

La première ligne fournit un commentaire avec les ID des qubits correspondants dans leur ordre significatif.
Qubit `2` étant le « plus significatif » signifie simplement que dans la représentation binaire du vecteur d’état de base $ \ket{i} $, l’état de qubit `2` correspond au chiffre le plus à gauche. Par exemple, $ \ket {6} = \ket {110} $ comprend qubits `2` et `1` les deux dans $ \ket {1} $ et qubit `0` dans $ \ket {0} $.


Les autres lignes décrivent l’amplitude de probabilité de la mesure du vecteur d’état de base $ \ket{i} $ à la fois dans les formats cartésien et polaire.
En détail pour la première ligne de notre état d’entrée $ \ket {000} $ :
* **`|0>:`** Cette ligne correspond à l' `0` État de la base de calcul (étant donné que notre état initial après allocation était de $ \ket {000} $, nous pensons qu’il s’agit du seul État avec une amplitude de probabilité à ce stade).
* **`1.000000 +  0.000000 i`**: amplitude de probabilité au format cartésien.
* **` == `**: le `equal` signe sépare les deux représentations équivalentes.
* **`********************`**: Représentation graphique de l’amplitude, le nombre de `*` est proportionnel à la probabilité de mesurer ce vecteur d’État. 
* **`[ 1.000000 ]`**: valeur numérique de l’amplitude
* **`    ---`**: Représentation graphique de la phase de l’amplitude.
* **`[ 0.0000 rad ]`**: valeur numérique de la phase (en radians).

L’amplitude et la phase sont toutes les deux affichées avec une représentation graphique. La représentation magnitude est simple : elle affiche une barre de `*` et plus la probabilité est élevée, plus la barre est grande. Pour la phase, consultez [test et débogage : fonctions de vidage](xref:microsoft.quantum.guide.testingdebugging#dump-functions) pour les représentations de symboles possibles en fonction des plages angulaires.


La sortie imprimée illustre donc que nos portes programmées ont transformé notre état à partir de

$ $ \ket{\Psi} \_ {initial} = \ket {000} $ $

to 

$ $ \begin{align} \ket{\Psi} \_ {final} &= \frac {1} {\sqrt {8} } \left (\ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{align} $ $

qui est précisément le comportement de la transformation de Fourier 3-qubit. 

Si vous êtes curieux de savoir comment d’autres États d’entrée sont affectés, nous vous invitons à vous lancer avec l’application d’opérations qubit avant la transformation.

## <a name="adding-measurements"></a>Ajout de mesures

Malheureusement, une pierre angulaire de la mécanique de Quantum nous dit qu’un système Quantum réel ne peut pas avoir une telle `DumpMachine` fonction. Au lieu de cela, nous sommes obligés d’extraire des informations par le biais de mesures, ce qui, en général, ne nous permet pas de fournir l’État quantum complet, mais peut également modifier radicalement le système lui-même.
Il existe de nombreux types de mesures de Quantum, mais nous allons nous concentrer sur les mesures projective sur une seule qubits.
En cas de mesure dans une base donnée (par exemple, la base de calcul $ \{ \ket {0} , \ket {1} \} $), l’État qubit est projeté sur tout état de base mesuré---détruisant ainsi la superposition entre les deux.

Pour implémenter des mesures dans un programme Q #, nous utilisons l' `M` opération (from `Microsoft.Quantum.Intrinsic` ), qui retourne un `Result` type.

Tout d’abord, nous modifions notre `Perform3QubitQFT` opération pour retourner un tableau de résultats de mesure, `Result[]` , au lieu de `Unit` .

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a>Définir et initialiser un `Result[]` tableau

Avant même d’allouer des qubits (c’est-à-dire avant l' `using` instruction), nous déclarons et Lions ce tableau de longueur-3 (un `Result` pour chaque qubit) : 

```qsharp
        mutable resultArray = new Result[3];
```

Le `mutable` mot clé `resultArray` en regard permet à la variable d’être reliée plus tard dans le code---par exemple, lors de l’ajout de nos résultats de mesure.

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a>Effectuer des mesures dans une `for` boucle et ajouter des résultats à un tableau

Après les opérations de transformation de Fourier à l’intérieur du `using` bloc, insérez le code suivant :

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
La [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) fonction appelée sur un tableau (par exemple, notre tableau de qubits `qs` ) retourne une plage sur les index du tableau. Ici, nous l’utilisons dans notre `for` boucle pour mesurer séquentiellement chaque qubit à l’aide de l' `M(qs[i])` instruction.
Chaque `Result` type mesuré ( `Zero` ou `One` ) est ensuite ajouté à la position d’index correspondante dans `resultArray` avec une instruction Update-and-réassign.

> [!NOTE]
> La syntaxe de cette instruction est propre à Q #, mais correspond à la réaffectation de variables similaires `resultArray[i] <- M(qs[i])` vue dans d’autres langages tels que F # et R.

Le mot clé `set` est toujours utilisé pour réassigner les variables liées à l’aide de `mutable` .

#### <a name="return-resultarray"></a>Renvoi`resultArray`

Avec les trois qubits mesurés et les résultats ajoutés à `resultArray` , nous sommes sûrs de réinitialiser et de libérer les qubits comme auparavant.
Après la `using` fermeture du bloc, insérez

```qsharp
        return resultArray;
```
pour retourner finalement la sortie de notre opération. 

### <a name="understanding-the-effects-of-measurement"></a>Comprendre les effets de la mesure

Nous allons modifier le placement de nos `DumpMachine` fonctions pour sortir l’état avant et après les mesures.
Le code d’opération final doit ressembler à ceci : 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

Si vous travaillez à partir de la ligne de commande, le tableau retourné sera simplement imprimé directement sur la console à la fin de l’exécution.
Dans le cas contraire, mettez à jour votre programme hôte pour traiter le tableau retourné.

#### <a name="command-line"></a>[Ligne de commande](#tab/tabid-cmdline)

Pour mieux comprendre le tableau retourné qui sera imprimé dans la console, nous pouvons ajouter un autre `Message` dans le fichier Q # juste avant l' `return` instruction :

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

Exécutez le projet, et votre sortie doit ressembler à ce qui suit :

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[Python](#tab/tabid-python)

Mettez à jour votre programme Python en procédant comme suit :

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

Exécutez le fichier, et votre sortie doit ressembler à ce qui suit :

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

Maintenant que notre opération retourne un résultat, remplacez l’appel de méthode `Wait()` par l’extraction de la `Result` propriété. Cela accomplit toujours le même synchronicité que celui abordé précédemment, et nous pouvons lier directement cette valeur à la variable `measurementResult` .

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

Exécutez le projet, et votre sortie doit ressembler à ce qui suit :

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

Cette sortie illustre plusieurs choses :
1. En comparant le résultat retourné à la pré-mesure `DumpMachine` , il n’illustre évidemment _pas_ la superposition QFT sur les États de base.
    Une mesure ne retourne qu’un seul État de base, avec une probabilité déterminée par l’amplitude de cet État dans le wavefunction du système.
2. À partir de l’après-mesure `DumpMachine` , nous voyons que la mesure _modifie_ l’État lui-même, en la projetant à partir de la superposition initiale sur les États de base jusqu’à l’état de base unique qui correspond à la valeur mesurée.

Si nous devions répéter cette opération plusieurs fois, nous verrions que les statistiques de résultat commencent à illustrer la superposition de l’État postérieur à la QFT qui donne lieu à un résultat aléatoire sur chaque capture.
_Toutefois_, en plus d’être inefficace et toujours imparfait, cela ne reproduirait néanmoins que les amplitudes relatives des États de base, et non les phases relatives entre elles.
Ce dernier n’est pas un problème dans cet exemple, mais nous verrions des phases relatives apparaître si une entrée plus complexe est donnée à QFT que $ \ket {000} $.

#### <a name="partial-measurements"></a>Mesures partielles 
Pour découvrir comment mesurer uniquement certains qubits du Registre peut affecter l’état du système, essayez d’ajouter le code suivant à l’intérieur de la `for` boucle, après la ligne de mesure :
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

Notez que pour accéder à la `IntAsString` fonction, vous devez ajouter 
```qsharp
    open Microsoft.Quantum.Convert;
```
avec les autres instructions d’espace de noms `open` .

Dans le résultat obtenu, vous verrez la projection progressive dans des sous-espaces à mesure que chaque qubit est mesuré.


## <a name="use-the-q-libraries"></a>Utiliser les bibliothèques Q #
Comme nous l’avons mentionné dans l’introduction, la plupart des déplacements d’énergie de Q # dans le fait qu’il vous permet de faire abstraction des soucis liés à la gestion de qubits individuels.
En effet, si vous souhaitez développer des programmes quantiques à grande échelle et applicables, vous vous inquiétez de savoir si une `H` opération doit être effectuée avant ou après une rotation particulière. 

Les bibliothèques Q # contiennent l’opération [QFT](xref:microsoft.quantum.canon.qft) , que vous pouvez simplement prendre et demander pour un nombre quelconque de qubits.
Pour essayer, définissez une nouvelle opération dans votre fichier Q # qui a le même contenu `Perform3QubitQFT` , mais avec tout ce qui est du premier `H` au `SWAP` remplacé par deux lignes simples :
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
La première ligne crée simplement une [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expression du tableau alloué de qubits, `qs` , qui est ce que prend l’opération [QFT](xref:microsoft.quantum.canon.qft) comme argument.
Cela correspond à l’ordre des index des qubits dans le registre.

Pour avoir accès à ces opérations, ajoutez `open` des instructions pour leurs espaces de noms respectifs au début du fichier Q # :
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

À présent, ajustez votre programme hôte pour appeler le nom de votre nouvelle opération (par exemple `PerformIntrinsicQFT` ,) et donnez-lui un essayons.

Pour voir l’avantage réel de l’utilisation des opérations de la bibliothèque Q #, modifiez le nombre de qubits à une valeur autre que `3` :
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
Vous pouvez ainsi appliquer le QFT approprié pour un nombre donné de qubits, sans avoir à vous soucier des nouvelles `H` opérations et des rotations sur chaque qubit.

Notez que le simulateur Quantum prend encore plus de temps pour s’exécuter au fur et à mesure que vous augmentez le nombre de qubits---précisément la raison pour laquelle nous sommes impatients de matériel Quantum réel !













