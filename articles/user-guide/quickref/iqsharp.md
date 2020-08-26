---
title: Q#Commandes magiques
description: Page de référence rapide pour les Q# commandes magiques avec les Q# blocs-notes Jupyter
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1d2d092588e1a5c69d12e5d50377e3e26412c094
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863698"
---
# <a name="ino-locq-magic-commands"></a>Q#Commandes magiques

### <a name="general"></a>Général

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Permet de définir ou d’interroger des options de configuration.
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Exécute une fonction ou une opération donnée sur l’ordinateur cible ResourcesEstimator.
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Retourne une liste de toutes les commandes Magic actuellement disponibles.
- [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen): Répertorie les espaces de noms actuellement ouverts et leurs alias.
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Permet de charger un package NuGet.
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Signale les métriques de performances actuelles pour ce noyau.
- [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project): Donne la possibilité d’afficher ou d’ajouter des Q# références de projet. 
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Exécute une fonction ou une opération donnée sur l’ordinateur cible QuantumSimulator.
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Exécute une fonction ou une opération donnée sur l’ordinateur cible ToffoliSimulator.
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Répertorie les Q# opérations disponibles dans la session active.
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Fournit des actions liées à l’espace de travail actuel.

### <a name="azure-quantum-integration"></a>Intégration d’Azure Quantum

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Se connecte à un espace de travail Quantum Azure ou affiche l’état actuel de la connexion.
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Exécute un travail dans un espace de travail Quantum Azure.
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Affiche la liste des travaux dans l’espace de travail Quantum Azure actuel.
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Affiche les résultats d’un travail dans l’espace de travail Quantum Azure actuel.
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Affiche l’état d’un travail dans l’espace de travail Quantum Azure actuel.
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Envoie un travail à un espace de travail Quantum Azure.
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Définit ou affiche la cible d’exécution active pour l' Q# envoi de tâches dans un espace de travail Quantum Azure.

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>Chimie (à partir du package Microsoft. Quantum. chimie)

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Charge et retourne la représentation du problème de structure électronique Broombridge à partir d’un fichier. YAML donné.
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Encode un fermion Hamilton dans un format utilisable par Q# .
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Ajoute des termes à un fermion Hamilton.
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Charge le fermion Hamilton pour un problème de structure électronique. Le problème est chargé à partir d’un fichier ou passé comme argument.
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Charge le problème de structure électronique Broombridge et retourne l’état d’entrée sélectionné.

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (à partir du package Microsoft. Quantum. katas)

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Exécute un seul test et signale si le test a réussi.
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Vérifie l’implémentation de référence pour un test de Kata unique.
    En particulier, il substitue l’implémentation de référence pour une tâche unique dans la cellule et signale si le test a réussi.
