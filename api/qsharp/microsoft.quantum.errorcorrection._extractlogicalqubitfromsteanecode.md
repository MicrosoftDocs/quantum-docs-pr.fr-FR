---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: Opération de _ExtractLogicalQubitFromSteaneCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 71390feb84660cc9bf7bb12b64eac6d3ca512387
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702577"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a><span data-ttu-id="3c51d-102">Opération de _ExtractLogicalQubitFromSteaneCode</span><span class="sxs-lookup"><span data-stu-id="3c51d-102">_ExtractLogicalQubitFromSteaneCode operation</span></span>

<span data-ttu-id="3c51d-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="3c51d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="3c51d-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c51d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c51d-105">Mesure du syndrome et l’inverse de l’incorporation.</span><span class="sxs-lookup"><span data-stu-id="3c51d-105">Syndrome measurement and the inverse of embedding.</span></span>

<span data-ttu-id="3c51d-106">$X $-et $Z $-stabilisants ne sont pas traités de la même manière, ce qui est dû au choix particulier du circuit d’encodage.</span><span class="sxs-lookup"><span data-stu-id="3c51d-106">$X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit.</span></span>
<span data-ttu-id="3c51d-107">Cette asymétrie provoque une autre routine d’extraction de syndrome.</span><span class="sxs-lookup"><span data-stu-id="3c51d-107">This asymmetry leads to a different syndrome extraction routine.</span></span>
<span data-ttu-id="3c51d-108">Il est possible de mesurer le syndrome en mesurant l’opérateur qubit Pauli directement sur l’état du code, mais pour l’objectif de la distillation, le qubit logique est renvoyé dans un qubit unique, ce qui permet d’effectuer des mesures de syndrome sans plus ancillas.</span><span class="sxs-lookup"><span data-stu-id="3c51d-108">One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.</span></span>

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a><span data-ttu-id="3c51d-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="3c51d-109">Input</span></span>

### <a name="code--logicalregister"></a><span data-ttu-id="3c51d-110">Code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="3c51d-110">code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>





## <a name="output--qubitintint"></a><span data-ttu-id="3c51d-111">Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="3c51d-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="3c51d-112">Le qubit logique et une paire d’entiers pour $X $-syndrome et $Z $-syndrome.</span><span class="sxs-lookup"><span data-stu-id="3c51d-112">The logical qubit and a pair of integers for $X$-syndrome and $Z$-syndrome.</span></span>
<span data-ttu-id="3c51d-113">Ils représentent l’index du code qubit sur lequel une seule $X $-ou $Z $-Error aurait provoqué le syndrome mesuré.</span><span class="sxs-lookup"><span data-stu-id="3c51d-113">They represent the index of the code qubit on which a single $X$- or $Z$-error would have caused the measured syndrome.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c51d-114">Notes</span><span class="sxs-lookup"><span data-stu-id="3c51d-114">Remarks</span></span>

<span data-ttu-id="3c51d-115">Notez que cette opération n’est pas marquée comme `internal` , car les tests unitaires dépendent directement de cette opération.</span><span class="sxs-lookup"><span data-stu-id="3c51d-115">Note that this operation is not marked as `internal`, as unit tests directly depend on this operation.</span></span> <span data-ttu-id="3c51d-116">Dans le cadre d’une amélioration future, les tests unitaires doivent être refactorés pour dépendre uniquement des callables publiques directement.</span><span class="sxs-lookup"><span data-stu-id="3c51d-116">As a future improvement, unit tests should be refactored to depend only on public callables directly.</span></span>

> [!WARNING]
> <span data-ttu-id="3c51d-117">Cette routine est adaptée à un circuit d’encodage particulier pour le code 7 qubit de Steane. Si le circuit d’encodage est modifié, le résultat du syndrome devra peut-être être interprété différemment.</span><span class="sxs-lookup"><span data-stu-id="3c51d-117">This routine is tailored to a particular encoding circuit for Steane's 7 qubit code; if the encoding circuit is modified then the syndrome outcome might have to be interpreted differently.</span></span>