---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: Opération de récupération
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: a659399f51794a4edc1d2ff43da84e46797103fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702427"
---
# <a name="recover-operation"></a><span data-ttu-id="b84fb-102">Opération de récupération</span><span class="sxs-lookup"><span data-stu-id="b84fb-102">Recover operation</span></span>

<span data-ttu-id="b84fb-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="b84fb-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="b84fb-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b84fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b84fb-105">Effectue un seul arrondi de correction d’erreur par un code de Quantum décrit par un `QECC` type.</span><span class="sxs-lookup"><span data-stu-id="b84fb-105">Performs a single round of error correction by a quantum code described by a `QECC` type.</span></span>

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="b84fb-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b84fb-106">Input</span></span>

### <a name="code--qecc"></a><span data-ttu-id="b84fb-107">Code : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="b84fb-107">code : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="b84fb-108">Un code de correction des erreurs de Quantum empaqueté en tant que `QECC` type décrit l’encodage et le décodage des données Quantum, ainsi que la mesure des syndromes d’erreur.</span><span class="sxs-lookup"><span data-stu-id="b84fb-108">A quantum error-correcting code packaged as a `QECC` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fn--recoveryfn"></a><span data-ttu-id="b84fb-109">FN : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="b84fb-109">fn : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="b84fb-110">`RecoveryFn`Qui mappe chaque syndrome d’erreur aux `Pauli[]` opérations qui corrigent l’erreur détectée.</span><span class="sxs-lookup"><span data-stu-id="b84fb-110">A `RecoveryFn` that maps each error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="b84fb-111">logicalRegister : [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="b84fb-111">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="b84fb-112">Tableau de qubits où le code stabilisant est défini.</span><span class="sxs-lookup"><span data-stu-id="b84fb-112">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b84fb-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b84fb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b84fb-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b84fb-114">See Also</span></span>

- [<span data-ttu-id="b84fb-115">Microsoft. Quantum. ErrorCorrection. QECC</span><span class="sxs-lookup"><span data-stu-id="b84fb-115">Microsoft.Quantum.ErrorCorrection.QECC</span></span>](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [<span data-ttu-id="b84fb-116">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="b84fb-116">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="b84fb-117">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="b84fb-117">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)