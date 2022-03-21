---
title: LCC 273 - 
author: 'Emmanuel Bernard'
team: 'Emmanuel Bernard, Guillaume Laforge, Vincent Massol, Antonio Goncalves, Arnaud Heritier, Audrey Neveu'
layout: blog-post
episode: 273
mp3_length: TODO
tweet: TODO
# tweet size: 91-93 -> 99-101 #######################################################################
---
CA SERA SUREMENT 276 ou 277

Enregistré le 25 mars 2022

Téléchargement de l'épisode [LesCastCodeurs-Episode-273.mp3](https://traffic.libsyn.com/lescastcodeurs/LesCastCodeurs-Episode-273.mp3)

## News

### Langages

[Remplacer vos APIs de logging avec System.Logger](https://renato.athaydes.com/posts/java-system-logging.html)
* Blog post rédigé suite à notre épisode 271 (où on avait cité System.Logger)
* Rapide histoire des APIs de log en Java
* Présentation de l’API System.Logger
* Formattage des messages basé sur java.text.MessageFormat
* Utilisation possible des ResourceBundle
* Niveaux TRACE, DEBUG, INFO, WARNING, ERROR (et non FINE, FINER, FINEST comme JUL)
* Le service System.LoggerFinder pour changer l’implémentation (JUG, Log4J, Logback, ...)
* Etude de perf: Logback est plus performant, suivit de JUG puis Log4J2


[Une série de petites librairies Java légères](https://jodd.org/). Librairies simples, avec chacune une tâche unique, dont :
* parsing JSON
* parsing HTML / CSS
* client HTTP
* client mail
* resolveur de noms de paramètres de méthode
* des Properties améliorés
* un depdenceny-injection léger

### Librairies

[Micronaut 3.3 sorti, avec des nouveautés](
https://micronaut.io/2022/01/27/micronaut-framework-3-3-released/)

[Hibernate 6: certains points clés](https://twitter.com/1ovthafew/status/1486818448055410690?s=21)

[Kubernetes Service Discovery and Selection with Stork](https://quarkus.io/blog/stork-kubernetes-discovery/)

### Infrastructure

### Cloud

[Sondage annuel “The State Of Cloud Native Development”](https://www.cncf.io/wp-content/uploads/2021/12/Q1-2021-State-of-Cloud-Native-development-FINAL.pdf)

* Sondage créé par Slash Data et soutenu par la CNCF
* Interrogent 19.000 développeurs sur : l’utilisation de Kubernetes, le Edge Computing, le Cloud Native, Containers et Orchestrateur
* Le nombre mondial de développeurs cloud native a augmenté au cours des 12 derniers mois de 0,3 million, pour atteindre 6,8 millions.
* Dans le même temps, la proportion de développeurs backend impliqués dans les technologies cloud native a diminué de 3 points de pourcentage, passant de 44 % à 41 %.
* Dans toutes les régions, l’Amérique du Nord (47 %) et l’Europe occidentale (46 %) affichent les taux d’adoption les plus élevés.
* Kubernetes est utilisé par 31% de tous les développeurs backend, ce qui représente une augmentation de 4 points de pourcentage au cours des 12 derniers mois. Actuellement, 5,6 millions de développeurs utilisent Kubernetes.
* Dans tous les secteurs, le Edge Computing a connu une croissance rapide de l’adoption de Kubernetes et présente désormais les taux d’utilisation les plus élevés des conteneurs et de Kubernetes.
* Parmi les développeurs spécialisés dans le Edge Computing, l’utilisation de Kubernetes a augmenté de 11 points au cours des 12 derniers mois, pour atteindre 63 %.
* L’architecture Serverless est également attrayante pour les développeurs  Edge Computing : 48 % de tous les développeurs edge utilisent serverless, contre seulement 33 % de tous les développeurs backend.
* Parmi les outils serverless, AWS Lambda continue de jouer un rôle prépondérant. Cependant, Google Cloud Run a considérablement gagné du terrain au cours des 12 derniers mois.

[SLO et dependences de service](https://queue.acm.org/detail.cfm?id=3096459)

* 99,99 en cible interne, au dessus, il y a tant de variables entre l'utilisateur et le service que c'est perdu dans le bruit (wifi, ISP etc)
* 99,999 pour les infra globales
* disponibilité est fonction du MTTF et MTBR = MTTF/(MTTF+MTTR)
* si on veut offrir 99,99, toutes les dependances critiques doivent offrir beaucoup plus, regle du 9 supplementaire
* sinon il faut des mitigation, cache, fail open etc
* dispo depend du temps de detection et du temps de recuperation
* donc forcer les clients (services dependants) à baisser leur niuveau ou engineerer pour compenser le bas niveau du service dont on est dependant
* faire des scenarios (e.g. 1 outage majeur, 3 faibles - e.g. un shard, 5 de dependances)
* considerer que la perte d'un shard du service veut dire SLO is 1/nieme indisponible (n étant le numbre de shards)
* donc il reste peut de temps pour reagir quand on compte temps de detection, temps de paging, etc.
* error budget: 1-SLO, sur un mois et peut etre une fenetre glissante pour remonter graduellement. si budget depensé, on ne fait plus de mise en prod sauf critical security issues ou si c'est pour corriger les causes du probleme qui a consommé le budget
* rendre le plus de dependances non critiques (par exemple en eliminatnles SPOF)
* faire revue d'architecture pour identifier ces dependances et leurs impacts
* appels a trois pools de serveurs indpendants et prendre le premier resultat
* dependences asynchrones peut reduire le nombre de dependancs critiques
* retours arriere rapide et automatisés: en enlevant un humaind e la boucle, on racourcit les temps de réponse
* et bien d'autres choses encore
* (modifié)

### Web

### Data

### Outillage

### Architecture

[Les design patterns pour les systèmes distribués et donc les microservices](https://medium.com/everything-full-stack/design-patterns-and-principles-that-support-large-scale-systems-f3c9adf89ad)

* survol et définitions des patterns qu'il faut connaître dans les microservices
* Pas trop dans le détail donc bon survol
* Idempotence, asynchronicite, helathcheck, feature flag, fallback
* Bulkhead: compartementalisation
* Metrics, monitoring, alarmes
* Rate limiting, backpressure, etc

### Méthodologies

[La pyramide des fondamentaux dans la revue de code](https://www.morling.dev/blog/the-code-review-pyramid)

### Sécurité

[Removed unencrypted Git protocol and certain SSH keys](https://github.blog/changelog/2022-03-15-removed-unencrypted-git-protocol-and-certain-ssh-keys/)

[Samsung utilise incorrectement la crypto rendant son enclave sécurisée, pas sécurisée](https://threatpost.com/samsung-shattered-encryption-on-100m-phones/178606/)

* l'article n'a pas les details techniques
* 100 m de telephones
* la meme clée était reutilisée (et pas encapsulée
* le vecteur d'initialisation pouvait être configuré et reutilisé à valeur unique
* n'importe quelle application pouvait essayer d'acceder aux secrets de l'enclave en essayant les conbos parce que l'application avait accès à ces paramêtres
* quand on reutilise les vacteurs d'initialisation, on peut faire un 1-1 entre le message clair et chiffré, ce qui permet de revenir a message clair si on produit le meme message cripté.
* https://knowledge-base.secureflag.com/vulnerabilities/broken_cryptography/reused_iv_key_pair_vulnerability.html

### Loi, société et organisation

[Alert: peacenotwar module sabotages npm developers in the node-ipc package to protest the invasion of Ukraine](https://snyk.io/blog/peacenotwar-malicious-npm-node-ipc-package-vulnerability/)

[Un développeur sabote son projet open source et paralyse des milliers d'applications](https://www.numerama.com/cyberguerre/813825-un-developpeur-sabote-son-projet-open-source-et-paralyse-des-milliers-dapplications.html#utm_medium=e-mail&utm_source=newsletter_hebdo&utm_campaign=20220115_global)

[Violation de RGPD par utilisation de Google fonts](https://news.ycombinator.com/item?id=30135264)

[French privacy regulator rules against use of Google Analytics](https://www.politico.eu/article/french-privacy-regulator-rules-against-use-of-google-analytics)

* [L'article de la CNIL](https://www.cnil.fr/fr/utilisation-de-google-analytics-et-transferts-de-donnees-vers-les-etats-unis-la-cnil-met-en-demeure)

[VMWare, Red Hat et d'autres s'ajoutent aux sanction contre le gouvernement Russe en arretant la vente et les services pour les entités Russes et Belarusse](https://www.redhat.com/en/blog/red-hats-response-war-ukraine)

[Une Entrée en bourse pour Sonatype](https://venturebeat.com/2022/01/27/sonatype-which-secures-the-use-of-open-source-software-lays-groundwork-for-ipo)


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