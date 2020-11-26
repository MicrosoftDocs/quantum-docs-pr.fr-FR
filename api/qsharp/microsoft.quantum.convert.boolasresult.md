---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: BoolAsResult fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 0190529dd804922a69499fbf1c2c4c916c4b720a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214243"
---
# <a name="boolasresult-function"></a>BoolAsResult fonction)

Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Convertit un `Bool` type en un `Result` type, où `true` est mappé à `One` et `false` est mappé à `Zero` .

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a>Entrée

### <a name="input--bool"></a>entrée : [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool` à convertir.



## <a name="output--__invalidresult__"></a>Sortie : __non <Result> valide__

`Result` représentant `input`.