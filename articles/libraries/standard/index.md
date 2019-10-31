---
title: Bibliothèques standard Q# - introduction | Microsoft Docs
description: Bibliothèques standard Q# - introduction
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 547f4f6066e3ead627cd2a5970b1555999e988bb
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73056384"
---
# <a name="introduction-to-the-q-standard-libraries"></a><span data-ttu-id="39ce0-103">Introduction aux bibliothèques standard Q#</span><span class="sxs-lookup"><span data-stu-id="39ce0-103">Introduction to the Q# Standard Libraries</span></span> #

<span data-ttu-id="39ce0-104">Q# est pris en charge par une série d’opérations, de fonctions et de types définis par l’utilisateur différents et utiles qui composent les *bibliothèques standard* Q# .</span><span class="sxs-lookup"><span data-stu-id="39ce0-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="39ce0-105">Le [`Microsoft.Quantum.Development.Kit` package NuGet](https://www.nuget.org/packages/microsoft.quantum.development.kit) installé au cours de [l’installation et de la validation](xref:microsoft.quantum.install) fournit le compilateur Q# et une partie de la bibliothèque standard qui est implémentée par les machines cibles.</span><span class="sxs-lookup"><span data-stu-id="39ce0-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="39ce0-106">Le [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) fournit la partie des bibliothèques standard Q# portables sur les machines cibles.</span><span class="sxs-lookup"><span data-stu-id="39ce0-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="39ce0-107">Les symboles définis par les bibliothèques standard Q# sont définis de manière bien plus détaillée et plus exhaustive dans la [documentation de l’API](xref:microsoft.quantum.standardlibsintro).</span><span class="sxs-lookup"><span data-stu-id="39ce0-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span>

<span data-ttu-id="39ce0-108">Dans les sections suivantes, nous décrirons les fonctionnalités les plus importantes de chaque partie de la bibliothèque standard et fournirons un contexte sur la façon dont chaque fonctionnalité peut être utilisée dans la pratique.</span><span class="sxs-lookup"><span data-stu-id="39ce0-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
