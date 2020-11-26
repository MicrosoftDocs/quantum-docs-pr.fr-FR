---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Opération Trotter2ImplCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 0e3a7e53a4d415e6b5af81d9bb3f52cddf36c4b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204740"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="730dd-102">Opération Trotter2ImplCA</span><span class="sxs-lookup"><span data-stu-id="730dd-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="730dd-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="730dd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="730dd-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="730dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="730dd-105">Implémentation de l’intégrateur Trotter-Suzuki de second ordre.</span><span class="sxs-lookup"><span data-stu-id="730dd-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="730dd-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="730dd-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="730dd-107">nSteps : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="730dd-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="730dd-108">Nombre d’opérations à décomposer en étapes horaires.</span><span class="sxs-lookup"><span data-stu-id="730dd-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="730dd-109">OP : ([int](xref:microsoft.quantum.lang-ref.int),[double](xref:microsoft.quantum.lang-ref.double), t) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="730dd-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="730dd-110">Opération qui accepte une entrée d’index (type `Int` ) et une entrée de temps (type) `Double` et un registre quantique (type `'T` ) pour la décomposition.</span><span class="sxs-lookup"><span data-stu-id="730dd-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="730dd-111">Procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="730dd-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="730dd-112">Multiplicateur de la taille de chaque étape de la simulation.</span><span class="sxs-lookup"><span data-stu-id="730dd-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="730dd-113">cible : 't</span><span class="sxs-lookup"><span data-stu-id="730dd-113">target : 'T</span></span>

<span data-ttu-id="730dd-114">Registre quantique sur lequel les opérations agissent.</span><span class="sxs-lookup"><span data-stu-id="730dd-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="730dd-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="730dd-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="730dd-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="730dd-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="730dd-117">Peut</span><span class="sxs-lookup"><span data-stu-id="730dd-117">'T</span></span>

<span data-ttu-id="730dd-118">Type sur lequel chaque étape doit agir ; en général, `Qubit[]` ou `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="730dd-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>