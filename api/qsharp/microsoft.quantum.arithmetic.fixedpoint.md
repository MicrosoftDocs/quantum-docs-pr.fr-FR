---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Type défini par l’utilisateur FixedPoint
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 0fea6e4ee1b8c5391e815217f1ddf9e511d46463
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223100"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="670ee-102">Type défini par l’utilisateur FixedPoint</span><span class="sxs-lookup"><span data-stu-id="670ee-102">FixedPoint user defined type</span></span>

<span data-ttu-id="670ee-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="670ee-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="670ee-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="670ee-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="670ee-105">Représente un registre de qubits codant un nombre à virgule fixe.</span><span class="sxs-lookup"><span data-stu-id="670ee-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="670ee-106">Se compose d’un entier qui est égal au nombre de qubits à gauche du point binaire, c’est-à-dire qubits de poids supérieur ou égal à 1, et d’un registre quantique.</span><span class="sxs-lookup"><span data-stu-id="670ee-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

