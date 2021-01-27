---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Type défini par l’utilisateur ComplexPolar
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847346"
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