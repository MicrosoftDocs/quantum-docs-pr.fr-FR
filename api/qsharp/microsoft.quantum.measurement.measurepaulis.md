---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Opération MeasurePaulis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 7348ab3941af391c451d5c66f888cf3b6662cf20
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706758"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="92e1e-102">Opération MeasurePaulis</span><span class="sxs-lookup"><span data-stu-id="92e1e-102">MeasurePaulis operation</span></span>

<span data-ttu-id="92e1e-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="92e1e-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="92e1e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="92e1e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="92e1e-105">À partir d’un tableau d’opérateurs Pauli à plusieurs qubit, les mesures de chacune à l’aide d’un gadget de mesure spécifié, puis retourne le tableau de résultats.</span><span class="sxs-lookup"><span data-stu-id="92e1e-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="92e1e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="92e1e-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="92e1e-107">Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="92e1e-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="92e1e-108">Tableau d’opérateurs Pauli à plusieurs qubit à mesurer.</span><span class="sxs-lookup"><span data-stu-id="92e1e-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="92e1e-109">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="92e1e-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="92e1e-110">Inscrivez-vous pour mesurer les opérateurs donnés.</span><span class="sxs-lookup"><span data-stu-id="92e1e-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="92e1e-111">Gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="92e1e-111">gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="92e1e-112">Opération qui effectue la mesure d’un opérateur multi-qubit donné.</span><span class="sxs-lookup"><span data-stu-id="92e1e-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="92e1e-113">Sortie : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="92e1e-113">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="92e1e-114">Tableau de résultats obtenus à partir de la mesure de chaque élément de `paulis` on `target` .</span><span class="sxs-lookup"><span data-stu-id="92e1e-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>