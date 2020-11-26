---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224375"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation fonction)

Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Convertit des fonctions en opérations.

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a>Description

Pour une fonction donnée, retourne une opération qui appelle cette fonction et qui ne fait rien d’autre.

## <a name="input"></a>Entrée

### <a name="fn--input---output"></a>FN : sortie’Input-> '

Fonction à convertir en une opération.



## <a name="output--input--output"></a>Sortie : sortie’Input => ' 

Opération `op` qui `op(input)` est identique à `fn(input)` pour All `input` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="input"></a>'Entrée

Type d’entrée de la fonction à convertir.
### <a name="output"></a>'Sortie

Type de sortie de la fonction à convertir.

## <a name="remarks"></a>Notes

Cela est principalement utile pour passer des fonctions à des fonctions ou des opérations qui attendent une opération comme entrée.