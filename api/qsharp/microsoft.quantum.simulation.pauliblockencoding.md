---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848007"
---
# <a name="pauliblockencoding-function"></a>PauliBlockEncoding fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crée un Unity d’encodage de bloc pour un produit Hamilton.

Le $H de Hamilton, = \ sum_ {j} \ alpha_j P_j $ est décrit par une somme de termes Pauli $P _j $, chacun avec un coefficient réel $ \ alpha_j $.

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Entrée

### <a name="generatorsystem--generatorsystem"></a>generatorSystem : [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Qui décrit $H $ en tant que somme de termes Pauli



## <a name="output--doubleblockencodingreflection"></a>Sortie : ([double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>Premier paramètre

La norme « One-normal » est $ \alpha = \ sum_ {j} | \ alpha_j | $.

## <a name="second-parameter"></a>Deuxième paramètre

Un `BlockEncodingReflection` $U unitaire $ du $H Hamilton Étant donné que cette unité répond à $U ^ 2 = I $, il s’agit également d’une réflexion.

## <a name="remarks"></a>Notes

Cela est obtenu en préparant et en dépréparant l’État $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $, et en construisant un ensemble unitaire contrôlé par multiplication <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> et <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .