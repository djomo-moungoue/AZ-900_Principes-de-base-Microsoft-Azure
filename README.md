# AZ-900_Principes-de-base-Microsoft-Azure

azure = AZ

## Définition des Termes

La `haute disponibilité` des infrastructures AZ est la capacité de ces derniers à assurer la continuité des applications hébergées en cas de problème.Elle est réalisée par le concept de rédondance qui concister à dupliquer les infrastures. Ceci s'effectue dans lors de la création du compte de stockage en choisissant une des 4 options suivante: Le stockage localement redondant (LRS), stockage géoredondant (GRS), stockage redondant interzone (ZRS) ou le stockage géoredondant interzone (GRS).

La `scalabilité (évolubilité)` d'une infrastructure AZ est sa capacité à augmenter ou diminuer les ressources disponibles verticalement ou horizontalement en fonction d'un besoin pontuel. Ceci s'effectue soit en ajoutant de nouvelles ressources (horizontal) ou en augmentant le puissance des ressources existantes (vertical). 

L`élasticité (agilité)` d'une infrastructure scalable est la capacité de celle-ci à augmenter ou diminuer (redimentioner) les ressources qu'elle héberge automatiquement en fonction de la variation de la charge de travail. Ceci peut se réaliser en définissant des métriques.

La `tolérance aux pannes` d'une infrastructure AZ est sa capacité à continuer à délivrer le même niveau de service même en cas de pannes causés par les aléats techniques et non techniques. Ceci s'effectue à travers la configuration de la zone de disponibilité (doublement complet/partiel des composants de l'infrastructure -> coût supplémentaire) lors de la création de votre machine virtuelle. Ce concept est donc limité par l'aspet budgetaire du propriétaire des infrastructures.

La `reprise après sinistre` est la capacité de votre application à redémarrer proprement quand vous avez un incident majeur. Elle est une alternative moins performante mais moins coûteuse que le tolérance aux pannes.

Contrèrement aux centres de calculs sur sites, les infractures cloud Azure permettent aux entreprises, sur le `plan économique`, de passer d'un modèle d'achat (dépenses d'investissement - CAPEX) qui mobilise beaucoup de ressources financières de l'entreprise à un modèle de fonctionnement (dépenses de fonctionnement - OPEX) qui repose sur la facturation à l'usage. L'effet de masse d'achat permet aux fournisseurs de cloud publique comme Microsoft d'acheter les infrastures moins chères et de les louer également à des coûts réduits. Microsoft permet de calculer les coûts des ressources utilisées grâce à la calcullatrice de prix.

Le `modèle de responsabilité partagée` permet de definir qui est de Microsoft ou vous est responsable des ressources et de la sécurité dans cloud Azure que vous utilisez. Ce niveau de responsabilité permet donc de définir les 3 catégories de services cloud à savoir: logiciel en tant que service (SaaS), plateforme en tant que service (PaaS) et infrastructure en tant que service (IaaS).
|N°|ressource|SaaS|PaaS|IaaS|On-premise|
|---|---|---|---|---|---|
|9 | Applications|Microsoft|Vous|Vous|Vous|
|8 | Données|Microsoft|Vous|Vous|Vous|
|7 | Runtime|Microsoft|Microsoft|Vous|Vous|
|6 | Middleware|Microsoft|Microsoft|Vous|Vous|
|5 | OS|Microsoft|Microsoft|Vous|Vous|
|4 | Vitualisation|Microsoft|Microsoft|Microsoft|Vous|
|3 | Serveurs|Microsoft|Microsoft|Microsoft|Vous|
|2 | Stockage|Microsoft|Microsoft|Microsoft|Vous|
|1 | Mise en réseau|Microsoft|Microsoft|Microsoft|Vous|

Lorsque vous loyez un logiciel Microsoft (SaaS) tel que `Outlook` (1-9) Microsoft s'occupe de tous. Cependant, si vous louez une plateforme Microsoft (PaaS) tel que `Azure Cloud Service` (8-9), Microsoft est s'occupe de la mise en réseau jusqu'à l'environnement d'exécution de l'application (1-7). Si Microsoft vous loue plutôt une infrastructure (IaaS) tel qu'une `machine virtuelle` (1-4), vous vous occuperez du système d'exploitation jusqu'à l'applications que vous exécuteriez (5-9).