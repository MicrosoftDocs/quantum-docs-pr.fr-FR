---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: Opération AssertAllZeroWithinTolerance
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 5e401904086323fabef7914d34463f50e4c38862
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702784"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="e9281-102">Opération AssertAllZeroWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="e9281-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="e9281-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e9281-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e9281-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e9281-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e9281-105">Déclarez que le qubits donné se trouve tous dans l’État $ \ket {0} $ jusqu’à une tolérance donnée.</span><span class="sxs-lookup"><span data-stu-id="e9281-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="e9281-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e9281-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="e9281-107">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e9281-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e9281-108">Qubits qui sont déclarés comme étant dans l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="e9281-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="e9281-109">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e9281-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e9281-110">Précision avec laquelle l’État doit être dans l’État $ \ket {0} $</span><span class="sxs-lookup"><span data-stu-id="e9281-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="e9281-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e9281-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e9281-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e9281-112">See Also</span></span>

- [<span data-ttu-id="e9281-113">Microsoft. Quantum. Diagnostics. AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="e9281-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)