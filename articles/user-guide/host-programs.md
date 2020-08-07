---
title: Méthodes d’exécution d’un Q# programme
description: Vue d’ensemble des différentes façons d’exécuter des Q# programmes. À partir de la ligne de commande, de Q# blocs-notes Jupyter et de programmes hôtes classiques en Python ou en langage .net.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8e3fa83700417a4ffaf9e3be91796c9e9513b253
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869730"
---
# <a name="ways-to-run-a-no-locq-program"></a>Méthodes d’exécution d’un Q# programme

L’un des principaux atouts du kit de développement Quantum est sa flexibilité sur les plateformes et les environnements de développement.
Toutefois, cela signifie également que Q# les nouveaux utilisateurs peuvent être déconcertés ou submergés par les nombreuses options figurant dans le [Guide d’installation](xref:microsoft.quantum.install).
Sur cette page, nous expliquons ce qui se passe lors de Q# l’exécution d’un programme et comparons les différentes façons dont les utilisateurs peuvent le faire.

Une distinction principale est que Q# peut être exécuté :
- en tant qu’application autonome, où Q# est le seul langage impliqué et le programme est appelé directement. Deux méthodes appartiennent en fait à cette catégorie :
  - l’interface de ligne de commande
  - Q#Blocs-notes Jupyter
- avec un *programme hôte*supplémentaire, écrit en Python ou un langage .net (par exemple, C# ou F #), qui appelle ensuite le programme et peut poursuivre le traitement des résultats retournés.

Pour mieux comprendre ces processus et leurs différences, nous envisageons un Q# programme simple et nous comparons les façons dont il peut être exécuté.

## <a name="basic-no-locq-program"></a>Programme de base Q#

Un programme Quantum de base peut consister à préparer un qubit dans une superposition égale des États $ \ket {0} $ et $ \ket {1} $, à le mesurer et à retourner le résultat, qui sera, de manière aléatoire, l’un de ces deux États avec une probabilité égale.
En effet, ce processus est au cœur du démarrage rapide du [Générateur de nombres aléatoires quantiques](xref:microsoft.quantum.quickstarts.qrng) .

Dans Q# , cette opération est effectuée par le code suivant :

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

Toutefois, ce code seul ne peut pas être exécuté par Q# .
Pour cela, il doit créer le corps d’une [opération](xref:microsoft.quantum.guide.basics#q-operations-and-functions), qui est ensuite exécutée quand elle est appelée---soit directement, soit par une autre opération. Par conséquent, vous pouvez écrire une opération de la forme suivante :
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
Vous avez défini une opération, `MeasureSuperposition` , qui ne prend aucune entrée et retourne une valeur de type [résultat](xref:microsoft.quantum.guide.types).

Alors que les exemples de cette page consistent uniquement en Q# *opérations*, tous les concepts que nous aborderons se rapportent de la même façon aux Q# *fonctions*et, par conséquent, nous les appelons collectivement *callables*. Leurs différences sont présentées dans [ Q# concepts de base : les opérations et les fonctions](xref:microsoft.quantum.guide.basics#q-operations-and-functions)et plus d’informations sur leur définition sont disponibles dans [opérations et fonctions](xref:microsoft.quantum.guide.operationsfunctions).

### <a name="callable-defined-in-a-no-locq-file"></a>Pouvant être appelé dans un Q# fichier

L’appelable est précisément ce qui est appelé et exécuté par Q# .
Toutefois, il faut quelques ajouts pour inclure un `*.qs` Q# fichier complet.

Tous les Q# types et callables (ceux que vous définissez et ceux qui sont intrinsèques au langage) sont définis dans les *espaces de noms*, qui fournissent chacun un nom complet qui peut ensuite être référencé.

Par exemple, les [`H`](xref:microsoft.quantum.intrinsic.h) [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) opérations et se trouvent dans les [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) espaces de noms et (qui font partie des [ Q# bibliothèques standard](xref:microsoft.quantum.qsharplibintro)).
En tant que tels, ils peuvent toujours être appelés par le biais de leurs noms *complets* `Microsoft.Quantum.Intrinsic.H(<qubit>)` et `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` , mais le fait de toujours effectuer cela entraînerait un code très encombré.

Au lieu de cela, `open` les instructions permettent de référencer callables avec un raccourci plus concis, comme nous l’avons fait dans le corps de l’opération ci-dessus.
Le Q# fichier complet contenant notre opération consiste donc à définir notre propre espace de noms, à ouvrir les espaces de noms pour les callables que notre opération utilise, puis à exécuter l’opération suivante :

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> Les espaces de noms peuvent également être dotés d’un *alias* lorsqu’ils sont ouverts, ce qui peut être utile si les noms d’appel/type dans deux espaces de noms sont en conflit.
> Par exemple, nous pourrions utiliser à la place `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` ci-dessus, puis appeler `H` via `NamespaceWithH.H(<qubit>)` .

> [!NOTE]
> La seule exception est l' [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) espace de noms, qui est toujours ouvert automatiquement.
> Par conséquent, callables [`Length`](xref:microsoft.quantum.core.length) peut toujours être utilisé directement.

### <a name="execution-on-target-machines"></a>Exécution sur les ordinateurs cibles

Désormais, le modèle d’exécution générale d’un Q# programme devient clair.

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

Tout d’abord, l’appel spécifique à exécuter a accès à tout autre callables et à tous les types définis dans le même espace de noms.
Elle y accède également à partir de l’une des [ Q# bibliothèques](xref:microsoft.quantum.libraries), mais celles-ci doivent être référencées par le biais de leur nom complet ou de l’utilisation d' `open` instructions décrites ci-dessus.

L’appel à lui-même est ensuite exécuté sur un *[ordinateur cible](xref:microsoft.quantum.machines)*.
Ces machines cibles peuvent être du matériel Quantum réel ou des simulateurs multiples disponibles dans le cadre du QDK.
Dans notre cas, la machine cible la plus utile est une instance du [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` , qui calcule le comportement du programme comme s’il était exécuté sur un ordinateur quantique sans bruit.

Jusqu’à présent, nous avons décrit ce qui se produit lorsqu’un Q# appel spécifique est en cours d’exécution.
Qu’il soit Q# utilisé dans une application autonome ou avec un programme hôte, ce processus général est plus ou moins le même---donc la flexibilité de QDK.
Les différences entre les différentes façons d’appeler dans le kit de développement Quantum s’affichent ainsi dans la *manière dont* cet Q# appel est appelé pour être exécuté, et de quelle manière les résultats sont retournés.
Plus précisément, les différences tournent autour 
1. indiquant l' Q# appelable à exécuter,
2. Comment les arguments pouvant être appelés peuvent être fournis,
3. spécifiant l’ordinateur cible sur lequel l’exécuter et
4. Comment les résultats sont retournés.

Tout d’abord, nous expliquons comment cela s’effectue avec l' Q# application autonome à partir de la ligne de commande, puis passez à l’utilisation des programmes hôtes Python et C#.
Nous nous réservons l’application autonome des Q# blocs-notes Jupyter pour la dernière version, car contrairement aux trois premières, les fonctionnalités principales ne sont pas centrées autour d’un Q# fichier local.

> [!NOTE]
> Bien que nous ne les illustrions pas dans ces exemples, l’une des similitudes entre les méthodes d’exécution est que tous les messages imprimés à partir du Q# programme (à l’aide de [`Message`](xref:microsoft.quantum.intrinsic.message) ou [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) , par exemple) sont généralement imprimés sur la console respective.

## <a name="no-locq-from-the-command-line"></a>Q#à partir de la ligne de commande
L’une des méthodes les plus simples pour commencer à écrire Q# des programmes consiste à éviter d’avoir à vous soucier des fichiers distincts et d’un autre langage.
L’utilisation de Visual Studio Code ou de Visual Studio avec l’extension QDK permet un workflow de travail transparent dans lequel nous exécutons Q# callables à partir d’un seul Q# fichier.

Pour ce faire, nous appellerons finalement l’exécution du programme en entrant
```dotnetcli
dotnet run
```
dans la ligne de commande.
Le flux de travail le plus simple est lorsque l’emplacement du répertoire du terminal est le même que celui du Q# fichier, qui peut être facilement géré avec Q# la modification de fichier à l’aide du terminal intégré dans vs code, par exemple.
Toutefois, la [ `dotnet run` commande](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepte de nombreuses options et le programme peut également être exécuté à partir d’un emplacement différent en fournissant simplement `--project <PATH>` l’emplacement du Q# fichier.


### <a name="add-entry-point-to-no-locq-file"></a>Ajouter un point d’entrée au Q# fichier

La plupart des Q# fichiers contiennent plus d’un appelable. naturellement, nous devons laisser le compilateur savoir *quel* appel peut s’exécuter lorsque nous fournissons la `dotnet run` commande.
Cela s’effectue avec une simple modification du Q# fichier lui-même : 
    - Ajoutez une ligne qui `@EntryPoint()` précède directement l’appelable.

Notre fichier ci-dessus serait donc
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

À présent, un appel de `dotnet run` à partir de la ligne de commande provoque `MeasureSuperposition` l’exécution, et la valeur retournée est ensuite imprimée directement sur le terminal.
Par conséquent, vous verrez ou vous pouvez l' `One` `Zero` Imprimer. 

Notez que cela n’a pas d’importance si vous avez plus de callables défini au-dessous, mais uniquement s' `MeasureSuperposition` exécutera.
En outre, ce n’est pas un problème si votre appelable comprend des [Commentaires de documentation](xref:microsoft.quantum.guide.filestructure#documentation-comments) avant sa déclaration, l' `@EntryPoint()` attribut peut être placé juste au-dessus de lui.

### <a name="callable-arguments"></a>Arguments pouvant être appelés

Jusqu’à présent, nous avons uniquement considéré une opération qui n’accepte aucune entrée.
Supposons que nous voulions effectuer une opération similaire, mais sur plusieurs qubits---le nombre de qui est fourni en tant qu’argument.
Une telle opération peut être écrite sous la forme
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
où la valeur retournée est un tableau des résultats de mesure.
Notez que [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) et [`ForEach`](xref:microsoft.quantum.arrays.foreach) se trouvent dans [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) les [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) espaces de noms et, nécessitant des `open` instructions supplémentaires pour chacun d’entre eux.

Si nous déplaçons l' `@EntryPoint()` attribut pour qu’il précède cette nouvelle opération (Notez qu’il ne peut y avoir qu’une seule ligne dans un fichier), tenter de l’exécuter avec `dotnet run` génère simplement un message d’erreur qui indique les options de ligne de commande supplémentaires requises et comment les exprimer.

Le format général de la ligne de commande est `dotnet run [options]` en réalité, et les arguments pouvant être appelés sont fournis ici.
Dans ce cas, l’argument `n` est manquant et il indique que nous devons fournir l’option `-n <n>` . Pour exécuter `MeasureSuperpositionArray` `n=4` qubits, nous utilisons donc

```dotnetcli
dotnet run -n 4
```

produire une sortie similaire à

```output
[Zero,One,One,One]
```

Ce bien évidemment s’étend à plusieurs arguments.

> [!NOTE]
> Les noms d’arguments définis dans `camelCase` sont légèrement modifiés par le compilateur pour être acceptés en tant qu' Q# entrées. Par exemple, si au lieu de `n` , nous avons utilisé le nom `numQubits` ci-dessus, cette entrée est fournie dans la ligne de commande via à la `--num-qubits 4` place de `-n 4` .

Le message d’erreur fournit également d’autres options qui peuvent être utilisées, notamment la modification de l’ordinateur cible.

### <a name="different-target-machines"></a>Ordinateurs cibles différents

Comme les sorties de nos opérations jusqu’à présent ont été les résultats attendus de leur action sur des qubits réels, il est clair que l’ordinateur cible par défaut à partir de la ligne de commande est le simulateur quauntum en état complet, `QuantumSimulator` .
Toutefois, nous pouvons demander à callables de s’exécuter sur un ordinateur cible spécifique avec l’option `--simulator` (ou le raccourci `-s` ).

Par exemple, nous pourrions l’exécuter sur [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

La sortie imprimée est alors

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

Pour plus d’informations sur ce que ces métriques indiquent, consultez [estimation des ressources : mesures signalées](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).

### <a name="command-line-execution-summary"></a>Résumé d’exécution de la ligne de commande
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a>Non- Q# `dotnet run` options

Comme nous l’avons brièvement mentionné plus haut avec l' `--project` option, la [ `dotnet run` commande](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepte également des options non liées aux Q# arguments pouvant être appelés.
Si vous fournissez les deux types d’options, les `dotnet` options spécifiques à doivent être fournies en premier, suivies d’un délimiteur, puis des `--` Q# options spécifiques à.
Par exemple, la spécification d’un chemin d’accès avec un nombre qubits pour l’opération ci-dessus est exécutée via `dotnet run --project <PATH> -- -n <n>` .

## <a name="no-locq-with-host-programs"></a>Q#avec les programmes hôtes

Avec notre Q# fichier en main, une alternative à l’appel d’une opération ou d’une fonction directement à partir de la ligne de commande consiste à utiliser un *programme hôte* dans un autre langage classique. Plus précisément, cela peut être fait avec Python ou un langage .NET tel que C# ou F # (par souci de concision, nous allons uniquement détailler C#).
Un peu plus de configuration est nécessaire pour activer l’interopérabilité, mais ces informations sont disponibles dans les [guides d’installation](xref:microsoft.quantum.install).

Pour résumer, la situation comprend maintenant un fichier programme hôte (par exemple, `*.py` ou `*.cs` ) au même emplacement que notre Q# fichier.
C’est maintenant le programme *hôte* qui est exécuté, et au cours de son exécution, il peut appeler des Q# opérations et des fonctions spécifiques à partir du Q# fichier.
Le noyau de l’interopérabilité est basé sur le Q# compilateur qui rend le contenu du Q# fichier accessible au programme hôte afin qu’il puisse être appelé.

L’un des principaux avantages de l’utilisation d’un programme hôte est que les données classiques renvoyées par le Q# programme peuvent ensuite être traitées plus en détail dans la langue de l’hôte.
Cela peut se composer d’un traitement de données avancé (par exemple, un processus qui ne peut pas être effectué en interne dans Q# ), puis de l’appel d' Q# actions supplémentaires en fonction de ces résultats, ou d’une opération aussi simple que le traçage des Q# résultats.

Le schéma général est présenté ici et nous aborderons les implémentations spécifiques de Python et C# ci-dessous. Vous trouverez un exemple d’utilisation d’un programme hôte F # dans les [exemples d’interopérabilité .net](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> L' `@EntryPoint()` attribut utilisé pour les Q# applications de ligne de commande ne peut pas être utilisé avec les programmes hôtes.
> Une erreur sera déclenchée si elle est présente dans le Q# fichier appelé par un hôte. 

Pour fonctionner avec différents programmes hôtes, aucune modification n’est requise dans un `*.qs` Q# fichier.
Les implémentations de programmes hôtes suivantes fonctionnent toutes avec le même Q# fichier :

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

Sélectionnez l’onglet correspondant à la langue de votre hôte qui vous intéresse.

### <a name="python"></a>[Python](#tab/tabid-python)
Un programme hôte Python est construit comme suit :
1. Importez le `qsharp` module, qui inscrit le chargeur de module pour l' Q# interopérabilité. 
    Cela permet Q# d’afficher les espaces de noms en tant que modules python, à partir desquels nous pouvons importer des Q# callables.
    Notez qu’il ne s’agit techniquement pas des Q# callables qui sont importés, mais plutôt des stubs Python qui permettent de les appeler.
    Ceux-ci se comportent ensuite comme des objets de classes Python, sur lesquels nous utilisons des méthodes pour spécifier les ordinateurs cibles vers lesquels envoyer l’opération pour l’exécution.

2. Importez ces Q# callables que nous appellera directement---dans ce cas, `MeasureSuperposition` et `MeasureSuperpositionArray` .
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    Une fois le `qsharp` module importé, vous pouvez également importer des callables directement à partir des espaces de noms de la Q# bibliothèque.

3. Parmi tout autre code Python, vous pouvez maintenant appeler ces callables sur des ordinateurs cibles spécifiques et leur attribuer des retours à des variables (s’ils retournent une valeur) pour une utilisation ultérieure.

#### <a name="specifying-target-machines"></a>Spécification d’ordinateurs cibles
L’appel d’une opération à exécuter sur un ordinateur cible spécifique s’effectue à l’aide de différentes méthodes Python sur l’objet importé.
Par exemple, `.simulate(<args>)` utilise `QuantumSimulator` pour exécuter l’opération, tandis que le `.estimate_resources(<args>)` fait sur le `ResourcesEstimator` .

#### <a name="passing-inputs-to-q"></a>Passage d’entrées à Q\#
Les arguments de l' Q# appelable doivent être fournis sous la forme d’un argument de mot clé, où le mot clé est le nom de l’argument dans la Q# définition pouvant être appelée.
Autrement dit, `MeasureSuperpositionArray.simulate(n=4)` est valide, alors qu' `MeasureSuperpositionArray.simulate(4)` une erreur est levée.

Par conséquent, le programme hôte python 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

génère une sortie semblable à la suivante :

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[C#](#tab/tabid-csharp)

Un programme hôte C# possède plusieurs composants et fonctionne très étroitement avec certains composants du QDK, tels que les simulateurs, qui sont eux-mêmes basés sur C#.

Le Q# compilateur fonctionne ici en générant un espace de noms C# nommé de façon équivalente à partir de l' Q# espace de noms dans notre Q# fichier.
Il génère davantage une classe C# nommée de manière équivalente pour chacun des Q# callables ou types définis dans celui-ci.

Tout d’abord, nous faisons en sorte que toutes les classes utilisées dans notre programme hôte soient disponibles avec des `using` instructions, qui sont à peu près analogue aux `open` instructions de notre Q# fichier :

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

Ensuite, nous déclarons notre espace de noms C#, quelques autres bits et éléments (consultez le bloc de code complet ci-dessous), puis toute programmation classique que nous aimerions (par exemple, le calcul d’arguments pour le Q# callables).
Ce dernier n’est pas nécessaire dans notre cas, mais un exemple d’utilisation de ce type est disponible dans l' [exemple d’interopérabilité .net](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

#### <a name="target-machines"></a>Ordinateurs cibles

En revenons à Q# , nous devons créer une instance de n’importe quel ordinateur cible sur lequel nous allons exécuter nos opérations.

```csharp
            using var sim = new QuantumSimulator();
```

L’utilisation d’autres ordinateurs cibles est aussi simple que l’instanciation d’un autre ordinateur, bien que la manière de procéder et le traitement des retours puissent être légèrement différents.
Par souci de concision, nous nous contenterons pour l' [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) instant, et inclurons les [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [ci-dessous](#including-the-resources-estimator).

Chaque classe C# générée à partir des Q# opérations a une `Run` méthode, dont le premier argument doit être l’instance de machine cible.
Ainsi, pour exécuter `MeasureSuperposition` sur le `QuantumSimulator` , nous utilisons `MeasureSuperposition.Run(sim)` .
Les résultats retournés peuvent ensuite être affectés à des variables en C# :

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> La `Run` méthode est exécutée de façon asynchrone, car ce sera le cas pour le matériel Quantum réel. par conséquent, le `await` mot clé bloque l’exécution jusqu’à ce que la tâche se termine.

Si l' Q# appelable n’a pas de retour (c’est-à-dire qu’il a un type de retour `Unit` ), l’exécution peut toujours être effectuée de la même manière sans l’assigner à une variable.
Dans ce cas, la ligne entière se compose simplement de 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>Arguments

Tous les arguments de l' Q# appelable sont simplement passés en tant qu’arguments supplémentaires après l’ordinateur cible.
Par conséquent, les résultats de `MeasureSuperpositionArray` sur `n=4` qubits seraient récupérés via 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

Un programme hôte C# complet peut donc ressembler à

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

À l’emplacement du fichier C#, le programme hôte peut être exécuté à partir de la ligne de commande en entrant
```dotnetcli
dotnet run
```
dans ce cas, vous verrez une sortie écrite dans la console, similaire à 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> En raison de l’interopérabilité du compilateur avec les espaces de noms, nous pourrions également rendre notre Q# callables disponible sans l' `using NamespaceName;` instruction et en faisant simplement correspondre le titre de l’espace de noms C# à celui-ci.
> Autrement dit, en remplaçant `namespace host` par `namespace NamespaceName` .

#### <a name="including-the-resources-estimator"></a>Inclusion de l’estimateur de ressources

Le [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requiert une implémentation légèrement différente pour récupérer la sortie.

Tout d’abord, au lieu de les instancier en tant que variable avec une `using` instruction (comme nous le faisons avec `QuantumSimulator` ), nous instancions plus directement les objets de la classe via

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

Notez qu’au lieu d’utiliser un simulateur cible unique pour plusieurs Q# opérations, nous avons instancié un pour chaque. Cela est dû au fait que les objets eux-mêmes sont modifiés lorsqu’ils sont utilisés en tant qu’ordinateurs cibles, et que leurs résultats peuvent ensuite être récupérés ultérieurement avec la méthode de classe `.ToTSV()` .

Pour exécuter les opérations sur les estimateurs de ressources, nous utilisons

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
puis, récupérez les résultats sous forme de valeurs séparées par des tabulations (TSV) avec `estimatorSingleQ.ToTSV()` et `estimatorMultiQ.ToTSV()` .

Ainsi, un programme hôte C# complet qui utilise à la fois le `QuantumSimulator` et `ResourcesEstimator` peut prendre la forme suivante :

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


ce qui donne une sortie similaire à

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="no-locq-jupyter-notebooks"></a>Q#Blocs-notes Jupyter
Q#Les blocs-notes Jupyter utilisent le Q# noyau I, qui vous permet de définir, compiler et exécuter des Q# callables dans un seul bloc-notes---à côté des instructions, des notes et d’autres contenus.
Cela signifie que, bien qu’il soit possible d’importer et d’utiliser le contenu de `*.qs` Q# fichiers, ils ne sont pas nécessaires dans le modèle d’exécution.

Ici, nous allons expliquer en détail comment exécuter les Q# opérations définies ci-dessus, mais une introduction plus étendue à l’utilisation des Q# blocs-notes Jupyter est fournie à l' [Introduction à Q# et aux blocs-notes Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).

### <a name="defining-operations"></a>Définition des opérations

Dans un Q# Jupyter Notebook, vous entrez du Q# code comme nous le feriez à l’intérieur de l’espace de noms d’un Q# fichier.

Nous pouvons donc activer l’accès à callables à partir des [ Q# bibliothèques standard](xref:microsoft.quantum.qsharplibintro) avec des `open` instructions pour leurs espaces de noms respectifs.
Lors de l’exécution d’une cellule avec une telle instruction, les définitions de ces espaces de noms sont disponibles dans l’ensemble de l’espace de travail.

> [!NOTE]
> Callables de [Microsoft. Quantum. Intrinsic](xref:microsoft.quantum.intrinsic) et [Microsoft. Quantum. Canon](xref:microsoft.quantum.canon) (par exemple [`H`](xref:microsoft.quantum.intrinsic.h) , et [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) ) sont automatiquement disponibles pour les opérations définies dans les cellules des Q# blocs-notes Jupyter.
> Toutefois, cela n’est pas le cas pour le code provenant de Q# fichiers sources externes (processus présenté à l' [Introduction à Q# et les blocs-notes Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)). 
> 

De même, la définition d’opérations requiert uniquement l’écriture du Q# code et l’exécution de la cellule.

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

La sortie répertorie ensuite ces opérations, qui peuvent ensuite être appelées à partir de cellules futures.

### <a name="target-machines"></a>Ordinateurs cibles

Les fonctionnalités permettant d’exécuter des opérations sur des ordinateurs cibles spécifiques sont fournies via les [ Q# commandes magiques](xref:microsoft.quantum.guide.quickref.iqsharp).
Par exemple, utilise `%simulate` le `QuantumSimulator` et `%estimate` utilise les `ResourcesEstimator` éléments suivants :

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a>Passage d’entrées aux fonctions et opérations

Actuellement, les commandes Magic d’exécution peuvent uniquement être utilisées avec des opérations qui ne prennent pas d’arguments. Ainsi, pour exécuter `MeasureSuperpositionArray` , nous devons définir une opération « wrapper » qui appelle ensuite l’opération avec les arguments :

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

Cette opération peut bien entendu être utilisée de la même façon avec `%estimate` et d’autres commandes d’exécution.
