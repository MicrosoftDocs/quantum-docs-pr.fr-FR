---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: Opération PrepareSingleQubitIdentity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 1c8c161ec2eae73a81c46e7941af49145cde0493
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193622"
---
# <a name="preparesinglequbitidentity-operation"></a><span data-ttu-id="fd02f-102">Opération PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="fd02f-102">PrepareSingleQubitIdentity operation</span></span>

<span data-ttu-id="fd02f-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="fd02f-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="fd02f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fd02f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fd02f-105">Prépare un qubit dans l’état maximal mélangé.</span><span class="sxs-lookup"><span data-stu-id="fd02f-105">Prepares a qubit in the maximally mixed state.</span></span>

<span data-ttu-id="fd02f-106">Elle prépare le qubit donné dans l’État $ \boldone/$2 en appliquant le canal de dépolarisation $ $ \begin{align} \Omega (\rho) \mathrel{ : =} \frac {1} {4} \ sum_ {\mu \Dans \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}, \end{align} $ $ où $ \sigma \_ i $ correspond à l’opérateur $i $ th Pauli et où $ \rho $ est un opérateur de densité représentant un État mixte.</span><span class="sxs-lookup"><span data-stu-id="fd02f-106">It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.</span></span>

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="fd02f-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="fd02f-107">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="fd02f-108">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fd02f-108">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fd02f-109">Un qubit dont l’État doit être dépolarisé de la manière décrite ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="fd02f-109">A qubit whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fd02f-110">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fd02f-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fd02f-111">Notes</span><span class="sxs-lookup"><span data-stu-id="fd02f-111">Remarks</span></span>

<span data-ttu-id="fd02f-112">L’État mixte $ \boldone/$2 décrivant le résultat de l’application de cette opération à un état décrit de façon implicite une valeur d’attente sur les choix aléatoires effectués dans cette opération.</span><span class="sxs-lookup"><span data-stu-id="fd02f-112">The mixed state $\boldone / 2$ describing the result of applying this operation to a state implicitly describes an expectation value over random choices made in this operation.</span></span>
<span data-ttu-id="fd02f-113">Ainsi, pour n’importe quelle application, cette opération mappe des États purs à des États purs, mais elle agit comme décrit en prévision.</span><span class="sxs-lookup"><span data-stu-id="fd02f-113">Thus, for any single application, this operation maps pure states to pure states, but it acts as described in expectation.</span></span>
<span data-ttu-id="fd02f-114">En particulier, cette opération peut être utilisée dans la tomographie de processus pour mesurer les composants *non unitaires* d’un canal.</span><span class="sxs-lookup"><span data-stu-id="fd02f-114">In particular, this operation can be used in process tomography to measure the *non-unital* components of a channel.</span></span>