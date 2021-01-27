---
uid: Microsoft.Quantum.Bitwise.Or
title: Fonction or
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Or
qsharp.summary: Returns the bitwise OR of two integers. This performs the same computation as the built-in `|||` operator.
ms.openlocfilehash: 811e7cf64424e8302c5745c4c71d76de50ab8c08
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845280"
---
# <a name="or-function"></a>Fonction or

Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Retourne l’opération or au niveau du bit de deux entiers.
Cela effectue le même calcul que l' `|||` opérateur intégré.

```qsharp
function Or (a : Int, b : Int) : Int
```


## <a name="input"></a>Entrée

### <a name="a--int"></a>r : [entier](xref:microsoft.quantum.lang-ref.int)




### <a name="b--int"></a>b : [entier](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>Exemple

```qsharp
let a = 248;      //                 11111000₂
let b = 63;       //                 00111111₂
let x = Or(a, b); // x : Int = 255 = 11111111₂.
```

## <a name="remarks"></a>Notes

Consultez [C# | Pour plus](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/or-operator) d’informations.