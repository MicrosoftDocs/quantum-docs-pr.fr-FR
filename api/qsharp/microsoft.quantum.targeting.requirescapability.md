---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Type défini par l’utilisateur RequiresCapability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 63b1952d402f1bcb81a8f9d0afc3cdf7aa7e5ed8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709137"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="cfc26-102">Type défini par l’utilisateur RequiresCapability</span><span class="sxs-lookup"><span data-stu-id="cfc26-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="cfc26-103">Espace de noms : [Microsoft. Quantum. Targeting](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="cfc26-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="cfc26-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cfc26-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cfc26-105">Attribut reconnu par le compilateur utilisé pour marquer un pouvant être appelé avec les fonctionnalités d’exécution dont il a besoin.</span><span class="sxs-lookup"><span data-stu-id="cfc26-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="cfc26-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="cfc26-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="cfc26-107">Niveau : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="cfc26-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="cfc26-108">Nom du niveau de fonctionnalité d’exécution requis par l’appelable.</span><span class="sxs-lookup"><span data-stu-id="cfc26-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="cfc26-109">Raison : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="cfc26-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="cfc26-110">Description de la raison pour laquelle l’appelable requiert cette fonctionnalité d’exécution.</span><span class="sxs-lookup"><span data-stu-id="cfc26-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="cfc26-111">Notes</span><span class="sxs-lookup"><span data-stu-id="cfc26-111">Remarks</span></span>

<span data-ttu-id="cfc26-112">Cet attribut est automatiquement ajouté à callables par le compilateur, sauf s’il existe déjà une instance de cet attribut sur l’appelable.</span><span class="sxs-lookup"><span data-stu-id="cfc26-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="cfc26-113">Elle ne doit pas être utilisée, sauf dans de rares cas où le compilateur ne déduit pas correctement la capacité requise.</span><span class="sxs-lookup"><span data-stu-id="cfc26-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="cfc26-114">Voici la liste des noms de niveau de fonctionnalité, par ordre croissant des capacités ou des restrictions décroissantes :</span><span class="sxs-lookup"><span data-stu-id="cfc26-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="cfc26-115">Les résultats des mesures ne peuvent pas être comparés pour déterminer leur égalité.</span><span class="sxs-lookup"><span data-stu-id="cfc26-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="cfc26-116">Les résultats de mesure peuvent être comparés pour l’égalité uniquement dans les expressions conditionnelles If-statement dans les opérations.</span><span class="sxs-lookup"><span data-stu-id="cfc26-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="cfc26-117">Le bloc d’une instruction If qui dépend d’un résultat ne peut pas contenir d’instructions SET pour des variables mutables déclarées en dehors du bloc, ou des instructions Return.</span><span class="sxs-lookup"><span data-stu-id="cfc26-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="cfc26-118">Aucune restriction au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="cfc26-118">No runtime restrictions.</span></span> <span data-ttu-id="cfc26-119">Tous les programmes Q # peuvent être exécutés.</span><span class="sxs-lookup"><span data-stu-id="cfc26-119">Any Q# program can be executed.</span></span>