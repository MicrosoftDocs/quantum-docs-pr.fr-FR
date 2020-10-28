---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Opération Trotter2ImplCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 98ba4db45fa7b7e8f442ba166929142aac4fa5a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703756"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="c234a-102">Opération Trotter2ImplCA</span><span class="sxs-lookup"><span data-stu-id="c234a-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="c234a-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c234a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c234a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c234a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c234a-105">Implémentation de l’intégrateur Trotter-Suzuki de second ordre.</span><span class="sxs-lookup"><span data-stu-id="c234a-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="c234a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c234a-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="c234a-107">nSteps : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c234a-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c234a-108">Nombre d’opérations à décomposer en étapes horaires.</span><span class="sxs-lookup"><span data-stu-id="c234a-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="c234a-109">OP : ([int](xref:microsoft.quantum.lang-ref.int),[double](xref:microsoft.quantum.lang-ref.double), t) [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="c234a-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c234a-110">Opération qui accepte une entrée d’index (type `Int` ) et une entrée de temps (type) `Double` et un registre quantique (type `'T` ) pour la décomposition.</span><span class="sxs-lookup"><span data-stu-id="c234a-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c234a-111">Procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c234a-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c234a-112">Multiplicateur de la taille de chaque étape de la simulation.</span><span class="sxs-lookup"><span data-stu-id="c234a-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="c234a-113">cible : 't</span><span class="sxs-lookup"><span data-stu-id="c234a-113">target : 'T</span></span>

<span data-ttu-id="c234a-114">Registre quantique sur lequel les opérations agissent.</span><span class="sxs-lookup"><span data-stu-id="c234a-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c234a-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c234a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c234a-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c234a-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c234a-117">Peut</span><span class="sxs-lookup"><span data-stu-id="c234a-117">'T</span></span>

<span data-ttu-id="c234a-118">Type sur lequel chaque étape doit agir ; en général, `Qubit[]` ou `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="c234a-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>