---
title: Bibliothèques du Quantum Development Kit | Microsoft Docs
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 7b51945a8aaf937856441cdb10e8a024bf816f88
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442428"
---
# <a name="overview-of-q-libraries"></a>Vue d’ensemble des bibliothèques Q#
Le Quantum Development Kit est fourni avec plusieurs bibliothèques pour faciliter le développement d’applications quantiques en Q#.
Dans cette section de la documentation, nous décrivons ces bibliothèques et comment les utiliser dans vos programmes.

- [**Bibliothèques standard**](xref:microsoft.quantum.libraries.standard.intro) : Cette section décrit le prélude, qui définit l’interface entre les programmes Q# et les machines cibles, et le « canon », une bibliothèque Q# qui fournit des opérations et des fonctions à usage général à utiliser pour écrire des programmes Q#.
- [**Bibliothèque de chimie quantique**](xref:microsoft.quantum.chemistry.concepts.intro) Cette section décrit la bibliothèque de chimie quantique, qui fournit un modèle de données pour le chargement des représentations d’opérateurs hamiltoniens fermioniques, et des opérations et des fonctions de simulation quantique qui agissent sur ces représentations.
- [**Bibliothèque de valeurs numériques quantiques**](xref:microsoft.quantum.numerics.intro) : Cette section décrit la bibliothèque de valeurs numériques quantiques, qui fournit des implémentations pour un hôte de fonctions mathématiques. Elle prend en charge les représentations de type entier (signé et non signé) et avec virgule fixe.

Les sources des bibliothèques ainsi que des exemples de code peuvent être obtenus auprès de GitHub. Pour plus d’informations, consultez également la section [Gestion des licences](xref:microsoft.quantum.libraries.licensing). Notez que des références de package (« binaires ») sont également disponibles pour les bibliothèques, ce qui offre un autre moyen d’inclure les bibliothèques dans des projets. Vous pouvez les obtenir facilement via [NuGet](https://nuget.org).  