---
title: Simulateurs quantiques et pilotes classiques | Microsoft Docs
description: 'Décrit comment utiliser les simulateurs quantiques avec un langage .NET de calcul classique, en général C# ou Q #.'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 5ac79280669ae0acfe993a1c2ae1c069b0c01848
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035116"
---
# <a name="classical-drivers-and-machines"></a>Pilotes et machines classiques

## <a name="what-youll-learn"></a>Ce que vous allez apprendre

> [!div class="checklist"]
> * Mode d’exécution des algorithmes quantiques
> * Les simulateurs quantiques inclus dans cette version
> * Comment écrire un pilote C# pour votre algorithme quantique

## <a name="the-quantum-development-kit-execution-model"></a>Modèle d’exécution du Quantum Development Kit

Dans [Écriture d’un programme quantique](xref:microsoft.quantum.write-program), nous avons exécuté notre algorithme quantique en passant un objet `QuantumSimulator` dans la méthode `Run` de la classe de l’algorithme.
La classe `QuantumSimulator` exécute l’algorithme quantique en simulant complètement le vecteur d’état quantique, ce qui est parfait pour l’exécution et le test de `Teleport`.
Pour plus d’informations sur les vecteurs d’état quantique, consultez le [guide des concepts](xref:microsoft.quantum.concepts.intro).

D’autres machines cibles peuvent être utilisées pour exécuter un algorithme quantique.
La machine est chargée de fournir des implémentations de primitives quantiques pour l’algorithme.
Cela comprend les opérations primitives telles que H, CNOT et Mesure, ainsi que la gestion et le suivi des qubits.
Différentes classes de machines quantiques représentent des modèles d’exécution différents pour le même algorithme quantique.

Chaque type de machine quantique peut fournir des implémentations différentes de ces primitives.
Par exemple, le simulateur de traces d’ordinateur quantique inclus dans le kit de développement ne réalise aucune simulation.
Au lieu de cela, il permet de suivre l’utilisation des portes, des qubits et d’autres ressources de l’algorithme.

### <a name="quantum-machines"></a>Machines quantiques

À l’avenir, nous définirons des classes de machines quantiques supplémentaires pour prendre en charge d’autres types de simulation et leur exécution sur des ordinateurs quantiques topologiques.
Permettre à l’algorithme de rester constant tout en modifiant l’implémentation de la machine sous-jacente facilite le test et le débogage d’un algorithme en simulation, puis son exécution sur du matériel réel avec la certitude que l’algorithme n’a pas changé.

### <a name="whats-included-in-this-release"></a>Éléments inclus dans cette version

Cette version du kit de développement quantique comprend plusieurs classes de machines quantiques.
Toutes sont définies dans l’espace de noms `Microsoft.Quantum.Simulation.Simulators`.

* Un [simulateur vectoriel d’état complet](xref:microsoft.quantum.machines.full-state-simulator), classe `QuantumSimulator`.
* Un [estimateur de ressources simple](xref:microsoft.quantum.machines.resources-estimator), classe `ResourcesEstimator`, qui permet une analyse de haut niveau des ressources nécessaires à l’exécution d’un algorithme quantique.
* Un [estimateur de ressources basé sur les traces](xref:microsoft.quantum.machines.qc-trace-simulator.intro), classe `QCTraceSimulator`, qui permet une analyse avancée des consommations de ressources pour l’ensemble du graphique d’appel de l’algorithme.
* Un [simulateur Toffoli](xref:microsoft.quantum.machines.toffoli-simulator), classe `ToffoliSimulator`.

## <a name="writing-a-classical-driver-program"></a>Écriture d’un programme pilote classique

Dans [Écriture d’un programme quantique](xref:microsoft.quantum.write-program), nous avons écrit un pilote en C# simple pour notre algorithme de téléportation. Un pilote en C# a quatre objectifs principaux :

* Construction de la machine cible
* Calcul de tous les arguments requis pour l’algorithme quantique
* Exécution de l’algorithme quantique à l’aide du simulateur
* Traitement du résultat de l’opération

Ici, nous aborderons chaque étape plus en détail.

### <a name="constructing-the-target-machine"></a>Construction de la machine cible

Les machines quantiques sont des instances de classes .NET normales. Elles sont donc créées en invoquant leur constructeur, comme n’importe quelle classe .NET.
Certains simulateurs, y compris le `QuantumSimulator`, implémentent l’interface <xref:System.IDisposable?displayProperty=nameWithType> .NET et doivent donc être incluses dans une instruction `using` en C#.

### <a name="computing-arguments-for-the-algorithm"></a>Calcul des arguments pour l’algorithme

Dans notre exemple `Teleport`, nous avons calculé quelques arguments relativement artificiels à transmettre à notre algorithme quantique.
Cependant, l’algorithme quantique requiert plus généralement des données significatives et il est plus facile de les fournir à partir du pilote classique.

Par exemple, lors de simulations chimiques, l’algorithme quantique requiert une grande table d’intégrales d’interactions orbitales moléculaires.
En général, elles sont lues à partir d’un fichier fourni lors de l’exécution de l’algorithme.
Comme Q# ne dispose pas d’un mécanisme permettant d’accéder au système de fichiers, la meilleure solution est que ce type de données soit collecté par le pilote classique, puis transmis à la méthode `Run` de l’algorithme quantique.

Le pilote classique joue également un rôle clé dans le cas des méthodes variationnelles.
Dans cette classe d’algorithmes, un état quantique est préparé à partir de certains paramètres classiques, et cet état est utilisé pour calculer une valeur intéressante.
Les paramètres sont ajustés en fonction d’un certain type d’algorithme d’escalade ou d’apprentissage automatique et l’algorithme quantique fonctionne à nouveau.
Pour ces algorithmes, l’algorithme d’escalade est le mieux implémenté comme fonction purement classique appelée par le pilote classique. Les résultats de l’escalade sont ensuite transmis à la prochaine exécution de l’algorithme quantique.

### <a name="running-the-quantum-algorithm"></a>Exécution de l’algorithme quantique

Cette partie est généralement très simple.
Chaque opération Q# est compilée dans une classe qui fournit une méthode `Run` statique.
Les arguments de cette méthode sont fournis par le tuple d’argument aplati de l’opération elle-même, plus un premier argument supplémentaire qui est le simulateur servant à l’exécution. Pour une opération qui attend le tuple nommé de type `(a: String, (b: Double, c: Double))`, son équivalent aplati est de type `(String a, Double b, Double c)`.


Il existe quelques subtilités lors du passage d’arguments à une méthode `Run` :

* Les tableaux doivent être inclus dans un objet `Microsoft.Quantum.Simulation.Core.QArray<T>`.
    Une classe `QArray` a un constructeur qui peut prendre n’importe quelle collection ordonnée (`IEnumerable<T>`) d’objets appropriés.
* Le tuple vide, `()` en Q#, est représenté par `QVoid.Instance` en C#.
* Les tuples non vides sont représentés sous forme d’instances `ValueType` .NET.
* Les types définis par l’utilisateur Q# sont passés comme type de base.
* Pour passer une opération ou une fonction à une méthode `Run`, vous devez obtenir une instance de la classe de l’opération ou de la fonction à l’aide de la méthode `Get<>` du simulateur.

### <a name="processing-the-results"></a>Traitement des résultats

Les résultats de l’algorithme quantique sont retournés à partir de la méthode `Run`.
La méthode `Run` s’exécute de façon asynchrone et retourne par conséquent une instance de <xref:System.Threading.Tasks.Task`1>.
Il existe plusieurs façons d’obtenir les résultats de l’opération réelle. La méthode la plus simple consiste à utiliser la [propriété `Result`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result) de `Task` :

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
mais d’autres techniques, telles que l’utilisation de la [méthode `Wait`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait)ou du [mot clé `await`](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) en C#, fonctionnent également.

Comme avec les arguments, les tuples Q# sont représentés par des instances `ValueTuple` et les tableaux Q# sont représentés par des instances `QArray`.
Les types définis par l’utilisateur sont retournés comme types de base.
Le tuple vide, `()`, est retourné en tant qu’instance de la classe `QVoid`.

De nombreux algorithmes quantiques nécessitent un post-traitement important pour en extraire des réponses utiles.
Par exemple, la partie quantique de l’algorithme de Shor n’est que le début d’un calcul qui recherche les facteurs d’un nombre.

Dans la plupart des cas, il est plus simple et plus facile d’effectuer ce type de post-traitement dans le pilote classique.
Seul le pilote classique peut rapporter les résultats à l’utilisateur ou les écrire sur le disque.
Le pilote classique aura accès à des bibliothèques analytiques et à d’autres fonctions mathématiques qui ne sont pas exposées en Q#.


## <a name="failures"></a>Échecs

Lorsque l’instruction `fail` en Q# est atteinte pendant l’exécution d’une opération, une `ExecutionFailException` est levée.

En raison de l’utilisation de `System.Task` dans la méthode `Run`, l’exception levée à la suite d’une instruction `fail` sera incluse dans une `System.AggregateException`.
Pour trouver la raison réelle de l’échec, vous devez itérer dans le `AggregateException` 
`InnerExceptions`, par exemple :

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a>Autres langages classiques de programmation

Bien que les exemples que nous avons fournis soient en C#, F# et Python, le Quantum Development Kit prend également en charge l’écriture de programmes hôtes classiques dans d’autres langages informatiques.
Par exemple, si vous souhaitez écrire un programme hôte en Visual Basic, [il devrait parfaitement fonctionner](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).
