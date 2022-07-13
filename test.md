---
title: LCC 999 -
author: 'Emmanuel Bernard'
team: 'Emmanuel Bernard, Guillaume Laforge, Vincent Massol, Antonio Goncalves, Arnaud Héritier, Audrey Neveu'
layout: blog-post
episode: 999
mp3_length: 85017000
tweet: TODO
# tweet size: 91-93 -> 99-101 #######################################################################
---

Résumé

Enregistré le 13 juil. 2022

Téléchargement de l’épisode [LesCastCodeurs-Episode-999.mp3](https://traffic.libsyn.com/lescastcodeurs/LesCastCodeurs-Episode-999.mp3)

## News

### Non catégorisées

lang: [https://foojay.io/today/7-reasons-why-after-26-years-java-still-makes-sense/](https://foojay.io/today/7-reasons-why-after-26-years-java-still-makes-sense/)

- communauté (dans toutes les grandes villes)
- **force** du _langage_ et de la plateforme
- plus de ~problèmes~ résolus que non résolus (librairies)
- `stabilité`
- Innovation (Java 9 accélère l’innovation)
- outillage
- opportunité d’emploi

lang: [https://openjdk.java.net/projects/leyden/notes/01-beginnings](https://openjdk.java.net/projects/leyden/notes/01-beginnings)

- Mark Reinhold lance le projet Leyden, pour adresser les problèmes de temps de démarrage lent de Java, de lenteur du temps jusqu’à la performance max, et d’empreinte un peu lourde
- à l’aide d’une image statique de votre application
- une image statique ne fait tourner qu’une seule et unique application sur son JDK, et est un “monde fermé” (ne peut pas charger de classe externes)
- mais les ingés de la JVM vont travailler sur une approche assez souple, et voire quelles contraintes peuvent être allégées, par rapport à un monde complètement fermé d’une image statique
- en espérant avoir des améliorations à différents niveaux, pour un max d’appli et de use case différents
- Le close world c’est ce qui amène la valeur de GraalVM native image et les avantages pour Micronaut, Quarkus et le autres
- donc pas de closed world: c’est encore un projet de recherche pour l’équipe de la JVM

lang: [https://egahlin.github.io/2022/05/31/improved-ergonomics.html](https://egahlin.github.io/2022/05/31/improved-ergonomics.html)

- un wizard en UI ou CLI pour generer le fichier .jfc

langage: [https://www.infoq.com/news/2022/06/java-structured-concurrency/](https://www.infoq.com/news/2022/06/java-structured-concurrency/)

- Targeted status for JDK 19.
- This incubating JEP, under the auspices of Project Loom,
- proposes to simplify multithreaded programming by introducing a library to treat multiple tasks running in different threads as a single unit of work.
- This can streamline error handling and cancellation, improve reliability, and enhance observability

language: [https://redmonk.com/jgovernor/2022/05/16/flutter-propels-dart-frameworks-language-adoption-and-cross-platform-development/](https://redmonk.com/jgovernor/2022/05/16/flutter-propels-dart-frameworks-language-adoption-and-cross-platform-development/)

- JavaScript, Python, Java, toujours en tête
- Mais Rust et Dart sont rentrés récemment
- L’arrivée de Dart coïncide surtout avec l’émergence de Flutter comme framework d’interface graphique, que ce soit pour Android/iOS, que pour le desktop et le web
- Sur les applis mobiles, il y a toujours eu beaucoup de développement natif, mais est aussi arrivé React Native, mais aussi Flutter
- Des applis de Google comme Google Pay et Google Ads sont développées en Flutter, mais aussi le récent SNCF Connect ou des entreprises telles que BMW ou Alibaba (modifié)
- (cf le talk sur le REX par les développeurs de SNCF Connect à Devoxx France)
- les investissements initiaux de Dart vs Kotlin ou Ceylon qui ont démarrés en meme temps étaient colossaux
- Dart en natif pour faire des applis iOS… qui tournent aussi sous Android

lib: [https://micronaut.io/2022/05/26/micronaut-framework-3-5-0/](https://micronaut.io/2022/05/26/micronaut-framework-3-5-0/)

- Passage à GRAALVM 22.1.0
- Compilation incrémentale lors des builds, en particulier intéressant pour les métadonnées pour GraalVM, ce qui permet d’éviter de faire tourner les processeurs d’annotation inutilement
- Inclusion de Micronaut Data 3.4, avec support des enums Postgres pour JDBC, la pagination pour les Reactive Repositories
- Intégration avec Turbo pour la vue (Turbo Frame et Turbo Views)
- Nouveau module pour MicroStream (un moteur de graphe d’objet natif Java, intégré à Helidon)
- Mise à jour de nombreux plugins et extensions (y compris plugins de build)

infra: [https://blog.sigstore.dev/kubernetes-signals-massive-adoption-of-sigstore-for-protecting-open-source-ecosystem-73a6757da73](https://blog.sigstore.dev/kubernetes-signals-massive-adoption-of-sigstore-for-protecting-open-source-ecosystem-73a6757da73)

- Kubernetes 1.24 (sorti en mai) est la première version utilisant officiellement Sigstore, permettant une vérification transparente des signatures pour protéger contre les attaques de la chaîne d’approvisionnement
- [Sigstore](https://www.sigstore.dev/) est une nouvelle norme pour la signature, la vérification et la protection des logiciels. Elle se veut être un remplaçant pour GPG par exemple.
- Sigstore offre une variété d’avantages à la communauté Kubernetes comme:
  - Sigstore’s keyless signing donne une grande expérience de développeur et supprime le besoin de la gestion de clé douloureuse.
  - Le journal public et transparent de Sigstore ([Rekor](https://github.com/sigstore/rekor)) avec ses API permettent aux consommateurs Kubernetes de vérifier les signatures.
  - ...

web: [https://www.rfc-editor.org/rfc/rfc9114.html](https://www.rfc-editor.org/rfc/rfc9114.html) (+ [RFC 9204 - QPACK: Field Compression for HTTP/3](https://www.rfc-editor.org/rfc/rfc9204.html) et [RFC 9218 - Extensible Prioritization Scheme for HTTP](https://www.rfc-editor.org/rfc/rfc9218.html))

- Basé sur le protocole de transport QUIC qui possède plusieurs fonctionnalités intéressantes telles que le multiplexage de flux, le contrôle de flux par flux et l’établissement de connexion à faible latence.
- QPACK : un format de compression pour représenter efficacement les champs HTTP à utiliser en HTTP/3. Il s’agit d’une variation de la compression HPACK qui vise à réduire la taille des headers.
- Extensible Prioritization Scheme for HTTP: schéma qui permet à un client HTTP de communiquer ses préférences quant à la façon dont le serveur en amont priorise les réponses à ses demandes, et permet également à un serveur d’indiquer à un intermédiaire en aval comment ses réponses devraient être priorisées lorsqu’elles sont transmises.

tooling: [https://twitter.com/vscodejava/status/1514687434805686278?s=21&amp;t=9B-Ur9W6tZf5mulv1K2KDA](https://twitter.com/vscodejava/status/1514687434805686278?s=21&amp;t=9B-Ur9W6tZf5mulv1K2KDA)

- Java 18 support, inlay hints for method parameters, and improvements to class declaration navigation are just a few of the enhancements to expect.

misc: [https://investors.broadcom.com/news-releases/news-release-details/broadcom-acquire-vmware-approximately-61-billion-cash-and-stock](https://investors.broadcom.com/news-releases/news-release-details/broadcom-acquire-vmware-approximately-61-billion-cash-and-stock)

- 61 milliards de dollars
- Avec un objectif de passer de 3,5 à 8,5 milliard d’EBITA par an
  - Bouger dans la division cloud avec Symantec
- VMWare était content de sa liberté retrouvée après la spin off de Dell
- Apparemment pas d’alignement de tech
- une expansion de portefeuiille dans le software pour broadcom
- VMWare a beaucoup changé de mains ces dernières années
- La strategie d’investissement de broadcom: acheter des franchises avec une bonne position de marcher et un potentiel de profitabilité augmenté sans gros investissements
- [La rumeur](https://www.bloomberg.com/news/articles/2022-05-22/broadcom-said-to-be-in-talks-to-acquire-vmware)
- un ex de VMWare [qui pense que c’est la mort de VMWare](https://www.linkedin.com/pulse/brian-maddens-brutal-unfiltered-thoughts-broadcom-vmware-brian-madden/)

tool: [https://copilot.github.com/](https://copilot.github.com/)

- A voir aussi: [Github Co-Pilot : Addictif ou Efficace ? (Johan Jublanc et Simon Provost)](https://www.youtube.com/watch?v=SQf9ZQsqW30) à Devoxx France 2022

C'est fait, les show notes sont disponibles sur [https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/lcc-1655747394.md](https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/lcc-1655747394.md).


C'est fait, les show notes sont disponibles sur [https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/lcc-1655747723.md](https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/lcc-1655747723.md).


C'est fait, les show notes sont disponibles sur [https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/lcc-1655747778.md](https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/lcc-1655747778.md).


C'est fait, les show notes sont disponibles sur [https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/lcc-1655748362.md](https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/lcc-1655748362.md).


C'est fait, les show notes sont disponibles sur [https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/lcc-1655751076.md](https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/lcc-1655751076.md).


C'est fait, les show notes sont disponibles sur [https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/test](https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/test).


[https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/test.md](https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/test.md) (puis ce que je veux)

sur plusieurs lignes

- test1
- test2


### Langages


### Librairies


### Infrastructure


### Cloud


### Web


### Data


### Outillage


### Architecture


### Méthodologies


### Sécurité


### Loi, société et organisation


## Outils de l’épisode


## Rubrique débutant


## Conférences

[Nom de la conf du x au y mois à Ville]() - [CfP]() jusqu’à y mois
TODO: reprendre celles de l’épisode d’avant


## Nous contacter

Soutenez Les Cast Codeurs sur Patreon <https://www.patreon.com/LesCastCodeurs>  
[Faire un crowdcast ou une crowdquestion](https://lescastcodeurs.com/crowdcasting/)  
Contactez-nous via twitter <https://twitter.com/lescastcodeurs>  
sur le groupe Google <https://groups.google.com/group/lescastcodeurs>
<!-- vim: set spelllang=fr : -->
