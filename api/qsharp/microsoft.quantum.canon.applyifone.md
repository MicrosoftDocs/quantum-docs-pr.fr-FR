---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: Opération ApplyIfOne
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: b7c07e01ebcaf2d475283bea0695aa68dd10776e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209398"
---
# <a name="applyifone-operation"></a>Opération ApplyIfOne

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération conditionnée sur une valeur de résultat classique qui en est une.

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a>Description

Pour une opération donnée `op` et une valeur de résultat `result` , s’applique `op` à `target` si `result` est `One` . Si `Zero` , rien ne se passe au `target` .

## <a name="input"></a>Entrée

### <a name="result--__invalidresult__"></a>résultat : __non <Result> valide__

Résultat de mesure qui contrôle si l’opération est appliquée ou non.


### <a name="op--t--unit"></a>OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit) 

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