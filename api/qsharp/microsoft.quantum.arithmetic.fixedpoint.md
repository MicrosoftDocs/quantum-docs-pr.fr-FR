---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Type défini par l’utilisateur FixedPoint
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: f1370cd2f8a7d6488ae0f6be841abd95e61f038e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707294"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="b7b79-102">Type défini par l’utilisateur FixedPoint</span><span class="sxs-lookup"><span data-stu-id="b7b79-102">FixedPoint user defined type</span></span>

<span data-ttu-id="b7b79-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b7b79-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b7b79-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7b79-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7b79-105">Représente un registre de qubits codant un nombre à virgule fixe.</span><span class="sxs-lookup"><span data-stu-id="b7b79-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="b7b79-106">Se compose d’un entier qui est égal au nombre de qubits à gauche du point binaire, c’est-à-dire qubits de poids supérieur ou égal à 1, et d’un registre quantique.</span><span class="sxs-lookup"><span data-stu-id="b7b79-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

