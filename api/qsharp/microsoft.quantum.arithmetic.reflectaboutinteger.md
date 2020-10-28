---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: Opération ReflectAboutInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706339"
---
# <a name="reflectaboutinteger-operation"></a>Opération ReflectAboutInteger

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Reflète un registre quantique sur un entier classique donné.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Description

À partir d’un registre Quantum initialement dans l’État $ \ sum_i \ alpha_i \ket{i} $, où chaque $ \ket{i} $ est un état de base représentant un entier $i $, reflète l’état du Registre à propos de l’état de base pour un entier donné $ \ket{j} $, $ $ sum_i (-1) ^ {\ delta_ {IJ}} \ alpha_i \ket{i} $ $

## <a name="input"></a>Entrée

### <a name="index--int"></a>index : [int](xref:microsoft.quantum.lang-ref.int)

Entier classique qui indexe l’état de base à partir duquel refléter.


### <a name="reg--littleendian"></a>Reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Cette opération est implémentée sur place, sans allocation explicite de qubits auxiliaire supplémentaires.