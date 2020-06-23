---
title: Introduction aux bibliothèques standard Microsoft Q#
description: Découvrez les bibliothèques standard Microsoft Q# qui définissent les opérations, fonctions et types de données utilisés dans les programmes quantiques.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 820ad885e7134aa723116d4c9f853d88210a5514
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273532"
---
# <a name="introduction-to-the-q-standard-libraries"></a>Introduction aux bibliothèques standard Q# #

Q# est pris en charge par une série d’opérations, de fonctions et de types définis par l’utilisateur différents et utiles qui composent les *bibliothèques standard* Q# .
Le [`Microsoft.Quantum.Development.Kit` package NuGet](https://www.nuget.org/packages/microsoft.quantum.development.kit) installé au cours de [l’installation et de la validation](xref:microsoft.quantum.install) fournit le compilateur Q# et une partie de la bibliothèque standard qui est implémentée par les machines cibles.
Le [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) fournit la partie des bibliothèques standard Q# portables sur les machines cibles.

Les symboles définis par les bibliothèques standard Q# sont définis de manière bien plus détaillée et plus exhaustive dans la [documentation de l’API](xref:microsoft.quantum.standardlibsintro).

Dans les sections suivantes, nous décrirons les fonctionnalités les plus importantes de chaque partie de la bibliothèque standard et fournirons un contexte sur la façon dont chaque fonctionnalité peut être utilisée dans la pratique.
