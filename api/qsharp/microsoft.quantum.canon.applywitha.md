---
uid: Microsoft.Quantum.Canon.ApplyWithA
title: Opération ApplyWithA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: b8847d4b3ddb88031ef360f183b86f6483706cc6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207868"
---
# <a name="applywitha-operation"></a>Opération ApplyWithA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir de deux opérations, applique une telle que conjuguée à l’autre.

```qsharp
operation ApplyWithA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj), target : 'T) : Unit is Adj
```


## <a name="description"></a>Description

À partir de deux opérations, décrites respectivement par les opérateurs d’unités $U $ et $V $, les applique dans la séquence $U ^ {\dagger} V U $. Autrement dit, cette opération implémente l’opérateur unitaire donné par $V $ conjugué avec $U $.

## <a name="input"></a>Entrée

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

L’opération $U $ qui doit être utilisée pour conjuguer $V $. Notez que l’opération externe $U $ doit être adjointable, mais qu’elle n’a pas besoin d’être contrôlable.


### <a name="inneroperation--t--unit--is-adj"></a>innerOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

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
- [Microsoft. Quantum. Canon. ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [Microsoft. Quantum. Canon. ApplyWithCA](xref:Microsoft.Quantum.Canon.ApplyWithCA)