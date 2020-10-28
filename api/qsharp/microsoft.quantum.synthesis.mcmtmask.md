---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Type défini par l’utilisateur MCMTMask
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 0d3ca12d55fa4b5e8332d50939954de29e39b715
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709293"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="8dc47-102">Type défini par l’utilisateur MCMTMask</span><span class="sxs-lookup"><span data-stu-id="8dc47-102">MCMTMask user defined type</span></span>

<span data-ttu-id="8dc47-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="8dc47-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="8dc47-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8dc47-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8dc47-105">Type pour représenter une porte Toffoli à plusieurs cibles multiples.</span><span class="sxs-lookup"><span data-stu-id="8dc47-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="8dc47-106">Le premier entier est un masque de bits pour les lignes de contrôle.</span><span class="sxs-lookup"><span data-stu-id="8dc47-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="8dc47-107">Les index binaires qui sont définis correspondent aux index de ligne de contrôle.</span><span class="sxs-lookup"><span data-stu-id="8dc47-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="8dc47-108">Le deuxième entier est un masque de bits pour les lignes cibles.</span><span class="sxs-lookup"><span data-stu-id="8dc47-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="8dc47-109">Les index binaires qui sont définis correspondent aux index de lignes cibles.</span><span class="sxs-lookup"><span data-stu-id="8dc47-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="8dc47-110">Les index binaires des deux entiers doivent être disjoints.</span><span class="sxs-lookup"><span data-stu-id="8dc47-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="8dc47-111">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="8dc47-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="8dc47-112">ControlMask : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8dc47-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="8dc47-113">TargetMask : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8dc47-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

