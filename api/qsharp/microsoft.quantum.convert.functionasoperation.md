---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833836"
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