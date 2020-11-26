---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBlockEncodingGeneratorSystem
title: OptimizedBlockEncodingGeneratorSystem fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: 1d59c7655b5534465717dd816848011527df4a42
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214583"
---
# <a name="optimizedblockencodinggeneratorsystem-function"></a><span data-ttu-id="0b059-102">OptimizedBlockEncodingGeneratorSystem fonction)</span><span class="sxs-lookup"><span data-stu-id="0b059-102">OptimizedBlockEncodingGeneratorSystem function</span></span>

<span data-ttu-id="0b059-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="0b059-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="0b059-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0b059-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="0b059-105">Convertit un sous-sein de Hamilton décrit par en `JWOptimizedHTerms` un `GeneratorSystem` exprimé en termes de Pauli `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="0b059-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.</span></span>

```qsharp
function OptimizedBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="0b059-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="0b059-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="0b059-107">données : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="0b059-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="0b059-108">Description de la structure de l’un au `JWOptimizedHTerms` format.</span><span class="sxs-lookup"><span data-stu-id="0b059-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--optimizedbegeneratorsystem"></a><span data-ttu-id="0b059-109">Sortie : [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="0b059-109">Output : [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span></span>

<span data-ttu-id="0b059-110">Représentation de Hamilton sous la forme `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="0b059-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>