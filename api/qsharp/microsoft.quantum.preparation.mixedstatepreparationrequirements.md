---
uid: Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
title: Type défini par l’utilisateur MixedStatePreparationRequirements
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparationRequirements
qsharp.summary: Represents the number of qubits required in order to prepare a given mixed state.
ms.openlocfilehash: 3ea4757f6aa5125418b1e81db9f32e7b668eb359
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228693"
---
# <a name="mixedstatepreparationrequirements-user-defined-type"></a>Type défini par l’utilisateur MixedStatePreparationRequirements

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente le nombre de qubits nécessaires pour préparer un État mixte donné.

```qsharp

newtype MixedStatePreparationRequirements = (NTotalQubits : Int, (NIndexQubits : Int, NGarbageQubits : Int));
```



## <a name="named-items"></a>Éléments nommés

### <a name="ntotalqubits--int"></a>NTotalQubits : [entier](xref:microsoft.quantum.lang-ref.int)


### <a name="nindexqubits--int"></a>NIndexQubits : [entier](xref:microsoft.quantum.lang-ref.int)


### <a name="ngarbagequbits--int"></a>NGarbageQubits : [entier](xref:microsoft.quantum.lang-ref.int)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. PurifiedMixedState](xref:Microsoft.Quantum.PurifiedMixedState)