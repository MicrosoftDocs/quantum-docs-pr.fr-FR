---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: a5ea9a776f522e927f2f4545bd417d35bda83994
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214345"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="3ea6d-102">MeasurementOperators fonction)</span><span class="sxs-lookup"><span data-stu-id="3ea6d-102">MeasurementOperators function</span></span>

<span data-ttu-id="3ea6d-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="3ea6d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="3ea6d-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="3ea6d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="3ea6d-105">Calcule tous les opérateurs de mesure requis pour calculer l’attente d’un terme Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="3ea6d-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="3ea6d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3ea6d-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="3ea6d-107">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ea6d-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ea6d-108">Nombre de qubits nécessaires pour simuler le système moléculaire.</span><span class="sxs-lookup"><span data-stu-id="3ea6d-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="3ea6d-109">index : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3ea6d-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3ea6d-110">Tableau contenant les index du qubit auquel chaque opérateur Pauli est appliqué.</span><span class="sxs-lookup"><span data-stu-id="3ea6d-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="3ea6d-111">termType : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ea6d-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ea6d-112">Type du terme Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="3ea6d-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="3ea6d-113">Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="3ea6d-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="3ea6d-114">Tableau d’opérateurs de mesure (chacun étant un tableau de Pauli).</span><span class="sxs-lookup"><span data-stu-id="3ea6d-114">An array of measurement operators (each being an array of Pauli).</span></span>