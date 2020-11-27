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
ms.openlocfilehash: c6e128ea8b3845336fb692d2bceefda998b935d9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228824"
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

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><b>VS Code<br>(2019 ou ultérieur)</b></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><b>Visual Studio<br>(2019 ou ultérieur)</b></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><b>Blocs-notes Jupyter</b></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><b>Ligne de commande</b></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><b>Prise en charge du système d’exploitation :</b></td>
        <td align="center">Windows, macOS, Linux</td>
        <td align="center">Windows uniquement</td>
        <td align="center">Windows, macOS, Linux</td>
        <td align="center">Windows, macOS, Linux</td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><b>Q# autonome</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Installer</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Installer</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.jupyter">Installer</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Installer</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><b>Q# et Python</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Installer</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Installer</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Installer</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Installer</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><b>Q# et .NET (C#, F#)</b></td> 
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Installer</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Installer</a></td>
        <td align="center">&#10006;</td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Installer</a></td>
   </tr>
</table>

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
