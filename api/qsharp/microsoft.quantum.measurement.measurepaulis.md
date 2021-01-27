---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Opération MeasurePaulis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853767"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="1ae8a-102">Opération MeasurePaulis</span><span class="sxs-lookup"><span data-stu-id="1ae8a-102">MeasurePaulis operation</span></span>

<span data-ttu-id="1ae8a-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="1ae8a-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="1ae8a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1ae8a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1ae8a-105">À partir d’un tableau d’opérateurs Pauli à plusieurs qubit, les mesures de chacune à l’aide d’un gadget de mesure spécifié, puis retourne le tableau de résultats.</span><span class="sxs-lookup"><span data-stu-id="1ae8a-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="1ae8a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1ae8a-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="1ae8a-107">Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="1ae8a-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="1ae8a-108">Tableau d’opérateurs Pauli à plusieurs qubit à mesurer.</span><span class="sxs-lookup"><span data-stu-id="1ae8a-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="1ae8a-109">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1ae8a-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1ae8a-110">Inscrivez-vous pour mesurer les opérateurs donnés.</span><span class="sxs-lookup"><span data-stu-id="1ae8a-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="1ae8a-111">Gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="1ae8a-111">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="1ae8a-112">Opération qui effectue la mesure d’un opérateur multi-qubit donné.</span><span class="sxs-lookup"><span data-stu-id="1ae8a-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="1ae8a-113">Sortie : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="1ae8a-113">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="1ae8a-114">Tableau de résultats obtenus à partir de la mesure de chaque élément de `paulis` on `target` .</span><span class="sxs-lookup"><span data-stu-id="1ae8a-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>