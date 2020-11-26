---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: BoolArrayAsBigInt fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 5a85fd9f81cec0f2de7e7807622aab9604a4db7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214311"
---
# <a name="boolarrayasbigint-function"></a>BoolArrayAsBigInt fonction)

Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Convertit un tableau de valeurs booléennes donné en un grand entier équivalent.
L’élément 0 du tableau est le bit le moins significatif du grand entier.

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a>Entrée

### <a name="a--bool"></a>a : [bool](xref:microsoft.quantum.lang-ref.bool)[]





## <a name="output--bigint"></a>Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Notes

Pour plus d’informations, consultez [constructeur BigInteger C#](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .