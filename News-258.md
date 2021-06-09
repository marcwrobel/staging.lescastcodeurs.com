- - - 
title: LCC 999 - 
author: 'Emmanuel Bernard'
layout: blog-post
episode: 999
mp3_length: 85017000
tweet: TODO
# tweet size: 91-93 -> 99-101 #######################################################################
- - - 
Résumé

TODO: comment ajouter une news

* titre en français si possible
* pas de bullet points mais ajouter deux espaces à la fin de la ligne (cela fait passer à la ligne)  

    * bullet points autorisés si plusieurs liens sur là même news

Enregistré le 1 septembre 2020

Téléchargement de l'épisode [LesCastCodeurs-Episode-999.mp3](https://traffic.libsyn.com/lescastcodeurs/LesCastCodeurs-Episode-999.mp3)

## News

### Langages

[GraalVM 21 sur InfoQ’France ](https://www.infoq.com/fr/news/2021/02/graalvm-21-jvm-java/?itm_source=infoq_en&itm_medium=link_on_en_item&itm_campaign=item_in_other_langs)

* Un interpréter Java en Java
* Plus simple a debugger
* Avant ils utilisaient hotspot
* Reste projet
* Java en tant que container de javas 
* Mélanger ahead of time et classique Java 

### Librairies

[Spring Boot 2.5.0est sorti](https://spring.io/blog/2021/05/20/spring-boot-2-5-is-now-ga) 

* Support for Java 16
* Support for Gradle 7
* Enhanced Docker image building
* New mechanism for Datasource initialisation pour préparer R2DBC
* Les dépendances mises à jour (Spring data, hateoas’ spring Kafka et)
* En gros rien de révolutionnaire, beaucoup de mise à jour et du nettoyage

[Hibernate a 20 ans !](https://twitter.com/hibernate/status/1396425771040792577?s=21)

* Première sortie 
* Ça ne nous rajeuni pas 

[Vert.x 4.1 est sorti](https://vertx.io/blog/eclipse-vert-x-4-1-0/)

* Reactive Microsoft SQLServer driver 
* Vert.x HTTP proxy plutôt que de l’écrire soit même 
* RxJava 3
* OpenTelemetry tracing
* Plus conforme à OAuth2 et OIDC
* Kotlin 1.5
* Flexibilité dans la configuration de pools (plusieurs event loops par pool, waiter cancellation, lock free impl, etc
* Web session stocké dans Infinispan 
* Et plus au niveau sécurité, openapi, service proxy

### Infrastructure

[Un problème chez Fastly et l'internet tousse](https://www.fastly.com/blog/summary-of-june-8-outage)

* Fastly est un CDN
* hoste beaucoup d'artefact de type NPM, Maven, JS resources etc
* consequence est sites defacé par manque de CSS ou JS, voir HTTP pages non accessibles
* bug declenché par une config client => fait tomber 85% du réseau

### Cloud

[Les services d’intelligence artificielle d’AWS ne respectaient pas le non déplacement des données hors de la région par défaut ](https://techmonitor.ai/techonology/cloud/aws-user-data)

* Et le défaut était très bien caché.  Les experts AWS n’avaient pas fait gaffe
* C’était légal mais en tout petit dans les conventions 
* Différence entre télémétrie et les données en propre en général. Pas pour les iA ;)
* Les services impacté AWS Terms 50.3 mention CodeGuru Profiler, Lex, Polly, Rekognition, Textract, Transcribe, and Translate. 60.4 also mentions this for SageMaker. 75.3 mentions this for Fraud Detector. 76.2 mentions this for Mechanical Turk and Augment AI.

### Web

[Vers un système unique et une API commune pour les extensions dans les navigateurs](https://appleinsider.com/articles/21/06/04/apple-mozilla-google-microsoft-form-group-to-standardize-browser-plug-ins)

* Des gens de Apple (Safari), Google (Chrome), Microsoft (Edge) et Mozilla (Firefox) vont collaborer ensemble, au sein du WECG
* [Web extensions community group](https://www.w3.org/community/webextensions/)
* Base sur le travail de safari de supporter les extensions des autres navigateurs 
* On a vu des défis et réduction de possibilités pour contrôler la sécurité et le tracking
* De toutes façons tout le,monde est sur Chromium ahaha 

### Data

### Outillage

[Gradle 7 est sorti et Cédric nous fait un crowdcast ](https://gradle.org/whats-new/gradle-7)

* D’ailleurs, Cédric quitte Graeme Inc après des années de bons et loyaux services 

[Prosus achète StaxkOverfloz pour 1,8 milliards](https://stackoverflow.blog/2021/06/02/prosus-acquires-stack-overflow/)

* Prosus avait déjà des parts dans des entreprises type Codeacademy, et Udemy, dans l’EDU/tech
* StackOverflow commence en 2008
* [Migration vers SaaS d StackOverflow](https://siliconangle.com/2020/05/18/stack-overflow-ramps-up-saas-model-as-it-builds-relationships-with-microsoft-and-developers-cubeconversations/) intéresse Prosus 
	* Jobs 50% du revenu
	* Team collaboration tool bonne croissance 
	* C’est stackoverflow pour les équipes internes 

### Architecture

### Méthodologies

[Le temps moyen de PR entre Stripe et Mozilla](https://twitter.com/jlongster/status/1400511441556459523?s=21)

* Des jours à attendre le feedback vs 10 minutes 
* C’est un débat assez fondamental je trouve. Comment organiser les équipes pour que les PR soient vues comme la chose importante. Plus que « le code ». 
* Différence Service vs product 

### Sécurité

### Loi, société et organisation

[Un article de rappel sur la copie privée](https://www.nextinpact.com/article/30201/108870-la-redevance-copie-privee-vache-a-lait-industries-culturelles)

* Copie privée basse sur les cassettes et VHS. Ensuite le stockage numérique explose 
* 270 millions d’euros en France en 2017
* Une commission administrative fixe les règles. Composée.  de 6 usagers, 6 vendeurs de stockage, 12 ayant droits et un président au droit de vote et pro ayant droit. Rapport de force clair
* Ils essaye de construire la vache à lait: prix basé sur la copie licite ou pas (cassé en 2008) ensuite argument de compression pour garder le barème haut 
* En théorie que pour les particuliers et procédure de remboursement pour les pros. Mais difficile à appliquer donc quasi jamais fait. 
* 25% des gains financent des festivals et manifestations culturelles : instrument d’influence des élus locaux et pas si locaux 
* Efforts pour taper sur tous les disques durs nus, faire entrer dans le champ le stream ripping
* Et maintenant [la copie privée sur la vente d’occasion](https://actualitte.com/article/100640/politique-publique/copie-privee-les-appareils-reconditionnes-pomme-de-discorde). La grande classe. 
	* Risque pour l’économie solidaire qui sont sur des populations fragiles 
	* Le sénat veut favoriser l’écologie de la seconde main et serait pour l’exclusion de la taxe dans ce cas là. 
	* Les smartphones c’est 70% de leurs revenus

## Outils de l'épisode

[Google ZX pour écrire des scripts en JavaScript](https://t.co/kDnarh0A13)

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