---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: Opération KnillDistill
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 4eff99eebb1e271d240513f827c6e93973ef79a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853115"
---
# <a name="knilldistill-operation"></a>Opération KnillDistill

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implémente l’algorithme de distillation Magic State Knill.

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a>Description

À partir de 15 copies approximatives d’un État magique $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket \end{align} {8} {1} , $ $ donne une copie de qualité supérieure.

## <a name="input"></a>Entrée

### <a name="roughmagic--qubit"></a>roughMagic : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registre de quinze qubits contenant des copies approximatives d’un État magique. L’application suivante de cette procédure de distillation `roughMagic[0]` contient une copie de qualité supérieure et le reste du Registre est réinitialisé à l’État $ \ket{00\cdots 0} $.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

Si `true` la valeur est, la procédure a réussi et la copie de qualité supérieure doit être acceptée. Si `false` la méthode est, la procédure a échoué et l’état du registre doit être considéré comme non défini.

## <a name="remarks"></a>Notes

Nous suivons l’algorithme de Knill.
Toutefois, l’implémentation actuelle est loin d’être optimale, car elle utilise un trop grand nombre de qubits.
Les États magiques sont injectés dans cette routine, auquel cas il y a de meilleurs protocoles.

## <a name="references"></a>Références

- [Knill](https://arxiv.org/abs/quant-ph/0402171)