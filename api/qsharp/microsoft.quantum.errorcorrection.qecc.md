---
uid: Microsoft.Quantum.ErrorCorrection.QECC
title: Type défini par l’utilisateur QECC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: QECC
qsharp.summary: Represents an error-correcting code as defined by its encoder, decoder, and syndrome measurement procedure.
ms.openlocfilehash: 6a00875f53928da4e0b8da6a3e32e37a551a56b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702445"
---
# <a name="qecc-user-defined-type"></a><span data-ttu-id="a5efe-102">Type défini par l’utilisateur QECC</span><span class="sxs-lookup"><span data-stu-id="a5efe-102">QECC user defined type</span></span>

<span data-ttu-id="a5efe-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="a5efe-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="a5efe-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5efe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5efe-105">Représente un code de correction des erreurs tel que défini par son encodeur, son décodeur et sa procédure de mesure de syndrome.</span><span class="sxs-lookup"><span data-stu-id="a5efe-105">Represents an error-correcting code as defined by its encoder, decoder, and syndrome measurement procedure.</span></span>

```qsharp

newtype QECC = (Microsoft.Quantum.ErrorCorrection.EncodeOp, Microsoft.Quantum.ErrorCorrection.DecodeOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp);
```

