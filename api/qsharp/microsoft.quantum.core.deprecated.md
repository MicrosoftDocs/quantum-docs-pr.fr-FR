---
uid: Microsoft.Quantum.Core.Deprecated
title: Type défini par l’utilisateur déconseillé
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 1a32d98f5d034c2673d42301b45379da1302ca7f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832086"
---
# <a name="deprecated-user-defined-type"></a>Type défini par l’utilisateur déconseillé

Espace de noms : [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Attribut reconnu par le compilateur utilisé pour marquer un type ou être appelé comme déconseillé.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Éléments nommés

### <a name="newname--string"></a>NewName : [chaîne](xref:microsoft.quantum.lang-ref.string)

Nom complet du type ou pouvant être appelé à utiliser à la place.
Est défini sur la chaîne vide si un type ou un appelable est déconseillé sans substitution.