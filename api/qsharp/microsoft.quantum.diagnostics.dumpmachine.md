---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702712"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="2609b-102">DumpMachine fonction)</span><span class="sxs-lookup"><span data-stu-id="2609b-102">DumpMachine function</span></span>

<span data-ttu-id="2609b-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2609b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2609b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2609b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2609b-105">Vide l’état actuel de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="2609b-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="2609b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2609b-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="2609b-107">emplacement : 't</span><span class="sxs-lookup"><span data-stu-id="2609b-107">location : 'T</span></span>

<span data-ttu-id="2609b-108">Fournit des informations sur l’emplacement de génération de l’image mémoire de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2609b-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2609b-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2609b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="2609b-110">Aucun.</span><span class="sxs-lookup"><span data-stu-id="2609b-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2609b-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2609b-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2609b-112">Peut</span><span class="sxs-lookup"><span data-stu-id="2609b-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="2609b-113">Notes</span><span class="sxs-lookup"><span data-stu-id="2609b-113">Remarks</span></span>

<span data-ttu-id="2609b-114">Cette méthode vous permet de vider les informations relatives à l’état actuel de l’ordinateur cible dans un fichier ou un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="2609b-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="2609b-115">Les informations réelles générées et la sémantique de `location` sont spécifiques à chaque ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="2609b-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="2609b-116">Toutefois, si vous fournissez un tuple vide comme emplacement ( `()` ) ou que vous omettez simplement le `location` paramètre, cela signifie généralement de générer la sortie dans la console.</span><span class="sxs-lookup"><span data-stu-id="2609b-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="2609b-117">Pour le simulateur d’état local distribué dans le cadre du kit de développement quantique, cette méthode attend une chaîne avec le chemin d’accès à un fichier dans lequel elle écrira la fonction Wave sous la forme d’un tableau unidimensionnel de nombres complexes, dans lequel chaque élément représente les amplitudes de la probabilité de mesure de l’état correspondant.</span><span class="sxs-lookup"><span data-stu-id="2609b-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>