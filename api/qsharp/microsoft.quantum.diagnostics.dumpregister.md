---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 9623d6d881f1f0ec048c3a951fe259bdfac84766
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202020"
---
# <a name="dumpregister-function"></a>DumpRegister fonction)

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Vide l’état de l’ordinateur cible actuel associé à l’qubits donné.

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="location--t"></a>emplacement : 't

Fournit des informations sur l’emplacement de génération de l’image mémoire de l’État.


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Liste des qubits à signaler.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

Aucun.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="remarks"></a>Notes

Cette méthode vous permet de vider les informations associées à l’état du qubits donné dans un fichier ou un autre emplacement.
Les informations réelles générées et la sémantique de `location` sont spécifiques à chaque ordinateur cible. Toutefois, le fait de fournir un tuple vide comme emplacement ( `()` ) signifie généralement que le résultat doit être généré dans la console.

Pour le simulateur d’état complet distribué dans le cadre du kit de développement quantique, cette méthode attend une chaîne avec le chemin d’accès à un fichier dans lequel elle écrira l’état du qubits donné (c.-à-d. la fonction Wave du sous-système correspondant) en tant que tableau unidimensionnel de nombres complexes, dans lequel chaque élément représente les amplitudes de la probabilité de mesure de l’état correspondant.
Si le qubits donné est enchevêtré avec un autre qubit et que son état ne peut pas être séparé, il signale simplement que les qubits sont enchevêtrés.