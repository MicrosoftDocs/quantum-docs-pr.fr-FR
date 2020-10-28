---
uid: Microsoft.Quantum.Logical.Conditioned
title: Fonction conditionnée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707054"
---
# <a name="conditioned-function"></a>Fonction conditionnée

Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Packages [](https://nuget.org/packages/)


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

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```