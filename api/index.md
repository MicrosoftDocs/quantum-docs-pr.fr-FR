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
# <a name="q-standard-libraries"></a><span data-ttu-id="c8791-103">Bibliothèques standard du langage Q#</span><span class="sxs-lookup"><span data-stu-id="c8791-103">Q# standard libraries</span></span> #

<span data-ttu-id="c8791-104">Q# est pris en charge par une série d’opérations, de fonctions et de types définis par l’utilisateur différents qui composent la *bibliothèque standard* du langage Q# .</span><span class="sxs-lookup"><span data-stu-id="c8791-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard library*.</span></span>
<span data-ttu-id="c8791-105">La bibliothèque standard du langage Q# est divisée en deux parties principales :</span><span class="sxs-lookup"><span data-stu-id="c8791-105">The Q# standard library is split into two main parts:</span></span>

- <span data-ttu-id="c8791-106">**Le préambule** : opérations et fonctions définies dans le cadre de la machine cible et du compilateur, généralement dans le code .NET natif classique.</span><span class="sxs-lookup"><span data-stu-id="c8791-106">**The prelude**: operations and functions defined as a part of the target machine and compiler, typically in classical native .NET code.</span></span>
  <span data-ttu-id="c8791-107">En général, différentes machines cibles peuvent avoir des implémentations différentes du préambule approprié à chaque système.</span><span class="sxs-lookup"><span data-stu-id="c8791-107">In general, different target machines may have different implementations of the prelude appropriate to each system.</span></span>
- <span data-ttu-id="c8791-108">**Le canon** : opérations et fonctions définies en Q# qui sont construites sur la logique définie dans le préambule.</span><span class="sxs-lookup"><span data-stu-id="c8791-108">**The canon**: operations and functions defined in Q# building on the logic defined in the prelude.</span></span>
  <span data-ttu-id="c8791-109">L’implémentation du canon est indépendante par rapport aux machines cibles.</span><span class="sxs-lookup"><span data-stu-id="c8791-109">The canon implementation is agnostic with respect to target machines.</span></span>
<span data-ttu-id="c8791-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span><span class="sxs-lookup"><span data-stu-id="c8791-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></span>