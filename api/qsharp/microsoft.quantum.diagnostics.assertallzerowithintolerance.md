---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: Opération AssertAllZeroWithinTolerance
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 281855ec79d280c903ebb4d05614081767840778
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830862"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="b6bed-102">Opération AssertAllZeroWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="b6bed-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="b6bed-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b6bed-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b6bed-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b6bed-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b6bed-105">Déclarez que le qubits donné se trouve tous dans l’État $ \ket {0} $ jusqu’à une tolérance donnée.</span><span class="sxs-lookup"><span data-stu-id="b6bed-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b6bed-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b6bed-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="b6bed-107">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b6bed-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b6bed-108">Qubits qui sont déclarés comme étant dans l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="b6bed-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="b6bed-109">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6bed-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6bed-110">Précision avec laquelle l’État doit être dans l’État $ \ket {0} $</span><span class="sxs-lookup"><span data-stu-id="b6bed-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="b6bed-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6bed-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b6bed-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b6bed-112">See Also</span></span>

- [<span data-ttu-id="b6bed-113">Microsoft. Quantum. Diagnostics. AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="b6bed-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)