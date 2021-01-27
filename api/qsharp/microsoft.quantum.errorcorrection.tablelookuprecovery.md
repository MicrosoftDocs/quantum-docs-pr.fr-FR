---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: 9f957155e42bb6b5163521171fcba5897f290335
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824397"
---
# <a name="tablelookuprecovery-function"></a>TableLookupRecovery fonction)

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pour une table d’opérations Pauli donnée sur un registre donné de qubits, cette fonction retourne un objet de type `RecoveryFn` qui contient toutes les informations nécessaires pour effectuer un décodage de recherche de table par rapport au tableau d’opérations Pauli donné.

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>Entrée

### <a name="table--pauli"></a>table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Table des opérations Pauli qui fonctionnent sur un registre qubit donné



## <a name="output--recoveryfn"></a>Sortie : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Objet de type `RecoveryFn` , c’est-à-dire un mappage `Syndrome -> Pauli[]` qui associe à un tableau de syndrome donné une opération de correction Pauli correspondante.