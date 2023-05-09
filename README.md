# AZ-900_Principes-de-base-Microsoft-Azure

azure = AZ

## Définition des Termes

La `haute disponibilité` des infrastructures AZ est la capacité de ces derniers à assurer la continuité des applications hébergées en cas de problème.Elle est réalisée par le concept de rédondance qui concister à dupliquer les infrastures. Ceci s'effectue dans lors de la création du compte de stockage en choisissant une des 4 options suivante: Le stockage localement redondant (LRS), stockage géoredondant (GRS), stockage redondant interzone (ZRS) ou le stockage géoredondant interzone (GRS).

La `scalabilité (évolubilité)` d'une infrastructure AZ est sa capacité à augmenter ou diminuer les ressources disponibles verticalement ou horizontalement en fonction d'un besoin pontuel. Ceci s'effectue soit en ajoutant de nouvelles ressources (horizontal) ou en augmentant le puissance des ressources existantes (vertical). 

L`élasticité (agilité)` d'une infrastructure scalable est la capacité de celle-ci à augmenter ou diminuer (redimentioner) les ressources qu'elle héberge automatiquement en fonction de la variation de la charge de travail. Ceci peut se réaliser en définissant des métriques.

La `tolérance aux pannes` d'une infrastructure AZ est sa capacité à continuer à délivrer le même niveau de service même en cas de pannes causés par les aléats techniques et non techniques. Ceci s'effectue à travers la configuration de la zone de disponibilité (doublement complet/partiel des composants de l'infrastructure -> coût supplémentaire) lors de la création de votre machine virtuelle. Ce concept est donc limité par l'aspet budgetaire du propriétaire des infrastructures.

La `reprise après sinistre` est la capacité de votre application à redémarrer proprement quand vous avez un incident majeur. Elle est une alternative moins performante mais moins coûteuse que le tolérance aux pannes.

