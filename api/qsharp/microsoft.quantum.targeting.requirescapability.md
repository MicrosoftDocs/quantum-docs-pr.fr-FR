---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Type défini par l’utilisateur RequiresCapability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855149"
---
# <a name="requirescapability-user-defined-type"></a>Type défini par l’utilisateur RequiresCapability

Espace de noms : [Microsoft. Quantum. Targeting](xref:Microsoft.Quantum.Targeting)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Attribut reconnu par le compilateur utilisé pour marquer un pouvant être appelé avec les fonctionnalités d’exécution dont il a besoin.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a>Éléments nommés

### <a name="level--string"></a>Niveau : [chaîne](xref:microsoft.quantum.lang-ref.string)

Nom du niveau de fonctionnalité d’exécution requis par l’appelable.
### <a name="reason--string"></a>Raison : [chaîne](xref:microsoft.quantum.lang-ref.string)

Description de la raison pour laquelle l’appelable requiert cette fonctionnalité d’exécution.

## <a name="remarks"></a>Notes

Cet attribut est automatiquement ajouté à callables par le compilateur, sauf s’il existe déjà une instance de cet attribut sur l’appelable. Elle ne doit pas être utilisée, sauf dans de rares cas où le compilateur ne déduit pas correctement la capacité requise.

Voici la liste des noms de niveau de fonctionnalité, par ordre croissant des capacités ou des restrictions décroissantes :

## `"BasicQuantumFunctionality"`

Les résultats des mesures ne peuvent pas être comparés pour déterminer leur égalité.

## `"BasicMeasurementFeedback"`

Les résultats de mesure peuvent être comparés pour l’égalité uniquement dans les expressions conditionnelles If-statement dans les opérations. Le bloc d’une instruction If qui dépend d’un résultat ne peut pas contenir d’instructions SET pour des variables mutables déclarées en dehors du bloc, ou des instructions Return.

## `"FullComputation"`

Aucune restriction au moment de l’exécution. Tous les programmes Q # peuvent être exécutés.