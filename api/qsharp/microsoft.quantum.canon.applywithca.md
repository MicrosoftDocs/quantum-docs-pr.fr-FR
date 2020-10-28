---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: Opération ApplyWithCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: abc62791416e78c1b2937a226327b71da8b8e288
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704579"
---
# <a name="applywithca-operation"></a>Opération ApplyWithCA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


À partir de deux opérations, applique une telle que conjuguée à l’autre.

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit
```


## <a name="description"></a>Description

À partir de deux opérations, décrites respectivement par les opérateurs d’unités $U $ et $V $, les applique dans la séquence $U ^ {\dagger} V U $. Autrement dit, cette opération implémente l’opérateur unitaire donné par $V $ conjugué avec $U $.

## <a name="input"></a>Entrée

### <a name="outeroperation--t--unit-adj"></a>outerOperation : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

L’opération $U $ qui doit être utilisée pour conjuguer $V $. Notez que l’opération externe $U $ doit être adjointable, mais qu’elle n’a pas besoin d’être contrôlable.


### <a name="inneroperation--t--unit-adj--ctl"></a>innerOperation : 't = [> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL

L’opération $V être conjuguée.


### <a name="target--t"></a>cible : 't

Entrée à fournir aux opérations externes et internes.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Cible sur laquelle les opérations internes et externes agissent.

## <a name="remarks"></a>Notes

L’opération externe est toujours supposée être adjointable, mais elle n’a pas besoin d’être contrôlable pour que l’opération combinée soit contrôlable.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)
- [Microsoft. Quantum. Canon. ApplyWithA](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [Microsoft. Quantum. Canon. ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)