---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Opération MeasureIdentity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216113"
---
# <a name="measureidentity-operation"></a>Opération MeasureIdentity

Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mesure l’opérateur d’identité sur un registre de qubits.

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a>Entrée

### <a name="register--qubit"></a>Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre à mesurer.



## <a name="output--__invalidresult__"></a>Sortie : __non <Result> valide__

Valeur de résultat `Zero` .

## <a name="remarks"></a>Notes

Étant donné que $ \boldone $ contient uniquement le eigenvalue $1 $, et qu’il n’a pas de eigenvalue négatif, cette opération retourne toujours `Zero` , ce qui correspond au eigenvalue $ + 1 = (-1) ^ 0 $ et n’entraîne pas la réduction de l’état de `register` .

En soi, cette opération n’est pas utile, mais elle est utile dans le contexte de la tomographie de processus, car elle fournit des informations sur la conservation de trace d’un processus de Quantum.
En particulier, une machine cible avec une mesure de perte doit remplacer cette opération par une mesure réelle de $ \boldone $.