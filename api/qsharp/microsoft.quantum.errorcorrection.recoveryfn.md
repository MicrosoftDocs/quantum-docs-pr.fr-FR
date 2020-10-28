---
uid: Microsoft.Quantum.ErrorCorrection.RecoveryFn
title: Type défini par l’utilisateur RecoveryFn
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoveryFn
qsharp.summary: Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.
ms.openlocfilehash: 6f4db7312fadbd8ca4c6b8533f78c2c5a886f30e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702421"
---
# <a name="recoveryfn-user-defined-type"></a><span data-ttu-id="9b80e-102">Type défini par l’utilisateur RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="9b80e-102">RecoveryFn user defined type</span></span>

<span data-ttu-id="9b80e-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="9b80e-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="9b80e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9b80e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9b80e-105">Type pour la fonction qui mappe un syndrome d’erreur à une séquence d' `Pauli[]` opérations qui corrigent l’erreur détectée.</span><span class="sxs-lookup"><span data-stu-id="9b80e-105">Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.</span></span>

```qsharp

newtype RecoveryFn = ((Microsoft.Quantum.ErrorCorrection.Syndrome -> Pauli[]));
```

