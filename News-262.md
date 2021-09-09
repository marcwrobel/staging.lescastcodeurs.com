---
title: LCC 999 - 
author: 'Emmanuel Bernard'
team: 'Emmanuel Bernard, Guillaume Laforge, Vincent Massol, Antonio Goncalves, Arnaud Heritier, Audrey Neveu'
layout: blog-post
episode: 999
mp3_length: 85017000
tweet: TODO
# tweet size: 91-93 -> 99-101 #######################################################################
---
Résumé

TODO: comment ajouter une news

* titre en français si possible
* pas de bullet points mais ajouter deux espaces à la fin de la ligne (cela fait passer à la ligne)  

    * bullet points autorisés si plusieurs liens sur là même news

Enregistré le 10 septembre 2021

Téléchargement de l'épisode [LesCastCodeurs-Episode-999.mp3](https://traffic.libsyn.com/lescastcodeurs/LesCastCodeurs-Episode-999.mp3)

## News

### Langages

[Au revoir AdopOpenJDK, bonjour Adoptium](https://blog.adoptopenjdk.net/2021/08/goodbye-adoptopenjdk-hello-adoptium/)

* Eclipse Temurin runtimes pour la partie JDK
* Grosse test suite
* License oracle (que Adopt OpenJDK avait perdu)
* Plus de OpenJ9 ni GraalVM (Oracle recule) mais IBM a [Rapatrié OpenJ9 sous le nom IBM Semurin](https://developer.ibm.com/languages/java/semeru-runtimes/)
* Nouvelles API (backward compatibles ?)
* Les anciens builds ne seront pas migrés

[Une interview des architectes Java](https://blogs.oracle.com/javamagazine/java-architects-loom-panama-valhalla?source=:em:nw:mt::::RC_WWMK200429P00043C0036:NSL400176960)

* Java longevity: stability (not removing things), readability, ecosystem’ well defined stable interfaces (JVM etc)
* Nouvelles fonctionnalités : qu’est que qui ne peut être fait en dehors de la plateforme 
	* Rendre Java plus extensible (Valhalla)
* Bloque en Java 8
	* Perds argent (meilleure mémoire, performance, temps de démarrage, pauses 2ms G1 etc
	* Sécurité 
* Loom
	* Réactive programming pour mieux utiliser le,hardware
	* Mais opposé à certains designs de la JVM (error report, débug, flight recorder)
	* Loom résout le même problème mais en harmonie avec la JVM
	* Api familières 
*  Next
	* Vallalah , panama
	* Tail call recursion
	* Etc

[Article en passant sur l’utilisation du foreign API avec libsodium](https://blog.arkey.fr/2021/09/04/a-practical-look-at-jep-412-in-jdk17-with-libsodium/)

* juste une mention

[Quoi de neuf dans Scala 3](https://medium.com/scala-3/scala-3-whats-changed-since-scala-3-0-0-be0830c059f5)

* Scala 3.0.1
	* Syntaxe given simplifiée (pas de with)
	* `@experimental`
* Scala 3.1
	* Experimental safer exception (checked exceptions mais sans les ennuis)
	* Warnings de compilation plus configurable
	* Multiversal equality (des classes différentes qui peuvent être égales)

[Kotlin a 10 ans](https://www.infoq.com/articles/kotlin-ten-years-qa/?utm_campaign=infoq_content&utm_source=twitter&utm_medium=feed&utm_term=mobile)

* annoncé en 2011, 1.0 en 2016, default Android en 2017
* pas theorique, problemes pragmatiques
* multi plateforme encore experimental, on prend notre temps
* ajoutent features dans le core lib plus lentement que Java
* prochains 10 ans: multiplatforme, langage reste relevant, reactive programming et immuabilité du front vers le back

### Librairies

[Spring 6 / SpringBoot 3 annoncé à SpringOne](https://twitter.com/mraible/status/1433072410182357000?s=21)

* Java 17 et plus
* Intègre Spring Native
* Tomcat 10 min
* Jakarta 9 avec cassage de packages 
* Q4 2022
* Spring 5.3 et SpringBoot 2.7 seront en maintenance open source entendue 
* [Autre lien](https://spring.io/blog/2021/09/02/a-java-17-and-jakarta-ee-9-baseline-for-spring-framework-6)

[Quarkus 2.2 et 2.1](http://quarkus.io/blog/quarkus-2-2-1-final-released/)

* 2.2 Solidification (utilisabilite, doc, corriger problèmes) 
* Mongodb service binding
* RESTEasy Réactive automatiquement choisi le thread bloquant ou non bloquant
	* Plus facile quand on vient de RESTEasy Classic
	* [Détails ici](https://quarkus.io/blog/resteasy-reactive-smart-dispatch/)
* 2.1 
	* Dev services pour keycloak
	* SQLServer réactive a son extension
	* Kotlin 1.5
	* [Blog post expliquant les nouvelles modularités de quarkus platform](http://quarkus.io/blog/quarkus-2x-platform-quarkiverse-registry/)

[Micronaut 3 est sorti](https://micronaut.io/2021/08/18/micronaut-framework-3-released/)

* RxJava n’est plus un dépendance transitive (choix du moteur réactive streams)
	* Utilisent Reactor en dessous
* Les annotations ne sont plus héritées par défaut 
* Support Jakarta lifecycle annotations, Jakarta inject 
* Injection qualifiée par le generic des arguments 
* Filtres servers plus consistant (appelés une seule fois)
* `@Introspected` ne rajoute plus les metadonnes pour GraalVM, utiliser `@ReflectiveAccess`
* Ajout des resources passe du compile time au build time donc utilisez les plugins maven de Micronaut ou faite le vous même 
* Quelques autres breaking changes
* OpenRewrite règles changent le code pour migrer pour vous

### Infrastructure

[Comment debugger son script Ansible](https://zwischenzugs.com/2021/08/27/five-ansible-techniques-i-wish-id-known-earlier/)

* `--step`
* In-line logging 
* Ansible-lint
* Ansible-console
* Ansible debugger

### Cloud

[Apple nous protégeras des photos pedophiles mais en ouvrant une brèche sur la sécurité de ses téléphones ](https://www.apple.com/child-safety/)

* [Une analyse techniques](https://twitter.com/MathisHammel/status/1425523073806110720)
* Il y a deux choses distinctes
* Détecter les images d’une base de donnée pedophile avec du hash sur le téléphone et en alertant quand trop’sonr flaggues positive (avec check humain)
	* Ça s’appuie sur iCloud photo car sur leur cloud mais pas un filtre serveur
	* Base de donnée Baked dans chaque iOS
	* NeuralHash
		* Hash résiste au ré cadrage et autres ajustement de photos 
	* Threshold secret sharing 
		* Au bout de n rapports remontés, on a capacité à reconstituer la clef de chiffrement 
	* Et un troisième mécanisme pour éviter de montrer qu’elles photos intéressent Apple
	* Quid d’une puissance étrangère qui veut rajouter des photos de discidents?
		* Apple dit on n’acceptera pas 
	* Où attaque sur le neural hash
* Détection de nudité et demande si l’nfznt veut voir avec alerte aux parents
* Ils se donnent quelques mois de retravail au final 

[AWS a 15 ans](https://aws.amazon.com/fr/blogs/aws/happy-15th-birthday-amazon-ec2/)

* demarre avec une region, un seul type d’instance et tout ephemère (pas de block storage)
* peu de feature et peu de details initialement
* prix a l’heure initialement qui etait innovant

### Web

### Data

[La guerre de la recherche - Les clients Elastic Search ne seront pas compatible avec OpenSearch](https://thenewstack.io/this-week-in-programming-the-elasticsearch-saga-continues/)

* Elastic vs AWS - Clash numéro ? Dans ce dernier épisode, Elastic rajoute des controles dans ses APIs clientes pour ne se connecter qu’a ses propres clusters et empêcher de les utiliser avec opensearch. 
	* Risques d’incompatibilité 
* Manque de chance ce changement bloque aussi l’utilisation de la version OSS d’elastic-search. 
* De son coté AWS promet de faire son possible pour fournir des drivers qui resteront compatibles Elasticsearch 7.10.2 (la version à partir de laquelle ils ont forké) et OpenSearch
* Bref la guerre continue ...

### Outillage

[AtomicJar release TestContainers 1.16](https://www.atomicjar.com/2021/07/testcontainers-1-16-0-release/)

* https://www.atomicjar.com/2021/07/testcontainers-1-16-0-release/ Test Containers 1.16.0 est la première release faite par AtomicJar, la société créée par les fondateurs du projet.
* Meilleure compatibilité Apple M1
* Couche de transport utilise Apache HTTP Client 5 au lieu de OKHTTP pour éviter la malediction Kotlin
* Meilleure stabilité et compatibilité sur Windows pour process natifs Windows et WSL 2
* docker.host peut etre configuré dans $HOME/.testcontainers.properties
* Aussi Support Portman amélioré récemment 

[GitHub vous laisse ouvrir un webIDE en tapant `.` sur un fichier. ](https://twitter.com/natfriedman/status/1425504734530650114?s=21)

* En fait ça ouvre GitHub.dev 

[Docker introduit un nouveau système d’abonnement avec Docker Business et différents niveaux: perso, pro, entreprise etc](https://www.docker.com/blog/updating-product-subscriptions/)

* donc pour les boites de plus de 250 personnes ou qui font 10 millions, tu dois payer pour Docker Desktop
* [Des articles paraissent listant les alternatives à Docker Desktop](https://matt-rickard.com/docker-desktop-alternatives/)
* [Sur l’impact macOS](https://twitter.com/idriss_neumann/status/1432943504485986305)

[Les différentes manières de déclarer les dépendances dans son projet Gradle](https://medium.com/agorapulse-stories/gradle-configurations-explained-4b9608dd5e35)  

* En particulier, les différences entre api, implementation, runtimeOnly, compileOnly, compileOnlyApi
Avec des exemples concrets pour bien illustre ces différents scopes.
* Gradle regroupe les dépendances dans des ensembles appelés des “configurations”. Ces configurations définissent le classpath lors de la compilation, ou le classpath pour le runtime lorsque votre code s’exécute.
* Gradle définit 3 types de configuration : api, implementation et runtimeOnly
* La configuration “api” est utilisée pour le classpath compilation et runtime et est exposé aux consommateurs de l’API aussi pour le classpath de compilation et runtime
* La configuration “implementation” est utilisée pour le classpath de compilation et runtime, mais est exposée pour le consommateur de l’API que pour le classpath au runtime
* La configuration “runtimeOnly” n’est utilisée que pour le classpath au runtime
* La configuration “compileOnly” est utilisée pour le classpath de compilation, mais n’est pas exposée pour les consommateurs
* Enfin la configuration “compileOnlyApi” est utilisée pour le classpath de compliation et est exposée au consommateurs à la compilation de leur code quand les metadata Gradle sont utilisées

### Architecture

### Méthodologies

[Opinion sur Googlespeak et les pratiques anti concurrentielles](https://zyppy.com/googlespeak/)

* Certains dont l’auteur voient Google utiliser Google search pour placer hautement leur propres services alternatifs. Google flight etc 
* Et les Googlers avec qui il interagissait trouvait ça « absurde » de penser ça. 
* Chercher un hôtel 
* Étude montre que Google offre 41% de sa première page à ses propres propriétés (inclus direct answers )
* Direct answer est mis rapide pour l’utilisateur mais prend le contenu 3rd party ( Wikipedia, IMDb etc) et nous fait rester sur une page Google. 
* Googlespeak d’après Orwell. Si le langage ne permet pas d’exprimer , on ne pense pas aux choses. 
* Pas dominant mais succès. Pas barrière à l’entrée , marché, effet réseau qui sont taboo dans un contexte de tension antitrust 
* Encourage à réfréner sa communication écrite. 
* Comme beaucoup de sociétés américaines à cause du processus de discovery 
* Market share -> user preference 
* Apple et epic ont levés des doc similaires mais Apple n’était pas gardé dans sa comm interne. Autour de l’app store. 
* Google dans ses formation mention non monopoly car beaucoup de compétiteurs. Et se defini en termes très large et donc avec de la compétition. (Dans la pub et dans la recuperation d'information. 
* Ils ne font pas d’analyse de marchés (sur les marchés dominants) quand demandés par le congrès. 
* 65% des recherches n’entraînent pas un clic sur un site externe - valeur réfutée par Google 
* C’est une réaction à la judiciarusarion de la vie des entreprises. 

### Sécurité

### Loi, société et organisation

[Matt Asay quitte AWS et reflecte sur l’open source chez AWS](https://www.infoworld.com/article/3631376/what-you-dont-know-about-working-with-aws.html)

* pleins de petites equipes et pas de décisions top down
* en tous cas pas pour open source
* Un langage specifique a Amazon pour convaincre
* Les Leadership Principles tendent à ne pas investir dans les elements side de type open source
* et quand on a deux pizza team, peut on contribuer sans se sentir trop contraint en temps
* si c’est une équipe de 12 sur 200 equipes ca ne m’étonnes pas trop 🙂

## Outils de l'épisode

## Rubrique débutant

[RISC vs CISC](https://medium.com/swlh/what-does-risc-and-cisc-mean-in-2020-7b4d42c9a9de)

* CISC roi quand la mémoire est chère, on crée des instructions haut niveau plus complexes
* RISC paye en mémoire mais simplifie la chaîne de travail (instructions de taille fixe)
* RISC plus d’opérations et donc de CPU clock mais pipelining possible
* RISC compensé par plus de registers et par la compression d’instructions set
* register mémoire interne CPU de taille fixe
* CISC fait du hardware hyper threading 
* RISC philosophiquement fait travailler les compilateurs beaucoup plus mais on ne code plus en assembleur

## Conférences

[Nom de la conf du x au y mois à Ville]() - [CfP]() jusqu'à y mois  
TODO: reprendre celles de l'épisode d'avant

Crowdcast devfest Lille de Emmanuel Demey 

[Pas de Devoxx Belgique en 2021](https://twitter.com/stephan007/status/1432254876436815874?s=21)

## Nous contacter

Soutenez Les Cast Codeurs sur Patreon <https://www.patreon.com/LesCastCodeurs>  
[Faire un crowdcast ou une crowdquestion](https://lescastcodeurs.com/crowdcasting/)  
Contactez-nous via twitter <https://twitter.com/lescastcodeurs>  
sur le groupe Google <https://groups.google.com/group/lescastcodeurs>  
ou sur le site web <https://lescastcodeurs.com/>
<!-- vim: set spelllang=fr : -->