---
title: Exemples d’applications de chimie quantique
description: Explorez des exemples d’applications de la bibliothèque de chimie quantique Microsoft.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 5168fc8592d34a32ba67e5a0c4793aa17599fd35
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2020
ms.locfileid: "77906489"
---
# <a name="quantum-chemistry-examples"></a><span data-ttu-id="9c26e-103">Exemples de chimie quantique</span><span class="sxs-lookup"><span data-stu-id="9c26e-103">Quantum chemistry examples</span></span>

<span data-ttu-id="9c26e-104">Dans les concepts de chimie quantique, nous avons construit manuellement l’exemple des fermions hamiltoniens.</span><span class="sxs-lookup"><span data-stu-id="9c26e-104">In the quantum chemistry concepts, we manually constructed example fermion Hamiltonians.</span></span> <span data-ttu-id="9c26e-105">Nous combinons maintenant les algorithmes de simulation chimique décrits dans [Simulation des dynamiques hamiltoniennes](xref:microsoft.quantum.libraries.standard.algorithms) avec l’[estimation des phases quantiques](xref:microsoft.quantum.libraries.characterization) dans la bibliothèque « canon ».</span><span class="sxs-lookup"><span data-stu-id="9c26e-105">We now combine the chemistry simulation algorithms outlined in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) with [quantum phase estimation](xref:microsoft.quantum.libraries.characterization) in the canon library.</span></span> <span data-ttu-id="9c26e-106">Cette combinaison nous permet d’obtenir des estimations des niveaux d’énergie dans la molécule représentée, ce qui est une des principales applications de la chimie quantique sur un ordinateur quantique.</span><span class="sxs-lookup"><span data-stu-id="9c26e-106">This combination allows us to obtain  estimates of energy levels in the represented molecule, which is one of the key applications of quantum chemistry on a quantum computer.</span></span> 

<span data-ttu-id="9c26e-107">Au lieu de spécifier les termes de l’opérateur hamiltonien un par un, nous travaillons également sur des exemples qui nous permettent d’effectuer des expériences de chimie quantique à grande échelle.</span><span class="sxs-lookup"><span data-stu-id="9c26e-107">Instead of specifying terms of the Hamiltonian one-by-one, we also work through some examples that allow us to perform quantum chemistry experiments at scale.</span></span> <span data-ttu-id="9c26e-108">Nous commençons par des exemples qui chargent un opérateur hamiltonien pour la chimie encodé dans le [schéma de Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span><span class="sxs-lookup"><span data-stu-id="9c26e-108">We begin with examples that load a chemistry Hamiltonian encoded in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span>

<span data-ttu-id="9c26e-109">Pour les molécules trop grandes pour être simulées sur le [simulateur d’états complet](xref:microsoft.quantum.machines.full-state-simulator), une recherche scientifique intéressante peut néanmoins être menée.</span><span class="sxs-lookup"><span data-stu-id="9c26e-109">For molecules that are too large to simulate on the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), interesting science can still be performed.</span></span> <span data-ttu-id="9c26e-110">Par exemple, les coûts en ressources liés à la réalisation de simulations chimiques à grande échelle peuvent toujours être évalués en ciblant le [simulateur de traces](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="9c26e-110">For instance, the resource costs of performing large chemistry simulations may still be evaluated by targeting the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>

<span data-ttu-id="9c26e-111">Nous allons maintenant illustrer les applications intéressantes de la bibliothèque de simulation chimique à travers quelques-uns des exemples fournis.</span><span class="sxs-lookup"><span data-stu-id="9c26e-111">Let us now illustrate interesting applications of the chemistry simulation library through a few of the provided samples.</span></span>
