---
title: 'Q # bibliothèques standard-correction des erreurs | Microsoft Docs'
description: 'Bibliothèques standard Q #-correction d’erreur'
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5aac40686ba9b45a51e0274a1828f2ff7cce6fc3
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184438"
---
# <a name="error-correction"></a>Correction des erreurs #

## <a name="introduction"></a>Présentation ##

Dans le calcul classique, si l’un d’eux veut protéger un peu contre les erreurs, il peut souvent suffire de représenter ce bit par un *bit logique* en répétant le bit de données.
Par exemple, laissez $ \overline{0} = $0 correspond à l’encodage du bit de données 0, où nous utilisons la ligne a au-dessus de l’étiquette 0 pour indiquer qu’il s’agit d’un encodage d’un bit dans l’État 0.
Si nous commençons de la même façon que $ \overline{1} = $111, nous disposons d’un code de répétition simple qui protège contre toute erreur d’inversion d’un bit.
Autrement dit, si l’un des trois bits est retourné, vous pouvez récupérer l’état du bit logique en prenant un vote majoritaire.
Même si la correction d’erreur classique est un sujet bien plus riche que cet exemple particulier (nous recommandons la présentation de la [théorie du codage de Lint](https://www.springer.com/us/book/9783540641339)), le code de répétition ci-dessus pointe déjà vers un problème possible pour la protection des informations de Quantum.
À savoir, le titre de [non-clonage](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) implique que si nous mesurons chaque qubit individuel et que nous prenons un vote majoritaire par analogie au code classique ci-dessus, nous avons perdu les informations précises que nous essayons de protéger.

Dans le paramètre Quantum, nous voyons que la mesure est problématique. Nous pouvons toujours implémenter l’encodage ci-dessus.
Il est utile de le faire pour voir comment vous pouvez généraliser la correction des erreurs dans le cas Quantum.
Par conséquent, laissez $ \ket{\overline{0}} = \ket{000} = \ket{0} \otimes \ket{0} \otimes \ket{0}$ et laissez $ \ket{\overline{1}} = \ket{111}$.
Ensuite, par linéarité, nous avons défini notre code de répétition pour toutes les entrées ; par exemple, $ \ket{\overline{+}} = (\ket{\overline{0}} + \ket{\overline{1}})/\sqrt{2} = (\ket{000} + \ket{111})/\sqrt{2}$.
En particulier, si vous laissez une erreur de retournement de bit $X _ 1 $ agir sur le qubit du milieu, nous constatons que la correction nécessaire dans les deux branches est précise $X _ 1 $ : $ $ \begin{align} X_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left (X_1 \ket{000} + X_1 \ket @no__ t_3_ \right) \\\\ & = \frac{1}{\sqrt{2}} \left (\ket{010} + \ket{101} \right).
\end{align} $ $

Pour voir comment nous pouvons déterminer que c’est le cas sans mesurer le tout l’état que nous tentons de protéger, il est utile de noter ce que fait chaque erreur de retournement de bits vers nos États logiques :

| Erreur $E $ | $E \ket{\overline{0}} $ | $E \ket{\overline{1}} $ |
| --- | --- | --- |
| $ \boldone $ | $ \ket{000}$ | $ \ket{111}$ |
| $X _0 $ | $ \ket{100}$ | $ \ket{011}$ |
| $X _ 1 $ | $ \ket{010}$ | $ \ket{101}$ |
| $X _2 $ | $ \ket{001}$ | $ \ket{110}$ |

Pour protéger l’état d’encodage, nous devons être en mesure de distinguer les trois erreurs les unes des autres et de l’identité $ \boldone $ sans faire la distinction entre $ \ket{\overline{0}} $ et $ \ket{\overline{1}} $.
Par exemple, si nous mesurons $Z _0 $, nous obtenons un résultat différent pour $ \ket{\overline{0}} $ et $ \ket{\overline{1}} $ dans le cas de non-erreur, afin de réduire l’État encodé.
En revanche, envisagez de mesurer $Z _0 Z_1 $, la parité des deux premiers bits dans chaque État de base de calcul.
Rappelez-vous que chaque mesure d’un opérateur Pauli vérifie les eigenvalue l’État mesuré correspond à. donc, pour chaque État $ \ket{\Psi} $ dans le tableau ci-dessus, nous pouvons calculer $Z _0 Z_1 \ket{\Psi} $ pour voir si nous obtenons $ \pm\ket{\Psi} $.
Notez que $Z _0 Z_1 \ket{000} = \ket{000}$ et que $Z _0 Z_1 \ket{111} = \ket{111}$, nous concluons que cette mesure fait la même chose pour les deux États encodés.
En revanche, $Z _0 Z_1 \ket{100} =-\ket{100}$ et $Z _0 Z_1 \ket{011} =-\ket{011}$, le résultat de la mesure de $Z _0 Z_1 $ révèle des informations utiles sur l’erreur qui s’est produite.

Pour souligner cela, nous répétons le tableau ci-dessus, mais nous ajoutons les résultats de la mesure $Z _0 Z_1 $ et $Z _ 1 Z_2 $ sur chaque ligne.
Nous désignons les résultats de chaque mesure par le signe du eigenvalue observé, $ + $ ou $-$, correspondant aux valeurs Q # `Result` de `Zero` et de `One`, respectivement.

| Erreur $E $ | $E \ket{\overline{0}} $ | $E \ket{\overline{1}} $ | Résultat de $Z _0 Z_1 $ | Résultat de $Z _ 1 Z_2 $ |
| --- | --- | --- | --- | --- |
| $ \boldone $ | $ \ket{000}$ | $ \ket{111}$ | $+$ | $+$ |
| $X _0 $ | $ \ket{100}$ | $ \ket{011}$ | $-$ | $+$ |
| $X _ 1 $ | $ \ket{010}$ | $ \ket{101}$ | $-$ | $-$ |
| $X _2 $ | $ \ket{001}$ | $ \ket{110}$ | $+$ | $-$ |

Ainsi, les résultats des deux mesures déterminent de manière unique l’erreur de retournement de bits qui s’est produite, mais sans révéler d’informations sur l’état que nous envoyons.
Nous appelons ces résultats un *syndrome*et revenons au processus de mappage d’un syndrome à l’erreur qui l’a provoquée comme *récupération*.
En particulier, nous insistons sur le fait que la récupération est une procédure d’inférence *classique* qui prend comme entrée le syndrome qui s’est produit, et retourne une prescription pour la résolution des erreurs qui se sont produites.

> [!NOTE]
> Le code d’inversion de bits ci-dessus peut être corrigé uniquement par rapport à des erreurs à inversion de bit. autrement dit, une opération `X` agissant sur un seul qubit.
> L’application d' `X` à plusieurs qubit mappera $ \ket{\overline{0}} $ à $ \ket{\overline{1}} $ après la récupération.
> De même, l’application d’une opération de basculement de phase `Z` mappera $ \ket{\overline{1}} $ à $-\ket{\overline{1}} $, et mappera donc $ \ket{\overline{+}} $ à $ \ket{\overline{-}} $.
> Plus généralement, il est possible de créer des codes pour gérer le plus grand nombre d’erreurs et de gérer les erreurs de $Z $, ainsi que les erreurs $X $.

L’information qui nous permet de décrire les mesures de correction des erreurs Quantum qui agissent de la même manière sur tous les États de code est l’Essen du *formalisme du stabilisant*.
Le moteur Q # Canon fournit une infrastructure pour décrire l’encodage et le décodage à partir de codes stabilisants, et pour décrire la façon dont l’un récupère des erreurs.
Dans cette section, nous décrivons cette infrastructure et son application à quelques codes de correction des erreurs Quantum simples.

> [!TIP]
> Une introduction complète au formalisme du stabilisateur dépasse le cadre de cette section.
> Nous faisons référence aux lecteurs qui souhaitent en savoir plus sur [Gottesman 2009](https://arxiv.org/abs/0904.2557).

## <a name="representing-error-correcting-codes-in-q"></a>Représentation des codes de correction des erreurs dans Q # ##

Pour vous aider à spécifier les codes de correction des erreurs, le moteur Q # Canon fournit plusieurs types définis par l’utilisateur distincts :

- <xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`: indique qu’un registre de qubits doit être interprété comme le bloc de code d’un code de correction des erreurs.
- <xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`: indique qu’un tableau de résultats de mesure doit être interprété comme le syndrome mesuré sur un bloc de code.
- <xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`: indique qu’une fonction *classique* doit être utilisée pour interpréter un syndrome et retourner une correction qui doit être appliquée.
- <xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`: indique qu’une opération prend qubits représentant des données avec des qubits de Ancilla actualisés afin de produire un bloc de code d’un code de correction des erreurs.
- <xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`: indique qu’une opération décompose un bloc de code d’une erreur de correction du code dans le qubits de données et le qubits Ancilla utilisé pour représenter les informations de syndrome.
- <xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`: désigne une opération qui doit être utilisée pour extraire les informations de syndrome d’un bloc de code, sans perturber l’État protégé par le code.

Enfin, Canon fournit le type de <xref:microsoft.quantum.errorcorrection.qecc> pour collecter les autres types requis pour définir un code de correction des erreurs Quantum. La longueur du code est associée à chaque code de Quantum stabilisateur $n $, le nombre $k $ de l’qubits logique et la distance minimale $d $, souvent regroupées dans la notation ⟦ $n $, $k $, $d $ ⟧. Par exemple, la fonction <xref:microsoft.quantum.errorcorrection.bitflipcode> définit le code d’inversion ⟦ 3, 1, 1 ⟧ bit :

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

Notez que le type de `QECC` n’inclut *pas* de fonction de récupération.
Cela nous permet de modifier la fonction de récupération utilisée pour corriger les erreurs sans modifier la définition du code lui-même. Cette fonctionnalité est particulièrement utile lors de l’incorporation de commentaires à partir de mesures de caractérisation dans le modèle supposé par la récupération.

Une fois qu’un code est défini de cette manière, nous pouvons utiliser l’opération <xref:microsoft.quantum.errorcorrection.recover> pour récupérer des erreurs :

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

Nous explorons ceci plus en détail dans l' [exemple de code de symétrie de bit](https://github.com/Microsoft/Quantum/tree/master/Samples/src/BitFlipCode).

Hormis le code d’inversion de bits, le moteur Q # Canon est fourni avec les implémentations du [code parfait qubit](https://arxiv.org/abs/1305.08)et du [Code de sept qubit](https://arxiv.org/abs/quant-ph/9705052), qui peuvent corriger une erreur de qubit unique arbitraire.