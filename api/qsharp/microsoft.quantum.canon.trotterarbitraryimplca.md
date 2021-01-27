---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: Opération TrotterArbitraryImplCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: bb93517a479ce344277bfe97d070e6630a8fccc0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840095"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="d7f09-102">Opération TrotterArbitraryImplCA</span><span class="sxs-lookup"><span data-stu-id="d7f09-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="d7f09-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d7f09-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d7f09-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d7f09-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d7f09-105">Implémentation récursive de l’intégrateur Trotter-Suzuki pair-Order.</span><span class="sxs-lookup"><span data-stu-id="d7f09-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d7f09-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d7f09-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="d7f09-107">commande : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d7f09-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d7f09-108">Ordre de Trotter-Suzuki intégrateur.</span><span class="sxs-lookup"><span data-stu-id="d7f09-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="d7f09-109">nSteps : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d7f09-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d7f09-110">Nombre d’opérations à décomposer en étapes horaires.</span><span class="sxs-lookup"><span data-stu-id="d7f09-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="d7f09-111">OP : ([int](xref:microsoft.quantum.lang-ref.int),[double](xref:microsoft.quantum.lang-ref.double), t) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="d7f09-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d7f09-112">Opération qui accepte une entrée d’index (type `Int` ) et une entrée de temps (type) `Double` et un registre quantique (type `'T` ) pour la décomposition.</span><span class="sxs-lookup"><span data-stu-id="d7f09-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="d7f09-113">Procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d7f09-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d7f09-114">Multiplicateur de la taille de chaque étape de la simulation.</span><span class="sxs-lookup"><span data-stu-id="d7f09-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="d7f09-115">cible : 't</span><span class="sxs-lookup"><span data-stu-id="d7f09-115">target : 'T</span></span>

<span data-ttu-id="d7f09-116">Registre quantique sur lequel les opérations agissent.</span><span class="sxs-lookup"><span data-stu-id="d7f09-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7f09-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7f09-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d7f09-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="d7f09-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d7f09-119">Peut</span><span class="sxs-lookup"><span data-stu-id="d7f09-119">'T</span></span>

<span data-ttu-id="d7f09-120">Type sur lequel chaque étape doit agir ; en général, `Qubit[]` ou `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="d7f09-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>