---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702655"
---
# <a name="equalityfactr-function"></a>EqualityFactR fonction)

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Déclare qu’une variable de résultat classique a la valeur attendue.

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a>Entrée

### <a name="actual--__invalidresult__"></a>réel : __non <Result> valide__

Variable à vérifier.


### <a name="expected--__invalidresult__"></a>ATTENDU : __non <Result> valide__

Valeur attendue.


### <a name="message--string"></a>message : [chaîne](xref:microsoft.quantum.lang-ref.string)

Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

