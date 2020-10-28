---
uid: Microsoft.Quantum.Diagnostics.Test
title: Type défini par l’utilisateur de test
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 8030f6378ac0cb393c7ed2b9e636a7561e8943a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702613"
---
# <a name="test-user-defined-type"></a>Type défini par l’utilisateur de test

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Attribut reconnu par le compilateur utilisé pour marquer un test unitaire.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a>Éléments nommés

### <a name="executiontarget--string"></a>ExecutionTarget : [chaîne](xref:microsoft.quantum.lang-ref.string)

