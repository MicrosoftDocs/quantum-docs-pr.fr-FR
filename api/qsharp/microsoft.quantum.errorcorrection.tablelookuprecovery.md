---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: c56a9bbb1db72b5ba03ee9976e648a59f651aa16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702358"
---
# <a name="tablelookuprecovery-function"></a>TableLookupRecovery fonction)

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Packages [](https://nuget.org/packages/)


Pour une table d’opérations Pauli donnée sur un registre donné de qubits, cette fonction retourne un objet de type `RecoveryFn` qui contient toutes les informations nécessaires pour effectuer un décodage de recherche de table par rapport au tableau d’opérations Pauli donné.

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>Entrée

### <a name="table--pauli"></a>table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Table des opérations Pauli qui fonctionnent sur un registre qubit donné



## <a name="output--recoveryfn"></a>Sortie : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Objet de type `RecoveryFn` , c’est-à-dire un mappage `Syndrome -> Pauli[]` qui associe à un tableau de syndrome donné une opération de correction Pauli correspondante.