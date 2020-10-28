---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: Type défini par l’utilisateur BlockEncoding
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 1b769c58fd23b4ebc9d779cec3c47d8275822e5a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708090"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="832a6-102">Type défini par l’utilisateur BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="832a6-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="832a6-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="832a6-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="832a6-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="832a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="832a6-105">Représente une unité où un opérateur arbitraire d’intérêt est encodé dans le bloc supérieur gauche.</span><span class="sxs-lookup"><span data-stu-id="832a6-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="832a6-106">Autrement dit, un `BlockEncoding` est un $U unitaire $ où un opérateur arbitraire $H $ d’intérêt qui agit sur le registre système `s` est encodé dans le bloc supérieur gauche correspondant à l’État auxiliaire $ \ket {0} _A $.</span><span class="sxs-lookup"><span data-stu-id="832a6-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="832a6-107">C'est</span><span class="sxs-lookup"><span data-stu-id="832a6-107">That is,</span></span>

<span data-ttu-id="832a6-108">$ $ \begin{align} (\bra {0} _a \otimes I_s) U (\ket {0} _a \otimes I_s) = H \end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="832a6-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

