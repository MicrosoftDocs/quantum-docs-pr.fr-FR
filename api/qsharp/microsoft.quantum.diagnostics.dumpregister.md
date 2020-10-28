---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: a6d29dbf0525077fd804563f85f189740fdc0429
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702697"
---
# <a name="dumpregister-function"></a><span data-ttu-id="80cbb-102">DumpRegister fonction)</span><span class="sxs-lookup"><span data-stu-id="80cbb-102">DumpRegister function</span></span>

<span data-ttu-id="80cbb-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="80cbb-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="80cbb-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80cbb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="80cbb-105">Vide l’état de l’ordinateur cible actuel associé à l’qubits donné.</span><span class="sxs-lookup"><span data-stu-id="80cbb-105">Dumps the current target machine's status associated with the given qubits.</span></span>

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="80cbb-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="80cbb-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="80cbb-107">emplacement : 't</span><span class="sxs-lookup"><span data-stu-id="80cbb-107">location : 'T</span></span>

<span data-ttu-id="80cbb-108">Fournit des informations sur l’emplacement de génération de l’image mémoire de l’État.</span><span class="sxs-lookup"><span data-stu-id="80cbb-108">Provides information on where to generate the state's dump.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="80cbb-109">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="80cbb-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="80cbb-110">Liste des qubits à signaler.</span><span class="sxs-lookup"><span data-stu-id="80cbb-110">The list of qubits to report.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80cbb-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80cbb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="80cbb-112">Aucun.</span><span class="sxs-lookup"><span data-stu-id="80cbb-112">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="80cbb-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="80cbb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="80cbb-114">Peut</span><span class="sxs-lookup"><span data-stu-id="80cbb-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="80cbb-115">Notes</span><span class="sxs-lookup"><span data-stu-id="80cbb-115">Remarks</span></span>

<span data-ttu-id="80cbb-116">Cette méthode vous permet de vider les informations associées à l’état du qubits donné dans un fichier ou un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="80cbb-116">This method allows you to dump the information associated with the state of the given qubits into a file or some other location.</span></span>
<span data-ttu-id="80cbb-117">Les informations réelles générées et la sémantique de `location` sont spécifiques à chaque ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="80cbb-117">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="80cbb-118">Toutefois, le fait de fournir un tuple vide comme emplacement ( `()` ) signifie généralement que le résultat doit être généré dans la console.</span><span class="sxs-lookup"><span data-stu-id="80cbb-118">However, providing an empty tuple as a location (`()`) typically means to generate the output to the console.</span></span>

<span data-ttu-id="80cbb-119">Pour le simulateur d’état complet distribué dans le cadre du kit de développement quantique, cette méthode attend une chaîne avec le chemin d’accès à un fichier dans lequel elle écrira l’état du qubits donné (c.-à-d. la fonction Wave du sous-système correspondant) en tant que tableau unidimensionnel de nombres complexes, dans lequel chaque élément représente les amplitudes de la probabilité de mesure de l’état correspondant.</span><span class="sxs-lookup"><span data-stu-id="80cbb-119">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the state of the given qubits (i.e. the wave function of the corresponding  subsystem) as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>
<span data-ttu-id="80cbb-120">Si le qubits donné est enchevêtré avec un autre qubit et que son état ne peut pas être séparé, il signale simplement que les qubits sont enchevêtrés.</span><span class="sxs-lookup"><span data-stu-id="80cbb-120">If the given qubits are entangled with some other qubit and their state can't be separated, it just reports that the qubits are entangled.</span></span>