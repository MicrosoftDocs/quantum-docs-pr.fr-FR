---
title: Estimation des ressources de Quantum-Kit de développement quantique
description: Découvrez l’estimateur des ressources Microsoft QDK, qui estime les ressources requises pour exécuter une instance donnée d’une Q# opération sur un ordinateur Quantum.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: d5338eb740716d9d7f408703347f572688bbccb2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868183"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Estimation des ressources du kit de développement quantique (QDK)

Comme son nom l’indique, la `ResourcesEstimator` classe estime les ressources requises pour exécuter une instance donnée d’une Q# opération sur un ordinateur Quantum. Pour ce faire, il exécute l’opération Quantum sans simuler réellement l’état d’un ordinateur quantique. pour cette raison, elle estime les ressources pour les Q# opérations qui utilisent des milliers de qubits, à condition que la partie classique du code s’exécute dans un délai raisonnable.

L’estimateur de ressources s’appuie sur le [simulateur de traces Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro), qui fournit un ensemble plus riche de métriques et d’outils pour déboguer les Q# programmes.

## <a name="invoking-and-running-the-resources-estimator"></a>Appel et exécution de l’estimateur de ressources

Vous pouvez utiliser l’estimateur de ressources pour exécuter toute Q# opération. Pour plus d’informations, consultez [méthodes d’exécution d’un Q# programme](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>Appel de l’estimateur de ressources à partir de C # 

Comme pour les autres ordinateurs cibles, vous devez d’abord créer une instance de la classe `ResourceEstimator`, puis la passer en tant que premier paramètre de la méthode `Run` d’une opération.

Notez que, contrairement à la classe `QuantumSimulator`, la classe `ResourceEstimator` n’implémente pas l’interface <xref:System.IDisposable>. Vous n’avez donc pas besoin de la placer dans une instruction `using`.

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

Comme le montre l’exemple, `ResourcesEstimator` fournit la `ToTSV()` méthode, qui génère une table avec des valeurs séparées par des tabulations (TSV). Vous pouvez enregistrer la table dans un fichier ou l’afficher dans la console pour l’analyse. Voici un exemple de sortie du programme précédent :

```output
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
> Une `ResourcesEstimator` instance ne réinitialise pas ses calculs à chaque exécution. Si vous utilisez la même instance pour exécuter une autre opération, elle agrège les nouveaux résultats avec les résultats existants. Si vous devez réinitialiser les calculs entre les exécutions, créez une nouvelle instance pour chaque exécution.

### <a name="invoking-the-resources-estimator-from-python"></a>Appel de l’estimateur de ressources à partir de Python

Utilisez la méthode [estimate_resources ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) à partir de la bibliothèque Python avec l’opération importée Q# :

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Appel de l’estimateur de ressources à partir de la ligne de commande

Quand vous exécutez un Q# programme à partir de la ligne de commande, utilisez le paramètre **--simulateur** (ou **-s** raccourci) pour spécifier l' `ResourcesEstimator` ordinateur cible. La commande suivante exécute un programme à l’aide de l’estimateur de ressources : 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Appel de l’estimateur de ressources des blocs-notes Juptyer

Utilisez la Q# commande magique [% estimation](xref:microsoft.quantum.iqsharp.magic-ref.simulate) pour exécuter l' Q# opération.

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>Récupération par programmation des données estimées

En plus d’une table TSV, vous pouvez récupérer par programmation les ressources estimées lors de l’exécution via la `Data` propriété de l’estimateur de ressources. La `Data` propriété fournit une `System.DataTable` instance de avec deux colonnes : `Metric` et `Sum` , indexées par les noms de métriques.

Le code suivant montre comment récupérer et imprimer le nombre total d' `QubitClifford` opérations, `T` et `CNOT` utilisées par une Q# opération :

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

L’estimateur de ressources effectue le suivi des mesures suivantes :

|Métrique|Description|
|----|----|
|__CNOT__    |Nombre d’exécutions d' `CNOT` opérations (également appelées opérations Pauli X contrôlées).|
|__QubitClifford__ |Nombre d’exécutions d’opérations qubit Clifford et Pauli uniques.|
|__mesure__    |Nombre d’exécutions de mesures.  |
|__R__    |Nombre d’exécutions de rotations à qubit unique, à l’exception des `T` opérations Clifford et Pauli.  |
|__T__    |Nombre d’exécutions d' `T` opérations et de leurs conjugués, y compris les `T` opérations, T_x = H. T. H et T_y = Hy. t. hy.  |
|__Profondeur__|Limite inférieure de la profondeur du circuit Quantum exécutée par l' Q# opération. Par défaut, la mesure de profondeur compte uniquement les `T` portes. Pour plus d’informations, consultez [compteur de profondeur](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Width__    |Limite inférieure pour le nombre maximal de qubits allouées pendant l’exécution de l' Q# opération. Il se peut qu’il ne soit pas possible d’atteindre simultanément les limites inférieures de __profondeur__ et de __largeur__ .  |
|__BorrowedWidth__    |Nombre maximal de qubits empruntés dans l' Q# opération.  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>Calcul de la probabilité des résultats de mesure

Vous pouvez utiliser <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> à partir de l' <xref:microsoft.quantum.diagnostics> espace de noms pour fournir des informations sur la probabilité attendue d’une opération de mesure. Pour plus d’informations, consultez [Quantum trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Voir aussi

- [Simulateur de traces Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Simulateur Toffoli quantique](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulateur d’état complet quantique](xref:microsoft.quantum.machines.full-state-simulator) 