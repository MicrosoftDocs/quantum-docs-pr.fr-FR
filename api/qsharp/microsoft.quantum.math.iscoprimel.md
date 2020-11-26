---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: c78e995801f67822cf98104a7319093d853b6afe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228132"
---
# <a name="iscoprimel-function"></a>IsCoprimeL fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la valeur true si $a $ et $b $ sont copremier et false dans le cas contraire.

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Entrée

### <a name="a--bigint"></a>r : [bigint](xref:microsoft.quantum.lang-ref.bigint)

le premier nombre de co-primality en cours de test


### <a name="b--bigint"></a>b : [bigint](xref:microsoft.quantum.lang-ref.bigint)

deuxième nombre de primality en cours de test



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

True si $a $ et $b $ sont copremier (par exemple, si leur plus grand diviseur commun est 1) et false dans le cas contraire