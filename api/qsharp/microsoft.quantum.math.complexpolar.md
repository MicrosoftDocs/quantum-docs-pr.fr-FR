---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Type défini par l’utilisateur ComplexPolar
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701329"
---
# <a name="complexpolar-user-defined-type"></a>Type défini par l’utilisateur ComplexPolar

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Packages [](https://nuget.org/packages/)


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