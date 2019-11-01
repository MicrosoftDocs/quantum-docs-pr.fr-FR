---
uid: microsoft.quantum.standardlibsintro
title: Bibliothèque standard du langage Q# pour Microsoft Quantum
description: Documentation de référence pour la bibliothèque standard du langage Q# pour Microsoft Quantum
author: natke
ms.author: nakersha
ms.date: 09/04/2019
ms.topic: landing-page
ms.openlocfilehash: 25a53e1cb8577761ef89cdcf2cfcddc509093f86
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73056961"
---
# <a name="q-standard-libraries"></a>Bibliothèques standard du langage Q# #

Q# est pris en charge par une série d’opérations, de fonctions et de types définis par l’utilisateur différents qui composent la *bibliothèque standard* du langage Q# .
La bibliothèque standard du langage Q# est divisée en deux parties principales :

- **Le préambule** : opérations et fonctions définies dans le cadre de la machine cible et du compilateur, généralement dans le code .NET natif classique.
  En général, différentes machines cibles peuvent avoir des implémentations différentes du préambule approprié à chaque système.
- **Le canon** : opérations et fonctions définies en Q# qui sont construites sur la logique définie dans le préambule.
  L’implémentation du canon est indépendante par rapport aux machines cibles.
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;