---
title: LCC 260 - 
author: 'Emmanuel Bernard'
team: 'Emmanuel Bernard, Guillaume Laforge, Vincent Massol, Antonio Goncalves, Arnaud Heritier, Audrey Neveu'
layout: blog-post
episode: 260
mp3_length: 85017000
tweet: TODO
# tweet size: 91-93 -> 99-101 #######################################################################
---
Résumé

TODO: comment ajouter une news

* titre en français si possible
* pas de bullet points mais ajouter deux espaces à la fin de la ligne (cela fait passer à la ligne)  

    * bullet points autorisés si plusieurs liens sur là même news

Enregistré le 16 juillet 2021

Téléchargement de l'épisode [LesCastCodeurs-Episode-999.mp3](https://traffic.libsyn.com/lescastcodeurs/LesCastCodeurs-Episode-999.mp3)

## News

### Langages

[Les prédictions d'Adam Bien pour la seconde moitié de 2021](https://adambien.blog/roller/abien/entry/mid_year_2021_observations_and)

* Kube a gagné la guerre. Les cloud providers fournissent des solutions dérivées plus simplifiées. La compatibilité kubernetes devient moins cruciale
* FaaS est utilise pour son usage listener et point d'intégration et plus en général purpose tool
* Prix du cloud et repatriation. Bouger une app existante dans le cloud n’amène pas d’avantage. Le monolith devient une best pratice
* Coût du cloud pousse a merger des microsercices dans un cadre de cloud cost driven development
* Cloud deviennent intéressant pour les services unique (text to speech, image recognition, etc). En parallèle la sécurité des cloud providers est reconnu. Donc boring load on prem, projects innovants dans le cloud. 
* Serverless va être le trend de 2021 (fonction mais aussi db, workflow, event streams etc) idée est scale down to zero
* La montée des frameworks next gen Micronaut et Quarkus est indisputable. Build time deployment.
* La popularité de quarkus a explosé, difficile de trouver un développeur Java qui n’a pas expérimenté. Le cocktail GraalVM api familières Jakarta ee et micro profile, sa do so mémoire et temps de démarrage lui donne un avantage. Mais la compétition ne dors pas (Helidon et micronaut)
* Moins de langages alternatifs parce que l’innovation dans Java a accéléré
* Lombok moins populaire parce que Java Records.
* Kafka sera plus un data store immuable et source de vérité que un remplacement pour JMS
* Kafka et réactive en combo va rendre la programmation réactive populaire
* ARM sur le serveur
* GraalVM pour remplacer OpenJDK car rapide et multi langage. Et competitor a GraalVM qui arrive
* Visual studio code et ses features pour Java  pas forcément connu et donc va croître encore.
* Payara cloud serverless server ou l’app server est un opérateur Kube et on déploie un thin jar.

[GraalVM offre des plugins Gradle et Maven pour la compilation native](https://medium.com/graalvm/gradle-and-maven-plugins-for-native-image-with-initial-junit-testing-support-dde00a8caf0b)

* Tester les libraires en natif avec les tests junit 5 qui tournent en natif
* Après tourne les tests en JVM, ils sont loggués et ajoutés en réflection et complication native.
* Et un binaire de test est créé
* plugin Gradle
* License Oracle Universal Permissive
    * probablement un dérivé de [Universal Permissive License](https://opensource.org/licenses/UPL)

[Le rapport sur l’écosystème JVM](https://snyk.io/jvm-ecosystem-report-2021/ le rapport sur l’écosystème JVM)

* Mon (Emmanuel) intuition c'est qu'il y un biais dans les gens mesurés
* 44% des Dev Java utilisent adoptopenjdk en prod. Oracle openjdk 28 et Oracle JDG 23
* 60% utilisent Java 11 en prod. Et 12 la dernière mais encore 60% de 8 en prod
* Java 91% kotlin 18% groovy 13 et scala 10 
* IntelliJ 70% eclipse 25 et vscode 23. 50% sont bi IDE
* Maven 76% gradle 38% ant 12W yah
* Spring Boot 58% Spring MVC 29% Jakarta ee 13% Quarkus 11%

### Librairies

[Spring Native 0.10.0](https://spring.io/blog/2021/06/14/spring-native-0-10-0-available-now)

* Utilise Native testing de GraalVM
* Passe au plugin Gradle de l'équipe GraalVM
* Ahead of time proxies pour les classes

[Quarkus 2.0 est sorti](https://quarkus.io/blog/quarkus-2-0-0-final-released/)

* Guide de migration mais les applis devraient essentiellement fonctionner (extensions ont plus de taf)
* JDK 11+ GraalVM 21.1
* Vert.x 4
* Microprofile 4
* Continuous testing : les tests impactes tournent automatiquement en Dev mode. Les tests qui cassent sur un changement sont visible tout de suite et en continu. Comme infinitest mais sans plugin IDE.
* Quarkus a une CLI pour simplifier l’interaction vs les plugins maven ou gradle.   Notamment création de projetas.* Guide de migration mais les applis devraient essentiellement fonctionner (extensions ont plus de taf)
* JDK 11+ GraalVM 21.1
* Vert.x 4
* Microprofile 4
* Continuous testing : les tests impactes tournent automatiquement en Dev mode. Les tests qui cassent sur un changement sont visible tout de suite et en continu. Comme infinitest mais sans plugin IDE.
* Quarkus a une CLI pour simplifier l’interaction vs les plugins maven ou gradle.   Notamment création de projets.
* GraphQL client (smallrye), CDI decorators supportés, transaction pour MongoDB avec Panache,
* Support kotlin grandement amélioré : resteasy rezctive, rest client, reactive messaging extensions supportent tous les coroutines
* Support d’Amazon services system manager

### Infrastructure

[Amazon sort son OpenSearch 1.0 et OpenSearch Dashboard, leur fork d’Elastic Search et Kibana](https://opensearch.org/blog/updates/2021/07/opensearch-general-availability-announcement/)

* 1.0 sortie
* Continual removal of proprietary code and marks.
* Upgrading: mise a jour d'ElasticSearch et Kibana aussi simple qu'une mise a jour de version
* Compatibility: travaux de reflexion autour de la compatibilité avec les outils existants
* Testing: modern and flexible testing infrastructur
* Support for the ARM64 architecture for Linux,
* Minimal artifacts for embedding of OpenSearch and OpenSearch Dashboards into existing products and services,
* Data stream support for OpenSearch Dashboards,
* Span attribute visibility and filtering in the Trace Analytics plugin,
* Scheduling and tenant support in the Reporting plugin.
* aussi mentionne la roadmap

[Kibernetes 1.22 enlève le support des vieilles versions de resource](https://kubernetes.io/blog/2021/07/14/upcoming-changes-in-kubernetes-1-22/#api-changes)

* faites le ménage en continu pas des grosses migrations tous les 3 ans

### Cloud

[Un tweet lance un faux service AWS InfiniDash qui a été repris par des devs et des boîtes](https://siliconangle.com/2021/07/05/fake-amazon-cloud-service-aws-infinidash-quickly-goes-viral/)

* La théorie est que la plupart des devs n’entendront parler de technologie que via les tweets et les articles.
* Aussi le métier de devrel c’est de surfer la vague du social media. Les dev rels AWS ont continué la farce (je crois)
* Werner Vogels, oui pour sur.
* gros effet boulle de neige

### Web

### Data

### Outillage

[GitHub copilot](https://copilot.github.com/)

* itellisense boosté par les projets visible et hostés dans GitHub et autre données publiques
* via l'intelligence artificelle, essaie de comprendre l'intention via le contexte
    * uniquement le fichier édité en contxte pour l'instant
* VSCode extension donc tourne partout où les plugins VSCode tournent
* 0,1% de copie exacte
* le code nous appartient en tant qu'utilisateur
* le code contexte est transmis a GitHub qui l'utilise pour ses telemetries et améliorer les modèles ML
* pas toujours du code de qualité
* [des secrets valides sont générés](https://twitter.com/alexjc/status/1411966249437995010) (du corpus originali e.g. SendGrid)
* [propose du code GPL (derivation?)](https://drewdevault.com/2021/07/04/Is-GitHub-a-derivative-work.html)
* attaque de sécurité vont venir :)

[Audacity 3 spyware ou pas après le rachat](https://arstechnica.com/gadgets/2021/07/no-open-source-audacity-audio-editor-is-not-spyware/)

* la communauté "niveau 2" s'est emballée, a crée une dizaine de forks.
* C’était déjà annoncé et discuté avec la communauté Audacity.
* OS, pays, cpu, erreurs, reports de crash
* Protection légale « law enforcement ». Les 13 ans, juste pour éviter des restrictions légales us
* 3.0.2 n’a pas le code des collections de données 
* Avec feedback initial passe de Google analytics à un hébergement propre.
* Quand compile le project c’est off par défaut (donc seuls les binaires distribués l’ont par défaut) donc pas dans les distros linux

### Architecture

### Méthodologies

### Sécurité

[LinkedIn la brèche qui donne des infos de 92% de ses utilisateurs y compris les salaires inférés](https://9to5mac.com/2021/06/29/linkedin-breach/amp/?__twitter_impression=true)

* API LinkedIn abusée.
* Email, noms, telephone, adresse physique,
* Presque interessé de fouiller pour voir mon salaire théorique :)

### Loi, société et organisation

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
