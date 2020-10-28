---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: Opération MultiplyAndAddByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 3f85f6aaea1d6f8095709c6f387322df7a5e047c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706403"
---
# <a name="multiplyandaddbymodularinteger-operation"></a>Opération MultiplyAndAddByModularInteger

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Effectue une multiplication et un ajout modulaires par des constantes entières sur un registre qubit.

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Description

Implémente le mappage $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $ $ pour un modulo donné $N $, multiplicateur de constante $a $ et opérande $y $.

## <a name="input"></a>Entrée

### <a name="constmultiplier--int"></a>constMultiplier : [entier](xref:microsoft.quantum.lang-ref.int)

Entier $a $ à ajouter à chaque étiquette d’état de base.


### <a name="modulus--int"></a>modulo : [entier](xref:microsoft.quantum.lang-ref.int)

Le modulo $N $, que l’addition et la multiplication sont prises en ce qui concerne.


### <a name="multiplier--littleendian"></a>multiplicateur : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registre quantique qui représente un entier non signé dont la valeur doit être ajoutée à chaque étiquette d’état de base de `summand` .


### <a name="summand--littleendian"></a>opérande : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registre quantique qui représente un entier non signé à utiliser comme cible pour cette opération.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

- Pour le schéma du circuit et l’explication, voir la figure 6 à la [page 7 de arXiv : quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)
- Cette opération correspond à CMULT (a) MOD (N) dans [arXiv : quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arithmetic. MultiplyAndAddPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)