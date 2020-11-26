---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerClusterOperatorGeneratorSystem
title: JordanWignerClusterOperatorGeneratorSystem fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerClusterOperatorGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: e6deca3c8261c7730e9b208d9f834ad0db101fd3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214804"
---
# <a name="jordanwignerclusteroperatorgeneratorsystem-function"></a><span data-ttu-id="2bb9c-102">JordanWignerClusterOperatorGeneratorSystem fonction)</span><span class="sxs-lookup"><span data-stu-id="2bb9c-102">JordanWignerClusterOperatorGeneratorSystem function</span></span>

<span data-ttu-id="2bb9c-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="2bb9c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="2bb9c-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2bb9c-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="2bb9c-105">Convertit un de Hamilton décrit par en `JWOptimizedHTerms` un `GeneratorSystem` exprimé en termes de la `GeneratorIndex` Convention définie dans ce fichier.</span><span class="sxs-lookup"><span data-stu-id="2bb9c-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JordanWignerClusterOperatorGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="2bb9c-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2bb9c-106">Input</span></span>

### <a name="data--jordanwignerinputstate"></a><span data-ttu-id="2bb9c-107">données : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="2bb9c-107">data : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="2bb9c-108">Description de la structure de l’un au `JWOptimizedHTerms` format.</span><span class="sxs-lookup"><span data-stu-id="2bb9c-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="2bb9c-109">Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="2bb9c-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="2bb9c-110">Représentation de Hamilton sous la forme `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="2bb9c-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>