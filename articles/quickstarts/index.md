---
title: Installation du kit de développement Microsoft Quantum (QDK)
description: Découvrez comment installer le kit de développement Microsoft Quantum pour différents environnements.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834480"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a>Installation du kit de développement Microsoft Quantum (QDK)

Découvrez comment installer le kit de développement Microsoft Quantum (QDK) dans votre environnement afin de pouvoir vous lancer dans la programmation quantique. Le QDK se compose des éléments suivants :

- Langage de programmation Q#
- Ensemble de bibliothèques qui résument des fonctionnalités complexes en Q#
- API pour Python et les langages .NET (C#, F# et VB.NET) pour exécuter des programmes quantiques écrits en Q#
- Outils pour faciliter votre développement

Les programmes Q# peuvent être exécutés en tant qu’applications autonomes avec Visual Studio Code ou Visual Studio, via des notebooks Jupyter avec le noyau Jupyter IQ# ou couplés avec un programme hôte écrit en Python ou en langage .NET (C#, F#). Vous pouvez aussi exécuter les programmes Q# en ligne avec [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) ou [Docker](#use-the-qdk-with-docker). 

## <a name="options-for-setting-up-the-qdk"></a>Options pour installer le QDK

Vous pouvez utiliser le QDK de trois manières :

- [Installer le QDK localement](#install-the-qdk-locally)
- [Utiliser le QDK en ligne](#use-the-qdk-online)
- [Utiliser une image Docker du QDK](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a>Installer le QDK localement

Vous pouvez développer le code Q# dans la plupart de vos IDE préférés et intégrer Q# dans d’autres langages comme Python et .NET (C#, F#).

|&nbsp; | **VS Code<br>(2019 ou ultérieur)**| **Visual Studio<br>(2019 ou ultérieur)** | **Blocs-notes Jupyter** | **Ligne de commande**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|**SE** |Windows, macOS, Linux |Windows uniquement |Windows, macOS, Linux |Windows, macOS, Linux |
|<br>**Q# autonome** |<br>[Installer](xref:microsoft.quantum.install.standalone) |<br> [Installer](xref:microsoft.quantum.install.standalone)  |<br> [Installer](xref:microsoft.quantum.install.jupyter) |<br>[Installer](xref:microsoft.quantum.install.standalone)|
|**Q# et Python** |[Installer](xref:microsoft.quantum.install.python) |[Installer](xref:microsoft.quantum.install.python) |[Installer](xref:microsoft.quantum.install.jupyter) |[Installer](xref:microsoft.quantum.install.python) |
|**Q# et .NET (C#, F#)**|[Installer](xref:microsoft.quantum.install.cs) |[Installer](xref:microsoft.quantum.install.cs)|&#10006; |[Installer](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a>Utiliser le QDK en ligne

Vous pouvez également développer le code Q# sans rien installer localement avec les options suivantes :

|Ressource|Avantages|Limites|
|---|---|---|
|[**Visual Studio Codespaces**](xref:microsoft.quantum.install.standalone)|Environnement de développement en ligne complet  |Nécessite un plan et un abonnement Azure |
|[**Binder**](xref:microsoft.quantum.install.binder) | Expérience de notebook en ligne gratuite |Aucune persistance |

## <a name="use-the-qdk-with-docker"></a>Utiliser le QDK avec Docker

Vous pouvez utiliser notre image Docker du QDK dans votre installation Docker locale ou dans le cloud via un service prenant en charge les images Docker, par exemple ACI.

Vous pouvez télécharger l’image Docker IQ# depuis https://github.com/microsoft/iqsharp/#using-iq-as-a-container. 

Vous pouvez aussi utiliser Docker avec un conteneur de développement distant Visual Studio Code pour définir rapidement des environnements de développement. Pour plus d’informations sur les conteneurs de développement VS Code, consultez https://github.com/microsoft/Quantum/tree/master/.devcontainer.

## <a name="next-steps"></a>Étapes suivantes

Le workflow de chacune de ces configurations est décrit et comparé aux autres dans [Méthodes d’exécution d’un programme Q#](xref:microsoft.quantum.guide.host-programs).
