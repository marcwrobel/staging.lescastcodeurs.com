# GraalVM

## Interview

### Ta vie, ton oeuvre

### GraalVM pour comprendre l’enjeu

GraalVM en 3 phrases

Les cas d’utilisation typique

### Les concepts clés

Graal le compilateur et le JIT  
* c’est quoi un JIT
* Pourquoi pas basé sur HotSpot  
* Pourquoi en Java?
* des cas d’utilisations préférés par GraalVM JIT vs HotSpot (et vice versa)

Truffle et polyglot
* Java qui tourne d’autres langages, lesquels?
* comment ça marche, génère du byte code? Interprète?
* Comment les codes de différents langages interagissent?

Espresso:
* Java sur Java (what??!), ca veut dire quoi exactement?
* Quels usages?
* niveau de stabilité, maturité?

Native:
* comment ca fonctionne
* Un JIT?
* quel GC
* Quels avantages
* Quels inconvénients?

Donc GraalVM c’est une JVM, quelles parties sont reprises de OpenJDK?

### Comment on l’utilise en pratique

Je veux utiliser GraalVM pour mon code nodeJS, je fais comment?  
Je veux utiliser GraalVM comme ma JVM de mon appli Java, je fais comment?  

Je veux faire du native, comment je fais?
* concrètement, je dois faire gaffe a quoi?

GraalVM Community vs Enterprise, quelles sont les différences ?

### Sous le capot


Comment on implémente un nouveau langage sur GraalVM?

Comment on implémente Java sur Java  
C'est dur de supporter des nouveaux langages avec leur semantique et leur stypes != de la JVM

Comment l'interpretation de langages s'optimise


Comment les optimisations sont construites?  
Des trucs cools à raconter sur les optimisations?

C’est un chemin de combien d’années?

WASM vs GraalVM, comment vous voyez la “standardisation de la VM” derrière WASM?

### La communauté et le futur

Quelle license?  
C’est juste Oracle?  
Pourquoi c’est pas dans OpenJDK?  
Comment la commmunauté code ensemble?  

Des idées sur là où vous voulez aller?  