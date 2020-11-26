---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: cc1a783dfbf97afae50f4b42e66cba2b2a2ec833
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207426"
---
# <a name="ccontrolledca-function"></a>CControlledCA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dans le cas d’une opération op, retourne une nouvelle opération qui applique le op si un bit de contrôle classique a la valeur true. Si la `false` valeur est, rien ne se produit.
Le modificateur `CA` indique que l’opération est contrôlable et adjointable.

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrée

### <a name="op--t--unit--is-adj--ctl"></a>OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opération à appliquer de manière conditionnelle.



## <a name="output--boolt--unit--is-adj--ctl"></a>Sortie : ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Nouvelle opération qui est op si le bit de contrôle classique a la valeur true.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération à appliquer de façon conditionnelle.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)