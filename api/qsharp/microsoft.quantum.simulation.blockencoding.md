---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: Type défini par l’utilisateur BlockEncoding
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 70cd18f04cbd449f4818ba3b40580303137f84db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857630"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="ebefc-102">Type défini par l’utilisateur BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="ebefc-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="ebefc-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ebefc-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ebefc-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebefc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebefc-105">Représente une unité où un opérateur arbitraire d’intérêt est encodé dans le bloc supérieur gauche.</span><span class="sxs-lookup"><span data-stu-id="ebefc-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="ebefc-106">Autrement dit, un `BlockEncoding` est un $U unitaire $ où un opérateur arbitraire $H $ d’intérêt qui agit sur le registre système `s` est encodé dans le bloc supérieur gauche correspondant à l’État auxiliaire $ \ket {0} _A $.</span><span class="sxs-lookup"><span data-stu-id="ebefc-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="ebefc-107">C'est</span><span class="sxs-lookup"><span data-stu-id="ebefc-107">That is,</span></span>

<span data-ttu-id="ebefc-108">$ $ \begin{align} (\bra {0} _a \otimes I_s) U (\ket {0} _a \otimes I_s) = H \end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="ebefc-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

