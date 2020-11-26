---
uid: Microsoft.Quantum.Convert.Call
title: Opération d’appel
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214209"
---
# <a name="call-operation"></a>Opération d’appel

Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Appelle une fonction avec une entrée donnée.

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>Description

À partir d’une fonction et d’une entrée de cette fonction, appelle la fonction et retourne sa sortie.

## <a name="input"></a>Entrée

### <a name="fn--input---output"></a>FN : sortie’Input-> '

Fonction à appeler.


### <a name="input--input"></a>entrée : 'Input

Entrée à passer à la fonction.



## <a name="output--output"></a>Sortie : 'Output

Résultat de l’appel de `fn`.

## <a name="type-parameters"></a>Paramètres de type

### <a name="input"></a>'Entrée


### <a name="output"></a>'Sortie



## <a name="remarks"></a>Notes

Cette opération est principalement utile pour forcer l’appel d’une fonction à un emplacement spécifique au sein d’une opération, ou pour appeler une fonction dans laquelle une opération est attendue.