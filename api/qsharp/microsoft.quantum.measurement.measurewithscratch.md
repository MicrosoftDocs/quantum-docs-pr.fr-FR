---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Opération MeasureWithScratch
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706747"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="7517f-102">Opération MeasureWithScratch</span><span class="sxs-lookup"><span data-stu-id="7517f-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="7517f-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="7517f-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="7517f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7517f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7517f-105">Mesure l’opérateur Pauli donné à l’aide d’un qubit de travail explicite pour effectuer la mesure.</span><span class="sxs-lookup"><span data-stu-id="7517f-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="7517f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="7517f-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="7517f-107">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="7517f-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="7517f-108">Opérateur qubit Pauli spécifié sous la forme d’un tableau d’opérateurs Pauli qubit uniques.</span><span class="sxs-lookup"><span data-stu-id="7517f-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="7517f-109">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7517f-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7517f-110">Registre qubit à mesurer.</span><span class="sxs-lookup"><span data-stu-id="7517f-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="7517f-111">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="7517f-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="7517f-112">Résultat de la mesure de l’opérateur Pauli donné sur le `target` Registre.</span><span class="sxs-lookup"><span data-stu-id="7517f-112">The result of measuring the given Pauli operator on the `target` register.</span></span>