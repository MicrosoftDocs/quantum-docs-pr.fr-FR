---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703057"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="fb64e-102">MeasurementOperators fonction)</span><span class="sxs-lookup"><span data-stu-id="fb64e-102">MeasurementOperators function</span></span>

<span data-ttu-id="fb64e-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="fb64e-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="fb64e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fb64e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fb64e-105">Calcule tous les opérateurs de mesure requis pour calculer l’attente d’un terme Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="fb64e-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="fb64e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="fb64e-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="fb64e-107">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fb64e-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fb64e-108">Nombre de qubits nécessaires pour simuler le système moléculaire.</span><span class="sxs-lookup"><span data-stu-id="fb64e-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="fb64e-109">index : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fb64e-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fb64e-110">Tableau contenant les index du qubit auquel chaque opérateur Pauli est appliqué.</span><span class="sxs-lookup"><span data-stu-id="fb64e-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="fb64e-111">termType : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fb64e-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fb64e-112">Type du terme Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="fb64e-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="fb64e-113">Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="fb64e-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="fb64e-114">Tableau d’opérateurs de mesure (chacun étant un tableau de Pauli).</span><span class="sxs-lookup"><span data-stu-id="fb64e-114">An array of measurement operators (each being an array of Pauli).</span></span>