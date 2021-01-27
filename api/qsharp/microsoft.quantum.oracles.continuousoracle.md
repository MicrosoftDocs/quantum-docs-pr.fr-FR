---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: Type défini par l’utilisateur ContinuousOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: ac254b7556878550216d5c0c9222620fdc5c5702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855934"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="bf52b-102">Type défini par l’utilisateur ContinuousOracle</span><span class="sxs-lookup"><span data-stu-id="bf52b-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="bf52b-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="bf52b-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="bf52b-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bf52b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bf52b-105">Représente une Oracle à temps continu.</span><span class="sxs-lookup"><span data-stu-id="bf52b-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="bf52b-106">Il s’agit d’un Oracle qui implémente $U (\delta t) : \ket{\Psi (t)} \mapsto \ket{\Psi (t + \delta t)} $ pour toutes les heures $t $, où $U $ est une opération fixe et où $ \delta t $ est un nombre réel non négatif.</span><span class="sxs-lookup"><span data-stu-id="bf52b-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

