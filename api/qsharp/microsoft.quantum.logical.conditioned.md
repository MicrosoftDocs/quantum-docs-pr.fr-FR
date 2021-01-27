---
uid: Microsoft.Quantum.Logical.Conditioned
title: Fonction conditionnée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817298"
---
# <a name="conditioned-function"></a>Fonction conditionnée

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne l’une des deux valeurs, en fonction de la valeur d’une condition booléenne.

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a>Entrée

### <a name="condition--bool"></a>condition : [bool](xref:microsoft.quantum.lang-ref.bool)

Condition utilisée pour contrôler l’entrée retournée.


### <a name="iftrue--t"></a>ifTrue : 't

Valeur à retourner lorsque a la `condition` valeur `true` .


### <a name="iffalse--t"></a>ifFalse : 't

Valeur à retourner lorsque a la `condition` valeur `false` .



## <a name="output--t"></a>Sortie : 't

`ifTrue` Si `condition` est `true` , et dans le `ifFalse` cas contraire.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="remarks"></a>Notes

Contrairement `?|` à l’opérateur, cette fonction n’a pas de court-circuit, de sorte que les deux entrées sont entièrement évaluées.

Jusqu’au comportement de court-circuit, les éléments suivants sont équivalents :

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```