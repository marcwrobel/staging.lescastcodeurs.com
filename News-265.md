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

Enregistré le 1 septembre 2020

Téléchargement de l'épisode [LesCastCodeurs-Episode-999.mp3](https://traffic.libsyn.com/lescastcodeurs/LesCastCodeurs-Episode-999.mp3)

## News

### Langages

[Oracle annonce des LTS de deux ans](https://inside.java/2021/09/14/moving-the-jdk-to-a-2-year-lts-candence/) 
* Donc une LTS tous les 2 au lieu de 3 ans
* Mais pas de détail sur le temps de security patch support gratuit. Oracle en payant c’est 8 ans

[Oracle offre Oracle JDK gratuitement avec support pendant 1 LTS + 1 an (donc 3 ans)](https://blogs.oracle.com/java/post/free-java-license) 
* Redistribution gratuite aussi. Pas de click through. 
* Ils en ont marre d’avoir de la compétition ?

[Dans JDK 18, avec le JEP 400, le charset par défaut va enfin passer à UTF-8](https://inside.java/2021/10/04/the-default-charset-jep400/) 
* Autant ce n’était plus vraiment un problème pour les systèmes sour mac OS ou Linux, qui utilisent depuis assez longtemps UTF-8 par défaut, mais c’est surtout pour les systèmes Windows où c’est plus problématique
* Dans JDK 17, la propriété système `System.getProperty("native.encoding")` avait été introduite
* si on veut lire par exemple un fichier avec
* Deux approches de mitigation pour les problèmes de compatibilité, 1) en recompilant et en utilisant cette propriété quand on ouvre un fichier, ou 2) en utilisant -Dfile.encoding=COMPAT sans recompilation, qui gardera le même comportement qu’en JDK 17 et avant
* L’équipe d’Oracle suggère de tester ses applications avec -Dfile.encoding=UTF-8 pour voir s’il n’y a pas de soucis 

### Librairies

[JUnit 5.8](https://twitter.com/junitteam/status/1437131139194494976?s=21)  
* Declarative test suites
* Test class ordering
* Multiple temp dir support
* Extension registration on fields/params
* LauncherSession and listener

[Stephen Colebourne avertit les utilisateurs de Joda Time de ne pas mettre à jour la base de données des fuseaux horaires](https://blog.joda.org/2021/09/big-problems-at-timezone-database.html) 
* Les personnes qui sont responsables de cette base de données veulent fusionner certaines zones ensemble, par exemple, Oslo et Berlin. Alors que ces deux villes (et d’autres) n’ont pas forcément toujours eu la même heure
* La base est censée référencer tous les changements depuis 1970
* mais de fusionner plusieurs zones, le risque est de perdre cet historique aussi pré-1970

[State of Spring 2021]()

Recap Spring.io : [Jour 1](https://tanzu.vmware.com/content/blog/springone-2021-day-1-recap-and-highlights) - [Jour 2](https://tanzu.vmware.com/content/blog/springone-2021-day-2-recap-and-highlights)
* State of Spring 2021
* Azure Spring Cloud Enterprise
* Tanzu Application Platform
* Spring Cloud Gateway for K8s and API Portal for VMware Tanzu 

### Infrastructure

### Cloud

[Azure installe des agents dans son image linux et ils sont vulnérables aux auto update](https://www.wiz.io/blog/secret-agent-exposes-azure-customers-to-unauthorized-code-execution)  
* Lié à open management infrastructure
* Dès qu’on utilise des services comme azure log, ils l’installent dans les VMs
* L’article dit que c’est la faute à l’open source et que seulement 20 contributeurs. C’est un peu BS.
* En fait si c’est installé via un service le service le mettra à jour
* Mais MS recommande de mettre à jour manuellement aussi

### Web

### Data

[Kafka 3.0](https://blogs.apache.org/kafka/)
* Another step closer to remove ZooKeeper dependency. And of course many other improvements, bug fixes, and new features.

### Outillage

[TravisCI fait un petit partage de vos secrets dans toutes les PRs de vos repos par accident](https://arstechnica.com/information-technology/2021/09/travis-ci-flaw-exposed-secrets-for-thousands-of-open-source-projects/) 
* le problème a duré 8 jours
* rotation des secrets recommandé
* Travis a patché discretement sans disclosure initialement ce qui a fait un raffut

### Architecture

[Facebook est tombé pendant environ 6H ](https://engineering.fb.com/2021/10/05/networking-traffic/outage-details/) 
* Facebook prévoit de faire une maintenance sur son backbone (classique)
* Un ingénieur lance par erreur une commande qui declare l’ensemble du backbone inaccessible
* Oups, le système d’audit qui devrait empêcher de lancer une telle commande est buggé, la commande passe ...
* Toute l’infra de Facebook est désormais déconnectée du net. Les avertissements BGP sont stoppées puisque l’infra FaceBook n’est plus dispo et les DNS déprovisionnent les entrées FaceBook, le monde ne peut plus accéder à FaceBook
* Les ingé comprennent vite le problème sauf que ils ont perdus les accès remotes aux services et la plupart de leurs systèmes internes sont KO à cause du retrait des DNS
* Ils envoient donc du personnel sur site dans les datacenters pour physiquement remettre en service l’infra mais l’accès physique aux machines est super protégé
* Ils finissent par y arriver SAUF que le fait de tout redémarrer pause un vrai challenge du fait de l’affluence du traffic qui reprend. Ils risquent de refaire tomber les datacenters du fait de la surcharge électrique. (sans parler de sproblèmes plus haut niveau comme le rechargement des caches etc)
* Heureusement ils ont un plan de reprise qu’ils testent régulièrement qui est plutôt prévu dans le cadre d’une tempête qui mettrait HS tout ou partie du réseau. Ce système marche bien et tout rentre dans l’ordre petit à petit, Facebook est sauvé, la planète a reperdu 5 points de QI
* [Julia Evans explore BGP et son fonctionnement dans cet article](https://jvns.ca/blog/2021/10/05/tools-to-look-at-bgp-routes/)
* [Vu de dehors avec Cloudflare](https://blog.cloudflare.com/october-2021-facebook-outage/) 
* Impact non seulement du DNS mais des routes BGP elles même. Ces routes disent qu'une IP (our série d’IP) appartient à une personne donnee. 
    * Fondamentalement modèle de confiance.
    * Intéressant de voir comment Facebook DNS down ajouté beaucoup de traffic aux serveurs de DNS principaux qui ne cachent pas le SERVFAIL

### Méthodologies

### Sécurité

[Julia Evans nous explique CORS](https://twitter.com/b0rk/status/1445039796804542473) 
* Julia explique comment se comporte le navigateur qui voit qu’on essaie d’accéder à une URL différente de celle du domaine de la page web chargée, et le navigateur se demande s’il a le droit de charger cette page
* Il va faire un “preflight” request (avec une méthode HTTP OPTIONS) pour savoir s’il a le droit ou non, puis si c’est le cas, pourra accéder à la resource (edited) 
* Julia explique la same-origin policy (càd qu’on ne doit accéder que des resources du domaine qu’on est en train de visiter dans son navigateur)

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