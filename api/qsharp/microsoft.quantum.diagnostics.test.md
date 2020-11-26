---
uid: Microsoft.Quantum.Diagnostics.Test
title: Type défini par l’utilisateur de test
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 80821cb46d773d84085838d9ee539a8a45c43e61
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201493"
---
# <a name="test-user-defined-type"></a>Type défini par l’utilisateur de test

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Attribut reconnu par le compilateur utilisé pour marquer un test unitaire.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a>Éléments nommés

### <a name="executiontarget--string"></a>ExecutionTarget : [chaîne](xref:microsoft.quantum.lang-ref.string)

