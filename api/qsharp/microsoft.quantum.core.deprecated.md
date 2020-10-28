---
uid: Microsoft.Quantum.Core.Deprecated
title: Type défini par l’utilisateur déconseillé
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: b1fcae9647b2a655d25773386ecffa826515516e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702883"
---
# <a name="deprecated-user-defined-type"></a>Type défini par l’utilisateur déconseillé

Espace de noms : [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Packages [](https://nuget.org/packages/)


Attribut reconnu par le compilateur utilisé pour marquer un type ou être appelé comme déconseillé.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Éléments nommés

### <a name="newname--string"></a>NewName : [chaîne](xref:microsoft.quantum.lang-ref.string)

Nom complet du type ou pouvant être appelé à utiliser à la place.
Est défini sur la chaîne vide si un type ou un appelable est déconseillé sans substitution.