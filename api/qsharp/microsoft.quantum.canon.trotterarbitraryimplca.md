---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: Opération TrotterArbitraryImplCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1c094d09ac8bdd71a59ef57d8715a6f90f18efc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703747"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="5a06c-102">Opération TrotterArbitraryImplCA</span><span class="sxs-lookup"><span data-stu-id="5a06c-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="5a06c-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5a06c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5a06c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5a06c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5a06c-105">Implémentation récursive de l’intégrateur Trotter-Suzuki pair-Order.</span><span class="sxs-lookup"><span data-stu-id="5a06c-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="5a06c-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="5a06c-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="5a06c-107">commande : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5a06c-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5a06c-108">Ordre de Trotter-Suzuki intégrateur.</span><span class="sxs-lookup"><span data-stu-id="5a06c-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="5a06c-109">nSteps : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5a06c-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5a06c-110">Nombre d’opérations à décomposer en étapes horaires.</span><span class="sxs-lookup"><span data-stu-id="5a06c-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="5a06c-111">OP : ([int](xref:microsoft.quantum.lang-ref.int),[double](xref:microsoft.quantum.lang-ref.double), t) [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="5a06c-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5a06c-112">Opération qui accepte une entrée d’index (type `Int` ) et une entrée de temps (type) `Double` et un registre quantique (type `'T` ) pour la décomposition.</span><span class="sxs-lookup"><span data-stu-id="5a06c-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="5a06c-113">Procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5a06c-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5a06c-114">Multiplicateur de la taille de chaque étape de la simulation.</span><span class="sxs-lookup"><span data-stu-id="5a06c-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="5a06c-115">cible : 't</span><span class="sxs-lookup"><span data-stu-id="5a06c-115">target : 'T</span></span>

<span data-ttu-id="5a06c-116">Registre quantique sur lequel les opérations agissent.</span><span class="sxs-lookup"><span data-stu-id="5a06c-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a06c-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a06c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5a06c-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="5a06c-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5a06c-119">Peut</span><span class="sxs-lookup"><span data-stu-id="5a06c-119">'T</span></span>

<span data-ttu-id="5a06c-120">Type sur lequel chaque étape doit agir ; en général, `Qubit[]` ou `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="5a06c-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>