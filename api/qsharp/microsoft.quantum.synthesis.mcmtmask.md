---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Type défini par l’utilisateur MCMTMask
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 50bec0f9aca95afab83491db6b742d1f0323371f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855375"
---
# <a name="mcmtmask-user-defined-type"></a>Type défini par l’utilisateur MCMTMask

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Type pour représenter une porte Toffoli à plusieurs cibles multiples.

Le premier entier est un masque de bits pour les lignes de contrôle.  Les index binaires qui sont définis correspondent aux index de ligne de contrôle.

Le deuxième entier est un masque de bits pour les lignes cibles.  Les index binaires qui sont définis correspondent aux index de lignes cibles.

Les index binaires des deux entiers doivent être disjoints.

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a>Éléments nommés

### <a name="controlmask--int"></a>ControlMask : [entier](xref:microsoft.quantum.lang-ref.int)


### <a name="targetmask--int"></a>TargetMask : [entier](xref:microsoft.quantum.lang-ref.int)

