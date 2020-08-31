---
title: Présentation du langage de programmation Q# et du QDK
description: Découvrez le kit de développement Quantum (QDK) et le langage de programmation Q# de Microsoft, et comment les utiliser pour créer des programmes quantiques.
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5db574b0380ffa1616cb3959d84925854df4e321
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863775"
---
# <a name="what-are-the-no-locq-programming-language-and-qdk"></a>Présentation du langage de programmation Q# et du QDK

Q# est le langage de programmation open source conçu par Microsoft pour le développement et l’exécution d’algorithmes quantiques. Il fait partie du kit de développement Quantum (QDK) qui comprend des [bibliothèquesQ#](xref:microsoft.quantum.libraries) , des [simulateurs quantiques](xref:microsoft.quantum.machines), des [extensions pour d’autres environnements de programmation](xref:microsoft.quantum.install) et la [documentation des API](xref:microsoft.quantum.standardlibsintro). En plus de la bibliothèque Q# standard, le QDK contient des bibliothèques de données numériques, de chimie et de Machine Learning.

Le langage de programmation Q# utilise des éléments connus des langages Python, C# et F#. Il prend en charge un modèle de procédure de base permettant l’écriture de programmes avec des boucles, des instructions if/then ainsi que des types de données courants. Il introduit également de nouvelles structures de données et opérations propres à l’informatique quantique.

## <a name="what-can-i-do-with-the-qdk"></a>À quoi sert le QDK ?

Le QDK est un kit de développement complet pour Q#. Vous pouvez l’utiliser avec des outils et des langages courants pour développer des applications quantiques exécutables dans divers environnements. Les programmes Q# peuvent s’exécuter en tant qu’application console, via les notebooks Jupyter, ou utiliser un programme hôte Python ou .NET.

### <a name="develop-in-common-tools-and-environments"></a>Développer dans des environnements et outils courants

Intégrez votre développement quantique avec [Visual Studio, Visual Studio Code](xref:microsoft.quantum.install.standalone) et des [notebooks Jupyter](xref:microsoft.quantum.install.jupyter). Utilisez les API intégrées pour associer vos programmes aux langages hôtes [Python](xref:microsoft.quantum.install.python) et [.NET](xref:microsoft.quantum.install.cs).

### <a name="try-quantum-operations-and-domain-specific-libraries"></a>Essayer les opérations quantiques et les bibliothèques spécifiques à un domaine

Écrivez et testez des algorithmes quantiques pour explorer la superposition, l’intrication et d’autres opérations quantiques. Avec les bibliothèques Q#, vous pouvez exécuter des opérations quantiques complexes sans avoir à concevoir les séquences des opérations de bas niveau.

### <a name="run-programs-in-simulators"></a>Exécuter des programmes dans des simulateurs

Exécutez vos programmes quantiques sur un simulateur quantique d’état complet ou un simulateur Toffoli à étendue limitée, ou testez votre code Q# dans différents estimateurs de ressources. 

## <a name="where-can-i-learn-more"></a>Où en savoir plus ?

|||
| ---- | ---- |
| **Je débute avec l’informatique quantique** | Découvrez quelques-uns des concepts fondamentaux de la physique quantique et de l’informatique quantique dans [Concepts clés](xref:microsoft.quantum.overview.understanding).|
| **Je souhaite approfondir mes connaissances du langage Q#** | Explorez les types, les expressions, les variables ainsi que la structure des programmes quantiques dans le [Guide de l’utilisateur Q#](xref:microsoft.quantum.guide).|
| **Je souhaite commencer directement à écrire des programmes quantiques** | Configurez votre environnement Q# et commencez à écrire des programmes quantiques en vous aidant des [démarrages rapides](xref:microsoft.quantum.install).|

## <a name="how-does-no-locq-work"></a>Comment Q# fonctionne-t-il ?

Un programme Q# peut être compilé dans une application autonome, ou être appelé par un programme hôte écrit en Python ou dans un langage .NET.

Quand vous compilez et exécutez le programme, celui-ci crée une instance du simulateur quantique et lui transmet le code Q#. Le simulateur utilise le code Q# pour créer des qubits (simulations de particules quantiques) et appliquer des transformations afin de changer leur état. Les résultats des opérations quantiques dans le simulateur sont ensuite retournés au programme.  

L’isolation du code Q# dans le simulateur garantit que les algorithmes suivent les lois de la physique quantique et s’exécutent correctement sur les ordinateurs quantiques.

![qsharp-code-flow](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a>Comment utiliser le QDK ?

Tous les éléments dont vous avez besoin pour écrire et exécuter des programmes Q#, y compris le compilateur Q#, les bibliothèques Q# et les simulateurs quantiques, peuvent être installés et exécutés sur votre ordinateur local. Vous pourrez peut-être un jour exécuter vos programmes Q# à distance sur un véritable ordinateur quantique, mais en attendant, les simulateurs quantiques inclus dans le QDK fournissent des résultats précis et fiables.

- Le développement d’[applications Q#](xref:microsoft.quantum.install.standalone) est le moyen le plus rapide de commencer.

- Vous pouvez opter pour une exécution autonome des [notebooks Jupyter avec IQ#](xref:microsoft.quantum.install.jupyter), une extension Jupyter conçue pour la compilation, la simulation et la visualisation des programmes Q#.

- Si vous êtes familiarisé avec [Python](xref:microsoft.quantum.install.python), vous pouvez l’utiliser comme plateforme de programmation hôte pour commencer. Python est largement utilisé, non seulement parmi les développeurs, mais aussi par les scientifiques, les chercheurs et les enseignants.

- Si vous avez déjà utilisé [C#, F# ou VB.NET](xref:microsoft.quantum.install.cs) et que vous êtes familiarisé avec l’environnement de développement Visual Studio, il vous suffit d’ajouter quelques extensions à Visual Studio afin de le préparer pour Q#.  

## <a name="summary"></a>Résumé

Q# est un langage de programmation open source conçu pour le développement de programmes quantiques. Ses bibliothèques vous aident à créer des opérations quantiques complexes, et ses simulateurs quantiques vous permettent d’exécuter et de tester correctement vos programmes. Les programmes Q# peuvent s’exécuter en tant qu’applications autonomes ou être appelés par un programme hôte Python ou .NET. Ils peuvent être écrits, exécutés et testés directement sur votre ordinateur local.

## <a name="next-steps"></a>Étapes suivantes

[Algèbre linéaire pour l’informatique quantique](xref:microsoft.quantum.overview.algebra)
