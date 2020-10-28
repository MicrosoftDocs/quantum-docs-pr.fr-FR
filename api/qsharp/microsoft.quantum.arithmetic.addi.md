---
uid: Microsoft.Quantum.Arithmetic.AddI
title: Opération AddI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 7ee2b9099ea65b95647422dadc1efe4bf043d147
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707654"
---
# <a name="addi-operation"></a>Opération AddI

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Choisit automatiquement entre l’ajout avec Carry et sans, en fonction de la taille du registre de `ys` .

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Entrée

### <a name="xs--littleendian"></a>XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n addend $-bit.


### <a name="ys--littleendian"></a>distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Addend avec au moins $n $ qubits. Contiendra le résultat.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

