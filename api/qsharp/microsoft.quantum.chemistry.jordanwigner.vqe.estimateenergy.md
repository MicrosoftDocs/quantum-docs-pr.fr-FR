---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: Opération EstimateEnergy
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: 52e527a68818c80f93bc177d3563064fd0f2aea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703087"
---
# <a name="estimateenergy-operation"></a>Opération EstimateEnergy

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Packages [](https://nuget.org/packages/)


Estime l’énergie de la molécule en additionnant l’énergie fournie par les conditions d' Jordan-Wigner individuelles.

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a>Description

Cette opération repose implicitement sur la Convention d’indexation Spin Down.

## <a name="input"></a>Entrée

### <a name="jwhamiltonian--jordanwignerencodingdata"></a>jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Jordan-Wigner Hamilton.


### <a name="nsamples--int"></a>nSamples : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre d’échantillons à utiliser pour l’estimation du terme attentes.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

L’énergie estimée de la molécule