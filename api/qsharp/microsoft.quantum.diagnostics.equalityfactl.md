---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702661"
---
# <a name="equalityfactl-function"></a>EqualityFactL fonction)

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


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

