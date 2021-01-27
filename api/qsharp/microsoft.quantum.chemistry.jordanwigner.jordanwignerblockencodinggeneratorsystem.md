---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerBlockEncodingGeneratorSystem
title: JordanWignerBlockEncodingGeneratorSystem fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: cffbb1e2d9b6566bf6c3da642e4479968f774ca3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839029"
---
# <a name="jordanwignerblockencodinggeneratorsystem-function"></a><span data-ttu-id="16804-102">JordanWignerBlockEncodingGeneratorSystem fonction)</span><span class="sxs-lookup"><span data-stu-id="16804-102">JordanWignerBlockEncodingGeneratorSystem function</span></span>

<span data-ttu-id="16804-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="16804-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="16804-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="16804-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="16804-105">Convertit un sous-sein de Hamilton décrit par en `JWOptimizedHTerms` un `GeneratorSystem` exprimé en termes de Pauli `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="16804-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.</span></span>

```qsharp
function JordanWignerBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="16804-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="16804-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="16804-107">données : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="16804-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="16804-108">Description de la structure de l’un au `JWOptimizedHTerms` format.</span><span class="sxs-lookup"><span data-stu-id="16804-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="16804-109">Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="16804-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="16804-110">Représentation de Hamilton sous la forme `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="16804-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>