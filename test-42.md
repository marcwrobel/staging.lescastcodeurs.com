---
title: LCC 42 -
author: 'Emmanuel Bernard'
team: 'Emmanuel Bernard, Guillaume Laforge, Vincent Massol, Antonio Goncalves, Arnaud Héritier, Audrey Neveu'
layout: blog-post
episode: 42
mp3_length: 85017000
tweet: TODO
# tweet size: 91-93 -> 99-101 #######################################################################
---

Résumé

Enregistré le 6 sept. 2022

Téléchargement de l’épisode [LesCastCodeurs-Episode-42.mp3](https://traffic.libsyn.com/lescastcodeurs/LesCastCodeurs-Episode-42.mp3)

## News

### Non catégorisées

[https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/test.md](https://github.com/marcwrobel/staging.lescastcodeurs.com/blob/main/test.md)

sur plusieurs lignes

- :lcc_include:

<!here> notification ici avec [https://github.com/lescastcodeurs/staging.lescastcodeurs.com/blob/main/news-281.md](https://github.com/lescastcodeurs/staging.lescastcodeurs.com/blob/main/news-281.md)



### Langages

JEP 428: Structured Concurrency to Simplify Java Multithreaded Programming
[https://www.infoq.com/news/2022/06/java-structured-concurrency/](https://www.infoq.com/news/2022/06/java-structured-concurrency/)

- Targeted status for JDK 19.
- This incubating JEP, under the auspices of Project Loom,
- proposes to simplify multithreaded programming by introducing a library to treat multiple tasks running in different threads as a single unit of work.
- This can streamline error handling and cancellation, improve reliability, and enhance observability

Et oui ! [https://foojay.io/today/7-reasons-why-after-26-years-java-still-makes-sense/](https://foojay.io/today/7-reasons-why-after-26-years-java-still-makes-sense/)

- communauté (dans toutes les grandes villes)
- **force** du _langage_ et de la plateforme
- plus de ~problèmes~ résolus que non résolus (librairies)
- `stabilité`
- Innovation (Java 9 accélère l’innovation)
- outillage
- opportunité d’emploi
- To be removed !

[https://openjdk.java.net/projects/leyden/notes/01-beginnings](https://openjdk.java.net/projects/leyden/notes/01-beginnings) : les début de leyden

- Mark Reinhold lance le projet Leyden, pour adresser les problèmes de temps de démarrage lent de Java, de lenteur du temps jusqu’à la performance max, et d’empreinte un peu lourde
- à l’aide d’une image statique de votre application
- une image statique ne fait tourner qu’une seule et unique application sur son JDK, et est un “monde fermé” (ne peut pas charger de classe externes)
- mais les ingés de la JVM vont travailler sur une approche assez souple, et voire quelles contraintes peuvent être allégées, par rapport à un monde complètement fermé d’une image statique
- en espérant avoir des améliorations à différents niveaux, pour un max d’appli et de use case différents
- Le close world c’est ce qui amène la valeur de GraalVM native image et les avantages pour Micronaut, Quarkus et le autres
- donc pas de closed world: c’est encore un projet de recherche pour l’équipe de la JVM

[https://egahlin.github.io/2022/05/31/improved-ergonomics.html](https://egahlin.github.io/2022/05/31/improved-ergonomics.html)

- un wizard en UI ou CLI pour generer le fichier .jfc

[https://redmonk.com/jgovernor/2022/05/16/flutter-propels-dart-frameworks-language-adoption-and-cross-platform-development/](https://redmonk.com/jgovernor/2022/05/16/flutter-propels-dart-frameworks-language-adoption-and-cross-platform-development/)

- Dart en natif pour faire des applis iOS… qui tournent aussi sous Android
- JavaScript, Python, Java, toujours en tête
- Mais Rust et Dart sont rentrés récemment
- L’arrivée de Dart coïncide surtout avec l’émergence de Flutter comme framework d’interface graphique, que ce soit pour Android/iOS, que pour le desktop et le web
- Sur les applis mobiles, il y a toujours eu beaucoup de développement natif, mais est aussi arrivé React Native, mais aussi Flutter
- Des applis de Google comme Google Pay et Google Ads sont développées en Flutter, mais aussi le récent SNCF Connect ou des entreprises telles que BMW ou Alibaba (modifié)
- (cf le talk sur le REX par les développeurs de SNCF Connect à Devoxx France)
- les investissements initiaux de Dart vs Kotlin ou Ceylon qui ont démarrés en meme temps étaient colossaux


### Librairies

[https://micronaut.io/2022/05/26/micronaut-framework-3-5-0/](https://micronaut.io/2022/05/26/micronaut-framework-3-5-0/)

- Passage à GRAALVM 22.1.0
- Compilation incrémentale lors des builds, en particulier intéressant pour les métadonnées pour GraalVM, ce qui permet d’éviter de faire tourner les processeurs d’annotation inutilement
- Inclusion de Micronaut Data 3.4, avec support des enums Postgres pour JDBC, la pagination pour les Reactive Repositories
- Intégration avec Turbo pour la vue (Turbo Frame et Turbo Views)
- Nouveau module pour MicroStream (un moteur de graphe d’objet natif Java, intégré à Helidon)
- Mise à jour de nombreux plugins et extensions (y compris plugins de build)


### Infrastructure

[https://blog.sigstore.dev/kubernetes-signals-massive-adoption-of-sigstore-for-protecting-open-source-ecosystem-73a6757da73](https://blog.sigstore.dev/kubernetes-signals-massive-adoption-of-sigstore-for-protecting-open-source-ecosystem-73a6757da73)

- Kubernetes 1.24 (sorti en mai) est la première version utilisant officiellement Sigstore, permettant une vérification transparente des signatures pour protéger contre les attaques de la chaîne d’approvisionnement
- [Sigstore](https://www.sigstore.dev/) est une nouvelle norme pour la signature, la vérification et la protection des logiciels. Elle se veut être un remplaçant pour GPG par exemple.
- Sigstore offre une variété d’avantages à la communauté Kubernetes comme:
  - Sigstore’s keyless signing donne une grande expérience de développeur et supprime le besoin de la gestion de clé douloureuse.
  - Le journal public et transparent de Sigstore ([Rekor](https://github.com/sigstore/rekor)) avec ses API permettent aux consommateurs Kubernetes de vérifier les signatures.
  - ...



### Web

[https://www.rfc-editor.org/rfc/rfc9114.html](https://www.rfc-editor.org/rfc/rfc9114.html) (+ [RFC 9204 - QPACK: Field Compression for HTTP/3](https://www.rfc-editor.org/rfc/rfc9204.html) et [RFC 9218 - Extensible Prioritization Scheme for HTTP](https://www.rfc-editor.org/rfc/rfc9218.html))

- Basé sur le protocole de transport QUIC qui possède plusieurs fonctionnalités intéressantes telles que le multiplexage de flux, le contrôle de flux par flux et l’établissement de connexion à faible latence.
- QPACK : un format de compression pour représenter efficacement les champs HTTP à utiliser en HTTP/3. Il s’agit d’une variation de la compression HPACK qui vise à réduire la taille des headers.
- Extensible Prioritization Scheme for HTTP: schéma qui permet à un client HTTP de communiquer ses préférences quant à la façon dont le serveur en amont priorise les réponses à ses demandes, et permet également à un serveur d’indiquer à un intermédiaire en aval comment ses réponses devraient être priorisées lorsqu’elles sont transmises.



### Outillage

[https://twitter.com/vscodejava/status/1514687434805686278?s=21&amp;t=9B-Ur9W6tZf5mulv1K2KDA](https://twitter.com/vscodejava/status/1514687434805686278?s=21&amp;t=9B-Ur9W6tZf5mulv1K2KDA)

- Java 18 support, inlay hints for method parameters, and improvements to class declaration navigation are just a few of the enhancements to expect.





### Loi, société et organisation

[https://investors.broadcom.com/news-releases/news-release-details/broadcom-acquire-vmware-approximately-61-billion-cash-and-stock](https://investors.broadcom.com/news-releases/news-release-details/broadcom-acquire-vmware-approximately-61-billion-cash-and-stock)

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


## Outils de l’épisode

[https://copilot.github.com/](https://copilot.github.com/)

- A voir aussi: [Github Co-Pilot : Addictif ou Efficace ? (Johan Jublanc et Simon Provost)](https://www.youtube.com/watch?v=SQf9ZQsqW30) à Devoxx France 2022



## Conférences

[Nom de la conf du x au y mois à Ville]() - [CfP]() jusqu’à y mois
TODO: reprendre celles de l’épisode d’avant

De la part de Youen:
> Hello,  
> Cette année Codeurs en Seine, c’est le 17 novembre et le cfp est ouvert. 
> N’hésitez pas à amener un peu de JVM dans l’appel à orateur (ca commence à se faire rare). 
> Pour rappel : codeurs en seine c’est 1000 personnes autour des métiers du développement dans une des plus grande salle de Rouen, le kindarena.



## Nous contacter

Pour réagir à cet épisode, venez discuter sur le groupe Google <https://groups.google.com/group/lescastcodeurs>

Contactez-nous via twitter <https://twitter.com/lescastcodeurs>  
[Faire un crowdcast ou une crowdquestion](https://lescastcodeurs.com/crowdcasting/)  
Soutenez Les Cast Codeurs sur Patreon <https://www.patreon.com/LesCastCodeurs>  
Tous les épisodes et toutes les infos sur <https://lescastcodeurs.com/>
<!-- vim: set spelllang=fr : -->
