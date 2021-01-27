---
uid: Microsoft.Quantum.Logical.Conditioned
title: Fonction conditionnée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817298"
---
# <a name="conditioned-function"></a><span data-ttu-id="275f5-102">Fonction conditionnée</span><span class="sxs-lookup"><span data-stu-id="275f5-102">Conditioned function</span></span>

<span data-ttu-id="275f5-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="275f5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="275f5-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="275f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="275f5-105">Retourne l’une des deux valeurs, en fonction de la valeur d’une condition booléenne.</span><span class="sxs-lookup"><span data-stu-id="275f5-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="275f5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="275f5-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="275f5-107">condition : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="275f5-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="275f5-108">Condition utilisée pour contrôler l’entrée retournée.</span><span class="sxs-lookup"><span data-stu-id="275f5-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="275f5-109">ifTrue : 't</span><span class="sxs-lookup"><span data-stu-id="275f5-109">ifTrue : 'T</span></span>

<span data-ttu-id="275f5-110">Valeur à retourner lorsque a la `condition` valeur `true` .</span><span class="sxs-lookup"><span data-stu-id="275f5-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="275f5-111">ifFalse : 't</span><span class="sxs-lookup"><span data-stu-id="275f5-111">ifFalse : 'T</span></span>

<span data-ttu-id="275f5-112">Valeur à retourner lorsque a la `condition` valeur `false` .</span><span class="sxs-lookup"><span data-stu-id="275f5-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="275f5-113">Sortie : 't</span><span class="sxs-lookup"><span data-stu-id="275f5-113">Output : 'T</span></span>

<span data-ttu-id="275f5-114">`ifTrue` Si `condition` est `true` , et dans le `ifFalse` cas contraire.</span><span class="sxs-lookup"><span data-stu-id="275f5-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="275f5-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="275f5-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="275f5-116">Peut</span><span class="sxs-lookup"><span data-stu-id="275f5-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="275f5-117">Notes</span><span class="sxs-lookup"><span data-stu-id="275f5-117">Remarks</span></span>

<span data-ttu-id="275f5-118">Contrairement `?|` à l’opérateur, cette fonction n’a pas de court-circuit, de sorte que les deux entrées sont entièrement évaluées.</span><span class="sxs-lookup"><span data-stu-id="275f5-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="275f5-119">Jusqu’au comportement de court-circuit, les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="275f5-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```