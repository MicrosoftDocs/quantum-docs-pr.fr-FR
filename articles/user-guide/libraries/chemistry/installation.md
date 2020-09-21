---
title: Installation de la Q# bibliothèque Microsoft chimie
description: Apprenez à installer la bibliothèque Microsoft Quantum chimie et à l’utiliser avec la plateforme de calcul de calcul NWChem.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
no-loc:
- Q#
- $$v
ms.openlocfilehash: f1a7d1d041dab73980d8debc179d6c79acac6d33
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759797"
---
# <a name="chemistry-library-installation"></a>Installation de la bibliothèque chimie

L' [exemple **MolecularHydrogen** ](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) utilise des données d’entrée moléculaires configurées manuellement.
Bien que cela soit parfait pour les petits exemples, la chimie Quantum à l’échelle requiert Hamiltonians avec des millions ou des milliards de termes.
Ces Hamiltonians, générés par des packages de chimie de calcul évolutif, sont trop volumineux pour être importés manuellement.

La bibliothèque Quantum chimie pour le kit de développement quantique est conçue pour fonctionner correctement avec les packages de chimie de calcul, notamment la plateforme de calcul de calcul [**NWChem**](http://www.nwchem-sw.org/) développée par le laboratoire Environmental-Sciences Environmental (EMSL) au laboratoire national du Nord-Ouest du Pacifique.
En particulier, le [package **Microsoft. Quantum. chimie** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) fournit des outils pour le chargement d’instances de problèmes de simulation de chimie Quantum représentés dans le [schéma Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), également pris en charge pour l’exportation par les versions récentes de NWChem.

La bibliothèque de chimie du kit de développement quantum fournit également un outil en ligne de commande, `qdk-chem` , pour la conversion entre les formats hérités et [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

Cette section explique en détail comment utiliser le kit de développement quantique avec NWChem et Broombridge, ou encore les formats hérités et `qdk-chem` .

## <a name="using-the-quantum-development-kit-with-nwchem"></a>Utilisation du kit de développement quantique avec NWChem

Pour vous familiariser avec NWChem avec le kit de développement quantique, utilisez l’une des méthodes suivantes :

- Commencez à utiliser les fichiers Broombridge existants fournis avec les exemples sur [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML).
- Utilisez le [Générateur de flèches EMSL pour le Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) qui est un serveur frontal Web à NWChem pour générer de nouveaux fichiers d’entrée moléculaire avec format Broombridge.  
- Utilisez l' [image de l’arrimeur](https://hub.docker.com/r/nwchemorg/nwchem-qc/) fournie par PNNL pour exécuter NWChem, ou
- [Compilez NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) pour votre plateforme.

Pour plus d’informations sur l’utilisation de NWChem sur des modèles chimiques à des fins d’analyse avec la bibliothèque de modèles de développement quantique, consultez la page de [bout en bout avec NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) .

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Prise en main des fichiers Broombridge fournis avec les exemples

Le dossier [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML) du référentiel d’exemples du kit de développement Quantum contient des fichiers de données de molécule en format Broombridge.  

En guise d’exemple simple, utilisez l’exemple de bibliothèque chimie [GetGateCount](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/GetGateCount) pour charger le modèle Hamilton à partir de l’un des fichiers Broombridge et effectuer des estimations de la porte de la simulation de Quantum algorigthms :

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

Pour plus d’informations sur la façon d’entrer des molécules représentées par le schéma Broombridge, consultez chargement d’un modèle de niveau de données [à partir d’un fichier](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .  

Pour plus d’informations sur l’estimation des ressources, consultez [obtention du nombre de ressources](xref:microsoft.quantum.chemistry.examples.resourcecounts) .  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>Prise en main du générateur de flèches EMSL

EMSL Arrows est un outil qui utilise des bases de données de calcul NWChem et Chemical pour générer des données de molécule.  [Le générateur de flèches EMSL pour la Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) vous permet d’entrer votre modèle à l’aide de plusieurs générateurs de modèles moléculaires et de générer le fichier de fichier Broombridge à utiliser par le kit de développement quantique.  

Dans la page EMSL, cliquez sur l’onglet ['instructions'] et suivez les instructions ['exemples simples'] pour générer des fichiers Broombridge.  Essayez ensuite d’exécuter ['GetGateCount'] pour voir les estimations de la ressource Quantum pour ces molécules.

### <a name="installing-nwchem-from-source"></a>Installation de NWChem à partir de la source

Des instructions complètes sur l’installation de NWChem à partir de la source [sont fournies par PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).

> [!TIP]
> Si vous souhaitez utiliser NWChem à partir de Windows 10, le sous-système Windows pour Linux est une option intéressante.
> Une fois que vous avez installé [Ubuntu 18,04 LTS pour Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), exécutez `ubuntu18.04` à partir de votre terminal préféré et suivez les instructions ci-dessus pour installer NWChem à partir de la source.

Une fois que vous avez compilé NWChem à partir de la source, vous pouvez exécuter le `yaml_driver` script fourni avec NWChem pour produire rapidement des instances Broombridge à partir de jeux d’entrée NWChem :

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Cette commande crée un nouveau `input.yaml` fichier au format Broombridge dans le répertoire actif.

### <a name="using-nwchem-with-docker"></a>Utilisation de NWChem avec l’ancrage

Les images prédéfinies pour l’utilisation de NWChem sont disponibles sur plusieurs plateformes via le hub de l' [arrimeur](https://hub.docker.com).
Pour commencer, suivez les instructions d’installation de la station d’accueil pour votre plateforme :

- [Installer la station d’accueil pour Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [Installer l’arrimeur pour macOS](https://docs.docker.com/docker-for-mac/install/)
- [Installer Docker pour Windows 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Si vous utilisez Docker pour Windows, vous devez partager le lecteur contenant votre répertoire temporaire (il s’agit généralement du `C:\` lecteur) avec le démon de l’ancrage. Pour plus d’informations, consultez la documentation de l' [ancrage](https://docs.docker.com/docker-for-windows/#shared-drives) .

Une fois que vous avez installé la station d’accueil, vous pouvez utiliser le module PowerShell fourni avec les exemples du kit de développement Quantum pour exécuter l’image, ou vous pouvez exécuter l’image manuellement.
Nous avons détaillé l’utilisation de PowerShell ici. Si vous souhaitez utiliser l’image de l’ancrer manuellement, consultez la [documentation fournie avec l’image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).

#### <a name="running-nwchem-through-powershell-core"></a>Exécution de NWChem via PowerShell Core

Pour utiliser l’image de l’Ancrable NWChem avec le kit de développement Quantum, nous fournissons un petit module PowerShell qui gère le déplacement des fichiers vers et depuis NWChem pour vous.
Si vous n’avez pas encore installé PowerShell Core, vous pouvez le télécharger sur plusieurs plateformes à partir du [référentiel PowerShell sur GitHub](https://github.com/PowerShell/PowerShell#get-powershell).

> [!NOTE]
> PowerShell Core est également utilisé pour certains exemples pour démontrer l’interopérabilité avec les flux de travail de science des données et d’analyse commerciale.

Une fois PowerShell Core installé, importez `InvokeNWChem.psm1` pour rendre les commandes NWChem disponibles dans votre session active :

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

La commande sera alors `Convert-NWChemToBroombridge` disponible dans votre session PowerShell actuelle.
Pour télécharger les images nécessaires à partir de la station d’accueil et les utiliser pour exécuter des jeux d’entrée NWChem et capturer la sortie sur Broombridge, exécutez la commande suivante :

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Cette opération crée un fichier Broombridge en exécutant NWChem sur `input.nw` .
Par défaut, la sortie Broombridge aura le même nom et le même chemin d’accès que le pont d’entrée, avec l' `.nw` extension remplacée par `.yaml` .
Cela peut être substitué à l’aide du `-DestinationPath` paramètre à `Convert-NWChemToBroombridge` .
Vous pouvez obtenir plus d’informations à l’aide des fonctionnalités d’aide intégrées de PowerShell :

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```

## <a name="using-the-quantum-development-kit-with-qdk-chem"></a>Utilisation du kit de développement quantique avec `qdk-chem`

Pour installer `qdk-chem` , vous pouvez utiliser la kit SDK .net Core sur la ligne de commande :

```dotnetcli
dotnet tool install --global Microsoft.Quantum.Chemistry.Tools
```

Une fois que vous avez installé `qdk-chem` , vous pouvez utiliser l' `--help` option pour obtenir plus de détails sur les fonctionnalités offertes par l' `qdk-chem` outil.

Pour convertir vers et à partir de Broombridge, vous pouvez utiliser la `qdk-chem convert` commande :

```
qdk-chem convert --from fcidump --to broombridge data.fcidump --out data.yml
```

La `qdk-chem convert` commande peut également accepter ses données à partir d’une entrée standard et peut écrire dans une sortie standard. cela est particulièrement utile dans les scripts et pour l’intégration avec les outils qui exportent vers les formats hérités.
Par exemple, dans Bash :

```bash
cat data.fcidump | qdk-convert --from fcidump --to broombridge - > data.yml
```
