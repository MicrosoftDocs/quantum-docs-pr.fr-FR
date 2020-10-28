---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704499"
---
# <a name="arrangedqubits-function"></a>ArrangedQubits fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Organiser le contrôle, la cible et les qubits d’assistance en fonction d’un index

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a>Description

Retourne un tableau qubit avec la cible à l’index 0 et le contrôle i à l’index 2 ^ i.  Les qubits d’assistance sont insérés à toutes les autres positions dans le tableau.

## <a name="input"></a>Entrée

### <a name="controls--qubit"></a>contrôles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="helper--qubit"></a>Helper : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--qubit"></a>Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

