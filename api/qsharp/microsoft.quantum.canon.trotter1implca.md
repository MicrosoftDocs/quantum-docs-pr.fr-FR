---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Opération Trotter1ImplCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1b4e0a9597f4f30b8e92ef91ff0780e7c7ecdc9b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204791"
---
# <a name="trotter1implca-operation"></a><span data-ttu-id="c238a-102">Opération Trotter1ImplCA</span><span class="sxs-lookup"><span data-stu-id="c238a-102">Trotter1ImplCA operation</span></span>

<span data-ttu-id="c238a-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c238a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c238a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c238a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c238a-105">Implémentation de l’intégrateur Trotter-Suzuki de premier ordre.</span><span class="sxs-lookup"><span data-stu-id="c238a-105">Implementation of the first-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c238a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c238a-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="c238a-107">nSteps : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c238a-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c238a-108">Nombre d’opérations à décomposer en étapes horaires.</span><span class="sxs-lookup"><span data-stu-id="c238a-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="c238a-109">OP : ([int](xref:microsoft.quantum.lang-ref.int),[double](xref:microsoft.quantum.lang-ref.double), t) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="c238a-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c238a-110">Opération qui accepte une entrée d’index (type `Int` ) et une entrée de temps (type) `Double` et un registre quantique (type `'T` ) pour la décomposition.</span><span class="sxs-lookup"><span data-stu-id="c238a-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c238a-111">Procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c238a-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c238a-112">Multiplicateur de la taille de chaque étape de la simulation.</span><span class="sxs-lookup"><span data-stu-id="c238a-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="c238a-113">cible : 't</span><span class="sxs-lookup"><span data-stu-id="c238a-113">target : 'T</span></span>

<span data-ttu-id="c238a-114">Registre quantique sur lequel les opérations agissent.</span><span class="sxs-lookup"><span data-stu-id="c238a-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c238a-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c238a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c238a-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c238a-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c238a-117">Peut</span><span class="sxs-lookup"><span data-stu-id="c238a-117">'T</span></span>

<span data-ttu-id="c238a-118">Type sur lequel chaque étape doit agir ; en général, `Qubit[]` ou `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="c238a-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>