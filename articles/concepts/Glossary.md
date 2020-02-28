---
title: Glossaire quantum computing
description: Glossaire des termes, actions et objets les plus courants utilisés dans quantum computing.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: f47d87f5bc9d677baa12a7ac1581af72894e8a4b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909889"
---
# <a name="quantum-computing-glossary"></a>Glossaire quantum computing

|Terme|Définition|
|-------------|----------|
|Voisin|Transposer le conjugué complexe de l’opération. Pour les opérations qui implémentent un opérateur unitaire, le voisin est l’inverse de l’opération.|
|Pouvant être appelé|Les opérations et les fonctions sont collectivement appelées *callables*.|
|standard|Opérations et fonctions définies dans Q # en génération sur la logique définie dans Préambule destiné à. L’implémentation de la bibliothèque standard est indépendante en ce qui concerne les ordinateurs cibles.|
|Groupe Clifford|Ensemble des opérations qui occupent le octants de la sphère Bloch. Il s’agit notamment des éléments suivants : `X`, `Y`, `Z`, `H` et `S`|
|Contrôl|Opération de Quantum qui prend un ou plusieurs qubits comme activateurs pour l’opération cible.|
|Notation Dirac|Représentation abrégée de l’État Quantum. Pour plus d’informations, consultez la section [notation Dirac](xref:microsoft.quantum.concepts.dirac) .|
|Valeurs propres et vecteurs propres|Pour plus d’informations, consultez la [section matrice avancée](xref:microsoft.quantum.concepts.matrix-advanced) .|
|Paire EPR|Également connu sous le nom d' [État de cloche](https://en.wikipedia.org/wiki/Bell_state)|
|Révolution|Comment l’état change dans le temps. Pour obtenir un exemple, consultez la section sur <xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials>. |
|Fonction|Routines purement classiques dans le langage Q #|
| <a id="global-phase"></a>Phase globale | Deux États identiques à un multiple d’un nombre complexe $e ^ {i\phi} $ sont considérés comme différents d’une phase globale. Contrairement aux phases locales, les phases globales ne peuvent pas être observées par mesure. Pour plus d’informations, consultez [mesures Pauli](xref:microsoft.quantum.concepts.pauli) . |
|Mesure|Obtention d’un bit classique à partir d’un qubit (ou d’un ensemble de qubits). Pour plus d’informations, consultez la section [concepts de qubit](xref:microsoft.quantum.concepts.qubit) .|
|Mutable|Variable dont la valeur peut être modifiée après sa création.|
|Espace de noms|Étiquette pour une collection de noms associés (en général, les opérations, les fonctions et les types). Par exemple, l’espace de noms [`Microsoft.Quantum.Preparation`](xref:microsoft.quantum.preparation) étiquette tous les symboles définis dans la bibliothèque standard qui facilitent la préparation des États initiaux.|
|Opération|Unité de base de l’exécution du quantum dans Q #. Elle est à peu près l’équivalent d’une fonction en C, C++ ou Python, ou d’une méthode statique en C# ou Java.|
|Application opérateur|Exécution d’une opération de Quantum. Cela applique généralement une matrice d’unités au vecteur d’état actuel. Pour plus d’informations, consultez [Présentation des concepts quantiques](xref:microsoft.quantum.concepts.intro) .|
|Oracle|Sous-routine qui fournit des informations dépendantes aux données à un algorithme Quantum au moment de l’exécution. En règle générale, l’objectif est de fournir une superposition des sorties correspondant aux entrées en superposition.   |
|Application partielle|Appel d’une fonction ou d’une opération sans tous les paramètres requis. Retourne un nouvel appelable qui n’a besoin que des paramètres manquants fournis au cours d’une prochaine application.|
|Pauli, opérateurs|`X`, `Y` et `Z` des portes de Quantum.|
|Préambule destiné à|Ensemble des opérations et des fonctions primitives et classiques définies par chaque ordinateur cible, plutôt qu’au niveau Q #.|
|Circuit quantique|Représentation d’un programme pour un ordinateur Quantum. Pour plus d’informations, consultez la section <xref:microsoft.quantum.concepts.circuits>.|
|État Quantum|Représentation de qubits dans le système. Il est généralement indiqué comme un vecteur de colonne complexe. Pour plus d’informations, consultez <xref:microsoft.quantum.concepts.vectors>. |
|Qubit|Unité de stockage quantique. Pour plus d’informations, consultez la section <xref:microsoft.quantum.concepts.qubit>.|
|Répéter jusqu’à réussite|Un algorithme Quantum qui fonctionne de façon probabiliste. En cas d’échec, la routine se réessaie jusqu’à ce qu’elle réussisse (ou qu’une limite a été atteinte). |
|Ordinateur cible|Cible de compilation qui réduit un programme Quantum abstrait en vue d’un matériel ou d’une simulation. Cela inclut généralement les réécritions pour de nombreuses raisons, notamment le remplacement de la porte, l’encodage pour la correction des erreurs, la disposition géométrique et autres.|
|Tuple|Types séparés par des virgules regroupés entre parenthèses. |
|Type défini par l'utilisateur|Collection de types intégrés ou définis précédemment qui peuvent être désignés sous le terme d’une seule unité.|

