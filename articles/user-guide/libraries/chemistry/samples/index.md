---
title: Exemples d’applications de chimie quantique
description: Explorez des exemples d’applications de la bibliothèque de chimie quantique Microsoft.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
no-loc:
- Q#
- $$v
ms.openlocfilehash: a0bc79c7fb41069ee7865dbf2f1cfd7851fda32d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869288"
---
# <a name="quantum-chemistry-examples"></a>Exemples de chimie quantique

Dans les concepts de chimie quantique, nous avons construit manuellement l’exemple des fermions hamiltoniens. Nous combinons maintenant les algorithmes de simulation chimique décrits dans [Simulation des dynamiques hamiltoniennes](xref:microsoft.quantum.libraries.standard.algorithms) avec l’[estimation des phases quantiques](xref:microsoft.quantum.libraries.characterization) dans la bibliothèque « canon ». Cette combinaison nous permet d’obtenir des estimations des niveaux d’énergie dans la molécule représentée, ce qui est une des principales applications de la chimie quantique sur un ordinateur quantique. 

Au lieu de spécifier les termes de l’opérateur hamiltonien un par un, nous travaillons également sur des exemples qui nous permettent d’effectuer des expériences de chimie quantique à grande échelle. Nous commençons par des exemples qui chargent un opérateur hamiltonien pour la chimie encodé dans le [schéma de Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

Pour les molécules trop grandes pour être simulées sur le [simulateur d’états complet](xref:microsoft.quantum.machines.full-state-simulator), une recherche scientifique intéressante peut néanmoins être menée. Par exemple, les coûts en ressources liés à la réalisation de simulations chimiques à grande échelle peuvent toujours être évalués en ciblant le [simulateur de traces](xref:microsoft.quantum.machines.qc-trace-simulator.intro).

Nous allons maintenant illustrer les applications intéressantes de la bibliothèque de simulation chimique à travers quelques-uns des exemples fournis.
