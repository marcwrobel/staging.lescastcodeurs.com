---
title: LCC 280 - 
author: 'Emmanuel Bernard'
team: 'Emmanuel Bernard, Guillaume Laforge, Vincent Massol, Antonio Goncalves, Arnaud Héritier, Audrey Neveu'
layout: blog-post
episode: 280
mp3_length: 85017000
tweet: TODO
# tweet size: 91-93 -> 99-101 #######################################################################
---
Résumé

TODO: comment ajouter une news

* titre en français si possible
* pas de bullet points mais ajouter deux espaces à la fin de la ligne (cela fait passer à la ligne)  

    * bullet points autorisés si plusieurs liens sur là même news

Enregistré le 2 janvier 2022

Téléchargement de l'épisode [LesCastCodeurs-Episode-280.mp3](https://traffic.libsyn.com/lescastcodeurs/LesCastCodeurs-Episode-280.mp3)

## News

### Langages

[Sept raisons pour lesquelles Java a a encore du sens après 26 ans](https://foojay.io/today/7-reasons-why-after-26-years-java-still-makes-sense/)  

* communauté (dans toutes les grandes villes
* force du langage et de la plateforme
* plus de problèmes résolus que non résolus (librairies)
* stabilité
* Innovation (Java 9 accélère l’innovation)
* outillage
* opportunité d’emploi



[Les débuts du projet Leyden](https://openjdk.java.net/projects/leyden/notes/01-beginnings)

* Mark Reinhold lance le projet Leyden, pour adresser les problèmes de temps de démarrage lent de Java, de lenteur du temps jusqu’à la performance max, et d’empreinte un peu lourde
* à l’aide d’une image statique de votre application
* une image statique ne fait tourner qu’une seule et unique application sur son JDK, et est un “monde fermé” (ne peut pas charger de classe externes)
* mais les ingés de la JVM vont travailler sur une approche assez souple, et voire quelles contraintes peuvent être allégées, par rapport à un monde complètement fermé d’une image statique
* en espérant avoir des améliorations à différents niveaux, pour un max d’appli et de use case différents
* Le close world c’est ce qui amène la valeur de GraalVM native image et les avantages pour Micronaut, Quarkus et le autres
* donc pas de closed world: c’est encore un projet de recherche pour l’équipe de la JVM

[JFR plus facile à configuer dans Java 17]( https://egahlin.github.io/2022/05/31/improved-ergonomics.html)

* un wizard en UI ou CLI pour generer le fichier .jfc

[Proposition de structured concurrency via le projet Loom](https://www.infoq.com/news/2022/06/java-structured-concurrency/)


[RedMonk analyse l’apparition du langage Dart, grâce à Flutter, dans leur top 20 des langages de programmation les plus populaires](https://redmonk.com/jgovernor/2022/05/16/flutter-propels-dart-frameworks-language-adoption-and-cross-platform-development/)  

* JavaScript, Python, Java, toujours en tête
* Mais Rust et Dart sont rentrés récemment
* L’arrivée de Dart coïncide surtout avec l’émergence de Flutter comme framework d’interface graphique, que ce soit pour Android/iOS, que pour le desktop et le web
* Sur les applis mobiles, il y a toujours eu beaucoup de développement natif, mais est aussi arrivé React Native, mais aussi Flutter
* Des applis de Google comme Google Pay et Google Ads sont développées en Flutter, mais aussi le récent SNCF Connect  ou des entreprises telles que BMW ou Alibaba (modifié) 
* (cf le talk sur le REX par les développeurs de SNCF Connect à Devoxx France)
* les investissements initiaux de Dart vs Kotlin ou Ceylon qui ont démarrés en meme temps étaient colossaux 
* Dart en natif pour faire des applis iOS… qui tournent aussi sous Android



### Librairies

[Sortie de Micronaut 3.5](https://micronaut.io/2022/05/26/micronaut-framework-3-5-0/)

* Passage à GRAALVM 22.1.0
* Compilation incrémentale lors des builds, en particulier intéressant pour les métadonnées pour GraalVM, ce qui permet d’éviter de faire tourner les processeurs d’annotation inutilement
* Inclusion de Micronaut Data 3.4, avec support des enums Postgres pour JDBC, la pagination pour les Reactive Repositories
* Intégration avec Turbo pour la vue (Turbo Frame et Turbo Views)
* Nouveau module pour MicroStream (un moteur de graphe d’objet natif Java, intégré à Helidon)
* Mise à jour de nombreux plugins et extensions (y compris plugins de build)


### Infrastructure

### Cloud

### Web

### Data

### Outillage

 [VSCode Java 1.5 est sorti](https://twitter.com/vscodejava/status/1514687434805686278?s=21&t=9B-Ur9W6tZf5mulv1K2KDA](https://twitter.com/vscodejava/status/1514687434805686278?s=21&t=9B-Ur9W6tZf5mulv1K2KDA) 

* Java 18 support, inlay hints for method parameters, and improvements to class declaration navigation are just a few of the enhancements to expect.


### Architecture

[L'architecture Netflix](https://medium.com/swlh/a-design-analysis-of-cloud-based-microservices-architecture-at-netflix-98836b2da45f)

* Pas fou fou dans les infos mais ça fait longtemps qu’on a pas eu d’archi
* analyze the system design in terms of availability, latency, scalability and resilience to network failure
* basé sur AWS
* clients via un SDK est intelligent, contrôle le backend utilisé et la bande passante en temps réel
* Open Connect CDN: là ou les vidéos sont stockées
* le reste du bon vieux microservice en backend
* ramène les dix meilleurs points d’accès et le client choisi voire change
* API Gateway via Zuul: dynamic routing, traffic monitoring and security, resilience to failures at the edge of the cloud deployment
* etc

### Méthodologies

### Sécurité

### Loi, société et organisation

[VMWare racheté par Broadcom](https://investors.broadcom.com/news-releases/news-release-details/broadcom-acquire-vmware-approximately-61-billion-cash-and-stock)

* 61 milliards de dollars
* Avec un objectif de passer de 3,5 à 8,5 milliard d’EBITA par an
	* Bouger dans la division cloud avec Symantec
* VMWare était content de sa liberté retrouvée après la spin off de Dell
* Apparemment pas d’alignement de tech
* une expansion de portefeuiille dans le software pour broadcom
* VMWare a beaucoup changé de mains ces dernières années
* La strategie d’investissement de broadcom: acheter des franchises avec une bonne position de marcher et un potentiel de profitabilité augmenté sans gros investissements
* [La rumeur](https://www.bloomberg.com/news/articles/2022-05-22/broadcom-said-to-be-in-talks-to-acquire-vmware)
* un ex de VMWare [qui pense que c’est la mort de VMWare](https://www.linkedin.com/pulse/brian-maddens-brutal-unfiltered-thoughts-broadcom-vmware-brian-madden/)


## Outils de l'épisode

## Rubrique débutant

## Conférences

[Nom de la conf du x au y mois à Ville]() - [CfP]() jusqu'à y mois  
TODO: reprendre celles de l'épisode d'avant

## Nous contacter

Soutenez Les Cast Codeurs sur Patreon <https://www.patreon.com/LesCastCodeurs>  
[Faire un crowdcast ou une crowdquestion](https://lescastcodeurs.com/crowdcasting/)  
Contactez-nous via twitter <https://twitter.com/lescastcodeurs>  
sur le groupe Google <https://groups.google.com/group/lescastcodeurs>  
ou sur le site web <https://lescastcodeurs.com/>
<!-- vim: set spelllang=fr : -->