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
Résumé

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

### Web

### Data

### Outillage

### Architecture

### Méthodologies

### Sécurité

[Samsung utilise incorrectement la crypto rendant son enclave sécurisée, pas sécurisée](https://threatpost.com/samsung-shattered-encryption-on-100m-phones/178606/)

* l'article n'a pas les details techniques
* 100 m de telephones
* la meme clée était reutilisée (et pas encapsulée
* le vecteur d'initialisation pouvait être configuré et reutilisé à valeur unique
* n'importe quelle application pouvait essayer d'acceder aux secrets de l'enclave en essayant les conbos parce que l'application avait accès à ces paramêtres
* quand on reutilise les vacteurs d'initialisation, on peut faire un 1-1 entre le message clair et chiffré, ce qui permet de revenir a message clair si on produit le meme message cripté.
* https://knowledge-base.secureflag.com/vulnerabilities/broken_cryptography/reused_iv_key_pair_vulnerability.html

### Loi, société et organisation

[Un développeur sabote son projet open source et paralyse des milliers d'applications](https://www.numerama.com/cyberguerre/813825-un-developpeur-sabote-son-projet-open-source-et-paralyse-des-milliers-dapplications.html#utm_medium=e-mail&utm_source=newsletter_hebdo&utm_campaign=20220115_global)

[Violation de RGPD par utilisation de Google fonts](https://news.ycombinator.com/item?id=30135264)

[French privacy regulator rules against use of Google Analytics](https://www.politico.eu/article/french-privacy-regulator-rules-against-use-of-google-analytics)

* [L'article de la CNIL](https://www.cnil.fr/fr/utilisation-de-google-analytics-et-transferts-de-donnees-vers-les-etats-unis-la-cnil-met-en-demeure)

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