# Salut Tristan voila t'es notes sur Java

Il s'agit d'un langage de programmation rapide, sécurisé et fiable qui permet de tout coder, des applications mobiles aux logiciels d'entreprise en passant par les applications de big data et les technologies côté serveur.


### Constructeur

Un constructeur en Java est une méthode spéciale utilisée pour initialiser des objets. Le constructeur est appelé lorsqu'un objet d'une classe est créé.

```Java

public class Main {
  int x;

  public Main(int y) {
    x = y;
  }

  public static void main(String[] args) {
    Main myObj = new Main(5);
    System.out.println(myObj.x);
  }
}
```

### Héritage : 

l'héritage permet de récuperer des données d'une class mere vers une clas fille grace à extends

```Java
public class FigureGeometrique {
    private int x;
    private int y;
    public void moveTo(int newX, int newY) {
        this.x = newX;
        this.y = newY;
    }
}

public class Carre extends FigureGeometrique {
    private long cote;
    public long getCote() {
        return cote;
    }
    public long getPerimetre(){
        return 4*cote;
    }
}
```
### Polymorphisme: 

Le polymorphisme permet de surcharger les méthodes de la classe mère pour redéfinir leurs comportements sans changer leurs signatures

```Java
class Animal {
    void deplacer() {
    System.out.println("Je me déplace");
}
}

class Chien extends Animal {

   void deplacer() {
      System.out.println("Je marche");
   }

}

class Oiseau extends Animal {

   void deplacer(){
      System.out.println("Je vole");
   }

}

class Pigeon extends Oiseau {

   void deplacer() {
      System.out.println("Je vole surtout en ville");
   }

}

public class Test {
public static void main(String[] args) {

    Animal a1 = new Animal();

    Animal a2 = new Chien();

    Animal a3 = new Pigeon();


    a1.deplacer();

    a2.deplacer();

    a3.deplacer();

    }

}

Je me déplace 
Je marche
Je vole surtout en ville
```


### Encapsulation

L' encapsulation a pour but de s'assurer que les données « sensibles » sont cachées aux utilisateurs. Pour y parvenir, vous devez :

déclarer les variables/attributs de classe commeprivate
fournir des méthodes publiques get et set pour accéder et mettre à jour la valeur d'une private variable



Vous avez appris dans le chapitre précédent que privateles variables ne sont accessibles qu'au sein d'une même classe (une classe extérieure n'y a pas accès). Cependant, il est possible d'y accéder si nous fournissons des méthodes get et set publiques .

La getméthode renvoie la valeur de la variable et la setméthode définit la valeur.

La syntaxe pour les deux est qu'ils commencent par soit getou set, suivi du nom de la variable, avec la première lettre en majuscule :

```Java
public class Person {
  private String name; // private = restricted access

  // Getter
  public String getName() {
    return name;
  }

  // Setter
  public void setName(String newName) {
    this.name = newName;
  }
}
```

### Les entrées clavier

```Java
import java.util.Scanner;
 
public class Test {
    public static void main(String args[]) {
        String nom;
        int age;
        double salaire;
        Scanner clavier = new Scanner(System.in);
        System.out.print("Saisir votre nom : ");
        nom = clavier.nextLine();
 
        System.out.print("Saisir votre age : ");
        age = clavier.nextInt();
 
        System.out.print("Saisir votre salaire : ");
        salaire = clavier.nextDouble();
 
        System.out.println("[nom = " + nom + " , age = " + age + " , salaire =" + salaire + "]");
 
        // fermer les ressources
        clavier.close();
 
    }
}
Saisir votre nom : Mostafa
Saisir votre age : 13
Saisir votre salaire : 9000.34
[nom = Mostafa , age = 13 , salaire =9000.34]
```
