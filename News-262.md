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

### Librairies

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