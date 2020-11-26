---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Type défini par l’utilisateur SyndromeMeasOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 65e47d82546b1df0beec2c00f435d3e7a28e6ae6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200252"
---
# <a name="syndromemeasop-user-defined-type"></a>Type défini par l’utilisateur SyndromeMeasOp

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente une opération utilisée pour mesurer le syndrome d’un bloc de code de correction des erreurs.

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a>Notes

La signature `(LogicalRegister => Syndrome)` représente une opération qui agit conjointement avec le qubits dans `LogicalRegister` et certains qubits auxiliaires suivis d’une mesure du qubits auxiliaire pour extraire une `Syndrome` valeur représentant le `Result[]` de ces mesures.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. Quantum. ErrorCorrection. syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)