---
uid: Microsoft.Quantum.Simulation.TimeDependentBlockEncoding
title: Type défini par l’utilisateur TimeDependentBlockEncoding
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentBlockEncoding
qsharp.summary: >-
  Represents a `BlockEncoding` that is controlled by a clock register.

  That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k. \end{align} $$.
ms.openlocfilehash: 1cb3a3cf1e16b194eebd1574da6f9934fc34e5f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709404"
---
# <a name="timedependentblockencoding-user-defined-type"></a><span data-ttu-id="5a06e-102">Type défini par l’utilisateur TimeDependentBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="5a06e-102">TimeDependentBlockEncoding user defined type</span></span>

<span data-ttu-id="5a06e-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5a06e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5a06e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5a06e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5a06e-105">Représente un `BlockEncoding` contrôlé par un registre d’horloge.</span><span class="sxs-lookup"><span data-stu-id="5a06e-105">Represents a `BlockEncoding` that is controlled by a clock register.</span></span>

<span data-ttu-id="5a06e-106">Autrement dit, un `TimeDependentBlockEncoding` est un $U unitaire $ contrôlé par un État $ \ket{k} _D $ dans le registre d’horloge `d` , de telle sorte qu’un opérateur arbitraire $H _K $ d’intérêt qui agit sur le registre système `s` est encodé dans le bloc supérieur gauche correspondant à l’État auxiliaire $ \ket {0} _A $.</span><span class="sxs-lookup"><span data-stu-id="5a06e-106">That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="5a06e-107">C'est</span><span class="sxs-lookup"><span data-stu-id="5a06e-107">That is,</span></span>

<span data-ttu-id="5a06e-108">$ $ \begin{align} (\bra {0} \_ a\otimes I_ {DS}) U (\ket {0} \_ a\otimes I_ {DS}) = \ sum_ {k} \ket{k}\bra{k} \_ d\otimes H_k.</span><span class="sxs-lookup"><span data-stu-id="5a06e-108">$$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k.</span></span>
<span data-ttu-id="5a06e-109">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="5a06e-109">\end{align} $$.</span></span>

```qsharp

newtype TimeDependentBlockEncoding = (((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

