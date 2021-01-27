---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Type défini par l’utilisateur ReflectionPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: fc3642b76c6e01f0709e78ea42c9ea7237389afa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847178"
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