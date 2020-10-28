---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Opération MeasureIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703609"
---
# <a name="measureidentity-operation"></a>Opération MeasureIdentity

Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)

Packages [](https://nuget.org/packages/)


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