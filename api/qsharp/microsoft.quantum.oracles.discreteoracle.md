---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: Type défini par l’utilisateur DiscreteOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: accbd7b88cc2f6522da20ec1959492310ff0e743
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193894"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="59152-102">Type défini par l’utilisateur DiscreteOracle</span><span class="sxs-lookup"><span data-stu-id="59152-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="59152-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="59152-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="59152-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59152-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59152-105">Représente une Oracle discrète.</span><span class="sxs-lookup"><span data-stu-id="59152-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="59152-106">Il s’agit d’un Oracle qui implémente $U ^ m $ pour une opération fixe $U $ et un entier non négatif $m $.</span><span class="sxs-lookup"><span data-stu-id="59152-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

