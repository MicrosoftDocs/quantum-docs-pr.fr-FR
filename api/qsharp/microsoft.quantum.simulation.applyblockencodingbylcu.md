---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Opération ApplyBlockEncodingByLCU
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707847"
---
# <a name="applyblockencodingbylcu-operation"></a>Opération ApplyBlockEncodingByLCU

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Implémentation de `BlockEncodingByLCU`.

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a>Entrée

### <a name="statepreparation--t--unit-adj--ctl"></a>statePreparation : 't = [> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL




### <a name="selector--ts--unit-adj--ctl"></a>sélecteur : ('t, 's) => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL




### <a name="auxiliary--t"></a>auxiliaire : 't




### <a name="system--s"></a>système :





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut


### <a name="s"></a>Examin

