---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 6c1917d6f1ee69cb29fed1ab173106af1e206533
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216623"
---
# <a name="curriedop-function"></a>CurriedOp fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne une version curryfiée d’une opération sur deux entrées.

Autrement dit, étant donné une opération avec deux entrées, cette fonction applique $f isomorphism (x, y) \equiv f (x) (y) $ de l’expression de la valeur pour retourner une opération d’une entrée qui retourne une opération d’une entrée.

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a>Entrée

### <a name="op--tu--unit"></a>OP : ('t, 'U) => [unité](xref:microsoft.quantum.lang-ref.unit) 

Opération dont l’entrée est une paire.



## <a name="output--t---u--unit"></a>Sortie : 't-> 'U => [unité](xref:microsoft.quantum.lang-ref.unit) 

Opération qui accepte le premier élément d’une paire et retourne une opération qui accepte comme entrée le deuxième élément de l’entrée de l’opération d’origine.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type du premier composant d’une fonction défini sur les paires.
### <a name="u"></a>'U

Type du deuxième composant d’une fonction définie sur les paires.

## <a name="remarks"></a>Notes

Les éléments suivants sont équivalents :

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```