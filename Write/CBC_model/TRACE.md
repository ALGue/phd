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

### Articles contre lesquels se positionner

Positionnement par rapport à :

- Bianchi et al 2007
- Bianchi et al 2010
- Mitchell et al. 2015
- Jonsson et al. (2014)
- Visser et al. (2009)
- Segoli et al. (2012)

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

<u>*Emergence:*</u>

 the results we are interested in are the patterns of pest - natural enemies dynamics, regulation of crop patches, and crop losses due to pests, which describe the biological control service. They all emerge from the interaction between landscape complexity, pest outbreak pattern, and the landscape-NE behaviour interaction. Other parameters such as the initial position of NE populations, and external morality rates can also affect the model outputs, as a consequence we analyzed the sensitivity of the model for them.

<u>*Adaptation:*</u>

<u>*Objectives:*</u>

<u>*Learning:*</u>

<u>*Prediction:*</u>

<u>*Sensing:*</u>

<u>*Interaction:*</u>

<u>*Stochasticity:*</u>

<u>*Collectives:*</u>

<u>*Observation:*</u>









Biological assumptions

*Meta-population of natural enemie*s 

A big assumption is the fact that agents do not represent individual NE but populations of NE, that move together

*Pest outbreak patterns*

We do not explicitly model the dynamics of pests, and use simple assumptions to describe the pattern. The simplest pattern uses an infection-rate = a given proportion of crops free of pests is infected every day, and they are randomly chosen in terms of location

*Life cycle of NEs*

- Reproduction

The dynamics of natural enemies strongly depends on infected crops, because they can only reproduce on them.

- Competition



- Mortality

pas de mortalité dans les snh / taux de mortalité posé dans les crops

- Foraging

déplacements : vitesse, capacité de dispersion / à l'échelle du paysage, détection des crops

- Overwintering

*Prey - Predator system / Regulation*

We consider that a NE population can always cure an infected crop, provided that they can stay a sufficient period of time on it.

A crop patch which has been cured cannot be infected again by pests.

*Service*

Biological control service can also be measured as a "crop loss", and it only depends on the date of arrival of the pests on the crop patch, in order to take into account the phenology of the crops, and of the time frame between this date and the date of arrival of the NE

3. Observations

we measure the dynamics of infected crops and of the population of NE, measuring abundances. We also measure the foraging distance of NE in order to relate it to the regulation of pests and the crop loss. 

4. Hypothesis

Our hypothesis are:

- We should find a negative relationship between landscape complexity (proportion of semi-natural patches in the landscape) and the average individual crop loss (for one crop patch). Indeed, increasing the proportion of semi-natural patches, we increase the probability to start 1 year with more NEs (increasing the total carrying capacity during overwintering) and the probability to decrease the initial distance between NEs and crops with pests.
- Regulation of crops, *id est* the total number of crop patches attacked by pests and then visited by NEs is not directly correlated to the average individual crop loss. Indeed, crop loss is a more complex function which also depends on the timing of arrival of the NEs on infected crops.

**Initialization** - 

At t = 0, a landscape grid is computed, according to these 2 inputs:

- proportion of semi-natural patches
- and agregation levels 

The observer has set the initial number of NEs, and they are located on semi-natural patches.

These two steps are described more in details in the section 'process overview'. Rather, we want here to underline the differences between 2 distinct simulations:

Whereas the values for

- landscape features
- and initial number of NEs

could be the same between 2 simulations, in order to allow comparisons, the landscape structure has changed, as the location of the NEs. Indeed, for each simulation, we compute a new lansdcape grid on which we allocate the given initial number of NEs. These two processes include stochasticity and as a consequence, two initial environments are not directly and totally comparable.

Simulation starts:

- At year = 0
- At day = 0 (day variable is re-initialized every year)
- day 0 should be considered as the 1st of March, id est the first day of the foraging period for NE's, or the last day of overwintering period.

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

Rajouter les catégories :

- Modèle biologique, pour décrire les assumptions tirées du modèle coccinelle aphids
- Hypthèses



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