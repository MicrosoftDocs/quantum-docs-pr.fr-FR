---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: Type défini par l’utilisateur EncodeOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: da947cdc25cb0edd3a4144022bbfc6ecb84c647f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702487"
---
# <a name="encodeop-user-defined-type"></a><span data-ttu-id="ddfcf-102">Type défini par l’utilisateur EncodeOp</span><span class="sxs-lookup"><span data-stu-id="ddfcf-102">EncodeOp user defined type</span></span>

<span data-ttu-id="ddfcf-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ddfcf-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ddfcf-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ddfcf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ddfcf-105">Représente une opération qui encode un registre physique en Registre logique, à l’aide du qubits Scratch fourni.</span><span class="sxs-lookup"><span data-stu-id="ddfcf-105">Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.</span></span>

<span data-ttu-id="ddfcf-106">Le premier argument est le registre physique qui sera encodé, tandis que le deuxième argument est considéré comme le registre de travail qui sera utilisé.</span><span class="sxs-lookup"><span data-stu-id="ddfcf-106">The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.</span></span>

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```
