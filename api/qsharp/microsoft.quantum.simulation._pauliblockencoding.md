---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 6ad3e692f68ec2d405e19a7e467ef8fe33d449fc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225565"
---
# <a name="_pauliblockencoding-function"></a>_PauliBlockEncoding fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crée un Unity d’encodage de bloc pour un produit Hamilton.

Le $H de Hamilton, = \ sum_ {j} \ alpha_j P_j $ est décrit par une somme de termes Pauli $P _j $, chacun avec un coefficient réel $ \ alpha_j $.

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Entrée

### <a name="generatorsystem--generatorsystem"></a>generatorSystem : [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Qui décrit $H $ en tant que somme de termes Pauli


### <a name="stateprepunitary--double---littleendian--unit--is-adj--ctl"></a>statePrepUnitary : [double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Une opération unitaire $V $ qui applique le $V unitaire _j $ contrôlé sur l’index $ \ket{j} $, étant donné une fonction $f : j\rightarrow V_j $.


### <a name="multiplexer--intint---qubit--unit--is-adj--ctl---littleendianqubit--unit--is-adj--ctl"></a>multiplexeur : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL





## <a name="output--doubleblockencodingreflection"></a>Sortie : ([double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>Premier paramètre

La norme « One-normal » est $ \alpha = \ sum_ {j} | \ alpha_j | $.

## <a name="second-parameter"></a>Deuxième paramètre

Un `BlockEncodingReflection` $U unitaire $ du $U Hamilton Étant donné que cette unité répond à $U ^ 2 = I $, il s’agit également d’une réflexion.

## <a name="remarks"></a>Notes

Exemples d’opérations la préparation et la dépréparation de l’État $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $, et la construction d’un Unity contrôlé par multiplication sont <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> et <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .