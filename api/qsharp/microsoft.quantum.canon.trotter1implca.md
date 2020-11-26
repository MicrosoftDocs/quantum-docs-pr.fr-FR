---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Opération Trotter1ImplCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1b4e0a9597f4f30b8e92ef91ff0780e7c7ecdc9b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204791"
---
# <a name="trotter1implca-operation"></a>Opération Trotter1ImplCA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implémentation de l’intégrateur Trotter-Suzuki de premier ordre.

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="nsteps--int"></a>nSteps : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre d’opérations à décomposer en étapes horaires.


### <a name="op--intdoublet--unit--is-adj--ctl"></a>OP : ([int](xref:microsoft.quantum.lang-ref.int),[double](xref:microsoft.quantum.lang-ref.double), t) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opération qui accepte une entrée d’index (type `Int` ) et une entrée de temps (type) `Double` et un registre quantique (type `'T` ) pour la décomposition.


### <a name="stepsize--double"></a>Procédure : [double](xref:microsoft.quantum.lang-ref.double)

Multiplicateur de la taille de chaque étape de la simulation.


### <a name="target--t"></a>cible : 't

Registre quantique sur lequel les opérations agissent.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type sur lequel chaque étape doit agir ; en général, `Qubit[]` ou `Qubit` .