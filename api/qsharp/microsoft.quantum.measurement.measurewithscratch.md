---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Opération MeasureWithScratch
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: c42316a811e0e4a81c7f244c093a2be88fe5c733
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227061"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="475bf-102">Opération MeasureWithScratch</span><span class="sxs-lookup"><span data-stu-id="475bf-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="475bf-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="475bf-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="475bf-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="475bf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="475bf-105">Mesure l’opérateur Pauli donné à l’aide d’un qubit de travail explicite pour effectuer la mesure.</span><span class="sxs-lookup"><span data-stu-id="475bf-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="475bf-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="475bf-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="475bf-107">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="475bf-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="475bf-108">Opérateur qubit Pauli spécifié sous la forme d’un tableau d’opérateurs Pauli qubit uniques.</span><span class="sxs-lookup"><span data-stu-id="475bf-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="475bf-109">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="475bf-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="475bf-110">Registre qubit à mesurer.</span><span class="sxs-lookup"><span data-stu-id="475bf-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="475bf-111">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="475bf-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="475bf-112">Résultat de la mesure de l’opérateur Pauli donné sur le `target` Registre.</span><span class="sxs-lookup"><span data-stu-id="475bf-112">The result of measuring the given Pauli operator on the `target` register.</span></span>