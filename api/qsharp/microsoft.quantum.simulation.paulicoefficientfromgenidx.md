---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: PauliCoefficientFromGenIdx fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: eb4f7a538e85ade4b095aa3ea5eab4448eda2491
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847989"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="e8cf5-102">PauliCoefficientFromGenIdx fonction)</span><span class="sxs-lookup"><span data-stu-id="e8cf5-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="e8cf5-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e8cf5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e8cf5-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8cf5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8cf5-105">Extrait le coefficient d’un terme Pauli décrit par un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="e8cf5-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="e8cf5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e8cf5-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="e8cf5-107">generatorIndex : [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e8cf5-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e8cf5-108">`GeneratorIndex` type qui encode un terme Pauli.</span><span class="sxs-lookup"><span data-stu-id="e8cf5-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="e8cf5-109">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8cf5-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8cf5-110">Coefficient du terme décrit par un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="e8cf5-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>