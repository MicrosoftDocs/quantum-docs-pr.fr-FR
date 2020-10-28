---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702667"
---
# <a name="equalityfactcp-function"></a>EqualityFactCP fonction)

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Déclare qu’un nombre complexe a la valeur attendue.

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a>Entrée

### <a name="actual--complexpolar"></a>réel : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Valeur à vérifier.


### <a name="expected--complexpolar"></a>ATTENDU : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Valeur attendue.


### <a name="message--string"></a>message : [chaîne](xref:microsoft.quantum.lang-ref.string)

Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

