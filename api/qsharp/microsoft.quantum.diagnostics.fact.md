---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fonction FACT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853318"
---
# <a name="fact-function"></a>Fonction FACT

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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



## <a name="example"></a>Exemple

L’extrait de code Q # suivant échoue :

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Diagnostics. contradiction](xref:Microsoft.Quantum.Diagnostics.Contradiction)