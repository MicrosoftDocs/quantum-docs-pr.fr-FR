---
uid: Microsoft.Quantum.Canon.Fst
title: FST, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704179"
---
# <a name="fst-function"></a>FST, fonction

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


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