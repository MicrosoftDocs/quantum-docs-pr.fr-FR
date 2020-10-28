---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702628"
---
# <a name="formattedfailure-function"></a>FormattedFailure fonction)

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Fonction interne utilisée pour échouer avec des messages d’erreur significatifs.

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a>Entrée

### <a name="actual--t"></a>réel : 't




### <a name="expected--t"></a>ATTENDU : 't




### <a name="message--string"></a>message : [chaîne](xref:microsoft.quantum.lang-ref.string)





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="remarks"></a>Notes

Cette fonction est destinée à être émulée par les runtimes de simulation, afin de permettre le transfert des contradictions mises en forme.