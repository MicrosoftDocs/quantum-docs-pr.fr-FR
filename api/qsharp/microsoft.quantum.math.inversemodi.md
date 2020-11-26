---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 217ce4cd113ecbc6a06ed83c6c1dcb7baa46387d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195373"
---
# <a name="inversemodi-function"></a>InverseModI fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne $b $ de telle sorte que $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a>Entrée

### <a name="a--int"></a>r : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre en cours d’inversion


### <a name="modulus--int"></a>modulo : [entier](xref:microsoft.quantum.lang-ref.int)

Modulo en fonction duquel les nombres sont inversés



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Entier $b $ de telle sorte que $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.