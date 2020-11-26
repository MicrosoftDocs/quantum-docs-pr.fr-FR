---
uid: Microsoft.Quantum.AmplitudeAmplification
title: Espace de noms Microsoft. Quantum. AmplitudeAmplification
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: namespace
qsharp.name: Microsoft.Quantum.AmplitudeAmplification
qsharp.summary: This namespace contains functions and operations for performing amplitude amplification.
ms.openlocfilehash: f265f1f8b41513f9201a758f85451e768b7564e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191412"
---
# <a name="microsoftquantumamplitudeamplification-namespace"></a>Espace de noms Microsoft. Quantum. AmplitudeAmplification

Cet espace de noms contient des fonctions et des opérations pour effectuer une amplification d’amplitude.



## <a name="description"></a>Description

L’amplification d’amplitude oublie avec des réflexions partielles est la forme la plus générale d’amplification d’amplitude implémentée ici.

Cette opération est appelée par le biais de l’opération AmpAmpObliviousByReflectionPhases.

Il a deux registres : `ancillaRegister` et `systemRegister` .

Cela accepte deux oracles pour ces réflexions de type `ReflectionOracle` qui agissent uniquement sur le `ancillaRegister` Registre.

Cela accepte une amplification d’amplitude Oracle spécial vers oublie de type `ObliviousOracle` qui agit conjointement sur les deux registres.

L’état d’entrée de `ancillaRegister` est supposé être le eigenstate unique $-$1 du premier opérateur de réflexion $I-2 \ Ket {s} \ Bra {s} $.

Les réflexions sur un État Quantum cible sont souvent implémentées en supposant l’accès à un Oracle qui prépare cet État à partir de la base de calcul $ \ket{0\cdots 0} $.

Notre convention pour ces Oracle requiert deux registres : un registre à qubit unique `flagQubit` et un registre pour tout le reste sur le registre ancillaRegister.

Le Oracle de type `StateOracle` agit conjointement sur les deux registres pour créer l’État cible marqué par $ \ket {1} $ dans le `flagQubit` Registre avec une amplitude réelle.

La réflexion `ReflectionOracle` à propos de cet état d’indicateur est générée par l’opération `TargetStateReflectionOracle` .

La réflexion à `ReflectionOracle` propos de l’état d’entrée à `ancillaRegister` est générée par le StateOracle inversé, puis reflète environ $ \ket{0\cdots 0} $ avec ReflectionStart ().

Le Oracle de type `DeterministicStateOracle` agit sur les `qubitState` registres pour créer l’État cible exactement sans indicateur.

`AmpAmpObliviousByOraclePhases` est une version de l’amplification d’amplitude oublie qui accepte Oracle `StateOracle` et `ObliviousOracle` non les réflexions.

Notez que l’amplification d’amplitude est un cas spécial d’amplification d’amplitude oublie où `ObliviousOracle` est l’opérateur d’identité et qu’il n’y a pas de qubits système, c’est-à-dire qu’il `systemRegister` est vide.

Elle est appelée par le biais de l’opération `AmpAmByReflectionPhases` et `AmpAmpByOraclePhases` .

Les phases des réflexions partielles dans le cas standard de la recherche Grover sont fournies par la fonction AmpAmpPhasesStandard.

Par exemple, nous avons les dépendances suivantes : AmpAmpByOracle-> AmpAmpByOraclePhases-> AmpAmpObliviousByOraclePhases-> AmpAmpObliviousByReflectionPhases.