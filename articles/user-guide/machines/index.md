---
title: Simulateurs quantiques et programmes Q#
description: Décrit les simulateurs quantiques qui sont disponibles en tant qu’ordinateurs cibles pour les programmes Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 77401ca3642b89d708f338f852dc60bf7346b87b
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868302"
---
# <a name="quantum-simulators"></a>Simulateurs quantiques

Les simulateurs quantiques sont des programmes logiciels que vous pouvez exécuter sur des ordinateurs classiques et qui peuvent être utilisés comme des *ordinateurs cibles* pour les programmes Q#. Vous pouvez ainsi exécuter et tester des programmes quantiques dans un environnement capable de prédire le comportement des qubits en réponse à différentes opérations. Cet article explique quels simulateurs quantiques sont inclus dans le kit de développement Quantum (QDK). En outre, il indique les différentes méthodes permettant de passer un programme Q# aux simulateurs quantiques, par exemple via la ligne de commande ou à l’aide d’un code de pilote écrit dans un langage classique.  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a>Les simulateurs quantiques du kit de développement Quantum (QDK)

Le simulateur quantique est chargé de fournir des implémentations de primitives quantiques pour un algorithme. Cela comprend les opérations primitives telles que `H`, `CNOT` et `Measure`, ainsi que la gestion et le suivi des qubits. Le QDK comprend différentes classes de simulateurs quantiques, qui représentent différents modèles d’exécution pour un même algorithme quantique. 


Chaque type de simulateur quantique peut fournir des implémentations différentes de ces primitives. Par exemple, le [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator) exécute l’algorithme quantique en simulant entièrement le [vecteur d’état quantique](xref:microsoft.quantum.glossary#quantum-state), alors que le [simulateur de traces d’ordinateur quantiques](xref:microsoft.quantum.machines.qc-trace-simulator.intro) ne prend pas du tout en compte l’état quantique réel. Au lieu de cela, il permet de suivre l’utilisation des portes, des qubits et d’autres ressources de l’algorithme.

### <a name="quantum-machine-classes"></a>Classes d’ordinateurs quantiques

À l’avenir, le QDK définira des classes d’ordinateurs quantiques supplémentaires permettant de prendre en charge d’autres types de simulation, ainsi que leur exécution sur du matériel quantique. Permettre à l’algorithme de rester constant tout en modifiant l’implémentation de la machine sous-jacente facilite le test et le débogage d’un algorithme en simulation, puis son exécution sur du matériel réel avec la certitude que l’algorithme n’a pas changé.

Le QDK comprend plusieurs classes d’ordinateurs quantiques, toutes définies dans l’espace de noms `Microsoft.Quantum.Simulation.Simulators`.

|Simulateur |Classe|Description|
|-----|------|---|
|[Simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | Exécute et débogue des algorithmes quantiques. Limité à environ 30 qubits. |
|[Estimateur de ressources simple](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | Permet une analyse simple des ressources nécessaires à l’exécution d’un algorithme quantique. Prend en charge des milliers de qubits.|
|[Estimateur de ressources basé sur les traces](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |Permet une analyse avancée des consommations de ressources pour l’ensemble du graphe d’appel de l’algorithme. Prend en charge des milliers de qubits.|
|[Simulateur Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |Simule des algorithmes quantiques qui sont limités à `X`, `CNOT`, ainsi qu’aux opérations quantiques `X` multicontrôleurs. Prend en charge un million de qubits. |

## <a name="invoking-the-quantum-simulator"></a>Appel du simulateur quantique

La rubrique [Méthodes d’exécution d’un programme Q#](xref:microsoft.quantum.guide.host-programs) décrit les trois méthodes qui permettent de passer du code Q# au simulateur quantique : 

* À l’aide de la ligne de commande
* À l’aide d’un programme hôte Python
* À l’aide d’un programme hôte C#

Les machines quantiques sont des instances de classes .NET normales. Elles sont donc créées en invoquant leur constructeur, comme n’importe quelle classe .NET. La procédure à suivre dépend de la façon dont vous exécutez le programme Q#.

## <a name="next-steps"></a>Étapes suivantes

* Pour plus d’informations sur l’appel des ordinateurs cibles pour les programmes Q# dans les différents environnements, consultez [Méthodes d’exécution d’un programme Q#](xref:microsoft.quantum.guide.host-programs).
