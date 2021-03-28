# Java 16
## Interview

### Ta vie, ton oeuvre

### Java et sa cadence de release

Retour général sur la cadence de release: Bien ou mal?

### Java 16

[JDK 16](https://openjdk.java.net/projects/jdk/16/)  
[JDK 16 Arrived : Java 16 Released with New Features | TechGeekNext >>](https://www.techgeeknext.com/java/java16-features)    

### Records

### Pattern matching

`instanceof`

Autres pattern patching qui sont arrivés?

### Sealed classes (preview)

C’est quoi?
Ca sert à quoi?

Et les hidden classes ?

### jpackage

Packager des apples indépendantes de la JVM

### Illegal access pass en deny par défaut (Henry)

JEP 396 (encapsulation force des parties internes du JDK.

[FEATURE Make Lombok compatible with JDK 16 · Issue #2681 · rzwitserloot/lombok · GitHub](https://github.com/rzwitserloot/lombok/issues/2681)


### Domain socket channel

Comm inter processus

### API vecteur

Les `Vector` sont de retour?!
Discussion ud parallelisme au niveau CPU (Simple Instruction Multiple Data)

### **Foreign Linker API**

Pour projet Panama  
Lier une méthode native avec du code Java  
Du coup on a aussi un foreign memory access API?  

[Project panama and jextract – Inside.java](https://inside.java/2020/10/06/jextract/) Jextract genera le code Java à partir du fichier de declaration C. 

### JVM sur d’autres plateformes

Alpine Linux et Musl

AArch64 (ARM) sous Windows

### ZGC

Move ZGC thread-stack processing from safepoints to a concurrent phase.

### Autres

* Mercurial -> git  
* Return unused HotSpot class-metadata (i.e., *metaspace*) memory to the operating system more promptly, reduce metaspace footprint, and simplify the metaspace code in order to reduce maintenance costs.

### Bonus Java 15

Shenandoah  
Text blocks  
Plus de Nashorn  

