---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Type défini par l’utilisateur SyndromeMeasOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850051"
---
# <a name="syndromemeasop-user-defined-type"></a>Type défini par l’utilisateur SyndromeMeasOp

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente une opération utilisée pour mesurer le syndrome d’un bloc de code de correction des erreurs.

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a>Exemple

Mesurez les syndromes du code de retournement binaire $S = \langle ZZI, IZZ \rangle $ à l’aide de Scratch qubits en mode non tolérant aux pannes :

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a>Notes

La signature `(LogicalRegister => Syndrome)` représente une opération qui agit conjointement avec le qubits dans `LogicalRegister` et certains qubits auxiliaires suivis d’une mesure du qubits auxiliaire pour extraire une `Syndrome` valeur représentant le `Result[]` de ces mesures.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. Quantum. ErrorCorrection. syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)