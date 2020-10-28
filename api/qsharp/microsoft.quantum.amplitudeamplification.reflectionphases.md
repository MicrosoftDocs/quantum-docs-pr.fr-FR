---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Type défini par l’utilisateur ReflectionPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707715"
---
# <a name="reflectionphases-user-defined-type"></a>Type défini par l’utilisateur ReflectionPhases

Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Packages [](https://nuget.org/packages/)


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