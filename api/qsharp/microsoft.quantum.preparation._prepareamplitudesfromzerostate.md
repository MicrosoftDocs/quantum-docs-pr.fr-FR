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
# <a name="_prepareamplitudesfromzerostate-operation"></a><span data-ttu-id="747f5-102">Opération de _PrepareAmplitudesFromZeroState</span><span class="sxs-lookup"><span data-stu-id="747f5-102">_PrepareAmplitudesFromZeroState operation</span></span>

<span data-ttu-id="747f5-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="747f5-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="747f5-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="747f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="747f5-105">À partir d’un ensemble de coefficients et d’un registre quantique encodé avec primauté des octets de poids faible (Little-endian) de qubits non enchevêtrés, tous ayant un état zéro, prépare un État sur ce registre décrit par les coefficients donnés.</span><span class="sxs-lookup"><span data-stu-id="747f5-105">Given a set of coefficients and a little-endian encoded quantum register of unentangled qubits, all of which are in zero state, prepares a state on that register described by the given coefficients.</span></span> <span data-ttu-id="747f5-106">Utilise l’émulation d’État si elle est prise en charge par la cible.</span><span class="sxs-lookup"><span data-stu-id="747f5-106">Uses state emulation if supported by the target.</span></span>

```qsharp
operation _PrepareAmplitudesFromZeroState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="747f5-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="747f5-107">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="747f5-108">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="747f5-108">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>




### <a name="qubits--littleendian"></a><span data-ttu-id="747f5-109">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="747f5-109">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="747f5-110">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="747f5-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

