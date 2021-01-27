---
uid: Microsoft.Quantum.Canon.Fst
title: FST, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840513"
---
# <a name="fst-function"></a>FST, fonction

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’une paire, retourne son premier élément.

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a>Entrée

### <a name="pair--tu"></a>paire : ('t, 'U)

Tuple avec deux éléments.



## <a name="output--t"></a>Sortie : 't

Premier élément de `pair`.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type du premier membre de la paire.
### <a name="u"></a>'U

Type du deuxième membre de la paire.