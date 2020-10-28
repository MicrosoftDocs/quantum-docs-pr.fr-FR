---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: BlochSphereCoordinates fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 6614b78c8e64c205cc94052cc64dd957814ab3d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708684"
---
# <a name="blochspherecoordinates-function"></a>BlochSphereCoordinates fonction)

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Packages [](https://nuget.org/packages/)


Calcule les coordonnées de la sphère Bloch pour un État à qubit unique.

Étant donné deux nombres complexes $a 0, a1 $ qui représentent l’État qubit, calcule les coordonnées sur la sphère Bloch, de sorte que $a 0 \ket {0} + a1 \ket {1} = r e ^ {it} (e ^ {-i \Phi/2}\cos{(\ Theta/2)} \ket {0} + e ^ {i \Phi/2}\sin{(\ Theta/2)} \ket {1} ) $.

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a>Entrée

### <a name="a0--complexpolar"></a>a0 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Coefficient complexe de l’État $ \ket {0} $.


### <a name="a1--complexpolar"></a>a1 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Coefficient complexe de l’État $ \ket {1} $.



## <a name="output--complexpolardoubledouble"></a>Sortie : ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar),[double](xref:microsoft.quantum.lang-ref.double),[double](xref:microsoft.quantum.lang-ref.double))

Tuple contenant `(ComplexPolar(r, t), phi, theta)` .