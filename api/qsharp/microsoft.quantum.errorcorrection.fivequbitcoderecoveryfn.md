---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 94b6c12f31b0e6367151d0ebb225cff5f82915e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853124"
---
# <a name="fivequbitcoderecoveryfn-function"></a>FiveQubitCodeRecoveryFn fonction)

Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne une fonction qui mappe les mesures de syndrome d’erreur aux opérateurs Pauli de correction des erreurs appropriés par recherche de table pour le code Quantum ⟦ 5, 1, 3 ⟧.

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Sortie : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Fonction de type `RecoveryFn` qui prend une mesure de syndrome `Result[]` et retourne les `Pauli[]` opérateurs qui corrigent l’erreur détectée.

## <a name="remarks"></a>Notes

En effectuant une itération sur toutes les erreurs de poids $1 $, nous obtenons un total de $3 \ Times 5 = 15 $ de syndromes non triviales possibles.
Avec l’identité, un tableau d’erreurs et le syndrome correspondant sont générés. Pour le code 5 qubit, cette table est donnée par : $X \_ 1 : (0, 0, 0, 1); X \_ 2 : (1,0, 0, 0); X \_ 3 : (1, 1, 0, 0); X \_ 4 : (0, 1, 1, 0); X \_ 5 : (0, 0, 1, 1) $, $Z \_ 1 : (1, 0, 1, 0); Z \_ 2 : (0, 1, 0, 1); Z \_ 3 : (0, 0, 1, 0); Z \_ 4 : (1, 0, 0, 1); Z \_ 5 : (0, 1, 0, 0) $ avec $Y _i $ obtenue en ajoutant le $X _i $ et $Z _i $ syndromes. Notez que le classement de la récupération de la table de recherche est donné en convertissant le bitvectors en entiers (à l’aide de Little endian).

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)