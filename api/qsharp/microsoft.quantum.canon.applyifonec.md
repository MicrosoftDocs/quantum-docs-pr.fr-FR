---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: Opération ApplyIfOneC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: 24a00d83c1bbe6b07adb27c58fc70bc76af0a910
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209415"
---
# <a name="applyifonec-operation"></a>Opération ApplyIfOneC

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération contrôlable conditionnée sur une valeur de résultat classique qui en est une.

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a>Description

Pour une opération donnée `op` et une valeur de résultat `result` , s’applique `op` à `target` si `result` est `One` . Si `Zero` , rien ne se passe au `target` .
Le suffixe `C` indique que l’opération à appliquer est contrôlable.

## <a name="input"></a>Entrée

### <a name="result--__invalidresult__"></a>résultat : __non <Result> valide__

Résultat de mesure qui contrôle si l’opération est appliquée ou non.


### <a name="op--t--unit--is-ctl"></a>OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL

Opération à appliquer de manière conditionnelle.


### <a name="target--t"></a>cible : 't

Entrée à laquelle l’opération est appliquée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération à appliquer de façon conditionnelle.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyIfOneC](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [Microsoft. Quantum. Canon. ApplyIfOneA](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [Microsoft. Quantum. Canon. ApplyIfOneCA](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)