---
uid: Microsoft.Quantum.Canon.ApplyWithA
title: Opération ApplyWithA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: f1ff31da53952931426d358cbedad44a50d87f5e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704603"
---
# <a name="applywitha-operation"></a>Opération ApplyWithA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


À partir de deux opérations, applique une telle que conjuguée à l’autre.

```qsharp
operation ApplyWithA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj), target : 'T) : Unit
```


## <a name="description"></a>Description

À partir de deux opérations, décrites respectivement par les opérateurs d’unités $U $ et $V $, les applique dans la séquence $U ^ {\dagger} V U $. Autrement dit, cette opération implémente l’opérateur unitaire donné par $V $ conjugué avec $U $.

## <a name="input"></a>Entrée

### <a name="outeroperation--t--unit-adj"></a>outerOperation : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

L’opération $U $ qui doit être utilisée pour conjuguer $V $. Notez que l’opération externe $U $ doit être adjointable, mais qu’elle n’a pas besoin d’être contrôlable.


### <a name="inneroperation--t--unit-adj"></a>innerOperation : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

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