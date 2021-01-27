---
uid: Microsoft.Quantum.Simulation.TimeDependentBlockEncoding
title: Type défini par l’utilisateur TimeDependentBlockEncoding
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentBlockEncoding
qsharp.summary: >-
  Represents a `BlockEncoding` that is controlled by a clock register.

  That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k. \end{align} $$.
ms.openlocfilehash: e2b191a4fc44f99c88f25da9b1ee6460d936740b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814264"
---
# <a name="timedependentblockencoding-user-defined-type"></a><span data-ttu-id="e8459-102">Type défini par l’utilisateur TimeDependentBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="e8459-102">TimeDependentBlockEncoding user defined type</span></span>

<span data-ttu-id="e8459-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e8459-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e8459-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8459-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8459-105">Représente un `BlockEncoding` contrôlé par un registre d’horloge.</span><span class="sxs-lookup"><span data-stu-id="e8459-105">Represents a `BlockEncoding` that is controlled by a clock register.</span></span>

<span data-ttu-id="e8459-106">Autrement dit, un `TimeDependentBlockEncoding` est un $U unitaire $ contrôlé par un État $ \ket{k} _D $ dans le registre d’horloge `d` , de telle sorte qu’un opérateur arbitraire $H _K $ d’intérêt qui agit sur le registre système `s` est encodé dans le bloc supérieur gauche correspondant à l’État auxiliaire $ \ket {0} _A $.</span><span class="sxs-lookup"><span data-stu-id="e8459-106">That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="e8459-107">C'est</span><span class="sxs-lookup"><span data-stu-id="e8459-107">That is,</span></span>

<span data-ttu-id="e8459-108">$ $ \begin{align} (\bra {0} \_ a\otimes I_ {DS}) U (\ket {0} \_ a\otimes I_ {DS}) = \ sum_ {k} \ket{k}\bra{k} \_ d\otimes H_k.</span><span class="sxs-lookup"><span data-stu-id="e8459-108">$$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k.</span></span>
<span data-ttu-id="e8459-109">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="e8459-109">\end{align} $$.</span></span>

```qsharp

newtype TimeDependentBlockEncoding = (((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

