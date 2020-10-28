---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Type défini par l’utilisateur ComplexPolar
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701329"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="ddc7f-102">Type défini par l’utilisateur ComplexPolar</span><span class="sxs-lookup"><span data-stu-id="ddc7f-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="ddc7f-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ddc7f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ddc7f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ddc7f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ddc7f-105">Représente un nombre complexe sous forme polaire.</span><span class="sxs-lookup"><span data-stu-id="ddc7f-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="ddc7f-106">La représentation polaire d’un nombre complexe est $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="ddc7f-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="ddc7f-107">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="ddc7f-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="ddc7f-108">Magnitude : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ddc7f-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ddc7f-109">Valeur absolue $r \ge $0 de $c $.</span><span class="sxs-lookup"><span data-stu-id="ddc7f-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="ddc7f-110">Argument : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ddc7f-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ddc7f-111">La phase $t \Dans \mathbb R $ de $c $.</span><span class="sxs-lookup"><span data-stu-id="ddc7f-111">The phase $t \in \mathbb R$ of $c$.</span></span>