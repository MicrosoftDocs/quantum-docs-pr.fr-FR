---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: 579300d4efb9e22cb671fbb4bce0a6f72dd0e2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853416"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="5ee12-102">DumpMachine fonction)</span><span class="sxs-lookup"><span data-stu-id="5ee12-102">DumpMachine function</span></span>

<span data-ttu-id="5ee12-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5ee12-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5ee12-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5ee12-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5ee12-105">Vide l’état actuel de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="5ee12-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="5ee12-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="5ee12-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="5ee12-107">emplacement : 't</span><span class="sxs-lookup"><span data-stu-id="5ee12-107">location : 'T</span></span>

<span data-ttu-id="5ee12-108">Fournit des informations sur l’emplacement de génération de l’image mémoire de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="5ee12-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5ee12-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ee12-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="5ee12-110">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5ee12-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5ee12-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="5ee12-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5ee12-112">Peut</span><span class="sxs-lookup"><span data-stu-id="5ee12-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="5ee12-113">Notes</span><span class="sxs-lookup"><span data-stu-id="5ee12-113">Remarks</span></span>

<span data-ttu-id="5ee12-114">Cette méthode vous permet de vider les informations relatives à l’état actuel de l’ordinateur cible dans un fichier ou un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="5ee12-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="5ee12-115">Les informations réelles générées et la sémantique de `location` sont spécifiques à chaque ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="5ee12-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="5ee12-116">Toutefois, si vous fournissez un tuple vide comme emplacement ( `()` ) ou que vous omettez simplement le `location` paramètre, cela signifie généralement de générer la sortie dans la console.</span><span class="sxs-lookup"><span data-stu-id="5ee12-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="5ee12-117">Pour le simulateur d’état local distribué dans le cadre du kit de développement quantique, cette méthode attend une chaîne avec le chemin d’accès à un fichier dans lequel elle écrira la fonction Wave sous la forme d’un tableau unidimensionnel de nombres complexes, dans lequel chaque élément représente les amplitudes de la probabilité de mesure de l’état correspondant.</span><span class="sxs-lookup"><span data-stu-id="5ee12-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>