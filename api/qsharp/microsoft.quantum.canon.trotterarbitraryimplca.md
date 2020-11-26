---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: Opération TrotterArbitraryImplCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 2abfbb9d51a98d8ede1b0835875a3771ffda0691
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204723"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="9b09f-102">Opération TrotterArbitraryImplCA</span><span class="sxs-lookup"><span data-stu-id="9b09f-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="9b09f-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9b09f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9b09f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b09f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b09f-105">Implémentation récursive de l’intégrateur Trotter-Suzuki pair-Order.</span><span class="sxs-lookup"><span data-stu-id="9b09f-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9b09f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9b09f-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="9b09f-107">commande : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9b09f-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9b09f-108">Ordre de Trotter-Suzuki intégrateur.</span><span class="sxs-lookup"><span data-stu-id="9b09f-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="9b09f-109">nSteps : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9b09f-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9b09f-110">Nombre d’opérations à décomposer en étapes horaires.</span><span class="sxs-lookup"><span data-stu-id="9b09f-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="9b09f-111">OP : ([int](xref:microsoft.quantum.lang-ref.int),[double](xref:microsoft.quantum.lang-ref.double), t) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="9b09f-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9b09f-112">Opération qui accepte une entrée d’index (type `Int` ) et une entrée de temps (type) `Double` et un registre quantique (type `'T` ) pour la décomposition.</span><span class="sxs-lookup"><span data-stu-id="9b09f-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="9b09f-113">Procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9b09f-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9b09f-114">Multiplicateur de la taille de chaque étape de la simulation.</span><span class="sxs-lookup"><span data-stu-id="9b09f-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="9b09f-115">cible : 't</span><span class="sxs-lookup"><span data-stu-id="9b09f-115">target : 'T</span></span>

<span data-ttu-id="9b09f-116">Registre quantique sur lequel les opérations agissent.</span><span class="sxs-lookup"><span data-stu-id="9b09f-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b09f-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b09f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9b09f-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9b09f-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9b09f-119">Peut</span><span class="sxs-lookup"><span data-stu-id="9b09f-119">'T</span></span>

<span data-ttu-id="9b09f-120">Type sur lequel chaque étape doit agir ; en général, `Qubit[]` ou `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="9b09f-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>