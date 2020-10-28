---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 4c7256f9a8c84b4e105b1cbff6b18d6dd99cc441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702673"
---
# <a name="equalityfactc-function"></a>EqualityFactC fonction)

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Déclare qu’un nombre complexe a la valeur attendue.

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a>Entrée

### <a name="actual--complex"></a>réel : [complexe](xref:Microsoft.Quantum.Math.Complex)

Valeur à vérifier.


### <a name="expected--complex"></a>ATTENDU : [complexe](xref:Microsoft.Quantum.Math.Complex)

Valeur attendue.


### <a name="message--string"></a>message : [chaîne](xref:microsoft.quantum.lang-ref.string)

Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

