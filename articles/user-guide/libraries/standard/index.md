---
title: Introduction aux bibliothèques standard Microsoft Q#
description: Découvrez les bibliothèques standard Microsoft Q# qui définissent les opérations, fonctions et types de données utilisés dans les programmes quantiques.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4db227fcf159331f9f8456c474ce6d64111c21df
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868472"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Introduction aux bibliothèques standard Q#

Q# est pris en charge par une série d’opérations, de fonctions et de types définis par l’utilisateur différents et utiles qui composent les *bibliothèques standard* Q#.
Le [`Microsoft.Quantum.Development.Kit` package NuGet](https://www.nuget.org/packages/microsoft.quantum.development.kit) installé au cours de [l’installation et de la validation](xref:microsoft.quantum.install) fournit le compilateur Q# et une partie de la bibliothèque standard qui est implémentée par les machines cibles.
Le [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) fournit la partie des bibliothèques standard Q# portables sur les machines cibles.

Les symboles définis par les bibliothèques standard Q# sont définis de manière bien plus détaillée et plus exhaustive dans la [documentation de l’API](xref:microsoft.quantum.standardlibsintro).

Dans les sections suivantes, nous décrirons les fonctionnalités les plus importantes de chaque partie de la bibliothèque standard et fournirons un contexte sur la façon dont chaque fonctionnalité peut être utilisée dans la pratique.
