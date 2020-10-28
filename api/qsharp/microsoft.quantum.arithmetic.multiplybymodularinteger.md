---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Opération MultiplyByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706390"
---
# <a name="multiplybymodularinteger-operation"></a>Opération MultiplyByModularInteger

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Effectue une multiplication modulaire par une constante entière sur un registre qubit.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Description

Faites-nous part `modulus` de $N $ et `constMultiplier` de $a $.
Cette opération implémente ensuite une opération unitaire définie par le mappage suivant sur la base du calcul : $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ pour tous les $y $ entre $0 $ et $N-$1.

## <a name="input"></a>Entrée

### <a name="constmultiplier--int"></a>constMultiplier : [entier](xref:microsoft.quantum.lang-ref.int)

Constante par laquelle le multiplicateur est multiplié. Doit être co-prime au modulo.


### <a name="modulus--int"></a>modulo : [entier](xref:microsoft.quantum.lang-ref.int)

L’opération de multiplication est effectuée par Modulo `modulus` .


### <a name="multiplier--littleendian"></a>multiplicateur : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Nombre multiplié par une constante.
Il s’agit d’un tableau de qubits codant un entier au format Little endian.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

- Pour le schéma du circuit et l’explication, voir la figure 7 à la [page 8 de arXiv : quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)
- Cette opération correspond à U ₐ dans [arXiv : quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)