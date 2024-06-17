# Algorithme 
## Semaine du 21/05/24 à 24/05/24

#### Pense : 
* Refléchir avant d'agir

* Schématise sur papier l'algo que tu veux créer

* Met des notes dans ton code pour comprendre ce que tu fais

### Les variables sont un conteneur ou tu peux stocker des données
int : pour créér une variable d'une nombre entier

float : pour créer une variable d'un nombre décimal

boolean : pour créér une variable qui a besoin d'etre true or false

Voici quelque exercice que tu as fait pour apprendre les bases : 
```java
c:5
int findCarre(int nombre){
  for(int i = 0;i<=nombre;i=i+1){
    if (i*i>nombre){
      return i*i;
    }
  }
  return -1;
}

void setup(){
  println(findCarre(7));
}

c:6
int findCarre(int nombre){
  for(int i = 0;i<=nombre;i=i+1){
    if (i*i>nombre){
      return (i-1)*(i-1);
    }
  }
  return -1;
}

void setup(){
  println(findCarre(8));
}
```
### le pouvoir de return :
mettre return à la fin d'une fonction permet de mettre fin à la fonction mais aussi permet de bloquer le resulat de la fonction par exemple :
si ma variable est un tableau alors return la fin  du tableau permet de faire  que la fonction prend pour resulat le tableau, cel apemert de retourner le tableau si jamais j'ai besoin de rappelr le tableau dans mon code 
```Java

c:7
int total;
void suite (){
  for(int i=1;i<=100;i=i+1){
    total=total+i;
  }
}
void setup(){
  suite();
  println(total);
}
```
##### Une fonction est une variable avec toujours des () à la fin, ses parenthèse permet de mettre des variable dedans pour les rappeller plus tard.

#### For : permet de créér une boucle, cette boucle à besoin de 3 parametres pour fonctionner : 
* une variable égal à quelque chose
* une condition de fin de boucle
* comment se déplace la boucle

#### Mettre des condition :
* if permet de créér une condition
* Else permet de mettre une autre condition si la 1er n'est pas réalisable.

#### Modulo :
Les modulo permet de savoir si un nombre est divisible.

Par exemple variable % 2 = 0 ,

cela veut dire que ma variable divisible par 2 à pour reste 0.

``` java
c8
void calculSyracuse (int nombreSyracuse){
  for(int i = nombreSyracuse;i!=1;i=nombreSyracuse){
    if (nombreSyracuse % 2 ==0){
  nombreSyracuse=nombreSyracuse/2;
}
 else { 
     nombreSyracuse=nombreSyracuse*3+1;
   }
   
   println( nombreSyracuse);
  }
   
 }

void setup(){
calculSyracuse(28);

}
c8 bonus 1

void chiffrePremier(int nombrePremier){
  for(int i=2;i<nombrePremier;i++){
    if (nombrePremier % i ==0){
      println("C'est pas un nombre premier");
      break;
    }else{
      println("c'est un nombre premier");

    }
  }
}
```
#### Tableau:

Les tableau se créér grâce à une fonction suivi de [].

Exemple de tableau : int[] numbers = {90, 150, 30, 60, 200, 300};

Variable.length permet de parler de la longueur du tableau.

A noter qu'un tableau peut etre un float et un boolean si besoin.

```java
void setup(){
  chiffrePremier(12);
}

d1
int total=0;
int moyenne=0;
int[] numbers = new int[6];
numbers[0] = 90; 
numbers[1] = 150; 
numbers[2] = 30;
numbers[3] = 60; 
numbers[4] = 200; 
numbers[5] = 300; 
 for (int i=0;i<numbers.length;i=i+1){
   total=total+numbers[i];
 }
  moyenne=total/numbers.length;
println(total);
println(moyenne);


int position = 0;
int walk=1;
int jump = 2;
boolean[] numbers ={false ,false ,true ,false ,true, false, false};


void go(){
  for (int i=0;i<numbers.length;i=i+1){
    println(i);
    
    if(i < numbers.length-1 && numbers[i+1]==true){
      i = i + 1;
    }
    
  }
}
  void setup(){
    go();
  }

void nombreMax(int []board){
  int getMax=0;
   for (int i=0;i<board.length;i=i+1){
     //println(i);
     // println(board[i]);
     if  (getMax < board[i]){
       getMax=board[i];
     }
   }
   println(getMax);
}

 void setup(){
  int[] numbers = {90, 150, 30, 60, 200, 300};
  int[] chiffres = {500, 150, 330, 660, 2040, 30};
  nombreMax(numbers);
  nombreMax(chiffres);
 }

```

