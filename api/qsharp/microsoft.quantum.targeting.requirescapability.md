---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Type défini par l’utilisateur RequiresCapability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855149"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="76bd8-102">Type défini par l’utilisateur RequiresCapability</span><span class="sxs-lookup"><span data-stu-id="76bd8-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="76bd8-103">Espace de noms : [Microsoft. Quantum. Targeting](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="76bd8-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="76bd8-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="76bd8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="76bd8-105">Attribut reconnu par le compilateur utilisé pour marquer un pouvant être appelé avec les fonctionnalités d’exécution dont il a besoin.</span><span class="sxs-lookup"><span data-stu-id="76bd8-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="76bd8-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="76bd8-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="76bd8-107">Niveau : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="76bd8-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="76bd8-108">Nom du niveau de fonctionnalité d’exécution requis par l’appelable.</span><span class="sxs-lookup"><span data-stu-id="76bd8-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="76bd8-109">Raison : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="76bd8-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="76bd8-110">Description de la raison pour laquelle l’appelable requiert cette fonctionnalité d’exécution.</span><span class="sxs-lookup"><span data-stu-id="76bd8-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="76bd8-111">Notes</span><span class="sxs-lookup"><span data-stu-id="76bd8-111">Remarks</span></span>

<span data-ttu-id="76bd8-112">Cet attribut est automatiquement ajouté à callables par le compilateur, sauf s’il existe déjà une instance de cet attribut sur l’appelable.</span><span class="sxs-lookup"><span data-stu-id="76bd8-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="76bd8-113">Elle ne doit pas être utilisée, sauf dans de rares cas où le compilateur ne déduit pas correctement la capacité requise.</span><span class="sxs-lookup"><span data-stu-id="76bd8-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="76bd8-114">Voici la liste des noms de niveau de fonctionnalité, par ordre croissant des capacités ou des restrictions décroissantes :</span><span class="sxs-lookup"><span data-stu-id="76bd8-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="76bd8-115">Les résultats des mesures ne peuvent pas être comparés pour déterminer leur égalité.</span><span class="sxs-lookup"><span data-stu-id="76bd8-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="76bd8-116">Les résultats de mesure peuvent être comparés pour l’égalité uniquement dans les expressions conditionnelles If-statement dans les opérations.</span><span class="sxs-lookup"><span data-stu-id="76bd8-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="76bd8-117">Le bloc d’une instruction If qui dépend d’un résultat ne peut pas contenir d’instructions SET pour des variables mutables déclarées en dehors du bloc, ou des instructions Return.</span><span class="sxs-lookup"><span data-stu-id="76bd8-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="76bd8-118">Aucune restriction au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="76bd8-118">No runtime restrictions.</span></span> <span data-ttu-id="76bd8-119">Tous les programmes Q # peuvent être exécutés.</span><span class="sxs-lookup"><span data-stu-id="76bd8-119">Any Q# program can be executed.</span></span>