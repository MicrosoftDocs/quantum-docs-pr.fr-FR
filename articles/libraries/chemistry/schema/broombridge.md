---
title: Broombridge-schéma chimie Quantum
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: c2a7636d0b3f07419e3312e04da5d811229ad854
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185322"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Schéma de chimie Quantum Broombridge # 

Un logiciel de chimie de calcul puissant, tel que [NWChem](http://www.nwchem-sw.org/) , permet de modéliser un large éventail de problèmes de chimie réels. Pour accéder aux modèles moléculaires NWChem avec la bibliothèque Microsoft Quantum chimie, nous utilisons un schéma basé sur [YAML](https://en.wikipedia.org/wiki/YAML)que nous appelons **Broombridge**. Le nom a été choisi en référence à un [repère](https://en.wikipedia.org/wiki/Broom_Bridge) qui, dans certains cercles, est célébré en tant que lieu de Hamiltonians. 

[NWChem](https://github.com/nwchemgit/nwchem) est un projet open source sous licence avec la licence ECL (permissif Education Community licence) 2,0. Broombridge est un schéma Open source qui est spécifié [ici](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) et qui est fourni avec une [définition](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) qui suit le [RFC 2119](https://tools.ietf.org/html/rfc2119) et le [script du validateur](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) sous licence MIT. 

Basé sur YAML, Broombridge est un moyen structuré, explicite et modifiable de représenter des problèmes de structure électronique. En particulier, les données suivantes peuvent être représentées : 
- Fermionic Hamiltonians peut être représenté à l’aide d’intégraux à un et deux électrons. 
- Les États de la terre et de l’enthousiasme peuvent être présentés à l’aide de séquences de création.
- Les limites supérieure et inférieure des niveaux d’énergie peuvent être spécifiées.

Le format de données peut être généré à partir de NWChem avec facilité : il existe une variété de méthodes qui vont d’une installation complète de NWChem pour exécuter des jeux de données chimiques, tels que ceux fournis [ici](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) et la sortie de Broombridge dans le cadre de l’exécution, sur un ancrage image de NWchem qui peut également être utilisée pour générer des Broombridge à partir de jeux de chimie. Enfin, une méthode visuelle pour la prise en main de la chimie de calcul rapidement sans avoir à installer de logiciel de chimie est fournie par l’interface [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) à NWChem. 

À un niveau élevé, l’interaction entre NWChem et le Microsoft Quantum Development Kit peut être visualisée comme suit : ![pile chimie](~/media/broombridge.png) la zone bleue grisée représente le schéma Broombridge, les différentes zones grisées représentent l’autre interne représentations de données qui ont été choisies pour représenter et traiter des algorithmes de Quantum pour la chimie de calcul basée sur des problèmes chimie réels. 

Plusieurs représentations chimiques définies à l’aide du schéma Broombridge sont fournies [ici](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).

