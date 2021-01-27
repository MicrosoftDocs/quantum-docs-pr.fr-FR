---
uid: Microsoft.Quantum.Convert.Call
title: Opération d’appel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850209"
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