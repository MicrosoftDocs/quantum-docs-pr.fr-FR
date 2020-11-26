---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 1d0efa7b83d2e8e75c4b293866f3929f357ec44b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210367"
---
# <a name="statepreparationcomplexcoefficients-function"></a>StatePreparationComplexCoefficients fonction)

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> StatePreparationComplexCoefficients est déconseillé. Utilisez plutôt <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP>.

Retourne une opération qui prépare un État Quantum spécifique.

L’opération retournée $U $ prépare un État Quantum arbitraire $ \ket{\Psi} $ avec des coefficients complexes $r _j e ^ {i t_j} $ de l’état de la base de calcul $n $-qubit $ \ket{0...0} $.

L’action de U sur un registre nouvellement alloué est donnée par $ $ \begin{align} U\ket {0... 0} = \ket{\Psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{align} $ $

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="coefficients--complexpolar"></a>coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

Tableau allant jusqu’à un maximum de $2 ^ n $ de coefficients complexes représentés par leur valeur absolue et la phase $ (r_j, t_j) $. Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.



## <a name="output--littleendian--unit--is-adj--ctl"></a>Sortie : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian est Adj + CTL

Une opération unitaire de préparation de l’État $U $.

## <a name="remarks"></a>Notes

Les coefficients d’entrée négatifs $r _j < $0 sont traités comme s’ils étaient positifs avec la valeur $ | r_j | $. `coefficients` sera complété avec les éléments $ (r_j, t_j) = (0,0, 0,0) $ si moins de $2 ^ n $ sont spécifiés.