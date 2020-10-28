---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708177"
---
# <a name="statepreparationpositivecoefficients-function"></a>StatePreparationPositiveCoefficients fonction)

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Packages [](https://nuget.org/packages/)


Retourne une opération qui prépare l’État Quantum donné.

L’opération retournée $U $ prépare un État Quantum arbitraire $ \ket{\Psi} $ avec des coefficients $ \ alpha_j \ge $0 à partir de l’état de $n la base de calcul $ qubit $ \ket{0...0} $.

L’action de U sur un registre nouvellement alloué est donnée par $ $ \begin{align} U \ket{0\cdots 0} = \ket{\Psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.
\end{align} $ $

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="coefficients--double"></a>coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]

Tableau allant jusqu’à $2 ^ n $ coefficients $ \ alpha_j $. Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.



## <a name="output--littleendian--unit-adj--ctl"></a>Sortie : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unité](xref:microsoft.quantum.lang-ref.unit) Adj + CTL

Une opération unitaire de préparation de l’État $U $.

## <a name="remarks"></a>Notes

Les coefficients d’entrée négatifs $ \ alpha_j < $0 sont traités comme s’ils étaient positifs avec la valeur $ | \ alpha_j | $. `coefficients` sera complété avec les éléments $ \ alpha_j = $0,0 si moins de $2 ^ n $ sont spécifiés.