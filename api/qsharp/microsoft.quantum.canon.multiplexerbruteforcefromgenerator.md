---
uid: Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator
title: MultiplexerBruteForceFromGenerator fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexerBruteForceFromGenerator
qsharp.summary: >-
  Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 650e10b92d9f6cee74765adc09132be36af5fba1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206185"
---
# <a name="multiplexerbruteforcefromgenerator-function"></a>MultiplexerBruteForceFromGenerator fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne une opération unitaire contrôlée par multiplication $U $ qui applique une $V unitaire _j $ lorsqu’elle est contrôlée par le numéro d’État n-qubit $ \ket{j} $.

$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
function MultiplexerBruteForceFromGenerator (unitaryGenerator : (Int, (Int -> (Qubit[] => Unit is Adj + Ctl)))) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="unitarygenerator--intint---qubit--unit--is-adj--ctl"></a>unitaryGenerator : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL)

Tuple où le premier élément `Int` est le nombre d’unités de $N $, et le deuxième élément `(Int -> ('T => () is Adj + Ctl))` est une fonction qui accepte un entier $j $ dans $ [0, N-1] $ et génère l’opération unitaire $V _J $.



## <a name="output--littleendianqubit--unit--is-adj--ctl"></a>Sortie : ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Une opération unitaire à contrôle multiple $U $ qui applique des unités de commande décrites par `unitaryGenerator` .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. MultiplexerBruteForceFromGenerator](xref:Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator)