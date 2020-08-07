---
title: Schéma de chimie Quantum Broombridge
description: Vue d’ensemble du schéma Broombridge Quantum chimie, utilisé pour modéliser les problèmes de chimie réels avec l’Microsoft Quantum Development Kit.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
no-loc:
- Q#
- $$v
ms.openlocfilehash: ed24fdd58dc16f97d1ba8051b1c8d0fd84ce0588
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869169"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Schéma de chimie Quantum Broombridge # 

Un logiciel de chimie de calcul puissant, tel que [NWChem](http://www.nwchem-sw.org/) , vous permet de modéliser un large éventail de problèmes de chimie réels. Pour accéder aux modèles moléculaires NWChem avec la bibliothèque Microsoft Quantum chimie, vous utilisez un schéma basé sur [YAML](https://en.wikipedia.org/wiki/YAML)nommé **Broombridge**. Le nom a été choisi en référence à un [repère](https://en.wikipedia.org/wiki/Broom_Bridge) qui, dans certains cercles, est célébré en tant que lieu de Hamiltonians. 

[NWChem](https://github.com/nwchemgit/nwchem) est un projet open source sous licence avec la licence ECL (permissif Education Community licence) 2,0. Le [schéma Broombridge Quantum chimie](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)) est un schéma Open source qui comprend une [définition](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) qui suit [RFC 2119](https://tools.ietf.org/html/rfc2119) et un [script de validateur](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) sous licence du MIT. 

Basé sur YAML, Broombridge est un moyen structuré, explicite et modifiable de représenter des problèmes de structure électronique. En particulier, les données suivantes peuvent être représentées :
- Fermionic Hamiltonians peut être représenté à l’aide d’intégraux à un et deux électrons.
- Les États de la terre et de l’enthousiasme peuvent être présentés à l’aide de séquences de création.
- Les limites supérieure et inférieure des niveaux d’énergie peuvent être spécifiées.

Les données peuvent être générées à partir de NWChem à l’aide de différentes méthodes, telles que l’utilisation d’une installation complète de NWChem pour exécuter des jeux de données chimiques (par exemple, celles fournies dans la [bibliothèque NWChem](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) qui génèrent Broombridge dans le cadre de l’exécution), ou une image d’ancrage de NWChem qui peut également être utilisée pour générer des Broombridge à partir de jeux de chimie. Pour vous familiariser rapidement avec la chimie de calcul sans avoir à installer de logiciel de chimie, vous pouvez utiliser l’interface visuelle pour NWChem fournie par les [flèches EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem).

À un niveau élevé, l’interaction entre NWChem et le Microsoft Quantum Development Kit peut être visualisée comme suit : ![ pile chimie ](~/media/broombridge.png) la zone bleue grisée représente le schéma Broombridge, les différentes zones grisées représentent d’autres représentations de données internes qui ont été choisies pour représenter et traiter des algorithmes de Quantum pour la chimie de calcul basée sur des problèmes chimie réels.

Le dossier [intégral/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) dans le référentiel d’exemples du kit de développement Quantum contient plusieurs représentations chimiques définies à l’aide du schéma Broombridge.
