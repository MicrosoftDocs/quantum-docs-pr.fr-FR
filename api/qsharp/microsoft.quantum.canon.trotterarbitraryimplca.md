---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: Opération TrotterArbitraryImplCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1c094d09ac8bdd71a59ef57d8715a6f90f18efc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703747"
---
# <a name="trotterarbitraryimplca-operation"></a>Opération TrotterArbitraryImplCA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Implémentation récursive de l’intégrateur Trotter-Suzuki pair-Order.

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a>Entrée

### <a name="order--int"></a>commande : [int](xref:microsoft.quantum.lang-ref.int)

Ordre de Trotter-Suzuki intégrateur.


### <a name="nsteps--int"></a>nSteps : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre d’opérations à décomposer en étapes horaires.


### <a name="op--intdoublet--unit-adj--ctl"></a>OP : ([int](xref:microsoft.quantum.lang-ref.int),[double](xref:microsoft.quantum.lang-ref.double), t) [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL

Opération qui accepte une entrée d’index (type `Int` ) et une entrée de temps (type) `Double` et un registre quantique (type `'T` ) pour la décomposition.


### <a name="stepsize--double"></a>Procédure : [double](xref:microsoft.quantum.lang-ref.double)

Multiplicateur de la taille de chaque étape de la simulation.


### <a name="target--t"></a>cible : 't

Registre quantique sur lequel les opérations agissent.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type sur lequel chaque étape doit agir ; en général, `Qubit[]` ou `Qubit` .