# AZ-900_Principes-de-base-Microsoft-Azure

## Les concepts du cloud

La `haute disponibilité` des infrastructures AZ est la capacité de ces derniers à assurer la continuité des applications hébergées en cas de problème technique avec des machines virtuelles ou le réseau par exemples.Elle est réalisée par le concept de rédondance qui conciste à dupliquer les infrastrutures. Ceci s'effectue lors de la création du compte de stockage en choisissant une des 4 options suivantes: Le stockage localement redondant (LRS), stockage géoredondant (GRS), stockage redondant interzone (ZRS) ou le stockage géoredondant interzone (GRS).

La `scalabilité (évolubilité)` d'une infrastructure AZ est sa capacité à augmenter ou diminuer les ressources disponibles verticalement ou horizontalement en fonction d'un besoin pontuel. Ceci s'effectue soit en ajoutant de nouvelles ressources (horizontal) ou en augmentant le puissance des ressources existantes (vertical). 

L`élasticité (agilité)` d'une infrastructure scalable est la capacité de celle-ci à ajouter ou supprimer (redimentioner) les ressources qu'elle héberge automatiquement en fonction de la variation de la charge de travail. Ceci peut se réaliser en définissant des métriques.

La `tolérance aux pannes` d'une infrastructure AZ est sa capacité à continuer à délivrer le même niveau de service même en cas de pannes causées par les aléats techniques et non techniques. Ceci s'effectue à travers la configuration de la zone de disponibilité (doublement complet/partiel des composants de l'infrastructure -> coût supplémentaire) lors de la création de votre machine virtuelle. Ce concept est donc limité par l'aspet budgetaire du propriétaire des infrastructures.

La `reprise après sinistre` est la capacité de votre application à redémarrer proprement quand vous avez un incident majeur. Elle est une alternative moins performante mais moins coûteuse que le tolérance aux pannes.

Contrèrement aux centres de calculs sur sites, les infractructures cloud Azure permettent aux entreprises, sur le `plan économique`, de passer d'un modèle d'achat (dépenses d'investissement - CAPEX) qui mobilise beaucoup de ressources financières de l'entreprise à un modèle de fonctionnement (dépenses de fonctionnement - OPEX) qui repose sur la facturation à l'usage. L'effet de masse d'achat permet aux fournisseurs de cloud publique comme Microsoft d'acheter les infrastures moins chères et de les louer également à des coûts réduits. Microsoft permet de calculer les coûts des ressources utilisées grâce à la calcullatrice de prix.

Le `modèle de responsabilité partagée` permet de definir le niveau de responsabilité entre Microsoft ou vous par rapport à la disponibilité et la sécurité des ressources du cloud Azure que vous utilisez. Ce niveau de responsabilité permet donc de définir les 3 catégories de services cloud à savoir: logiciel en tant que service (SaaS), plateforme en tant que service (PaaS) et infrastructure en tant que service (IaaS).
|N°|ressource|SaaS|PaaS|IaaS|On-premise|exemples|
|---|---|---|---|---|---|---|
|9 | `Applications (+ Données)`|Microsoft|Vous|Vous|Vous|docker, python, node.js, GitHub, java, etc.|
|7 | `Environnement d'exécution ou de développement` |Microsoft|Microsoft|Vous|Vous||
|6 | Intergiciel|Microsoft|Microsoft|Vous|Vous||
|5 | Système d'exploitation|Microsoft|Microsoft|Vous|Vous|Windows ou Linux|
|4 | `Logiciel de virtualisation (hyperviseur)`|Microsoft|Microsoft|Microsoft|Vous|vmware, Microsoft Hyper-V Server, Citrix XenServer, KVM|
|3 | Serveurs physiques (noeuds ou hôte) |Microsoft|Microsoft|Microsoft|Vous|Serveur SQL Database|
|2 | Stockage (disque dur) |Microsoft|Microsoft|Microsoft|Vous|compte de stockage Azure, disque dur|
|1 | Mise en réseau|Microsoft|Microsoft|Microsoft|Vous|192.168.1.0/24 (Espaca d'adressage IPv4), ace:cab:deca::/48 (Espace d'adressage IPv6)|

Lorsque vous loyez un logiciel Microsoft (SaaS) tel que `Office 365 (Excel, Outlook, Word, PowerPoint ), salesforce, slack, Jira, Google (GMail, Sheet, Slide, etc.), WebEx` (1-9) Microsoft s'occupe de tous. Contrairement aux PaaS et IaaS qui s'obtiennent à travers l'achat de licnce, Les SaaS s'obtiennent à travers un abonnement mensuel. Le fournisseur cloud est responsable de la mise à jour de l'infrastructure, de la mise à jour des l'application et des la sauvegarde des données.

Cependant, si vous louez une plateforme Microsoft (PaaS) tel que des `App Services` (8-9), Microsoft est s'occupe de la mise en réseau jusqu'à l'environnement d'exécution de l'application (1-7). Ce type de service est généralement approprié à l'équipe de développement afin qu'il puisse développer, tester et déployer des application sans se soucier des infrastructures sous-jacents. Le fournisseur cloud est uniquement responsable de la mise à jour de l'infrastructure et vous êtes responsable de la mise à jour des l'application et des la sauvegarde des données.

Si Microsoft vous loue plutôt une infrastructure (IaaS) tel que `Machine virtuelle Azure, Machine virtuelle Azure VMWare Solution` (1-4), vous vous occuperez du système d'exploitation jusqu'à l'applications que vous exécuteriez (5-9). Le fournisseur cloud est responsable en partie de la mise à jour de l'infrastructure (mise en réseau, compte de stockage azure et erveurs). Vous êtes également responsable en partie de la mise à jour de l'infrastructure (machines virtuelles, système d'exploitation, intergiciel, environnement d'exécution) ainsi que la a mise à jour des l'application et des la sauvegarde des données.

L'`informatique sans serveur` fait référence au fait que vous n'avez pas à vous soucier de l'infrasture. Le plateforme en tant que service (PaaS) est donc un service de type informatique sans serveur (Serverless).

La notation CIDR représente une adresse IP et un suffixe qui indique les bits d'identification du réseau dans un format spécifié. Par exemple, vous pouvez exprimer 192.168.1.0 avec un identifiant réseau 24 bits sous la forme 192.168.1.0/24.

L'`infrastructure en tant que code` est une technique qui permet de coder sous forme de script l'ensemble de création et de suppression de ressources comme des machines virtuelles. L'`infrastructure en tant que code` est très important pour gérer les IaaS au sein d'une entreprise.

Lors du choix d'un service cloud le plus approprié pour votre organisation, garder à l'esprit que:
- L'`IaaS` (Machine virtuelle) vous permet d'être flexible lors de la gestion des ressources de votre infrastructure, de ne payer que le temps d'utilisation de vos ressources, et de supprimer/créer vos ressources à la volée à travers l'infrastructe en tant que code. Cependant elle vous oblige à mobiliser des compétences techniques pointues dans différents domaines. Elle est de ce fait appropriée pour les entreprises ayant des serveurs sur site et qui veulent adopter le modèle cloud progressivement.
- Le `PaaS` (Environnement de développement) de son côté, vous épargnera de la gestion des infrastrures sous-jacent lors du développement de vos applications tout en vous permettant d'avoir de multiples environnments facturés à leur durée d'utilisation. Ce type service est donc appropriée pour les entriprises qui créer leurs logiciel directement dans le cloud. Cependant vous pourriez être limité par le fait que l'infrastructure sous-jacente ne supporte pas certains langages et certaines mises à jour de la plate-forme de développement par le fournisseur de cloud pourrait effecter vos configurations et vos applications.
- Avec le `SaaS` (Applications) en revanche, vous benefier d'une gamme de logiciels extrêmement vaste sans vous soucier de la gestion de l'infrastructure sous-jacent ainsi que de la sauvegarde des données. Cependant le gestion budgetaire à long terme (facturation mensuelle par utilisateur) peut devenir exponentielle en fonction de l'évolution de votre activité. En plus il vous est impossible de personnaliser l'application parce qu'elle ne vous appartient pas.

Le `cloud public` est un cloud multi-tenant c'est à dire accessible à tout le monde via Internet. Microsoft Azure est un exemple de cloud publique qui couvre environ 140 pays, possède près de 200 de centres de données physiques, organisés en régions et connectés les uns au autres par plus de 250000 km de câble optique sous-marin. Un cloud publique est intéressant parce qu'il est facilement accessible, offre des services très riche, contrôle des coûts avec le paiement à l'utilisation. cependant vous êtes dépendant des services proposés; vous êtes également confrontés à un problème de sécurité dû au fait que vous utilisez une infrastructure partagée avec d'autres clients. D'autres exemples de fournisseurs: Alibaba Cloud, AWS, Google Cloud Platform, Orange Business Services.

Le `cloud privée` est un cloud à simple tenant c'est à dire offfre des infrastructures accessibles exclusivement par un seul client pour assurer la confidentialité des données et les contraintes réglementaires. Dans ce modèle aucun moyen de communication n'existe entre les infrastructures de différents clients. A cause du coût élevé de ce dernier, il est à privilégier si le cloud publique est impossible. Exemple de fournisseurs: Openstack, WMWare. Un cloud privé peut appartir au client ou à un fournisseur de cloud qui a dédié exclusivement une infrastructure à un client.

Le `cloud hybride` est composé du cloud public, cloud privé et éventuellement d'un environnement on-premise.

Microsoft Azure propose son catalogue de services à travers sa place de marché Azure où vous pouvez choisir les services aux caractéristiques qui vous conviennent. Il ne faut pas confondre les 3 types de cloud (SaaS, PaaS et IaaS) aux 3 modèles de cloud (publique, privé et hybride).

Le `SLA` est un accord entre le fournisseur de cloud et vou qui guarantit le niveu de disponibilité de leurs infrastrustures.

Les `OPEX` sont des dépenses opérationnelles proportionnelles à la quantité de ressources et au temps d'usage des ressources d'un cloud. 

L'`autoscaling` (à ne pas confondre avec la tolérance aux pannes) est un service Azure permettant d'ajuster automoatiquement les ressources liées à votre application.

Les machines virtuelles stoppées ne sont pas facturées.

## Les Services principaux d'Azure

L'[infrastructure globale d'Azure](https://datacenters.microsoft.com/globe/explore) est repartie par géographie. Une géographie est un marché distinct marqué par les frontières d'un pays; elle peut contenir une ou plusieurs régions. Une `région` comporte plusieurs centres de données. Une `paire régionale` est constituée de 2 régions dans la même géographie; elle permet d'assurer la redondance de données liée à un compte de stockage. Un `centre de données` contient le hardware (serveurs, réseaux, stockage) utilisé par Microsoft Azure. Tout le trafic réque entrant et sortant du centre de données circule sur un réseau fibre optique de Microsoft.

La `latence du réseau` est le délai de communication réseau.

Une `zone de disponibilité` correspond à 1 centre de données particulier dans une région, isolé physiquement des autres centres de données de la région.Il est recommandé de mettre en place des zones de disponibilité si l'interruption du service des vos applications coute plus cher que le cout supplémentaire que génèrent les données repliquées dans les zones de disponibilité.

Un `groupe de ressources` permet de regrouper vos ressources de manière logique afin de les administrer plus facilement.

Un `abonnement ou souscription` est lié à une seule `facture` et un quota de ressources par régions et par types de ressource; l'augementation du quota se fait par une `demande de support`. Un `groupe d'administration (ou de gestion)` est lié à des politiques et permet de regrouper vos abonnements en fonction des politiques/stratégies de sécurité d'accès et de conformité au niveau des ressources appartenant aux abonnements.

Un modèle `Azure Resource Manager (ARM)` est constitué d'un fichier JSON qui contient tous les paramètres de la ressource. A l'aide d'un modèle ARM existant, vous pouvez utiliser `Azure PowerShell` pour automatiser la gestion de vos ressources Azure et `Azure CLI` pour automatiser la gestion de vos groupes de ressources Azure.

[Les partenaires Azure Expert MSP](https://portal.azure.com/#view/Microsoft_Azure_Marketplace/MarketplaceOffersBlade/selectedMenuItemId/home) sont des fournisseurs de services cloud ayant un badge Azure Expert MSP qui est un gage de confiance pour les clients recherchant un partenaire pour les aider à atteindre leurs objectifs de transformation numérique. Exemples:
- Luxembourg (Henson Group Services Ireland Limited, Sogeti, IBM, Fujitsu Limited)
- Allemagne (Claranet GmbH, Avanade Deutschland GmbH, Fujitsu, Hewlett-Packard Galway Ltd, InTWO International, Crayon Deutschland GmbH, Nordcloud, Eviden SAS UK, Rackspace Gemany GmbH, Cognizant Technology Solutions US Corporation, IBM, SoftwareONE Inc., Henson Group, Insight Direct (UK) Limited)

Une `machine virtuelle (invité)` est un ordinateur qui est basé sur un logiciel côntrolé par un `hyperviseur` qui est installé sur un serveur physique. Une machine virtuelle a des `caractéristiques standards` liées au serveur physique sous-jacent et des `caratéristiques écosystèmes` liées au réseau virtuel sous-jacent.

L'`hyperviseur` est installé sur un serveur physique et permet de créer des instances de machines virtuelles.

Un `machine/serveur physique (hôte)` en revanche, contient une carte mère avec des processeurs, des barettes de mémoire, un ou plusieurs disques durs ou SSD et fonctionne avec un système d'exploitation Linux, Windows ou MacOS. Les serveurs physiques contenu dans les salles machines sont généralement appelés `noeud` regroupés dans des racks qui sont à leurs tour empilés dans des armoires. `salle machine (armoires ( racks (noeuds)))`.

L'`adresse IP publique` de votre machine virtuelle peut changer automatiquement lorsque vous stoppez votre VW sans la reserver (cette reservation est une ressource payante). Ne soyez donc pas surpris si elle est différente au redémarrage.

Lorsque vous créez une machine virtuelle linux, il est recommandé de la mettre à jour avant de l'utiliser afin d'y installer tous les nouveaux packages crées par linux aprés la création de l'image de la dite machine virtuelle par Microsoft.
~~~
$ sudo apt-get update
~~~

La connexion aux machines virtuelles windowns se fait par le port RDP (3389) tandis que la connexion à une machine virtuelle linux se fait à travers le port SSH (22). 

Une machine virtuelle est susceptible d'être arrêtée à cause de 3 événements:
- une `maintenance planifiée` du serveur physique par Microsoft. Exemple: mise à jour OS, drivers, etc.
- une `maintenance non planifiée` du serveur physique par Microsoft. Exemple: détection d'un problème sur l'hôte qui nécessite une mise en pause de la VW.
- un `arrête brutal` du serveur physique. Exemple: problème grave sur l'hôte qui provoque un arrête immédiat de la VW.

Le `domaine d'erreur` (vm sur différentes racks) vous permet d'assurer la haute disponibilité de vos application lors d'une maintenance planifiée et un arrêt brutal. Le `domaine de mise à jour` vous permettra d'assurer la haute disponibilité des vos apps lors des maintenances planifiées.

Un `groupe à haute disponibilité` est une fonctionnalité de regroupement logique qui permet d’isoler les ressources de machine virtuelle les unes des autres quand elles sont déployées. Il contient 2-3 domaines d'erreur et 5-20 domaines de mise à jour.

L'`équilibrage de charge`

Les `groupes de machines virtuelles identiques Azure` vous permettent de créer et de gérer un groupe de machines virtuelles avec équilibrage de charge. Le nombre d’instances de machine virtuelle peut augmenter ou diminuer automatiquement en réponse à la demande ou à une planification définie. Les groupes identiques offrent une haute disponibilité à vos applications et vous permettent de centraliser la gestion, la configuration et la mise à jour d’un grand nombre de machines virtuelles.

La `réservation` de ressources permet économiser lorsque vous savez que vous utliserez une ressources pendant une longue période. 

Le `service d'application` vous permet de déployer vos applications dans Azure sans vous soucier de l'administration des machines vituelles sous-jacentes. Le plan service d'applicaition l'ensemble des machines virtuelles créer automatique par Microsoft pour assurer le déployement de vos applications.

`Azure containair registry` permet d'enregistrer et de gérer les images Docker. `Azure container instance` permet d'exécuter les containeurs Docker. `Web app` vous permet d'empaqueter une application web en tant que image Docker.
