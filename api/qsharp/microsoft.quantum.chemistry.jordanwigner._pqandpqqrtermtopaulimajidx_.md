---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliMajIdx_
title: _PQandPQQRTermToPauliMajIdx_ fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 4ba13f42064d9311ffb29dbd9363aa3be978e702
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703351"
---
# <a name="_pqandpqqrtermtopaulimajidx_-function"></a><span data-ttu-id="debd1-102">_PQandPQQRTermToPauliMajIdx_ fonction)</span><span class="sxs-lookup"><span data-stu-id="debd1-102">_PQandPQQRTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="debd1-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="debd1-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="debd1-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="debd1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="debd1-105">Convertit un GeneratorIndex décrivant un terme PQ ou PQQR en une expression’GeneratorIndex [] 'en termes de Paulis</span><span class="sxs-lookup"><span data-stu-id="debd1-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="debd1-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="debd1-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="debd1-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="debd1-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="debd1-108">`GeneratorIndex` représentant un terme PQ ou PQQR.</span><span class="sxs-lookup"><span data-stu-id="debd1-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="debd1-109">Sortie : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="debd1-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="debd1-110">'GeneratorIndex [] 'exprimant PQ ou PQQR term comme termes Pauli.</span><span class="sxs-lookup"><span data-stu-id="debd1-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>