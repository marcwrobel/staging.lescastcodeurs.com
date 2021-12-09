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

## Interview

### Ta vie ton oeuvre

### Introduction à la techno

Docker en 1 minute  
Docker compose d'où vient l'idée et le besoin  

### La techno en concepts

Un container c'est quoi ?  
Ca tourne comment ?  

Du coup, on veut en faire tourner plusieurs  
Comment on les "lie"?  
Network  
autre chose?  

Mais c'est pas le job de Kubernetes?  

* deploy
* scaling
* rollback


La spécification  

Discussion sur les notions:

* service
* build
* label
* network
* sécurité (cap_add)

docker-compose vs docker compose

### Comment on l’utilise en pratique pour un dev

Comment je définie mon multi container  
Lien vers des dockerfiles?  
Echange d'infos (e.g. DB connection ou mot de passe entre DB et l'appli)  
Ma DB doit démarrer avant mon app  
Ca fait les health check?  


Je commite ce fichier où typoiquement ?
comment je partage avec mon équipe ?
Et ma CI ?

Comment je mets en prod ?  Je mets en prod hein, ça marche sur ma machine.  

v2 vs v3  

### Sous le capot

Et donc comment ça marche docker compose?  
Zoom sur le network 

La sécurité  

### La communauté, le futur

Roadmap  
Docker desktop payant  

## Nous contacter

Soutenez Les Cast Codeurs sur Patreon <https://www.patreon.com/LesCastCodeurs>  
[Faire un crowdcast ou une crowdquestion](https://lescastcodeurs.com/crowdcasting/)  
Contactez-nous via twitter <https://twitter.com/lescastcodeurs>  
sur le groupe Google <https://groups.google.com/group/lescastcodeurs>  
ou sur le site web <https://lescastcodeurs.com/>
<!-- vim: set spelllang=fr : -->