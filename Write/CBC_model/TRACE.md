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
- compétition forte entre les prédateurs
- reproduction dans les crops / cycle de vie plus globalement
- pas de description des dynamiques de pests
- pas de mortalité dans les snh / taux de mortalité posé dans les crops
- taux de reproduction
- déplacements : vitesse, capacité de dispersion / à l'échelle du paysage, détection des crops

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

Notes :

Est-ce que les attributs qu'on fixe aux NEs sont vraiment des attributs ? En soi tous les NEs prennent les mêmes variables, et on ne joue pas sur l'hétérogénéité de ces valeurs (ce que l'on pourrait faire si on considérait différentes espèces de NEs par exemple)

Est-ce qu'on kill les pops de NEs d'une année à l'autre (pas possible de survivre plusieurs années) ? Normalement les coccinelles sortent d'overwintering, pondent puis meurent, et ce sont leurs descendants qui font overwintering + colonisation l'année suivante.

Peut-être envisager trois leviers :

- augmentation de la quantité d'habitats
- fragmentation
- isolement des habitats (cf. Visser et al. 2009)

avec 3 mesures différentes :

- persistance des prédateurs
- pic d'abondance / audpc ?
- régulation
- crop loss

Distinguer du coup des scénarios de crop loss moyenne / sd(crop loss), les deux indicateurs étant complémentaires pour une gestion au paysage.

Le tout médié via des propriétés émergentes des systèmes proies-prédateurs qui sont échelle-dépendantes mais qui dérivent de processus qui ne sont pas échelle-dépendants : propriétés de dispersion des prédateurs (ability, foraging-frequency), taux de croissance des ravageurs (infection-rate), pattern de dispersion / apparition des ravageurs (random, depuis les snh, depuis les crops = où est-ce que se produit l'overwintering des pests)



A vérifier : est-ce que les NEs sont attirés par tous les patchs crops infectés (y compris ceux qui contiennent des NEs) ?

Benoît Collard FARRE

### Concepts à mobiliser

**<u>Meta-population</u>**

Papiers de référence : Levins et al. (1969), Ives et Settle (1997)

Levins et al. (1969) : en l'absence de prédateurs des ravageurs, l'application de mesures de contrôle des ravageurs (ici entendu pesticides) est optimale lorsque ces mesures sont synchrones splutôt qu'asynchrones, car les mesures synchrones permettent de supprimer la possibilité de reguges temporaires pour les ravageurs.	 

Ives et Settle (1997) : en présence de prédateurs des ravageurs, le caractère optimal des mesures synchrones relativement aux mesures asynchrones est moins évident. Leur modèle retrouve l'optimalité des mesures synchrones (ici la synchronicité dans la plantation des cultures, plutôt que dans l'application d'un pesticide) en l'absence de prédateurs. Mais lorsque ceux-ci sont présents, le fait de planter les cultures de manière asynchrone peut être plus efficace, selon les taux de migration des ravageurs et des prédateurs dans les champs.

**<u>Island biogeography theory</u>**

Papier de référence : MacArthur et Wilson (1967), voir Segoli et al. (2012) pour une application

"Des îles plus grandes ont une plus forte diversité spécifique, ce qui sous-entend aussi que les densités de populations devraient être plus importantes dans les habitats les plus grands".

<u>**Resource concentration hypothesis**</u>

Papier de référence : Root et al. (1973)

Elle prédit que les herbivores spécialistes ont plus de chances de trouver et de demeurer sur leurs plantes hôtes dans les grandes monocultures, provoquant l'augmentation des densités de quelques espèces de ravageurs seulement, ce qui réduit la persistence des prédateurs généralistes.

**<u>Spatial heterogeneity hypothesis</u>**

Papiers de référence : Huffaker (1958), Beddington et al. (1978), Kareiva et al. (1987), Hassell et al. (1993)

L'importance de l'hétérogénéité spatiale (**<u>synonyme souvent de fragmentation</u>**) sur les interactions hôte-parasitoïde est connue depuis l'expérience fondatrice de Huffaker (1958).

L'hétérogénéité spatiale a été classiquement vue comme stabilisatrice du comportement oscillatoire des dynamiques hôte-parasitoïdes, augmentant donc la persistance de ces interactions. Elle a donc été perçus comme favorable au contrôle biologique, et comme un mécanisme autorisant la suppression forte des ravageurs (Beddington et al., 1978).

Néanmoins, d'autres travaux empiriques (Kareiva et al., 1987) comme de modélisation (Hassell et al., 1993) ont remis en question ce rôle favorable de la fragmentation comme stabilisateur des interactions, pour plutôt souligner le fait que la fragmentation peut aussi causer des explosions de ravageurs prolongées dans le temps, et favoriser l'extinction des parasitoïdes.

Ce rôle négatif de la fragmentation sur les interactions hôtes-parasitoïdes ou proie-prédateurs pourrait trouver son origine dans deux causes distinctes :

- une capacité de dispersion limitée des parasitoïdes (Tscharntke et al., 2005)
- un comportement spécifique de recherche des proies par leurs prédateurs selon les caractéristiques du paysage (With et al., 2002)

<u>**Landscape complementation**</u>

Papiers de référence : Dunning et al. (1992)

Les individus se déplacent dans le paysage, entre patches, afin de trouver des ressources non-substituables entre elles.

### Articles contre lesquels se positionner

Positionnement par rapport à :

- Bianchi et al 2007
- Bianchi et al 2010
- Mitchell et al. 2015
- Jonsson et al. (2014)
- Visser et al. (2009)
- Segoli et al. (2012)

Voir aussi Kasai et Karpis (2011) sur la façon dont ils utilisent un ABM dans un contexte de conservation.

Pour UML et pour dynamic flowchart voir Arrignon et al. (2007)

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

## ODD 1

Methodological literature:

- Thiele et al. (2014)
- Grimm et al. (2010)
- Grimm et al. (2014)

The model description following the ODD protocol (Grimm et al., 2010) is adapted from Railsback et Grimm (2012). The source code of the NetLogo model is included in the Supplementary Material.

The model represents, in a simplified way, the meta-population dynamics of a natural enemy of crop pests, and how it affects the delivery of a biological control service, considered like a regulation service as far as a measure of crop loss. We model an agricultural landscape, as a matrix of crop and semi-natural patches. Natural enemies are able to forage, in order to find food (pests) and reproduce in crops during the season, while they flee to semi-natural patches for overwintering. The model provides a laboratory for developing a theory for the landscape management of natural enemies populations, regulation of pests and delivery of biological control service. We consider that farmers are able to modify the landscape complexity of agricultural landscapes, by varying composition or configuration of patches, and they have to address various patterns of pest outbreaks. Given the lifecycle of natural enemies, different submodels of foraging ability and capacity to survive in semi-natural habitats or in hostile matrix can be implemented. The interaction between landscape management and the characteristics of the lifecycle affects the dynamics of natural enemies and the regulation of pests, resulting in a biological control service and this output is compared to patterns observed in the reality for the corresponding lansdcape complexity, pest outbreak patterns and natural enemies characteristics.

**Purpose** - 

The purpose of the model is to investigate the relationship between agricultural landscape management and the delivery of a service of biological control of crop pests. 

Because some landscape features, such as the total quantity of semi-natural elements, may influence the dynamic of a pest-predator system and its output in terms of biological control, it has been suggested that landscape design could offer some management levers.

We wanted to explore how emergent properties of the pest-predator system at the landscape scale, such as:

- the persistence and the dynamic of predators
- the regulation of pests
- the mean intensity, the temporal and spatial patterns of biological control, 

could be influenced, in distinct ways, by:

- landscape features variations,

- processes that are entirely scale independant, and rather depend on the ecology of pests and predators,

- and their interplay.

Our model complement previous approaches, by focusing on the service delivery, and by exploring various aspects of the delivery (spatial and temporal patterns) in a management context. This is allowed by using a spatially explicit and agent-based model. 

**Entities, state variables and scales** - 

<u>*Entities:*</u>

We distinguish two basic entities:

- Patches, which are the square units of the cell grid, and can be divided into two sub-types, corresponding to a different subset of attributes and properties:
  - Crops
  - Semi-natural 
- Natural enemies populations (NEs) which are agents / individuals. We model populations (a certain number of individuals) of adult natural enemies as one agent.  All the individuals of the population have the same features, which are the attributes of the agent.

And two spatial collective entities:

- Clusters: clusters are groups of semi-natural patches which share at least one edge.
- Landscape: the whole collection of patches, crops as semi-natural, on the cell grid

<u>*About the state variables / attributes:*</u>

All patches have spatial coordinates on the grid cell. 

Crop patches also hold three variables relative to the specific location with respect to semi-natural patches:

- the spatial coordinates of the closest semi-natural patch
- the distance to the closest semi-natural patch

Semi-natural patches are grouped by clusters when they share a edge, and each cluster owns an id. 

It is important to consider clusters as entities, because we can give them specific carrying capacities which set how many NEs can overwinter in the clusters of semi-natural patches.

Grouping all patches, crops and semi-natural, we get a landscape which is described with two variables:

- proportion of semi-natural patches: percentage of semi-natural patches according to the total number of patches on the grid
- agregation level of semi-natural patches: with respect to one semi-natural patch, the number of neighbours (patches which share at least one edge) of the same type 

We use proportion of semi-natural patches as a proxy of landscape complexity, as the literature does. We also uderstand agregation level as a proxy of landscape connectivity. However, these two aspects are correlated, because in our model the proportion of semi-natural patches on the landscape grid constrains the agregation level.

Crop patches have also specific attributes according to the model dynamic. At the beginning of a simulation, crop patches are free of pests, and can be attacked, to be finally "cured" by natural enemies. As a consequence, we decided to hold to crops an attribute which model the status of the patch, in the same way that a SIR-model could do, and therefore this variable can take the four following and successive values:

- free of pests
- with pests and without natural enemies
- with pests and with natural enemies feeding on it before laying eggs
- with pests, no adult natural enemies but regulated by juveniles

Crops with pests experience a crop loss, which is regulated by natural enemies. In order to compute this crop loss, we need two additional variables, attached to these crops, which are:

- date of pest infestation of the considered crop patch
- date of arrival of natural enemies on crops with pests

We have chosen these variables as drivers of crop loss, according to various assumptions (see biological assumptions) that allow us to define and use a crop loss model.

About the pest-NEs complex:

Pests are not modeled as entities, rather we used a simple pattern for pest outbreak that affects crop patches and these attributes (see above the SIR-like model for crop patches).

Agents that represent populations of individual NEs are described with several state variables:

- the date they begin to forage: NEs start to forage, from the semi-natural patches where they were overwintering, in order to find crops with pests
- a foraging speed: NEs jump from one patch to another, and the foraging speed is the number of jumps that NEs are able to do during one tick
- an ability to detect crops with pests: when NEs jump, they need to choose one direction. As they search for crops with pests, if they detect one, they are going to take its direction in priority, otherwise they jump randomly. Their ability is the radius in which they are able to detect crops with pests.

Finally, we also attach some output variables to NEs, in order to measure the total number of foraging movements that they do in each type of environment (crops or semi-natural).

*<u>Temporal scale:</u>*

Simulations were run several successive years, generally at least 5 in order to reach an equilibrium. One year is the succession of three distinct periods, with distinct time-steps:

- overwintering: a six-months period, which corresponds to the fall plus the winter. Crops are free of pests and NEs are overwinternig in the semi-natural habitat. We do not model explicitely the population dynamic during this period, and we only fit the population of NEs with the carrying capacity of semi-natural clusters. As a consequence, the time-step of this period is only one tick.
- foraging for food and reproduction: a five-months period, and the time-step is one day, *id est* 150 ticks. Pests attack crops and NEs are searching for crops with pests in order to reproduce.
- foraging for overwintering habitat: one-month period, and the time-step is one day, *id est* 30 ticks. NEs are trying to reach the closest semi-natural habitat, where they will be able to spend the overwintering period.

*<u>Spatial scale</u>*:

One grid cell represents 1ha and the model landscape comprised 33*33 ha, *id est* 1089ha.

**Process overview and scheduling** - 

Each simulation starts with the initialization of the landscape and of the natural enemies populations, located in semi-natural patches. 

- Each grid cell is randomly assigned with a patch type (crop or semi-natural), according to the proportion of the semi-natural patches which is set by the observer
- According to their types, grid cells are arranged by permutations thanks to an algorithm, in order to reach the wanted agregation of semi-natural patches
- Clusters of semi-natural patches are identified and the relative attributes are updated
- Some specific attributes of crop patches are updated, such as the identity of anf the distance from the closest semi-natural patches
- Other attributes of patches are initialized
- NEs populations are created and located on semi-natural patches, according to the initial number which is set by the observer. They are randomly located, however the spatial allocation program avoids to locate two NEs on the same patch if possible.
- Attributes of NEs are initialized.

Once this environment is set, the simulation is run for several years without any change in the landscape structure. Each year is divided into the three periods of:

- (A) foraging for food and reproduction, 
- (B) foraging for overwintering habitat, 
- (C) and overwintering. 

We now list and order the executed processes for each period:

(A) foraging for food and reproduction (t = 0-150):

- Date is updated
- State variables of crop patches already infected by pests are updated
- Pest outbreak pattern occurs: a given number of crop patches is considered as infected with pests, and their dates of infection for these patches are updated
- External mortality pattern occurs for NEs foraging in crops: we compute a probability each NEs die, and if the mortality occurs, the agent is killed
- Foraging pattern: NEs move if they are not on a crop patch with sufficient pest density, or if they have reproduced. 
  - Depending on their speed, they need one or more ticks to do one jump to a neighbouring patch. To orient themselves, they try to detect crops with pests in a given radius around their location. The length of the radius depends on their ability to detect, which is set by the observer. They always orient themselves towards the crop which has been the first attacked in the radius. If there is no crop with pests in the radius, they randomly choose one neighbouring patch, whatever a crop or a semi-natural patch.
  - When they have found a crop patch with a sufficient population of pests, they stay a week on it, until reproducing. After they have given birth to juveniles, the agent leaves the crop patch and continues foraging. The juveniles stay on the crop patch during around three weeks, the time-frame they need to become adults and be able to forage in turn.
- Output is produced to measure the dynamics of the pest-natural enemies complex.

(B) foraging for overwintering habitat (t = 150-180):

- Date is updated
- Crop patches are updated if they have been attacked by pests in the former period, but none new infection occurs. Also, when the juveniles have reached the date to become adults, a new agent NEs is created.
- External mortality pattern can still occur for natural enemies foraging in crops
- We consider that NEs are able to detect from their location the closest semi-natural patch, and to orient themselves towards its direction. 
  - If they are not yet on a semi-natural patch, NEs move by jumping from patch to patch according to the same following speed than during the former period. 
  - When they stay on a a semi-natural patch, they no longer forage.

- Output is produced to measure the dynamics of the pest-natural enemies complex.

(C) overwintering (t = 180):

- For each cluster of semi-natural habitat, we compare the total number of natural enemies populations which flee to this cluster with its carrying capacity. NEs in excess are killed. Other ones are randomly allocated to patches of the cluster, and if possible we avoid to allocate two NEs on the same patch.
- Output is produced to measure the dynamics of NEs.
- New year starts and globals / attributes are re-initialized if necessary.

**Design concepts** - 

<u>*Basic principles:*</u>

Empirical results show a diversity of relationships between the structure of agricultural landscapes and the delivery of the service of conservation biological control, sometimes positive, negative or neutral. Especially, the proportion of semi-natural elements in the landscape seems to be an important feature, however with ambiguous results. 

It has often been argued that manipulating landscape features could be efficient agroecological levers in order to benefit from biological control, especially with the strained context about the use of chemicals to manage pests. However, the ambiguity of field results questions the mechanisms controlling the success or failure of these levers. There is a lot of difficulties in empirically investigating the relationship between landscape management and biological control, as the underlying mechanisms, because of the large spatio-temporal scales that are needed to consider, or also of the correlation between explanatory or output variables. As a consequence, modelling can help to generate and assess multiple hypothesis and scenarios.

Many NEs need no substituable resources to sustain themselves, and they find them into different habitats. That is why the presence of semi-natural elements is often correlated to the persistence and the dynamic of these NEs. This influence of landscape is known as the concept of landscape complementation.

The landscape structure affects both the dynamic of individual species and species interactions. For instance, landscape complexity and fragmentation can interplay with the dispersal ability of NEs (for instance their foraging speed and their ability to detect various resources), which affects the probability for them to find crops with pests, and finally influence both the persistence of NEs but also the regulation of pests. As a consequence, the consequences of the landscape features on the pest-predator system can emerge from ecological features which are not scale dependent.

However, the influence of landscape features on the dynamic is not necessary the same than on the delivery of the biological control service. Indeed, while fragmentation is often seen as a risk factor for persistence of NEs, it could  also be related to a positive and more homogenized provision of service. It suggests the possibility of tradeoff between the outcomes relative to prey-predator dynamics and the biological control service delivery when landscape management levers are implemented. Indeed, biological control can be assessed through indicators such as the crop loss experienced in crop fields. It is well established that the negative impact of pests on crops depends on the phenology of the plant, and so of the time into the plant growing period. It also depends on how much time pests can spend on crops without regulation, *id est* of the timing of arrival of predators on crops. As a consequence, while a certain landscape structure can ensure the persistence of predators, and finally a good regulation of pests, it is not necessary going hand in hand with the wanted crop loss threshold.

We model an agricultural landscape with crops and semi-natural elements, and a tri-trophic species module: the crop, an herbivore (a crop pest) and a predator (the natural enemy of the pest). We assume that NEs experience landscape complementation, and need crops for reproducing and semi-natural elements for overwinternig, as no substituable resources, during their life-cycle. Under a variety of scenarios regarding the ecological features of individual species, we explore the consequences of the landscape complexity on the pest-predator dynamic and the delivery of the biological control service, understood as a crop loss indicator. In our model, this indicator depends on both timings of successive pest and predator arrivals on crops. We explore the variation in average crop loss, depending on the landscape complexity, and also the spatial heterogeneity of crop loss in the landscape. Results in terms of crop loss are confronted with the dynamic outputs, in order to test the coherence of these distinct indicators.

<u>*Emergence:*</u>

With our model, we want to test if we are able to reproduce different relationships (positive, negative) between the landscape complexity (total amount of semi-natural elements in the landscape) and some indicators of:

- NEs dynamics,
- regulation of pests,
- biological control service (crop loss),

when we implement distinct scenarios for ecological features of the pest-predator system.

These scenarios are about:

- pest features: intensity of the attacks of crops by pests
- predator features: external mortality in crops when foraging, dispersal ability (foraging speed and ability to detect crops with pests)

The output patterns emerge from the interplay between the landscape structure and the ecological features which drive the pest-predator system dynamic through the behaviour of NEs.

<u>*Adaptation:*</u>

We do not implement any evolutive trait, nor any capacity for agents to adapt their decision-making modes in our model.

However, NEs take decisions when foraging, to orient themselves. This decision depends on the landscape structure around them and on how they are able to perceive it.

<u>*Objectives:*</u>

Actions to find crops with pests and overwintering habitats when necessary are the two determinants of the individual fitness for one NEs popoulation (= one agent).

When foraging for food, NEs have to choose in a radius one patch to orient themselves before jumping from their location to one neighbour. We choose a deterministic way for decision-making. Indeed, NEs choose in the radius they are able to perceive the crop patch where pests have spent the longer time, whatever the distance from their current location. As a consequence, NEs may prefer to orient towards a further patch whereas other patches with pests are in the vicinity.

When foraging for overwintering habitats, the decision is deterministic and we assume that NEs have a complete understanding of the landscape and are able to detect the closest semi-natural patch from their location. As a consequence, they always do the best choice in orienting themselves.

<u>*Learning:*</u>

Agents (NEs) can not adapt their traits over time as a consequence of their experience. As a consequence, all the ecological features are set during the initialization of the simulation.

<u>*Prediction:*</u>

We do not consider predictions from agents, based on their experience, to adapt their decision process because all the ecological features are set before the beginning of the simulation.

<u>*Sensing:*</u>

NEs are able to detect food, id est crops with pests in radius around their location with varying length, depending on the ability that the observer has set.

Whatever the distance, NEs are assumed to be able to detect the closest semi-natural patch from their location when foraging to find overwintering habitats.

<u>*Interactions:*</u>

Of course we assume direct interactions between pests and predators, trophic interactions. When they encounter crops with a sufficient density of pests, *id est* pests are on this crop patch for long enough, NEs stay on this crop until reproducing. Juveniles are not modeled as agents, rather we model a crop patch status "with pests and juveniles". Reproduction rate is of 1, *id est* one NEs population on a crop with pests will give birth to one another NEs population modeled as an agent. This reproduction rate is not variable and does not depend on other conditions.

We also assume indirect interactions of competition, between NEs, of two types:

- competition for food: when a NEs has found a crop with pests, it stays on it until reproducing. Although the other NEs are able to detect this same crop patch and orient themselves towards it, because of pests, they are not allowed to stay on it if it is already occupied by NEs. 
- competition for overwintering habitats: clusters of semi-natural patches have a certain carrying capacity, in terms of the total number of NEs populations they are able to shelter for overwintering. When too many NEs have reached the same cluster, they are not able to search for less crowded clusters, and the populations in excess are killed.

<u>*Stochasticity:*</u>

We use different sources of stochasticity in our simulations:

The first source is about the landscape structure, which can vary between 2 simulations, whereas the same values aer used for descriptors such as the amount of semi-natural patches and the agregation level.

Also during the initialization, the location of the NEs is randomized between simulations.

A second source is about the spatial pest attack pattern, because the location of crops which are attacked by pests is randomized.

A third source is about the conditions that endure NEs and their behaviour:

- at first, NEs experience external mortality each time they are in crops. As a consequence they can die when foraging in crops with a certain probability.
- when they forage, if there is no crops with pests in the radius, NEs have to randomly choose any patch in their neighbourhood

<u>*Collectives:*</u>

We consider groups of semi-natural patches, *id est* patches which share at least one side, as a collective entity called 'cluster', with specific attributes and properties.

Especially, they interact with NEs during overwintering, because clusters have a carrying capacity depending on their size (number of patches in the cluster).

<u>*Observations:*</u>

During each simulation, we pick a collection of variables, which could be explanatory as outputs.

Explanatory variables are:

- descriptors of the landscape structure: proportion of semi-natural elements ; agregation ; for each crop patch, the distance from the closest semi-natural patch
- ecological features of the pest-predator system: infection-rate of pests, foraging-speed and ability to detect crops with pests for predators, external mortality of predators in crops, sensibility to the overwintering effect

Outputs are:

- dynamics: abundance of predators, number of foraging-movements
- regulation: proportion of crops with / without pests
- service: for each patch attacked by pests and visited by predators, we pick the timing of arrivals for pests and NEs on this patch, in order to compute crop loss

**Biological assumptions for the model **-

Our reference to draw the model design and the parametrization was the aphid-ladybird system, which is very classical for studying conservation biological control.

<u>*Meta-population of NEs:*</u> 

We choose to consider NEs agents as populations of NEs rather than as individual NEs. This choice make us easier to model a large number of arthropods.

Ladybirds are not very gregarious, and rather they have an individual behaviour of foraging. However they are able to detect clues for resources on large distance, and from a macro-perspective, a group of ladybirds can have more or less the same dispersal pattern, that is why we have chosen to model these groups as populations.

Ladybirds are sensible to the landscape scale, and classically empirical studies show that the best predictive scale is around 1km (Elliott et al. 1999, Gardiner et al., 2009, Taki et al., 2013).

<u>*Pest outbreak patterns:*</u>

We do not explicitly model the dynamics of pests, in terms of densities. Rather, we use an attribute of crops to mimick a SIR model. We did it because we focused more on the presence of pests, and on the timing of arrival on crops, in order to define and compute crop loss.

Also, spatial allocation of newly attacked crops is randomized. We do not model specific spatial patterns of pest dispersal, such as the infection by neighbours, or as a density-dependence function. Rather, we suppose that pests arrive from outside the landscape grid, for instance flying on long distances, and fall on the crops.

<u>*Life cycle of NEs*:</u>

We suppose landscape complementation, and NEs survival and reproduction depend on 2 non-substituable resources, which are crops with pests for food and overwintering habitats.

We suppose that NEs can reproduce only on crops with pests. They are not able to detect crops with pests before a certain amount of time. Also, we suppose that only one NEs population can stay on a crop patch with pests, and if other NEs are attracted by the same patch, they do not stay and rather are searching for another patch.

These assumptions are based on the ladybird model. Indeed, ladybirds search for preys with sufficient density and lay eggs only if this condition is satisfied. As the preys are more available in crops than in semi-natural elements during the season, they essentially reproduce in crops. Also, there is a strong interaction of competition between ladybirds, because when food (preys) is scarce, juveniles are subject to cannibalism. As a consequence, adults avoid to lay eggs on the same food spot.

We suppose external mortality when NEs are foraging in crops. Contrary to semi-natural habitats, less disturbed, we assume the possibility of NEs agent extinction when foraging in crops, for instance in consequence of a pesticide application.

We assume that NEs are able to detect crops with pests, as overwintering habitats, on large distances. Ladybirds are able to detect different clues in their environment, notably chemicals and molecular clues, which allow them to orient themselves. 

We assume that NEs are not able to overwinter in crops. In reality, crops often face some disturbances (pesticides, ploughing...) that are detrimental to NEs, which often need to find specific conditions to overwinter. A lot of ladybird species are supposed to overwinter in semi-natural patches rather than in crops, and to colonize crops when a new season starts.

<u>*Prey - Predator system / Regulation:*</u>

In our model, regulation is always the consequence of NEs arrival on crop with pests. We do not model the dynamics of the densities of pests and of the NEs (in one population, at the individual scale). As soon as NEs have spent around 7 days on a crop with pests, juveniles are born and around three weeks later they become adults and can forage. At this point, we consider than crop patch do no longer experience pests. These durations are parametrized from the ladybird model.

For simplicity, we also suppose that a crop patch can not be attacked twice by pests during a season.

<u>*Service:*</u>

We define biological control service as a percentage of crop loss.

It depends on two outputs:

- timing of pest arrival: considering the phenology of crops, we suppose that the later pest attack crops, the less they experience crop loss
- timing of NEs arrival: NEs are able to control pest damage, and we compute the coefficient of damage regulation according to the timing of arrival of NEs. The later they arrive after pests, the less they are able to control pest damage.

This mechanism comes from the literature (Costamagna et al., 2015).

**Hypothesis** - 

Our hypothesis are:

*<u>Hypothesis 1:</u>*

We should find a negative relationship between landscape complexity (proportion of semi-natural patches in the landscape) and the average individual crop loss (for one crop patch). 

Indeed, increasing the proportion of semi-natural patches in the landscape:

- the global carrying capacity of the landscape for overwintering increases, and the total abundance of NEs when a new year starts should increase
- as the number of NEs should be higher, and the distance for each crop to the closest semi-natural patch should be lesser, NEs should arrive sooner on crops with pests

*<u>Hypothesis 2:</u>*

Regulation of pests by NEs is not always correlated to the delivery of a 'good' biological control service.

Indeed, crop loss depends not only of the regulation (proportion of crops attacked by pests and visited by NEs), but also of the timings of arrival for pests and NEs. The relationship between regulation and crop loss could be modulated by:

-  landscape features
- ecological features

**Initialization** - 

At t = 0, a landscape grid is computed, according to these 2 inputs:

- proportion of semi-natural patches
- and agregation levels 

The observer has set the initial number of NEs, and they are located on semi-natural patches.

These two steps are described more in details in the section 'process overview'. Rather, we want here to underline the differences between 2 distinct simulations:

Whereas the values for:

- landscape features,
- and initial number of NEs,

could be the same between 2 simulations, in order to allow comparisons, the landscape structure has changed, as the location of the NEs. Indeed, for each simulation, we compute a new lansdcape grid on which we allocate the given initial number of NEs. These two processes include stochasticity and as a consequence, two initial environments are not directly and totally comparable. In order to overcome this difficulty, we run for each scenario of initial environment a set of simulations and we average the results.

Simulation starts:

- At year = 0
- At day = 0 (this variable is re-initialized every year)

**Input data** - The model does not include any external input.

**Submodels** - Submodels are listed in Table 1

*Pattern of pest outbreak:*

For the moment we use a very simple pattern for pest dynamic. 

The observer sets for the simulation an infection rate. Infection rate is the percentage of crops, among the crops without pests on them, which is attacked by pests, every tick. As a consequence, every tick and for a given infection rate, the same number of crops is infected, until the stock of crops without pests is insuficient. In this situation, all the residual crops without pests are infected. 

One consequence is thet for this pattern, the infection rate is not dependant of the number of crops already infected (no density-dependence).

Also, the spatial location of the crops to be infected is random. We do not consider here that the proximity of crops with pests influence the probability for a neighbour to be infected.

The two last assumptions can be understood as a long-distance infestation phenomenon: pests disperse from a very large distance, exceeding the landscape scale, for instance thanks to the wind, and arrive randomly on cells of the grid.

We consider only one infection per year.

We do not explicitly model pests as entities. Rather, we update the attribute of crops, as a SIR model could do.

*Foraging behaviour:*

We consider two distinct temporal patterns:

- Between t = 0 and t = 150, NEs search for food in crops, id est crops with pests where they are able to reproduce
- Between t = 150 and t = 180, NEs search for refugees, id est semi-natural patches where they are able to overwinter

The foraging speed is always the same during the simulation, whatever the temporal pattern, and does not depend on landscape features. We model the foraging speed as the number of jumps between two cells that a NEs population is able to do between two ticks.

When foraging for food, NEs have a certain ability to detect crops with pests. Depending on the value of the ability, NEs are able to orient themselves towards crops with pests in larger radius around their own location.

When foraging for refugees, we consider that NEs are able to detect and orient themselves towards the closest semi-natural patch, whatever the distance from this patch or the features of its cluster.

*Mortality pattern:*

We consider crops as a hostile matrix, where NEs experience mortality when foraging. Every foraging movement occurs a certain probability to die.

This mortality is set by the observer and does not change during the simulation. It does not depend on the total number of previous foraging movements of the agent (distance-dependence), nor of the total number of NEs in the landscape (density-dependence).

On the contrary, we consider that NEs can not die when they forage in semi-natural patches or are reproducing on crops.

*Crop loss computation:*

We model the delivered service of biological control under the form of a crop loss, for each crop patch infected with pests. 

Crop loss depends on:

- plant phenology: the earlier is the attack of crops by pests, the higher is the crop loss. As a consequence, the date of arrival of pests on crops, or infection-date, is a crucial parameter that we need to pick during the simulation.
- regulation rate: the regulation activity of pests by NEs modulates the crop loss value. We consider that the ability of NEs in regulating pests depends on the time that pests had to develop, before the arrival of NEs. As a consequence, we pick the time between pest and NEs arrival, in order to compute the regulation rate on a crop patch.

(equations)

**Parameters** - Parameters are listed in Table 2

| Module    | Parameter                    | Values                        | Unity  | Description                                                  | Article de référence |
| --------- | ---------------------------- | ----------------------------- | :----: | ------------------------------------------------------------ | -------------------- |
| Landscape | Proportion                   | 0-90                          |   %    | % of semi-natural patches in the landscape                   |                      |
| Landscape | Agregation-level             | 1-5                           |   x    | Coefficient of agregation between semi-natural patches, computed thanks to the average number of shared edges between semi-natural patches |                      |
| Landscape | Accuracy                     | 0.1                           |   x    | Quality of the match between the agregation level that the observer set and the agregation level of the computed virtual landscape |                      |
| Landscape | Max-permutations             | 150                           |   x    | Maximal number of allowed permutations of patches in order to reach the wanted agregation-level. |                      |
| Time      | Nb-Years                     | 5                             | years  | Total number of years of the simulation                      |                      |
| Time      | Length-season                | 180                           | ticks  | Total number of ticks for the foraging season                |                      |
| Time      | Date-to-flee                 | 150                           | ticks  | Date for which NEs end to forage for food and start for finding semi-natural patchs for overwintering |                      |
| Pest      | latent-period-duration       | 6                             | ticks  | Number of ticks before a patch which has been infected may be detected by NE's |                      |
| Pest      | Infection-rate               | 0.1-10                        |   %    | Percentage of crops without pests which are attacked every tick |                      |
| NEs       | External-mortality           | 0.01-0.1                      |   x    | Probability of death, for each foraging-movement from a crop |                      |
| NEs       | foraging-frequency           | 1-5                           |  tick  | Number of ticks which is necessary to move from one patch to a neigbouring one |                      |
| NEs       | ability-to-detect            | 9/25/49                       | radius | Distance at which NEs are able to detect crops with pests    |                      |
| NEs       | mortality-pattern            | constant / density-dependence |   x    | type of mortality pattern                                    |                      |
| NEs       | duration-before-eggs         | 8                             | ticks  | Number of ticks NEs need to spend on crops with pests before being able to lay eggs and starting forage again |                      |
| NEs       | duration-juvenile-occupation | 21                            | ticks  | Number of ticks juvenile NEs need to spend on crops with pests before definitely regulating them and becoming adult NEs |                      |
| NEs       | gamma-without-CBC            | (- log(0.75) / (7 / 180))     |   x    | Coefficient for service computation, in order to compute the maximal crop loss on a crop patch, without any regulation from NEs |                      |
| Service   | gamma-regulation-rate        | (- log(0.75) / (7 / 180))     |   x    | Coefficient for service computation, in order to compute the regulation rate of pests by NEs |                      |
| Service   | folder-path                  | /folder-path                  |   x    | Folder path for output files                                 |                      |
|           |                              |                               |        |                                                              |                      |

## ODD 2

**<u>2.1 Overview</u>**

**2.1.1. Purpose** -

The purpose of the model was to investigate how the spatial arrangement of crops and semi-natural elements in an agricultural landscape can deliver various patterns for the ecosystem service of conservation biological control, emerging from the ecological features of the pest-predator system.

**2.1.2. State variables and scales** -

We represent an agricultural landscape with a spatial grid, each cell of the grid is a patch and can be either a crop field  or a semi-natural element. Semi-natural elements in agricultural landscapes are woody, herbaceous or flowering elements, which are not cultivated nor intensively managed by farmers. We discretized the spatial domain in 33 * 33 cells of 1ha. The landscape structure can be summarized thanks to several indicators, such as the proportion of semi-natural elements, or their agregation. Time-step is the day, and simulations for one iteration of the model were run several successive years in order to reach an equilibrium.

Predators populations are the main entities of the model, represented as individuals taking any location in the landscape grid, *id est* we assume that an individual on a patch is like a population covering the whole area of the patch. We have only explicitely modelled adult predator stage, which is characterized by a dispersal ability. We have not explicitely modelled juvenile predators, nor pests, which are implicitely encapsulated in attributes of patches. As a consequence, individual predators only interact with patches, no other individual entities.

Pests are characterized by the attacking intensity, *id est* the number of crops that they are able to infect each day, and by the spatial pattern of infection. This pattern can be completely randomized, or being oriented by spreading in the vicinity from intial sources in crops or semi-natural elements. Predators can have different abilities to forage, according to the foraging speed (the number of jumps from patch to neighboour patch they are able to do in one day) and the ability to detect crops with pests (the distance radius in which they can detect them). Predators also experience varying mortality, in crops because of disturbances, and in semi-natural elements during overwintering, because of the limited carrying capacity of semi-natural elements during this season which drives the competition between predators. According to these ecological features of the pest-predator system, we have built different scenarios that we have implemented while varying the landscape structure, in order to understand how they interplay to produce distinct patterns of crop loss at the landscape scale.

**2.1.3. Process overview and scheduling** -  

Each year is characterized by a succession of events grouped into 3 seasons: foraging for food, foraging for overwintering habitats and overwintering. During the 'foraging for food' season, predators forage in the whole landscape in order to find crops with pests. When they find them, they stay until reproducing and once it is done they are still foraging. Juvenile predators regulate pests, become adults and start foraging. At a certain point, predators change their foraging behaviour, in order to find overwinternig habitats rather than crops with pests. They detect the closest semi-natural patch from their location and try to move to it. When the 'overwintering' season starts, predators that are still in crops are killed. Semi-natural elements have a limited carrying capacity and as a consequence, predators in excess on a semi-natural element died. A new year starts once the overwintering season is completed. One iteration of the model represents successive years.

We present below the sequence of the events describing the course of the year:

(A) 'foraging for food' season (days 0 - 150)

- Procedure *UpdateCropStatus* (Section 2.3.1.1) updates the attributes of crops according to the presence of pests or predators on themselves
- Procedure *PestPattern*  (Section 2.3.1.2) converts some crops which were free of pests into crops with pests
- Procedure *MortalityInCrops*  (Section 2.3.1.3) makes a certain number of predators foraging in crops to die
- Procedure *ForagingForCrops*  (Section 2.3.1.4) decides for each predator which is not yet on a crop with pest to move

(B) 'foraging for overwintering habitats' season (days 150 - 180)

- Procedure *UpdateCropStatus* updates the attributes of crops according to the presence of pests or predators on themselves
- Procedure *MortalityInCrops* makes a certain number of predators foraging in crops to die
- Procedure *ForagingForOverwinteringHabitats*  (Section 2.3.1.5) decides for each predator which is not yet on a semi-natural patch  to move

(C) 'Overwintering' season (day 180 - day 0: this season represents half a year but is computed in only 1 tick)

- Procedure *OverwinteringInSemiNaturals*  (Section 2.3.1.6) delete predators in excess according to the carrying capacity of the semi-natural element where they sheltered, and dispatch them into the semi-natural patches of the same cluster

**<u>2.2 Design concepts</u>**

**Basic principles** -