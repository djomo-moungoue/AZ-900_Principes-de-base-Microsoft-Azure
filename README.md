# AZ-900_Principes-de-base-Microsoft-Azure

## Définition des Termes

La `haute disponibilité` des infrastructures AZ est la capacité de ces derniers à assurer la continuité des applications hébergées en cas de problème.Elle est réalisée par le concept de rédondance qui concister à dupliquer les infrastures. Ceci s'effectue dans lors de la création du compte de stockage en choisissant une des 4 options suivante: Le stockage localement redondant (LRS), stockage géoredondant (GRS), stockage redondant interzone (ZRS) ou le stockage géoredondant interzone (GRS).

La `scalabilité (évolubilité)` d'une infrastructure AZ est sa capacité à augmenter ou diminuer les ressources disponibles verticalement ou horizontalement en fonction d'un besoin pontuel. Ceci s'effectue soit en ajoutant de nouvelles ressources (horizontal) ou en augmentant le puissance des ressources existantes (vertical). 

L`élasticité (agilité)` d'une infrastructure scalable est la capacité de celle-ci à augmenter ou diminuer (redimentioner) les ressources qu'elle héberge automatiquement en fonction de la variation de la charge de travail. Ceci peut se réaliser en définissant des métriques.

La `tolérance aux pannes` d'une infrastructure AZ est sa capacité à continuer à délivrer le même niveau de service même en cas de pannes causés par les aléats techniques et non techniques. Ceci s'effectue à travers la configuration de la zone de disponibilité (doublement complet/partiel des composants de l'infrastructure -> coût supplémentaire) lors de la création de votre machine virtuelle. Ce concept est donc limité par l'aspet budgetaire du propriétaire des infrastructures.

La `reprise après sinistre` est la capacité de votre application à redémarrer proprement quand vous avez un incident majeur. Elle est une alternative moins performante mais moins coûteuse que le tolérance aux pannes.

Contrèrement aux centres de calculs sur sites, les infractures cloud Azure permettent aux entreprises, sur le `plan économique`, de passer d'un modèle d'achat (dépenses d'investissement - CAPEX) qui mobilise beaucoup de ressources financières de l'entreprise à un modèle de fonctionnement (dépenses de fonctionnement - OPEX) qui repose sur la facturation à l'usage. L'effet de masse d'achat permet aux fournisseurs de cloud publique comme Microsoft d'acheter les infrastures moins chères et de les louer également à des coûts réduits. Microsoft permet de calculer les coûts des ressources utilisées grâce à la calcullatrice de prix.

Le `modèle de responsabilité partagée` permet de definir qui est de Microsoft ou vous est responsable des ressources et de la sécurité dans cloud Azure que vous utilisez. Ce niveau de responsabilité permet donc de définir les 3 catégories de services cloud à savoir: logiciel en tant que service (SaaS), plateforme en tant que service (PaaS) et infrastructure en tant que service (IaaS).
|N°|ressource|SaaS|PaaS|IaaS|On-premise|exemples|
|---|---|---|---|---|---|---|
|9 | Applications|Microsoft|Vous|Vous|Vous|docker, python, node.js, GitHub, java, etc.|
|8 | Données|Microsoft|Vous|Vous|Vous||
|7 | Environnement d'exécution|Microsoft|Microsoft|Vous|Vous||
|6 | Intergiciel|Microsoft|Microsoft|Vous|Vous||
|5 | Système d'exploitation|Microsoft|Microsoft|Vous|Vous|Windows ou Linux|
|4 | Vitualisation|Microsoft|Microsoft|Microsoft|Vous|Machine virtuelle Azure, Machine virtuelle Azure VMWare Solution|
|3 | Serveurs|Microsoft|Microsoft|Microsoft|Vous|Serveur SQL Database|
|2 | Stockage|Microsoft|Microsoft|Microsoft|Vous|compte de stockage Azure|
|1 | Mise en réseau|Microsoft|Microsoft|Microsoft|Vous|192.168.1.0/24 (Espaca d'adressage IPv4), ace:cab:deca::/48 (Espace d'adressage IPv6)|

Lorsque vous loyez un logiciel Microsoft (SaaS) tel que `Office 365 (Excel, Outlook, Word, PowerPoint ), salesforce, slack, Jira, Google (GMail, Sheet, Slide, etc.), WebEx` (1-9) Microsoft s'occupe de tous. Contrairement aux PaaS et IaaS qui s'obtiennent à travers l'achat de licnce, Les SaaS s'obtiennent à travers un abonnement mensuel. Le fournisseur cloud est responsable de la mise à jour de l'infrastructure, de la mise à jour des l'application et des la sauvegarde des données.

Cependant, si vous louez une plateforme Microsoft (PaaS) tel que des `App Services` (8-9), Microsoft est s'occupe de la mise en réseau jusqu'à l'environnement d'exécution de l'application (1-7). Ce type de service est généralement approprié à l'équipe de développement afin qu'il puisse développer, tester et déployer des application sans se soucier des infrastructures sous-jacents. Le fournisseur cloud est uniquement responsable de la mise à jour de l'infrastructure et vous êtes responsable de la mise à jour des l'application et des la sauvegarde des données.

Si Microsoft vous loue plutôt une infrastructure (IaaS) tel que `Machine virtuelle Azure, Machine virtuelle Azure VMWare Solution` (1-4), vous vous occuperez du système d'exploitation jusqu'à l'applications que vous exécuteriez (5-9). Le fournisseur cloud est responsable en partie de la mise à jour de l'infrastructure (mise en réseau, compte de stockage azure et erveurs). Vous êtes également responsable en partie de la mise à jour de l'infrastructure (machines virtuelles, système d'exploitation, intergiciel, environnement d'exécution) ainsi que la a mise à jour des l'application et des la sauvegarde des données.

L'`informatique sans serveur` fait référence au fait que vous n'avez pas à vous soucier de l'infrasture. Le plateforme en tant que service (PaaS) est donc un service de type informatique sans serveur (Serverless).

La notation CIDR représente une adresse IP et un suffixe qui indique les bits d'identification du réseau dans un format spécifié. Par exemple, vous pouvez exprimer 192.168.1.0 avec un identifiant réseau 24 bits sous la forme 192.168.1.0/24.

L'`infrastructure en tant que code` est une technique qui permet de coder sous forme de script l'ensemble de création et de suppression de ressources comme des machines virtuelles. L'`infrastructure en tant que code` est très important pour gérer les IaaS au sein d'une entreprise.

Lors du choix d'un service cloud le plus approprié pour votre organisation, garder à l'esprit que:
- L'IaaS vous permet d'être flexible lors de la gestion des ressources de votre infrastructure, de ne payer que le temps d'utilisation de vos ressources, et de supprimer/créer vos ressources à la volée à travers l'infrastructe en tant que code. Cependant elle vous oblige à mobiliser des compétences techniques pointues dans différents domaines. Elle est de ce fait appropriée pour les entreprises ayant des serveurs sur site et qui veulent adopter le modèle cloud progressivement.
- Le PaaS de son côté, vous épargnera de la gestion des infrastrures sous-jacent lors du développement de vos applications tout en vous permettant d'avoir de multiples environnments facturés à leur durée d'utilisation. Ce type service est donc appropriée pour les entriprises qui créer leurs logiciel directement dans le cloud. Cependant vous pourriez être limité par le fait que l'infrastructure sous-jacente ne supporte pas certains langages et certaines mises à jour de la plate-forme de développement par le fournisseur de cloud pourrait effecter vos configurations et vos applications.



## Tarification

|Ressource|critère de tarification|
|Apllication de fonction|temps d'exécution de la fonction|
|Machine Virtuelle|temps d'utilisation de la VM|
|Serveurs||
|Compte de stockage||
|Mise en réseau||

