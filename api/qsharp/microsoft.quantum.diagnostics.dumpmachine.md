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
# <a name="dumpmachine-function"></a>DumpMachine fonction)

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Vide l’état actuel de l’ordinateur cible.

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a>Entrée

### <a name="location--t"></a>emplacement : 't

Fournit des informations sur l’emplacement de génération de l’image mémoire de l’ordinateur.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

Aucun.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="remarks"></a>Notes

Cette méthode vous permet de vider les informations relatives à l’état actuel de l’ordinateur cible dans un fichier ou un autre emplacement.
Les informations réelles générées et la sémantique de `location` sont spécifiques à chaque ordinateur cible. Toutefois, si vous fournissez un tuple vide comme emplacement ( `()` ) ou que vous omettez simplement le `location` paramètre, cela signifie généralement de générer la sortie dans la console.

Pour le simulateur d’état local distribué dans le cadre du kit de développement quantique, cette méthode attend une chaîne avec le chemin d’accès à un fichier dans lequel elle écrira la fonction Wave sous la forme d’un tableau unidimensionnel de nombres complexes, dans lequel chaque élément représente les amplitudes de la probabilité de mesure de l’état correspondant.