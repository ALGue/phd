Module setup 

- clear all

- initialize parameters

- landscape design

- initialize adults

- initialize file-names for outputs

date = 0 

transition-between-years

On pose :

Un formalisme paysager

- des patchs disposant d'un land cover, d'une position, d'un attribut occupé / non-occupé par un agent

- une vue d'ensemble du paysage défini en termes de composition / configuration

- chaque patch, en fonction de son land-cover, dispose d'attributs qui caractérisent les relations entretenues avec les agents

- il existe une méthode qui permet aux patchs crops de se faire infecter par les pests, et permet la transition entre certains des états décrivant la dyamique des patchs crops

Des agents = des ennemis naturels qui disposent d'une écologie

- cycle de vie = ils vivent deux périodes chaque année, foraging + overwintering, et sont obligés de trouver deux types de ressources distinctes pour se reproduire et survivre dans les deux types de land cover

- des règles de reproduction et de déplacements = implémentation d'une théorie écologique implicite sur leur cycle de vie décrite ci-dessus

  - hypothèse de déplacement en population

  - détection des patchs = attractifs à partir seulement d'un certain degré d'infestation + capacité à les repérer de loin (+ rajouter propension à l'agrégation des prédateurs ?)

  - pas de compétition sur les patchs (pas de dépôt d'oeufs en compétition)

  - arrêt sur un patch + reproduction dépend de la présence de food

  - déplacement vers un habitat semi-naturel pour l'overwintering

  - capacité d'overwintering d'un patch = cela suppose que les prédateurs ont un certain nb de besoins pendant cette période, corrélée à la taille du cluster de SNH

- ces règles sont conditionnées par des valeurs d'attribut = coefficient de reproduction, temps avant reproduction, capacité de déplacement qui dépendent du choix de l'espèce

un formalisme de service

- une relation entre date d'infection et crop loss : on peut s'appuyer sur Kieckhefer et al. (1995), chercher d'autres références

- une relation entre timing d'arrivée des prédateurs et potentiel de régulation / crop-loss : Costamagne et al. (2015)

=> pour ce dernier point, il y a pas mal de littérature dans Zotero, peut-être se faire un résumé des résultats clés

Remarque :

peut-on trouver des études à reproduire ? Une étude avec description de nos mécanismes, une sans pour servir de test (= des études qui ont collecté des données d'abondance + variable de contrôle)

Hypothèses fortes :

- déplacement en populations des ravageurs
- pas de description des dynamiques de pests
- pas de mortalité dans les snh / taux de mortalité posé dans les crops
- taux de reproduction
- déplacements : vitesse, capacité de dispersion / à l'échelle du paysage

### Modules

Pattern-infection :

- définir période d'infection
- rythme de l'infection = nombre de patchs à infecter
- spatial-pattern : disposition spatiale des patchs à infecter
- dynamique de l'infection = seuils de temps des nouveaux stades (+ update des attributs)

Agents :

- cycle de vie = état / attribut = en foraging / en déplacement d'overwintering / en overwintering
- pattern du foraging
- pattern de déplacement 
- comportement d'overwintering

### Remarques

Bianchi et van der Werf 2003, in Bianchi et al. 2006 : Small scale landscapes that are rich in non-crop habitats have extended crop and non-crop interfaces and allow an effective early season field colonization by natural enemies. 

Zabel et Tscharntke 1998 ; Kruess et Tscharnke, 2000 ; Cronin, 2004, in Bianchi et al. 2006 : There are indications that parasitoids and predators may generally act at smaller spatial scales than herbivores and are therefore more susceptible to habitat fragmentation.

=> introduire un paramètre de vitesse de déplacement ? 

Quelle vitesse de déplacement pour les coccinelles ? Peuvent-elles réaliser de grands déplacements dans une saison ? Peuvent-elles rester dans les champs ou font-elles des allers-retours avec les snh ?

Comportement des coccinnelles : articles d'Alexandra Magro

Evans 2003, Maes et al. 2014

In Bianchi et al 2006 : In the study of Östman et al (2001) in which lower aphid pressure was found in complex landscapes than in simple landscapes, there was no indication that R.padi colonized cereal crops from non-crop habitats. In this case, non-crop habitats may have favoured natural enemies only and not R. Padi. 

=> A mettre en parallèle des études de Roschewitz et al 2005 et Thies et al. 2005 aussi avec des aphids, mais qui eux auraient pu bénéficier des non-crops en raison des alternative host plants    

2 questions :

comment les landscape features (composition / structure) influencent les prédateurs => 

- comment les snh influencent les NE ?

- comment les crops influencent les NE ?

Conservation des NE = viabilité de la pop., influencée par les landscape features => à lire d'urgence : Bianchi et al. 2007

Remarque : d'après Karp et al. (2018) => différences entre

- landscape composition = proportional area of different land use types (various snh)

- landscape configuration = spatial arrangement of surrounding land use types

- landscape diversity = nb d'habitats différents dans le surrounding landscape

### Articles contre lesquels se positionner

Positionnement par rapport à :

- Bianchi et al 2007

- Bianchi et al 2010

- Mitchell et al. 2015

- Jonsson et al. (2014)

Articulation entre conservation des populations : différents besoins localisés spatialement, nécessaire connectivité, et service = fragmentation qui peut servir à la répartition du service, capacités de déplacements + timing

Regarder Alignier et al. 2014 ?

Question : comment distinguer les effets de la structure du paysage des effets de composition ? => Martin et al. 2016

### Idée à exploiter

1/ Mapping du CBC se base sur un potentiel fourni par les habitats semi-naturels =>

- possibilité d'identifier des zones de faible potentiel, ou même mieux, de forte demande ? (mapping de la demande existe pour CBC ?) => zones prioritaires où intervenir par des mesures de restauration des snh, nécessite de connaître à quel point on doit les restaurer, s'il y a des particularités du contexte à prendre en comte (discussion sur l'infection-rate)

- possibilité de critiquer aussi la façon dont ces modèles de mapping sont conçus, avoir plus de snh étant toujours bon

2/ Resource availability : importance relative des deux types de ressource, est-ce que l'on peut mesurer l'intensité de la relation entre les deux ? Minimum pour que la pop de préds subsiste ?

3/ Notre modèle permet de mesurer la dynamique au cours de la saison des abondances de pests / ennemies, ce que peut d'études de terrain ont fait (cf. Karp et al. 2018) => se référer à Chaplin-Kramer et al. (2013) et Plecas et al. (2014)
