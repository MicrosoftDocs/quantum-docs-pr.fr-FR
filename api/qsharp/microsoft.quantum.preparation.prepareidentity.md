---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Opération PrepareIdentity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: 6e0a43e61e3c49edef94db63f07ed29132d84c83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210435"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="e16a2-102">Opération PrepareIdentity</span><span class="sxs-lookup"><span data-stu-id="e16a2-102">PrepareIdentity operation</span></span>

<span data-ttu-id="e16a2-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e16a2-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e16a2-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e16a2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e16a2-105">Pour un registre donné, prépare ce registre dans l’état le plus maximal mélangé.</span><span class="sxs-lookup"><span data-stu-id="e16a2-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="e16a2-106">Le Registre est préparé dans l’État $ \boldone/2 ^ N $ en appliquant le canal de dépolarisation complet à chaque qubit, où $N $ est la longueur du Registre.</span><span class="sxs-lookup"><span data-stu-id="e16a2-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e16a2-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="e16a2-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="e16a2-108">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e16a2-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e16a2-109">Un registre dont l’État doit être dépolarisé de la manière décrite ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="e16a2-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e16a2-110">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e16a2-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e16a2-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e16a2-111">See Also</span></span>

- [<span data-ttu-id="e16a2-112">Microsoft. Quantum. PREPARATION. PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="e16a2-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)