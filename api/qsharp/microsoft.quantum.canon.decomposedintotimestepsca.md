---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: e82df36d2e4f3767a152d5c92d7b1897c744a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840687"
---
# <a name="decomposedintotimestepsca-function"></a>DecomposedIntoTimeStepsCA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne une opération implémentant l’intégrateur Trotter – Suzuki pour une opération donnée.

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="nsteps--int"></a>nSteps : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre d’opérations à décomposer en étapes horaires.


### <a name="op--intdoublet--unit--is-adj--ctl"></a>OP : ([int](xref:microsoft.quantum.lang-ref.int),[double](xref:microsoft.quantum.lang-ref.double), t) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opération qui accepte une entrée d’index (type `Int` ) et une entrée de temps (type `Double` ) pour la décomposition.


### <a name="trotterorder--int"></a>trotterOrder : [entier](xref:microsoft.quantum.lang-ref.int)

Sélectionne l’ordre de l’intégrateur Trotter-Suzuki à utiliser.
Ordre 1 et même commandes 2, 4, 6,... sont actuellement pris en charge.



## <a name="output--doublet--unit--is-adj--ctl"></a>Sortie : ([double](xref:microsoft.quantum.lang-ref.double), 't) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Retourne un qui implémente l’intégrateur Trotter – Suzuki, où le premier paramètre `Double` est la taille de l’étape d’intégration, et le deuxième paramètre est la cible sur laquelle agir.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type sur lequel chaque étape doit agir ; en général, `Qubit[]` ou `Qubit` .

## <a name="remarks"></a>Notes

Quand `order` elle est appelée avec égal à `1` , cette fonction retourne une opération qui peut être simulée par l’intégrateur Trotter – Suzuki Integrator $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $ où nous avons suivi la notation de [quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) et laissons à $ \lambda $ le temps d’évolution (représenté par la première entrée de l’opération renvoyée). et \{ que \} la valeur de $ H_j _ {j = 1} ^ {m} $ soit le jeu de générateurs dynamiques (skew-Hermitian) qui est intégré, ce qui `op(j, lambda, _)` est simulé par l’opérateur unitaire $e ^ {H_j \lambda} $.

De même, un `order` de `2` retourne l’Trotter symétrique de deuxième ordre, Suzuki Integrator $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j' = m} ^ {1} e ^ {H_ {j'} \lambda/2}.
\end{align} $ $

Les valeurs paires les plus élevées de `order` sont implémentées à l’aide de la construction récursive de [quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).

## <a name="references"></a>Références

- [*D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders*](https://arxiv.org/abs/quant-ph/0508139)