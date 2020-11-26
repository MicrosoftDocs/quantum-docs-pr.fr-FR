---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 0d768114c84025a067e0b60762e6834fbd36deb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228183"
---
# <a name="inversemodl-function"></a>InverseModL fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne $b $ de telle sorte que $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Entrée

### <a name="a--bigint"></a>r : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Nombre en cours d’inversion


### <a name="modulus--bigint"></a>modulo : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Modulo en fonction duquel les nombres sont inversés



## <a name="output--bigint"></a>Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Entier $b $ de telle sorte que $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.