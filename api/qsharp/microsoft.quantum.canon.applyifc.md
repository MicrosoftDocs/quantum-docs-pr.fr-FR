---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: Opération ApplyIfC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: 35430cb7cf491965b7b69ace6d3f41599dbadd51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218714"
---
# <a name="applyifc-operation"></a>Opération ApplyIfC

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération contrôlable conditionnée sur un bit classique.

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a>Description

Pour une opération donnée `op` et une valeur de bit `bit` , s’applique `op` à `target` si `bit` est `true` . Si `false` , rien ne se passe au `target` .
Le suffixe `C` indique que l’opération à appliquer est contrôlable.

## <a name="input"></a>Entrée

### <a name="op--t--unit--is-ctl"></a>OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL

Opération à appliquer de manière conditionnelle.


### <a name="bit--bool"></a>bit : [bool](xref:microsoft.quantum.lang-ref.bool)

valeur booléenne qui contrôle si l’opération est appliquée ou non.


### <a name="target--t"></a>cible : 't

Entrée à laquelle l’opération est appliquée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération à appliquer de façon conditionnelle.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyIfC](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Microsoft. Quantum. Canon. ApplyIfA](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Microsoft. Quantum. Canon. ApplyIfCA](xref:Microsoft.Quantum.Canon.ApplyIfCA)