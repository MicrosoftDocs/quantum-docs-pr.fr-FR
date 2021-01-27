---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Type défini par l’utilisateur MCMTMask
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 50bec0f9aca95afab83491db6b742d1f0323371f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855375"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="97005-102">Type défini par l’utilisateur MCMTMask</span><span class="sxs-lookup"><span data-stu-id="97005-102">MCMTMask user defined type</span></span>

<span data-ttu-id="97005-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="97005-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="97005-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97005-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97005-105">Type pour représenter une porte Toffoli à plusieurs cibles multiples.</span><span class="sxs-lookup"><span data-stu-id="97005-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="97005-106">Le premier entier est un masque de bits pour les lignes de contrôle.</span><span class="sxs-lookup"><span data-stu-id="97005-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="97005-107">Les index binaires qui sont définis correspondent aux index de ligne de contrôle.</span><span class="sxs-lookup"><span data-stu-id="97005-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="97005-108">Le deuxième entier est un masque de bits pour les lignes cibles.</span><span class="sxs-lookup"><span data-stu-id="97005-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="97005-109">Les index binaires qui sont définis correspondent aux index de lignes cibles.</span><span class="sxs-lookup"><span data-stu-id="97005-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="97005-110">Les index binaires des deux entiers doivent être disjoints.</span><span class="sxs-lookup"><span data-stu-id="97005-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="97005-111">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="97005-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="97005-112">ControlMask : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97005-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="97005-113">TargetMask : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97005-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

