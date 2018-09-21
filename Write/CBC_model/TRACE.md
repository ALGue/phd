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

Ladybirds are expected to be generalist aphid predators within crop fields and are abundant when fields are surrounded by non-crop lands (Elliott et al. 1999, Gardiner et al., 2009, Taki et al., 2013) => optimal scale 1000m radius 

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



Papiers expérimentaux:

Pfister et al. (2017)

Yang et al. (2018)

Zhao et al. (2013)

Martin et al. (2016)

Woltz et al (2012)

## ODD

Methodological literature:

- Thiele et al. (2014)
- Grimm et al. (2010)
- Grimm et al. (2014)

The model description following the ODD protocol (Grimm et al., 2010) is adopted from Railsback et Grimm (2012). The source code of the NetLogo model is included in the Supplementary Material.

The model represents, in a simplified way, the meta-population dynamics of a natural enemy of crop pests, and how it affects the delivery of a biological control service, considered like a regulation service as far as a measure of crop loss. We model an agricultural landscape, as a matrix of crop and semi-natural patches. Natural enemies are able to forage, in order to find food (pests) and reproduce in crops during the season, while they flee to semi-natural patches for overwintering. The model provides a laboratory for developing a theory for the landscape management of natural enemies populations, regulation of pests and delivery of biological control service. We consider that farmers are able to modify the landscape complexity of agricultural landscapes, by varying composition or configuration of patches, and they have to address various patterns of pest outbreaks. Given the lifecycle of natural enemies, different submodels of foraging ability and capacity to survive in semi-natural habitats or in hostile matrix can be implemented. The interaction between landscape management and the characteristics of the lifecycle affects the dynamics of natural enemies and the regulation of pests, resulting in a biological control service and this output is compared to patterns observed in the reality for the corresponding lansdcape complexity, pest outbreak patterns and natural enemies characteristics.

**Purpose** - The purpose to the model is to explore how landscape complexity and pest outbreak patterns could influence the meta-population dynamic of natural enemies and drive the temporal and spatial patterns of the biological control service that they deliver.

**Entities, state variables and scales** - The entities of the model are patches and populations of natural enemies. 

Patches can be crops or semi-natural habitats. Crops can be attacked during the season by pests, and as a consequence are modeled with a state variable representing a SIR-like status: 

- free of pests
- with pests and without natural enemies
- with pests and with natural enemies (adults)
- with pests and with natural enemies (juveniles)

Two variables attached to crops allow us to compute the service of biological control: date of pest infestation, and date of natural enemies arrival on infected crops. 

We also attach to crops a variable holding the distance to the closest semi-natural patch, as a possible explanatory variable of the relationship between the landscape complexity and the biological control service. 

Semi-natural patches are grouped by clusters when they share a edge, and each cluster owns an id. Natural enemies overwinter in semi-natural patches, depending on the carrying capacity of the cluster.

Grouping all patches, crops and semi-natural, we get a landscape which is described with two variables:

- proportion of semi-natural patches
- agregation level of semi-natural patches

The two variables are two aspects of landscape complexity and connectivity, though landscape complexity is generally understood in the landscape ecology literature only as the proportion of semi-natural elements. While they are different aspects, the two variables are also correlated, especially when the proportion of semi-natural patches is high, because it constrained the agregation. Indeed, agregation is defined as the number of neighbours patches of the same type for every patch of the landscape.

Natural enemies and pests are modeled from model-species, ladybirds and aphids. Pests are not modeled as entities, however we model a pattern of pest outbreak which directly affect crop patches. For natural enemies, entities do not represent individuals but rather populations of individuals of the same specie, and as a consequence the total of the agents that we modeled form a meta-population. In the reality, even if natural enemies forage according to individual behaviour, they often detect the same clues in the landscape, and from a macro-scale perspective, they forage in the same direction, allowing us to represent them as a group of individuals or a population. We attached to natural enemies agents several state variables:

- date they begin to forage
- foraging speed
- ability to detect crops with pests

and explanatory variable such as the number of foraging movements that they do in each type of environment (crops or semi-natural).

The time step of the model is one day, and we consider each year a season of six months, during which occurs the pest and natural enemies dynamics, followed by an overwintering period of six months to complete the year. Each simulation of the model run several years, in order to reach an equilibrium.

**Process overview and scheduling** - Each simulation begins by the initialization of the landscape and of the natural enemies populations, located in semi-natural patches. Then, the simulation runs several years, divided into the three periods of foraging, back to semi-natural patches and overwintering. 

For the periods of foraging, the following list of processes is executed in the given order once per time step:

- Date is updated
- State variables of crop patches, which describe the SIR-like status of patches are updated
- Pest outbreak pattern occurs: a given number of crop patches is considered as infected with pests, and their dates of infection for these patches are updated
- External motality pattern occurs: natural enemies populations-agents have individually a probability to die, depending on if they are in crops (probability > 0, because we consider crops as a hostile matrix) or in semi-natural habitats (probability = 0 because we consider that semi-natural habitats can always sustain populations of natural enemies, without reproduction)
- Foraging pattern: the natural enemies populations forage, choosing a patch in their neigbourhood. They choose in priority crop patches with pests, but their abilities to detect them vary with the given submodels we used.  When they have found a crop patch with a sufficient population of pests, they stay a week on it, until reproducing. After they have given birth to juveniles, adult populations leave the crop patch and continue foraging. The juveniles stay on the crop patch during around three weeks, the time-frame they need to become adults and be able to forage in turn.
- Output is produced to measure the dynamics of the pest-natural enemies complex.

At date = 150 days begins the period of coming back to semi-natural patches for natural enemies, in prevision of the overwintering period. Each day:

- Date is updated
- External mortality pattern can still occur for natural enemies
- They move in direction of the closest semi-natural patch, that we consider they are able to detect in the surrounding landscape. If they have found a semi-natural patch they stay.

At date = 180 days begins the overwintering period. The time frame for this period is also 180 days (six months) but we do not model each day as for the crop growing season. We execute the following list of processes and then directly start a new year:

- For each cluster of semi-natural habitat, we compare the total number of natural enemies populations which flee to this cluster with the carrying capacity of the cluster. The excess populations are killed, the other ones are allocated to one patch of the cluster.
- Attributes of crop patches measuring the biological service are updated 

- Output is produced in order to have a final snapshot of the spatial distribution of the biological control service within the year.

**Design concepts** - 

- Emergence: the results we are interested in are the patterns of pest - natural enemies dynamics, regulation of crop patches, and crop losses due to pests, which describe the biological control service. They all emerge from the interaction between landscape complexity, pest outbreak pattern, and the landscape-NE behaviour interaction. Other parameters such as the initial position of NE populations, and external morality rates can also affect the model outputs, as a consequence we analyzed the sensitivity of the model for them.
- Meta-population of natural enemies: a big assumption is the fact that agents do not represent individual NE but populations of NE, that move together
- Pest outbreak patterns: we do not explicitly model the dynamics of pests, and use simple assumptions to describe the pattern. The simplest pattern uses an infection-rate = a given proportion of crops free of pests is infected every day, and they are randomly chosen in terms of location
- The dynamics of natural enemies strongly depends on infected crops, because they can only reproduce on them.
- We consider that a NE population can always cure an infected crop, provided that they can stay a sufficient period of time on it.
- Biological control service can also be measured as a "crop loss", and it only depends on the date of arrival of the pests on the crop patch, in order to take into account the phenology of the crops, and of the time frame between this date and the date of arrival of the NE
- Observations: we measure the dynamics of infected crops and of the population of NE, measuring abundances. We also measure the foraging distance of NE in order to relate it to the regulation of pests and the crop loss. 

**Initialisation** - Simulations start in March (month 1). Every landscape begins with ten populations of NE, which start foraging on the same date.

**Input data** - The model does not include any external input.

**Submodels** -