---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: Opération ApplyUnitary
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859164"
---
# <a name="applyunitary-operation"></a><span data-ttu-id="a606e-102">Opération ApplyUnitary</span><span class="sxs-lookup"><span data-stu-id="a606e-102">ApplyUnitary operation</span></span>

<span data-ttu-id="a606e-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a606e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a606e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a606e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a606e-105">Applique la porte définie par la matrice unitaire 2 ^ n x 2 ^ n.</span><span class="sxs-lookup"><span data-stu-id="a606e-105">Applies gate defined by 2^n x 2^n unitary matrix.</span></span>

<span data-ttu-id="a606e-106">Échoue si la matrice n’est pas une unité ou a une taille incorrecte.</span><span class="sxs-lookup"><span data-stu-id="a606e-106">Fails if matrix is not unitary, or has wrong size.</span></span>

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a606e-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="a606e-107">Input</span></span>

### <a name="unitary--complex"></a><span data-ttu-id="a606e-108">Unity : [complexe](xref:Microsoft.Quantum.Math.Complex)[] []</span><span class="sxs-lookup"><span data-stu-id="a606e-108">unitary : [Complex](xref:Microsoft.Quantum.Math.Complex)[][]</span></span>

<span data-ttu-id="a606e-109">2 ^ n x 2 ^ n matrice d’unités décrivant l’opération.</span><span class="sxs-lookup"><span data-stu-id="a606e-109">2^n x 2^n unitary matrix describing the operation.</span></span>
<span data-ttu-id="a606e-110">Si la matrice n’est pas une unité ou une taille appropriée, lève une exception.</span><span class="sxs-lookup"><span data-stu-id="a606e-110">If matrix is not unitary or not of suitable size, throws an exception.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="a606e-111">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a606e-111">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a606e-112">Qubits auquel appliquer l’opération-Registre de longueur n.</span><span class="sxs-lookup"><span data-stu-id="a606e-112">Qubits to which apply the operation - register of length n.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a606e-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a606e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

