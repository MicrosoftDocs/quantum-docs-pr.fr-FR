---
title: Estimateur des ressources du kit de développement Quantum
description: 'En savoir plus sur l’estimateur de ressources, qui estime les ressources requises pour exécuter une instance donnée d’une opération Q # sur un ordinateur Quantum.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: b0c800c3946d2e4ba4457127fb9495dc9dcf2934
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630133"
---
# <a name="the-resources-estimator-target-machine"></a>Ordinateur cible de l’estimateur de ressources

Comme son nom l’indique, le `ResourcesEstimator` estime les ressources requises pour exécuter une instance donnée d’une opération Q # sur un ordinateur Quantum.
Pour ce faire, il exécute l’opération Quantum sans simuler réellement l’état d’un ordinateur quantique. pour cette raison, il peut estimer des ressources pour les opérations Q # qui utilisent des milliers de qubits, si la partie classique du code peut être exécutée dans un délai raisonnable.

## <a name="usage"></a>Usage

Le `ResourcesEstimator` n’est qu’un autre type d’ordinateur cible. il peut donc être utilisé pour exécuter n’importe quelle opération Q #. 

Comme les autres ordinateurs cibles, pour l’utiliser sur un programme hôte C#, créez une instance et transmettez-la en tant que premier paramètre de la méthode de l’opération `Run` :

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

Comme le montre l’exemple, le `ResourcesEstimator` fournit une `ToTSV()` méthode pour générer une table avec des valeurs séparées par des tabulations (TSV) qui peuvent être enregistrées dans un fichier ou écrites dans la console pour l’analyse. La sortie du programme ci-dessus doit ressembler à ceci :

```Output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> Le `ResourcesEstimator` ne réinitialise pas ses calculs à chaque exécution, si la même instance est utilisée pour exécuter une autre opération, il conserve le nombre d’agrégations en plus des résultats existants.
> Si vous devez réinitialiser les calculs entre les exécutions, créez une nouvelle instance pour chaque exécution.


## <a name="programmatically-retrieving-the-estimated-data"></a>Récupération par programmation des données estimées

En plus d’une table TSV, les ressources estimées peuvent être récupérées par programme par le biais de la `ResourcesEstimator` `Data` propriété de. `Data`fournit une `System.DataTable` instance de avec deux colonnes : `Metric` et `Sum` , indexées par les noms de métriques.

Le code suivant montre comment récupérer et imprimer le nombre total de `QubitClifford` , `T` ainsi que les `CNOT` portes utilisées par une opération Q # :

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a>Métriques signalées

Voici la liste des métriques estimées par `ResourcesEstimator` :

* __Cnotin__: le nombre de portes cnotin (également appelées portes Pauli X contrôlées) exécutées.
* __QubitClifford__: nombre de toutes les passerelles qubit Clifford et Pauli exécutées.
* __Mesure__: nombre de mesures exécutées.
* __R__: nombre de rotations qubit uniques exécutées, à l’exception des portes T, Clifford et Pauli.
* __T__: le nombre de portes t et leurs conjugués, y compris la porte t, T_x = H. T. H et T_y = Hy. t. HY, exécutés.
* __Profondeur__: profondeur du circuit Quantum exécuté par l’opération Q #. Par défaut, seules les portes T sont comptées en profondeur. pour plus d’informations, consultez [compteur de profondeur](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .
* __Width__: nombre maximal de qubits alloués lors de l’exécution de l’opération Q #.
* __BorrowedWidth__: nombre maximal de qubits empruntés à l’intérieur de l’opération Q #.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Génération de la probabilité des résultats de mesure

<xref:microsoft.quantum.intrinsic.assertprob>à partir de l' <xref:microsoft.quantum.intrinsic> espace de noms peut être utilisé pour fournir des informations sur la probabilité attendue d’une mesure pour aider à piloter l’exécution du programme Q #. L'exemple suivant illustre ce mécanisme :

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

Quand le `ResourcesEstimator` rencontre, `AssertProb` il enregistre cette mesure `PauliZ` sur `source` et `q` doit recevoir un résultat de `Zero` avec une probabilité de 0,5. Lorsqu’il est exécuté `M` ultérieurement, il trouve les valeurs enregistrées des probabilités de résultat et `M` retourne `Zero` ou avec la `One` probabilité 0,5.


## <a name="see-also"></a>Voir aussi

Le `ResourcesEstimator` repose sur le [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Computer trace, qui fournit un ensemble plus riche de métriques, la possibilité de rapporter des métriques sur le graphique d’appel complet et des fonctionnalités telles que l' [outil de vérification des entrées distinctes](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) pour faciliter la détection des bogues sur les programmes Q #. Pour plus d’informations, consultez la documentation de [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .

