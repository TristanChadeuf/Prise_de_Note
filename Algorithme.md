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

## Voici le démineur que tu as eu du mal à faire

``` Java 
int mine =99;
  int[][] board = initBoard(10, 10, 10);

void isAmine(int[][] vision) {//création de la fonction vision pour mettre des X ou O à, la place des 0 et 99
  for (int i = 0; i<vision.length; i++) {
    for (int k=0; k<vision.length; k++) {
      if (vision[i][k]==99) {
        print("X ");
      } else {
        int v = getMines(vision,i,k);
        String content = str(v) + " ";
        print(content);
      }
    }
    println();
  }
}


int getMines(int[] [] tableau, int position, int positionL) {//création de la fonction qui permet de signaler si une bombe se trouve à une case
  int mineProche=0;

  if (position > 0 && positionL > 0 ) {
    if (tableau[position-1][positionL-1]== 99) {
      mineProche=mineProche+1;
    }
  }
if  (position >0){
    if (tableau[position-1][positionL]== 99) {
      mineProche=mineProche+1;
    }
}
if (position <9) {
    if (tableau[position+1][positionL]== 99) {
      mineProche=mineProche+1;
    }
}

if  (position > 0 && positionL < 9) {
    if (tableau[position-1][positionL+1]== 99) {
      mineProche=mineProche+1;
    }
}
if ( position < 9 && positionL > 0 ) {
    if (tableau[position+1][positionL-1]== 99) {
      mineProche=mineProche+1;
    }
}
  if  (positionL < 9){
    if (tableau[position][positionL+1] == 99) {
      mineProche=mineProche+1;
    }
  }
  
  
  if  (position < 9 && positionL < 9){
    if (tableau[position+1][positionL+1] == 99) {
      mineProche=mineProche+1;
    }
  }
  
  if  ( positionL > 0 ){
    if (tableau[position][positionL-1] == 99) {
      mineProche=mineProche+1;
    }
  }
  
  return mineProche;
}


int[][] initBoard (int size, int sizeL, int nbMine) {//creation d'un tableau

  int board [][] = new int [size][sizeL];//le tableau prend la taille de la variable size donc 10
  while (nbMine!=0) {//creation d'une boucle qui s'arrete quand la variable nbmine sera égale à 0
    int randomL = (int)random(sizeL6+);
    int random = (int)random(size);// création de la variable random qui met au hasard des mines
    if (board[randomL][random]==0) {//si la case du tableau est un 0 alors une bombe peut etre poser
      board[randomL] [random]=mine;
      nbMine = nbMine -1;// donc la variable nbmine perds 1 de valeurs
    }
  }
  return board;// je retoune ma fonction pour qu'elle soit égale au tableau
}
void setup() {
  //int[][] board = initBoard(10, 10, 10);
  isAmine(board);
  // println("nombre de bombe autour", getMines(board, 5,5));

}
```

## Jeux de l'oie (pas fini)
```Java 
int taillePlateau = 64;//Variable pour crrer la longueur de mon tableau
int nbJoueur = 4;
int [] Joueur =  new int [nbJoueur];//variable appeler dans la fonction plateau pour creer la longueur de la boucle
int [] tableauY =  new int [nbJoueur];
int [] plateauDeJeux = new int[taillePlateau];//Création de du tableau servant de terrain de jeux

void avancement(int p) {//fonction qui sert à creer les joueurs
fill(15, 157, 232);
tableauY[p]= 310+(35*p);
 rect(plateauDeJeux[Joueur[p]], tableauY[p], 19, 19);// rectangle représentant 1 joueur

 fill(255);
 textSize(30);
 text(Joueur[p], tableauY[p],50);
}


void lanceDes (int y) {//fonction qui permet de lancer les dés et permet de revenir en arriere si les dés depasse les 63
    int des1= (int)random(6)+1;// création de dés avec un chiffre aléatoire de 1 à 6
    int des2 = (int)random(6)+1;//création de dés avec un chiffre aléatoire de 1 à 6

    //println(desF);//imprime le chiffre aléatoire
    //println(desS);//imprime le chiffre aléatoire

    int desJoueur= des1+des2;// création d'une variable qui additionne les 2 valeurs aleéatoire des dés
   

    if (Joueur[y]+desJoueur>63) {// création d'une condition pour éviter que la boucle se boucle à l'infini
      int reste=(Joueur[y]+desJoueur)-63;
      int retour = 63 -reste;
      Joueur[y] = retour;
    } else {
      Joueur[y] = Joueur[y]+desJoueur;
    }
    
    //if (Joueur== 9 || Joueur== 18 || Joueur== 27 || Joueur== 36 || Joueur== 45 || Joueur== 54){
      //Joueur = Joueur+ desJoueur;
    //}
   
    println(Joueur);//imprime ma boucle en respectant mes condition
    if (Joueur[y] ==63){
      fill(255);
      text("WIN!!!",80,80);
      println("Win");
      noLoop();
    }
 
  }



void terrain() {// création d'une fonction qui sert à creer en visuel un tableau de 63 cases
  background(152, 190, 100);//met de la couleur au fond
  int posX=0;//creation d'une variable pour représenter les rectangle
  for (int i=0; i<64; i++) {//creer une boucle de 63 qui va de 1 à1
    posX = posX+20;//permet d'utiliser une variable pour permettre à mes rectangle de pas etre coller les un sur les autre
    fill(255);
    rect(posX+150, 300, 20, 150);// coordonnées d'un rectangle que je boucle 63 fois
      plateauDeJeux[i]=posX+150;

  }
}

void setup() {
  size(1600, 800);//création de la fenetre d'affichage
 terrain();//appel ma fonction
 println(plateauDeJeux);
}




void draw(){
  terrain();
  for (int i=0; i<nbJoueur;i++){
   lanceDes(i);//appel ma fonction
  avancement(i);
  delay(500/nbJoueur);
  }
}
```