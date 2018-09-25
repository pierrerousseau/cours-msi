# Modélisation des systèmes d'information


## Introduction

Plus les outils informatique se développent, plus la quantité d'information à appréhender et à produire devient importante. La gestion de cette information devient alors un facteur prépondérant quant aux diverses prises de décisions de tout type d'organisation et se déroule dans ce que nous nommons les systèmes d'informations.
La question de cette gestion a commencé à être étudiée dès les années 1970 et n'a cessée de prendre de l'importance et de s'adapter aux contraintes apportées par l'évolution des outils et des méthodes de développement de ces systèmes d'information.  

Ce cours a pour but de faire comprendre ce que sont les systèmes d'information et de donner de premières pistes quant à la conception de ceux-ci. Pour concevoir les systèmes d'information nous nous baserons ici sur la méthode de modélisation Merise, tout en l'adaptant pour faire face aux contraintes actuelles qui tendent à pousser le développement logiciel vers des méthodes dites plus agiles. 
Dans ce but, ce cours nécessite que les étudiants apprennent à appliquer une démarche segmentée en différentes étapes liées de manière cohérente, ce qui sera notre premier objectif. 

À noter que ce texte, les exercices, [contrôles](https://pierrerousseau.github.io/cours-msi/#/16) et [diapositives](https://pierrerousseau.github.io/cours-msi/) forment un tout qui s'assemble explicitement lors du cours en classe.


## Système d'Information

Nous allons tout d'abord essayer de définir ce qu'est un système d'information. Pour cela nous allons commencer par définir les notions d'information et de système. Nous prendrons ensuite le point de vue de l'analyse systémique, méthode dédiée à l'analyse des systèmes pour placer le système d'information dans son contexte. Enfin nous nous intéresserons aux qualités et aux éléments composant un système d'information. 
Ces différents angles de vues nous aiderons à préciser la notion de système d'information et ainsi comprendre ce que l'on va chercher à modéliser par la suite.

### Système et information

Donner la définition d'un système d'information est complexe. En effet, chacun, selon le point de vue où il se trouve et le niveau de granularité qui lui est utile peut donner une définition qui lui est propre. De plus, le fait que de nombreux ouvrages et que divers cours d'enseignement supérieur existent sur le sujet montre que comprendre ce qu'est un système d'information de manière à l'architecturer et à le gérer nécessite plus qu'une simple définition issue du dictionnaire. 

Cependant, pour une première approche, il me semble nécessaire de comprendre les différents mots utilisés dans le terme "système d'information". C'est également une première mise en pratique de la segmentation d'un problème. Méthode très utile dans le monde du développement que ce soit aux niveaux conceptuel ou technique : on définit chaque mot un à un, puis on assemble les définitions pour obtenir la définition du terme dans son ensemble. 

#### information

Commençons donc par définir ce qu'est une information. Comme ce terme est lui même complexe à définir allons au plus basique et commençons par ouvrir un dictionnaire.

    Information : "Données susceptibles d'être représentées à l'aide de conventions pour être conservées, traitées ou communiquées."

Pour préciser ce qu'est une donnée, on se contentera ici de prendre les deux exemples de la figure de la diapositive [2.1](https://pierrerousseau.github.io/cours-msi/#/1) : 

Le premier pictogramme une base de données, le second de simples dossiers. Les deux supports contiennent des données. Ces données, une fois traitées peuvent être visualisée, par exemple, sous forme de graphique sur un écran ou imprimé sur un fascicule. 
Un autre point mis en valeur sur cette figure est que selon la manière que l'on a de les traiter et de les représenter, on peut faire émerger de nouvelles informations qui pourront donc à leur tour être conservées, traitées ou communiquées en tant que données.

#### système

Après cette première définition, continuons de la même manière sur la notion de système.

    Système : "Ensemble d'éléments considérés dans leurs relations à l'intérieur d'un tout fonctionnant de manière unitaire."

Ce qui nous intéresse ici, c'est la vision d'un système selon deux points de vue. En interne, le système est vu selon les relations entre ses éléments, chacune ayant sa fonction. En externe, le système est un tout ayant une ou plusieurs fonctions communes à tous ses éléments.

#### système d'information

Maintenant que nous avons étudié les deux mots composant le terme "système d'information", il ne nous reste qu'à les rassembler pour trouver une définition qui sera sans doute très proche de celle données par R. De Courcy 

    Système d'information : "Un système d'information est un ensemble organisé de ressources permettant de collecter, stocker, traiter et diffuser de l'information"

Définition qui m'a semblé admise par la plus grande partie de ceux cherchant à comprendre la gestion de ce type de système et qui nous permet d'avoir une idée générale de ce qu'est un système d'information.

Nous abrégerons le terme système d'information en SI à partir d'ici.

### Analyse systémique

Un SI est par définition un système. Nous avons cherché à avoir une première idée de ce qu'est un système à travers sa définition. Nous allons maintenant essayer d'approfondir celle-ci à travers la notion d'analyse systémique.

L'analyse systémique permet de considérer la plupart des ensembles comme des des systèmes quels que soient les domaines d'appartenance de ceux-ci (société, être vivant, organisation, ...). Elle décrit un systéme comme étant :

* complexe, c'est à dire composé de différentes parties. Par exemple une université est composée de différentes UFR (Unité de Formation et de Recherche) ainsi que d'autres services (administration, inscription, ...)
* cohérent, car ces parties sont organisées et ont chacune leur place les unes par rapport aux autres. Pour reprendre notre exemple, deux UFR ne dispensent pas les mêmes formations et les différents services ne s'occupent pas des mêmes tâches
* complet, on retrouve ici la notion de tout car le système ne comporte pas de partie manquante. Même si rien n'est jamais parfait, les missions de l'université sont menées à bien : on peut s'inscrire, suivre des cours, les examens se déroulent et des diplômes sont délivrés aux étudiants
* récursif, les parties du systèmes peuvent souvent être également elles-mêmes vue comme des systèmes à part entière. Les différents services de l'université peuvent sans doute être décomposés de la même manière. On peut, par exemple, imaginer que le service d'inscription est séparé en différents guichets selon les conditions d'inscription.

S'intéresser au fonctionnement d'une organisation à travers l'analyse systémique va également nous permettre de situer le SI et de préciser ses fonctions. Prenons l'exemple d'une entreprise. De l'extérieur elle peut-être vue comme un tout, recevant et émettant des flux d'information. En effectuant un premier rapprochement, on peut la décomposer en trois sous-systèmes comme montré sur la diapositive [3.2](https://pierrerousseau.github.io/cours-msi/#/2/1) :
* le système de pilotage (SP), c'est à dire où se prennent les décisions. Par exemple le choix de la salle à réserver pour l'organisation d'un examen
* le système opérant (SO), c'est à dire où sont effectuées les actions. Pour continuer sur notre exemple, il s'agit de faire passer l'examen (installation dans la salle, distribution des sujets, ...) 
* et enfin le système d'information (SI) qui permet aux deux autres systèmes de communiquer. Le moyen par lequel le SO et le SP communiquent (comment les élèves et professeurs savent dans quelle salle se rendre)

Attention à ne pas confondre cette figure avec l'organisation hiérarchique de l'entreprise. La prise de décision est évidemment plus fréquente chez les dirigeants d'une entreprise, mais elle n'est pas inexistante à plus bas échelon. Un même individu peut interagir tour à tour avec les trois systèmes composant l'entreprise.

Nous rappelons également ici que nous discutons d'un SI et non pas de son informatisation (nous le ferons evidemment plus tard). Ainsi un document papier ou une discussion peuvent faire partie du SI s'ils permettent d'échanger des informations.

Nous venons donc de décrire plus précisément un système à travers un premier raffinement : en le décomposant en trois sous-systèmes. Ceci nous a permi de situer le SI dans un système plus large. Nous allons désormais nous concentrer sur le SI. 


### Fonctions

Nous avons donc cherché à définir la notion de SI, puis nous avons cherché à comprendre sa place dans un système plus large. Une autre manière de comprendre ce qu'est un SI est de l'appréhender à travers les qualités que l'on attend de lui. 

Fondamentalement, il doit être utile à la prise de décisions et faciliter l'application de celles-ci. Plus précisément, il doit être :
* pertinent, assez intuitivement, l'information apportée au SP doit permettre de prendre la décision du moment, de le faire avancer dans son processus de prise de décision et doit permettre au SO de comprendre celles-ci
* rapide, évidemment le SP doit recevoir l'information avant de devoir prendre sa décision et le SO doit recevoir celle-ci tant que son application est utile 
* fiable, car tant le SP que le SO ne doivent pas hésiter à prendre en compte l'information apportée par le SI
* sûr, le SI doit être en mesure de fournir la bonne information au bon destinataire
* et enfin adapté. On voudrait toujours avoir le SI le plus complet qui saura prendre en compte les événements qui pourraient arriver ... mais parfois le mieux est l'ennemi du bien. S'il faut toujours considérer le SI en fonction des besoins du système auquel il appartient, il faut aussi prendre en compte les contraintes auxquelles on doit faire face et notamment les ressources disponibles (temps, moyens, ...).


 ### Composants

Pour finir, nous allons regarder le SI sous un dernier angle en tentant de se poser la question de ce qu'est concrètement un SI. Nous apportons une réponse à travers ce qui le compose :
* outils : ils peuvent être divers, tels que les logiciels, les protocoles d'échange, mais également toute manière d'échanger de l'information
* infrastructure : on s'intéresse ici aux matériels et aux réseaux utilisés pour échanger l'information
* procédures : cela correspond à l'organisation interne, qui communique avec qui et selon quelles règles
* humains : enfin le coeur du système ses utilisateurs et au sens large ses acteurs (ceux qui fournissent ou reçoivent de l'information)


Nous venons donc de tenter de comprendre ce qu'est un SI. Comme nous l'avons vu, suivant la position d'où on le regarde cette définition peut changer. Il n'est donc pas possible de le définir de manière universelle. Cependant, en le regardant sous différents angles, nous en avons maintenant une idée suffisamment précise pour essayer de le représenter suivant un besoin concret.


## Modélisation

### Pourquoi modéliser ?

Maintenant que nous avons une idée générale de ce qu'est un SI notre but va être d'être capable d'architecturer et de gérer un SI. Pour cela nous devons : le comprendre, le structurer, le documenter et communiquer sur ces sujets. La modélisation du système va nous aider à :
* comprendre le SI, en particulier déceler les obstacles qui ne seraient pas visibles au premier abord
* le structurer, la modélisation nous apporte une démarche, nous permet de rester homogène tout au long du processus et au final de gagner du temps
* le communiquer, un modèle étant un formalisme défini et contraint il permet de lever de nombreuses ambiguïtés lié au langage courant
* le documenter, s'il faut pouvoir expliciter le quoi, il ne faut pas oublier de décrire le pourquoi

Comme le montre l'exercice de la diapositive [4.3](https://pierrerousseau.github.io/cours-msi/#/3/2), si on essaie de décrire un SI sans méthode, on ne sait pas par où commencer, le voisin ne comprend pas forcément ce que l'on a décrit, ... bref modéliser est important, le faire avec méthode nécessaire.


### Merise

La méthode de modélisation que nous avons choisie est Merise. Elle se base sur divers niveaux d'abstraction et fournit divers outils pour y arriver. 

Son défaut est sa lourdeur, surtout aujourd'hui après l'essor des méthodes dites "agiles". Par lourdeur on entend le coût complet de la modélisation et celui d'une modification dans le modèle réalisé. 
C'est une critique tout à fait valable, on n'accepte plus aujourd'hui d'attendre 6 mois avant de commencer un projet ou encore 3 semaines pour corriger une petite anomalie sur un SI opérationnel. 

Comme l'ont montré les méthode agiles, on doit adapter les procédures et choisir les outils utiles pour être réactif. C'est l'ambition de ce cours : utiliser Merise, mais dans une version plus légère et plus dynamique, mais certes moins précise. On pourrait même penser à utiliser ses méthodes et formalismes dans une gestion itérative d'un SI. On perd en précision, mais on gagne en flexibilité. Si ce n'est pas toujours le bon choix, ça l'est le plus souvent. De plus la méthode Merise elle-même se déroule elle même en deux phases, la première ne cherchant pas à modéliser chaque détail.


##### Dimensions

Un des premiers principes sur lequel se base Merise est celui des dimensions qu'elle présente sur trois axes :
* le cycle de vie : la vision classique commençant par la conception du logiciel, suivie par son développement, suivi par une phase d'exploitation et de maintenance (correction de bugs, ajout de nouvelles fonctionnalité, ...). Phases inévitablement suivies par une phase de déclin qui amène le logiciel dans un état où il ne peut finalement plus évoluer et est difficilement corrigé. S'impose alors une réécriture complète commençant par une nouvelle phase de conception
* le cycle de décision : représentant les différents choix fait lors du cycle de vie
* le cycle d'abstraction : celui que nous allons étudier, la modélisation du SI

#### Cycle d'abstraction

Le cycle d'abstraction se décompose en quatre niveaux précédés par une étape d'analyse des besoins. L'ensemble du processus va permettre de définir ces besoins, de les exprimer et de les détailler concrètement. Le but va être de ne plus laisser de zones d'ombres, de "on verra plus tard" ou d'à peu près.

* le niveau conceptuel, que l'on va essayer de garder le plus stable possible, c'est à dire qu'un changement dans un autre niveau n'affecte pas celui-ci.
* le niveau organisationnel, que l'on peut voir comme une extension du niveau conceptuel, qui prend en compte les personnes et le matériel. On étudie ces besoins séparément pour qu'ils n'interfèrent pas avec ceux étudié au niveau conceptuel.
* le niveau logique, qui est un raffinement du niveau conceptuel prenant en compte les détails technique de la modélisation, tout en restant indépendant des détails liés aux outils. Au niveau conceptuel, on s'intéresse à la structure de la donnée. Au niveau logique, on va modéliser, par exemple, une base de donnée, sans prendre en compte les détails du système de gestion de base de données que l'on va utiliser (le niveau logique doit être applicable sur une base postgres, mysql ou autre sans modification). L'idée est de pouvoir changer ce système sans modifier la modélisation au niveau logique. Au niveau du code, c'est, par exemple, un diagramme de classe qui ne change pas en changeant le langage final.
* Et enfin le niveau physique, qui adapte le niveau logique aux choix techniques.

Ainsi on le voit, chaque niveau permet de se focaliser sur une partie de la modélisation sans se préoccuper des autres. Soit en suivant une méthode basée sur le célèbre "diviser pour gagner" souvent très efficace dans les divers champs touchant à la conception. Soit par le raffinement, en allant du plus général au plus particulier. 


#### Découplage données/traitements

Merise ajoute une autre séparation plus particulière se basant sur la séparation de la statique du système (la structure des données) et la dynamique du système (les flux et manipulation de données). Cette séparation est explicite et nous permet encore une fois de découper la modélisation du SI. On ne se pose qu'une question à la fois, on peut se concentrer pour y répondre.

#### Outils

Pour y arriver, Merise se base sur les outils que nous allons énumérer ici (tableau de la diapositive [5.6](https://pierrerousseau.github.io/cours-msi/#/4/5)) et que nous allons détailler dans la suite de ce cours. Ce tableau résume de manière synthétique les étapes choisies par Merise et les outils mis à disposition pour les réaliser.


## Recueil des besoins

### Analyse préalable

N'oublions pas que nous nous concentrons sur les systèmes d'information. Le coeur de notre étude, sa matière première, sont donc les données. Les besoins que nous allons analyser ne sont pas les besoins métier de telle ou telle organisme mais quelles sont les données dont il a besoin et comment sont elles gérées, notamment à travers leurs flux de ces données. Le recueil des besoins pour une modélisation du SI va donc consister à lister les données et leurs flux.

Pour cette étape, Merise nous donne peu d'outils. On se base alors sur des techniques classiques en commençant par l'étude de l'existant : collecter les documents (ils contiennent forcément des informations), s'intéresser aux normes/procédures suivies dans l'organisme et réaliser des entretiens avec les utilisateurs du SI.
Le but de cette étape étant de déterminer les entrées d'information dans le SI, les sorties d'information, ainsi que les flux menant des unes aux autres.

Pour comprendre, on passe à directement à l'exercice de la diapositive [6.2](https://pierrerousseau.github.io/cours-msi/#/5/1). Cette étape peut être longue et son résultat restera flou, car nous n'allons justement pas encore être capable modéliser le SI formellement. 

Le recueil est souvent incomplet, il faut, en pratique, souvent revenir vers les utilisateurs. Et malgré tout, au moment de détailler, on se rend régulièrement compte qu'il nous manque des informations. 
En effet, il est difficile de recueillir les besoins car il est difficile de les exprimer. Il faut guider les utilisateurs tout en les laissant s'exprimer, car ce sont eux qui connaissent le métier. Un utilisateur connaît toujours son besoin, mais il ne sait pas toujours comment l'exprimer, ce qui est possible, ce qui est trop couteux techniquement. Et souvent il ne sait pas ce qui n'est pas évident pour quelqu'un qui n'est pas du métier, il peut utiliser un vocabulaire spécifique, ....
Ici, nous abordons cette étape au moins une fois, dans la suite, vous commencerez votre modélisation à la fin de cette étape. Le format choisi ici pour le résultat de cet exercice est celui qui sera utilisé lors des examens. Il peut y avoir des imprécisions voulues (pour l'exercice), des imprécisions non voulues (des points qui me seraient devenus évidents en travaillant sur l'exercice et que je n'explicite pas suffisamment) mais pas de tromperie (le but est de vous faire comprendre l'intérêt de ne pas s'arrêter au recueil des besoins, pas de vous égarer).

La solution donnée pour cet exercice pourrait être tout autre. Elle a été choisie en fonction de ce que l'on veut montrer dans les exercices suivants qui se baseront dessus.


## Dictionnaire de Données (DD)

Comme nous l'avons vu, l'élément de base d'une information est la donnée. Avant de pouvoir la structurer et analyser ses flux, il faut connaître les "atomes" composant notre SI.

La première étape de la modélisation consiste donc à lister les données récoltées lors de l'analyse préalable de manière à les avoir sous la main pour la suite. Pour cela, on construit ce que l'on appelle le dictionnaire de données (noté DD).
Pour simplifier cette étape, on ne se demande pas comment ces données se structurent ni même comment elles vont être utilisées.

Le plus simple est de commencer par les documents et lister les données qui s'y trouvent. Dans une modélisation réelle, il serait important de se poser la question de la pertinence de ces données : sont-elles encore utiles, y en a-t-il qui sont manquantes, mais toujours en se basant sur la connaissance métier des utilisateurs. Dans les exercices de ce cours, ce ne sera pas le cas. 
Ensuite il peut être utile de réfléchir sur les autres éléments de l'étude préalable, voir si des informations ne sont pas échangées informellement ou si de nouveaux besoins ne sont pas décelables.

Une fois la collecte effectuée, toutes les données ne sont pas conservées dans le DD. En effet, ce sont les données que nous allons stocker, on ne veut pas que cela soit coûteux ou fouilli. Pour pallier cela, il faut classifier les données et ne conserver que les données dites élémentaires, c'est à dire qui ne sont pas calculées ou composées à partir d'autres données. 

Ensuite, on va préciser ces données de manière assez technique, en définissant le type et le format des données. Ce point pouvant être finalisé plus tard. Cela peut une autre manière de définir la donnée, en tout cas, cela nous aide à préciser concrètement une donnée.

Enfin, on épure les données en supprimant les doublons (on n'essaye de ne pas le faire lors de la collecte, de manière à se concentrer sur une tache à chaque fois : la collecte, puis la classification, puis la réflexion sur les doublons).

Note : lors des examens, ne détaillez que quelques données. Le but sera de montrer que vous savez remplir chaque colonne. S'il est important d'être rigoureux, le temps d'un examen est réellement trop court pour cette tache fastidieuse et la réaliser complètement ne montrera que peu de chose sur ce que vous avez compris.


## Diagramme de Flux (DF)

Une fois les données listées dans le dictionnaire de données, nous allons chercher à décomposer le système d'information en domaines d'activités. Cela va nous permettre de préciser quels sont les acteurs du SI et quelles flux d'information il existe entre eux. On essaye ici uniquement de déterminer les différents échanges de manière générale, les flux seront détaillés précisément dans l'étape du MCC.

La méthode proposée pour déterminer les acteurs et leurs interaction est donc de décomposer le système en domaines d'activité, c'est à dire en ensembles d'activités ayant une finalité commune (par exemple la gestion des stocks ou encore la vente, ...). Puis nous allons procéder par raffinement. En décomposant ces domaines d'activités en sous-domaines puis décomposer ceux-ci avec les acteurs qui les composent.

Pour détailler cette méthode, nous allons nous intéresser à l'exemple de la diapositive [8.4](https://pierrerousseau.github.io/cours-msi/#/7/3). Ici nous étudions le SI d'un supermarché mais pour avoir un exemple simple, nous nous concentrons sur la gestion de livraison.

La première étape consiste à déterminer les échanges du SI avec l'extérieur. C'est le diagramme de contexte, on considère le SI comme un tout échangeant avec l'extérieur. Dans cet exemple, on ne trouve qu'un seul acteur externe, ce sont les fournisseurs à qui le supermarché achète des marchandises. On détermine également 3 flux d'information : commander (véhiculant des informations nécessaire au fournisseur pour nous livrer), livrer (ici, les informations obtenues concernent les marchandises effectivement livrées) et payer facture (ici les données intéressantes seront sans doute liées au prix finalement payé).
On pourrait les abstraire en un seul flux (commander), mais ces flux ayant des temps bien distincts, il semble intéressant de les préciser ici.

Dans un deuxième temps, on construit le diagramme d'activité. Ici, on va détailler le SI et le décomposer en domaines d'activités. Attention, tous les flux déterminés sur le diagramme de contexte doivent être présents sur le diagramme d'activité. Ici, on considère qu'un domaine d'activité prend en charge la gestion des achats et un autre la gestion du stock. 
Les flux commander et payer facture sont maintenant échangé entre le fournisseur et le domaine d'activité de gestion des achats alors que le flux livrer est maintenant dirigé vers le domaine d'activité de gestion du stock.
Pour des raisons de gestion interne, on détermine deux nouveaux flux entre le stock et les achats : demander achats et informer livraison.

Enfin on obtient notre diagramme de flux final en détaillant cette fois les domaines d'activités avec les acteurs qui les composent.
Le domaine d'activité Stocks ne comporte qu'un seul acteur, qui l'on nommera gestionnaire de stock (un petit rappel : nous ne nous intéressons ici qu'aux informations de livraison et non pas à la gestion du stock lui-même). Le domaine d'activité des Achats est lui composé de deux acteurs : le gestionnaire de commande et le trésorier. Tous les flux du diagramme d'activité doivent être reportés sur le diagramme de flux. On en détermine un de plus entre le gestionnaire de commande et le trésorier, le premier informant le second des commandes passées et qui seront payées une fois livrées.

Dans cet exemple, les choix sont guidés par le métier et la manière dont est organisé le SI étudié. Cela a du être compris lors du recueil des besoins, si des questions surviennent à cette étape, il faut compléter celui-ci. Pour ce même SI, on pourrait faire des choix différents, ici je joue le rôle d'utilisateur.


## Matrice de flux

La matrice de flux reprend les acteurs et les flux décrits par le diagramme de flux. On peut la voir comme une vue plus générale de ceux-ci permettant de les repérer plus facilement. Le diagramme de flux étant parfois complexe il peut être difficile d'en avoir une vue globale en un coup d'oeil, la matrice de flux peut palier ce problème.

On peut en outre s'en servir pour s'assurer de la validité de notre DF. Pour cela, il faut évidemment qu'elle soit cohérente avec le DF. Chaque flux et chaque acteur doit se retrouver dans l'un et dans l'autre, avec la même dénomination.


## Modèle Conceptuel de Communication (MCC)

La phase de recueil des besoins se termine par la construction du modèle conceptuel de communication (dit MCC). C'est sur celui-ci que nous nous baserons par la suite pour modéliser notre SI. Le MCC permet de formaliser les besoins du SI récolté informellement. De plus, il se présente sous l'angle de vue de la donnée, c'est ce qui nous aidera par la suite à la structurer et à déterminer les fonctionnalités nécessaires aux échanges d'informations. 

Pour cela le MCC nous donne un outil qui est le message, représentant la transmission d'une information complète tout en précisant son émetteur et son récepteur ainsi que les données qu'il véhicule.

Sa construction se base sur le DD et le DF. Nous allons regrouper les informations acquises lors de ces deux étapes. En effet pour construire un MCC, nous allons détailler chaque flux d'information en messages concrets échangés par les différents acteurs. 
Ainsi, le choix des étapes de la méthodes suivie jusqu'ici va prendre tout son sens :
* le DD liste les données 
* le DF détermine les acteurs et les flux 
* Puis le MCC détaille chaque flux en messages 
* pour qu'enfin le MCC détaillé explicite ces messages avec les données du DD

Dans les cas simples, on pourrait essayer d'écrire le MCC détaillé immédiatement, mais il faudrait alors faire ces quatre opérations en une passe, ce qui complexifierai inutilement la démarche. En découpant le travail en plusieurs étapes, on se simplifie la tache et on assure un travail avec des bases plus solides et finalement avec moins d'effort.

Encore une fois il faut être cohérent avec le DF, chaque flux de celui-ci doit être détaillé. Une bonne pratique facilitant le travail est d'y aller par ordre chronologique. En plus d'assurer de ne rien manquer, cela aide à réfléchir sur les besoins des acteurs et donc du SI.


## Modèle Conceptuel de Données (MCD)

C'est le modèle permettant de décrire la statique du SI. C'est à dire la structure des données. Pour cela on reprend un modèle de type entité-association classique permettant de décrire les données et leurs relations. On peut ainsi savoir comment stocker nos données de manière à réponde aux besoins du SI.

En premier lieu, le MCD permet de regrouper les données en ensembles cohérents. Ces données, proviennent du MCC (et donc du DD). Elles sont ici nommées propriétés et les groupes de propriétés forment ce que l'on appelle des entités. On peut imaginer ces entités, voire les matérialiser. Une partie des propriété d'une entité doit permettre d'identifier chaque occurrence de celle-ci (cette partie peut, comme c'est souvent le cas, être composée d'une seule propriété).

Les entités sont liées entre elles par des associations. À l'inverse des entités, leur représentation ne peut être qu'abstraite. Elles lient les entités pour former la structure du SI. Elles peuvent également être porteuses de propriétés et leur identifiant est alors composé des identifiants des entités liées.

Pour construire le MCD, nous devons regrouper les données issues des messages du MCD. Cela nous permet de suivre les besoins du SI par construction. Il n'y a pas de règle absolue ici, mais si des données sont véhiculées par un même message, c'est qu'elles  sont souvent liées. Pour matérialiser ce lien, on les place alors soit dans la même entité, soit on lie les entités auxquelles elles appartiennent par une association. Nous devons assurer l'exhaustivité, c'est à dire que toutes les données des messages du MCC détaillé doivent se retrouver dans le MCD : si notre structure permet de stocker toutes les données du MCC détaillé, alors elle permet de répondre au besoin de notre SI.

Une fois le MCD construit, on le valide à travers l'unicité des propriétés et la normalisation. Ceci nous assure d'éviter toute redondance d'information qui peut devenir coûteuse, non seulement en stockage mais aussi en traitement pour assurer la cohérence entre les duplicats de données.


## Modèle Conceptuel de Traitements (MCT)

Si le MCD décrit la structure des données, le MCT va s'intéresser aux traitements à appliquer à celles-ci. Pour cela on se base sur les notions d'événement déclencheurs et de résultat d'opération. Une opération est réalisée par le SI suite à un événement déclencheur et consiste en une suite non-interruptible d'actions d'un acteur ayant pour but de produire un résultat.

Il n'y a pas de méthode définie pour le construire comme pour le MCD. On prend donc chaque acteur et on se pose la question de ses actions vis-à-vis du SI. On considérera, dans un deuxième temps, tout de même les messages reçus pour se demander s'il ne sont pas déclencheurs ou résultat d'une action d'un acteur du SI. C'est probable, mais pas automatique.


## Modèle Organisationnel de Données (MOD)

Après avoir décrit la structure des données, on peut s'intéresser à un autre aspect de la modélisation de notre système d'information. Avec le développement des SI, ceux-ci doivent s'adapter aux lieux et aux supports à partir desquels on y accède.

Par là on entend le besoin d'accès aux données, soit pour des raisons de droit (tout le monde n'a pas accès à toutes les données du SI), soit pour des raisons de performance (on ne peut pas dupliquer toute la base de donnée d'une banque dans chaque agence de quartier par exemple).

Pour cela, on commence par déterminer les différents sites où opèrent les utilisateurs. Une fois ce classement réalisé, on s'intéresse aux droits d'accès de ces utilisateurs. Lorsque la matrice de droits est réalisé, on créé un MCD pour chaque site en fonction des droits des utilisateurs présents sur le site. On économise ainsi du travail de réplication et donc des ressources (stockage et programmes assurant la cohérence des copies).

La matrice de droits se construit simplement en donnant pour chaque acteur du système les droits de création, de lecture, d'écriture et de suppression de chaque entité et chaque association porteuse. 


## Modèle Organisationnel de Traitement (MOT)

Le MOT, comme le MOD pour le MCD, est une extension du MCT permettant de prendre en compte de nouveaux éléments à définir au niveau du MCT sans gêner la conception de celui-ci. 
Nous y ajoutons donc la définition des poste de travail, l'ordre d'exécution des phases (regroupement de processus) ainsi que le degré d'automatisation des différentes opérations. Régler ces questions au moment de l'élaboration du MCT ne ferai qu'ajouter du bruit à celle-ci, on le fait donc ici dans un deuxième temps.

On le construit donc naturellement en se basant sur le MCT, en regroupant les processus et en y ajoutant les informations nécessaires.


## Conclusion

On a ainsi couvert, à un premier niveau, la modélisation de notre SI avec la structure des données (MCD et MOD) et les processus s'opérant sur celles-ci (MCT et MOT). 
La suite des étapes sera, soit l'augmentation de cette modélisation en rapport avec des contraintes structurelles imposées sur les données soit un raffinement de la modélisation pour la spécifier vis-à-vis de contraintes techniques.

On aborde pas ici les notions de modèle logique de données (MLD, qui correspond à un schéma de données qui s'applique à n'importe quel système de gestion de base de données (SGBD) ni de modèle physique de données (MPD, qui correspond aux requêtes SQL de création de la base de données). Ces deux notions sont vues en détail pendant le cours de base de données et peuvent être automatisées à partir du MCD (ce que nous verrons si le temps le permet).

On ne voit pas non plus les notions de modèle logique de traitement (MLT, que l'on pourrait mettre au même niveau qu'un diagramme de classe UML) ni de modèle physique de traitement (MPT, qui correspond au code de l'application), car encore une fois ces étapes (ou leurs équivalents) sont en réalité vues en détail lors d'autres cours.

Un autre piste que nous explorerons si l'application de la méthode décrite ici est assimilée, est son utilisation en contexte agile, mode de fonctionnement de plus en plus utilisé de nos jour et par forcément totalement incompatible avec les outils offerts par la méthode Merise.