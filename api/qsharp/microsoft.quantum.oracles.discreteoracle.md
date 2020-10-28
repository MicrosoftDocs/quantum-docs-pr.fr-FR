---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: Type défini par l’utilisateur DiscreteOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: ccbcc92d4b6f1c800b576ad54739d26665e6d6d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709047"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="ee23c-102">Type défini par l’utilisateur DiscreteOracle</span><span class="sxs-lookup"><span data-stu-id="ee23c-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="ee23c-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="ee23c-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="ee23c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ee23c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ee23c-105">Représente une Oracle discrète.</span><span class="sxs-lookup"><span data-stu-id="ee23c-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="ee23c-106">Il s’agit d’un Oracle qui implémente $U ^ m $ pour une opération fixe $U $ et un entier non négatif $m $.</span><span class="sxs-lookup"><span data-stu-id="ee23c-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

