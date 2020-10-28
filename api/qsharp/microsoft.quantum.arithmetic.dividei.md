---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Opération de division
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707342"
---
# <a name="dividei-operation"></a>Opération de division

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Divise deux entiers quantiques.

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Description

`xs` contiendra le reste `xs - floor(xs/ys) * ys` et contiendra `result` `floor(xs/ys)` .

## <a name="input"></a>Entrée

### <a name="xs--littleendian"></a>XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n dividende de $ bits, sera remplacé par le reste.


### <a name="ys--littleendian"></a>distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

diviseur de $n $ bits


### <a name="result--littleendian"></a>résultat : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n résultat de $ bits, doit être initialement dans l’État $ \ket {0} $ et sera remplacé par le résultat de la Division d’entier.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Utilise une approche standard de décalage et de soustraction pour implémenter la Division.
La version contrôlée est spécialisée, de sorte que la soustraction ne nécessite pas de contrôles supplémentaires.