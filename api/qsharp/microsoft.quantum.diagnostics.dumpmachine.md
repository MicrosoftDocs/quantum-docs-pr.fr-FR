---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: e7eb2dfce060b61e27deae31e3c1fc6dc3d7655c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202105"
---
# <a name="dumpmachine-function"></a>DumpMachine fonction)

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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