---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: Type défini par l’utilisateur ContinuousOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: 9bc9b4bbdab6905a6a79893b1d559425ac679400
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708786"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="87109-102">Type défini par l’utilisateur ContinuousOracle</span><span class="sxs-lookup"><span data-stu-id="87109-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="87109-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="87109-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="87109-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87109-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="87109-105">Représente une Oracle à temps continu.</span><span class="sxs-lookup"><span data-stu-id="87109-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="87109-106">Il s’agit d’un Oracle qui implémente $U (\delta t) : \ket{\Psi (t)} \mapsto \ket{\Psi (t + \delta t)} $ pour toutes les heures $t $, où $U $ est une opération fixe et où $ \delta t $ est un nombre réel non négatif.</span><span class="sxs-lookup"><span data-stu-id="87109-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

