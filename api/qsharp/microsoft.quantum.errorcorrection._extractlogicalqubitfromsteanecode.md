---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: Opération de _ExtractLogicalQubitFromSteaneCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: fe64343e30a0a3f0d05382e7812d37d5b13133d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853216"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a>Opération de _ExtractLogicalQubitFromSteaneCode

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mesure du syndrome et l’inverse de l’incorporation.

$X $-et $Z $-stabilisants ne sont pas traités de la même manière, ce qui est dû au choix particulier du circuit d’encodage.
Cette asymétrie provoque une autre routine d’extraction de syndrome.
Il est possible de mesurer le syndrome en mesurant l’opérateur qubit Pauli directement sur l’état du code, mais pour l’objectif de la distillation, le qubit logique est renvoyé dans un qubit unique, ce qui permet d’effectuer des mesures de syndrome sans plus ancillas.

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a>Entrée

### <a name="code--logicalregister"></a>Code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)





## <a name="output--qubitintint"></a>Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

Le qubit logique et une paire d’entiers pour $X $-syndrome et $Z $-syndrome.
Ils représentent l’index du code qubit sur lequel une seule $X $-ou $Z $-Error aurait provoqué le syndrome mesuré.

## <a name="remarks"></a>Notes

Notez que cette opération n’est pas marquée comme `internal` , car les tests unitaires dépendent directement de cette opération. Dans le cadre d’une amélioration future, les tests unitaires doivent être refactorés pour dépendre uniquement des callables publiques directement.

> [!WARNING]
> Cette routine est adaptée à un circuit d’encodage particulier pour le code 7 qubit de Steane. Si le circuit d’encodage est modifié, le résultat du syndrome devra peut-être être interprété différemment.