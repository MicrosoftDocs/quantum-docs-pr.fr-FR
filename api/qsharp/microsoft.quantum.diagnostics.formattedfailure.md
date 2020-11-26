---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: da809c04059d4fd0f0ec92412a3094f5b582fd91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201697"
---
# <a name="formattedfailure-function"></a>FormattedFailure fonction)

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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