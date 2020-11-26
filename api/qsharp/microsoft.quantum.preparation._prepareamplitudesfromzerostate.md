---
uid: Microsoft.Quantum.Preparation._PrepareAmplitudesFromZeroState
title: Opération de _PrepareAmplitudesFromZeroState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: _PrepareAmplitudesFromZeroState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register of unentangled qubits, all of which are in zero state, prepares a state on that register described by the given coefficients. Uses state emulation if supported by the target.
ms.openlocfilehash: 3d90b455bace7b0de1c8c01a5b9b007d719df950
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226585"
---
# <a name="_prepareamplitudesfromzerostate-operation"></a>Opération de _PrepareAmplitudesFromZeroState

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un ensemble de coefficients et d’un registre quantique encodé avec primauté des octets de poids faible (Little-endian) de qubits non enchevêtrés, tous ayant un état zéro, prépare un État sur ce registre décrit par les coefficients donnés. Utilise l’émulation d’État si elle est prise en charge par la cible.

```qsharp
operation _PrepareAmplitudesFromZeroState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Entrée

### <a name="coefficients--complexpolar"></a>coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]




### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

