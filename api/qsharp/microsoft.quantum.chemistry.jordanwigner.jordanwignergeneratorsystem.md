---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: JordanWignerGeneratorSystem fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 0f6719cfac1c50cd55da30e57b0b5c5214813f24
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214719"
---
# <a name="jordanwignergeneratorsystem-function"></a><span data-ttu-id="33565-102">JordanWignerGeneratorSystem fonction)</span><span class="sxs-lookup"><span data-stu-id="33565-102">JordanWignerGeneratorSystem function</span></span>

<span data-ttu-id="33565-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="33565-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="33565-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="33565-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="33565-105">Convertit un de Hamilton décrit par en `JWOptimizedHTerms` un `GeneratorSystem` exprimé en termes de la `GeneratorIndex` Convention définie dans ce fichier.</span><span class="sxs-lookup"><span data-stu-id="33565-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="33565-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="33565-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="33565-107">données : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="33565-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="33565-108">Description de la structure de l’un au `JWOptimizedHTerms` format.</span><span class="sxs-lookup"><span data-stu-id="33565-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="33565-109">Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="33565-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="33565-110">Représentation de Hamilton sous la forme `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="33565-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>