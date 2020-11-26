---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Type défini par l’utilisateur ReflectionPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: 743ece778239c223573a3a8536ae8059cea09d5f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191344"
---
# <a name="reflectionphases-user-defined-type"></a>Type défini par l’utilisateur ReflectionPhases

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Phases pour une séquence de réflexions partielles dans l’amplification d’amplitude.

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a>Éléments nommés

### <a name="aboutstart--double"></a>AboutStart : [double](xref:microsoft.quantum.lang-ref.double)[]

Tableau de phases pour la réflexion à propos de l’état de démarrage.
### <a name="abouttarget--double"></a>AboutTarget : [double](xref:microsoft.quantum.lang-ref.double)[]

Tableau de phases pour la réflexion sur l’État cible.

## <a name="remarks"></a>Notes

Les deux tableaux doivent être de longueur égale. Notez que dans de nombreux cas, la première phase à propos de l’état de démarrage et de la dernière phase de l’État cible introduit une phase de décalage global et peut être définie sur $0 $.