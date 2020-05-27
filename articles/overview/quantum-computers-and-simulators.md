---
title: Ordinateurs quantiques et simulateurs quantiques
description: Découvrez ce qu’est le matériel quantique, ce que sont les simulateurs quantiques et comment fonctionnent les opérations quantiques.
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.simulators
ms.openlocfilehash: 04f90e9f88cf17259f96532617ef6f092b56b859
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430745"
---
# <a name="quantum-computers-and-quantum-simulators"></a>Ordinateurs quantiques et simulateurs quantiques

Les ordinateurs quantiques ne sont encore qu’au début de leur développement. Le matériel quantique et sa maintenance ont un coût élevé, et la plupart des systèmes se trouvent dans les universités et les laboratoires de recherche. Cette technologie est néanmoins en plein progrès, et certains systèmes sont déjà disponibles publiquement en accès limité.

Les simulateurs quantiques sont des programmes logiciels que vous pouvez exécuter sur des ordinateurs classiques afin d’utiliser et de tester des programmes quantiques dans un environnement capable de prédire le comportement des qubits en réponse à différentes opérations.

## <a name="quantum-hardware"></a>Matériel quantique

Un ordinateur quantique se compose de trois parties principales : une unité qui héberge les qubits, une méthode qui transmet les signaux aux qubits, et un ordinateur classique qui exécute un programme et envoie des instructions.

- Le matériel quantique utilisé pour les qubits est fragile et très sensible aux interférences environnementales. Pour certaines méthodes de stockage des qubits, l’unité qui héberge les qubits doit être conservée à une température juste au-dessus du zéro absolu pour garantir leur cohérence maximale. D’autres types d’hébergements des qubits utilisent une chambre à vide pour réduire au maximum les vibrations et stabiliser les qubits.  
- Les signaux peuvent être envoyés aux qubits au moyen de diverses méthodes, comme les micro-ondes, le laser et la tension.

Les ordinateurs quantiques font face à une multitude de difficultés pour fonctionner correctement. Sur les ordinateurs quantiques, la correction des erreurs est un problème majeur, et le taux d’erreur augmente avec les opérations de scale-up (ajout de qubits). À cause de ces limitations, on est encore très loin de l’ordinateur quantique pour le travail de bureau. En revanche, le lancement d’un ordinateur quantique de laboratoire et viable commercialement est envisageable dans un avenir plus proche.

## <a name="quantum-simulators"></a>Simulateurs quantiques

Les simulateurs quantiques qui s’exécutent sur des ordinateurs classiques vous permettent de simuler l’exécution d’algorithmes quantiques sur un système quantique.  Le kit de développement Quantum (QDK) de Microsoft comprend un simulateur vectoriel d’état complet et plusieurs autres simulateurs quantiques spécialisés.

## <a name="topological-qubit"></a>Qubit topologique

Microsoft développe un ordinateur quantique basé sur des qubits topologiques. Un qubit topologique est moins impacté par les changements dans son environnement, ce qui réduit le degré de correction d’erreur externe nécessaire.

Les qubits topologiques se caractérisent par une stabilité accrue et une résistance au bruit ambiant. Cela signifie qu’ils peuvent adapter leur échelle plus facilement et rester fiables plus longtemps.

## <a name="microsoft-and-quantum-hardware-partnerships"></a>Partenariats entre Microsoft et des fabricants de matériel quantique

Microsoft travaille en partenariat avec les fabricants de matériel quantique IonQ, Honeywell et QCI en vue de rendre les ordinateurs quantiques accessibles aux développeurs dans le futur. En exploitant la plateforme Azure Quantum, les développeurs pourront utiliser le langage Q# et le kit de développement Quantum (QDK) de Microsoft pour écrire des programmes quantiques et les exécuter à distance.

## <a name="quantum-computations"></a>Calculs quantiques

L’exécution de calculs sur un ordinateur quantique ou un simulateur quantique suit un processus de base :

- Accéder aux qubits
- Initialiser les qubits à l’état souhaité
- Effectuer les opérations de transformation des états des qubits
- Mesurer les nouveaux états des qubits

L’initialisation et la transformation des qubits s’effectuent par le biais d’**opérations quantiques** (parfois appelées portes quantiques). Les opérations quantiques sont similaires aux opérations logiques classiques comme AND, OR, NOT et XOR. Une opération peut être aussi simple que l’inversion de l’état d’un qubit de 1 à 0 ou l’intrication de deux qubits, ou plus complexe comme l’utilisation de plusieurs opérations en série pour influencer la probabilité qu’un qubit superposé soit réduit dans un sens ou l’autre.

> [!NOTE] 
> Les [bibliothèques Q#](xref:microsoft.quantum.libraries) fournissent des opérations intégrées qui définissent des combinaisons complexes d’opérations quantiques de bas niveau. Vous pouvez utiliser les opérations des bibliothèques pour transformer les qubits et créer des opérations définies par l’utilisateur plus complexes.  

La mesure du résultat du calcul nous donne une réponse, mais pour certains algorithmes quantiques, ce n’est pas toujours la réponse correcte. Étant donné que le résultat de certains algorithmes quantiques dépend de la probabilité qui a été configurée par les opérations quantiques, ces calculs sont exécutés plusieurs fois pour obtenir une distribution de probabilités et affiner la précision des résultats.  L’assurance qu’une opération a retourné une réponse correcte est connue sous le terme de contrôle quantique et constitue un défi majeur pour l’informatique quantique.

## <a name="summary"></a>Résumé

L’informatique quantique a plusieurs concepts en commun avec l’informatique classique, mais elle utilise aussi de nouveaux concepts qui lui sont propres. Voici les principaux points à retenir :

- Le matériel quantique est onéreux et fragile. C’est pourquoi on utilise des simulateurs quantiques pour écrire et tester les programmes.
- Les ordinateurs classiques et quantiques utilisent tous des opérations logiques (ou portes) pour préparer les calculs.
- Les calculs quantiques retournent des probabilités comme résultats.

Grâce aux avancées observées dans le matériel et les techniques quantiques, ce secteur connaît une évolution rapide. Consultez quelques exemples des [développements actuels](https://phys.org/search/?search=quantum+computer&s=0).

## <a name="next-steps"></a>Étapes suivantes

> [!div class="nextstepaction"]
> [Présentation du langage de programmation Q# et du QDK](xref:microsoft.quantum.overview.q-sharp)