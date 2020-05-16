---
title: Commandes magiques IQ#
description: 'Page de référence rapide pour les commandes Magic # Magic avec des blocs-notes Jupyter Q #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431017"
---
# <a name="iq-magic-commands"></a>Commandes magiques IQ#

### <a name="general"></a>Général

- `%config`: Définit ou obtient des préférences de configuration.
- `%estimate`: Exécute une fonction ou une opération donnée sur l’ordinateur cible QuantumSimulator.
- `%lsmagic`: Retourne une liste de toutes les commandes Magic actuellement disponibles.
- `%package`: Permet de charger un package NuGet.
- `%performance`: Signale les métriques de performances actuelles pour ce noyau.
- `%simulate`: Exécute une fonction ou une opération donnée sur l’ordinateur cible QuantumSimulator.
- `%toffoli`: Exécute une fonction ou une opération donnée sur l’ordinateur cible du simulateur ToffoliSimulator.
- `%who`: Fournit des actions liées à l’espace de travail actuel.
- `%workspace`: Retourne une liste de toutes les opérations et fonctions définies dans la session active, de manière interactive ou chargée à partir de l’espace de travail actuel.

### <a name="chemistry"></a>Chimique

- `%chemistry.broombridge`: Charge et retourne la représentation du problème de structure électronique Broombridge à partir d’un fichier. YAML donné.
- `%chemistry.encode`: Encode un fermion Hamilton dans un format utilisable par Q #.
- `%chemistry.fh.add_terms`: Ajoute des termes à un fermion Hamilton.
- `%chemistry.fh.load`: Charge le fermion Hamilton pour un problème de structure électronique. Le problème est chargé à partir d’un fichier ou passé comme argument.
- `%chemistry.inputstate.load`: Charge le problème de structure électronique Broombridge et retourne l’état d’entrée sélectionné.

### <a name="from-microsoftquantumkatas-package"></a>À partir du package Microsoft. Quantum. katas

- `%kata`: Exécute un seul test et signale si le test a réussi.
- `%check_kata`: Vérifie l’implémentation de référence pour un test de Kata unique.
    En particulier, il substitue l’implémentation de référence pour une tâche unique dans la cellule et signale si le test a réussi.
