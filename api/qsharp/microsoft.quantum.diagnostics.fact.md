---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fonction FACT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 6a08703f68f9f38f2224fe4c6a4d255b00756908
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702631"
---
# <a name="fact-function"></a>Fonction FACT

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Déclare qu’une condition classique a la valeur true.

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Entrée

### <a name="actual--bool"></a>réel : [bool](xref:microsoft.quantum.lang-ref.bool)

Condition à déclarer.


### <a name="message--string"></a>message : [chaîne](xref:microsoft.quantum.lang-ref.string)

Chaîne de message d’échec à imprimer dans le cas où la condition classique est false.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Diagnostics. contradiction](xref:Microsoft.Quantum.Diagnostics.Contradiction)