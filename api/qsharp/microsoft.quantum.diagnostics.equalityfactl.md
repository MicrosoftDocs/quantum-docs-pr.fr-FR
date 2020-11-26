---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 2aaabf39d6ce49952466a877685776490ef438ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201799"
---
# <a name="equalityfactl-function"></a>EqualityFactL fonction)

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Déclare qu’une variable BigInt classique a la valeur attendue.

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a>Entrée

### <a name="actual--bigint"></a>réel : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Nombre à vérifier.


### <a name="expected--bigint"></a>ATTENDU : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Valeur attendue.


### <a name="message--string"></a>message : [chaîne](xref:microsoft.quantum.lang-ref.string)

Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

