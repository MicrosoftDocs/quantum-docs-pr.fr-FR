---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 835c7a9edb22b4be630ebfc04587c12b3ff668b2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829234"
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