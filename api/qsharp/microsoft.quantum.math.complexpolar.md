---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Type défini par l’utilisateur ComplexPolar
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: a4f3a7b6ffa73271d7ac9674d8c718f6f09c0291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210979"
---
# <a name="complexpolar-user-defined-type"></a>Type défini par l’utilisateur ComplexPolar

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente un nombre complexe sous forme polaire.

La représentation polaire d’un nombre complexe est $c = r e ^ {i t} $.

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a>Éléments nommés

### <a name="magnitude--double"></a>Magnitude : [double](xref:microsoft.quantum.lang-ref.double)

Valeur absolue $r \ge $0 de $c $.
### <a name="argument--double"></a>Argument : [double](xref:microsoft.quantum.lang-ref.double)

La phase $t \Dans \mathbb R $ de $c $.