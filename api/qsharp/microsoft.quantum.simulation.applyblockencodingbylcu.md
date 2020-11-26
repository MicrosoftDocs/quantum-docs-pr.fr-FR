---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Opération ApplyBlockEncodingByLCU
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 8ce6eb16b1dc5a83dd3a9559592c20d6b7b999b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225480"
---
# <a name="applyblockencodingbylcu-operation"></a>Opération ApplyBlockEncodingByLCU

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implémentation de `BlockEncodingByLCU`.

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="statepreparation--t--unit--is-adj--ctl"></a>statePreparation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL




### <a name="selector--ts--unit--is-adj--ctl"></a>sélecteur : ('t, s) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL




### <a name="auxiliary--t"></a>auxiliaire : 't




### <a name="system--s"></a>système :





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut


### <a name="s"></a>Examin

