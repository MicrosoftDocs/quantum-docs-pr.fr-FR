---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704403"
---
# <a name="ccontrolledc-function"></a>CControlledC fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Dans le cas d’une opération op, retourne une nouvelle opération qui applique le op si un bit de contrôle classique a la valeur true. Si la `false` valeur est, rien ne se produit.
Le modificateur `C` indique que l’opération est contrôlable.

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a>Entrée

### <a name="op--t--unit-ctl"></a>OP : t => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)

Opération à appliquer de manière conditionnelle.



## <a name="output--boolt--unit-ctl"></a>Sortie : ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)

Nouvelle opération qui est op si le bit de contrôle classique a la valeur true.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération à appliquer de façon conditionnelle.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)