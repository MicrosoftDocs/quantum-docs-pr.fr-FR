---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Opération PrepareIdentity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: ec7e813110ccd9e6d499fc469fa27249a182b870
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855887"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="f10c4-102">Opération PrepareIdentity</span><span class="sxs-lookup"><span data-stu-id="f10c4-102">PrepareIdentity operation</span></span>

<span data-ttu-id="f10c4-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f10c4-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f10c4-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f10c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f10c4-105">Pour un registre donné, prépare ce registre dans l’état le plus maximal mélangé.</span><span class="sxs-lookup"><span data-stu-id="f10c4-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="f10c4-106">Le Registre est préparé dans l’État $ \boldone/2 ^ N $ en appliquant le canal de dépolarisation complet à chaque qubit, où $N $ est la longueur du Registre.</span><span class="sxs-lookup"><span data-stu-id="f10c4-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f10c4-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="f10c4-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="f10c4-108">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f10c4-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f10c4-109">Un registre dont l’État doit être dépolarisé de la manière décrite ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="f10c4-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f10c4-110">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f10c4-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="f10c4-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f10c4-111">See Also</span></span>

- [<span data-ttu-id="f10c4-112">Microsoft. Quantum. PREPARATION. PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="f10c4-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)