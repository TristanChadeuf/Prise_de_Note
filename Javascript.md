# Salut connard c'est tes notes sur Javascript



```javascript
console.log("exo-6");

var joeInfo = {
    name: "Joe's house",
    rooms: 5,
    garage: false,
    bathrooms: 1 + 2,
    cars: ['Clio', 'Van'],
};

console.log(joeInfo.cars.length);
console.log(joeInfo.bathrooms-2);
console.log(joeInfo.garage=true);


let team ={
players:[{
    firstName: "Pablo",
    lastName: "Sanchez",
    age: 11
}],

games:[{

    opponent: "Broncos",
    teamPoints: 42,
    opponentPoints: 27,
    

}],



addPlayer(prenom,nom,annee){

    team.players.push( { 
        firstName:prenom,
        lastName: nom,
        age:annee,
    
    } )
},




addGames(opposant,pointsEquipe,pointsEnnemi){
    
    team.games.push( {
    opponent:opposant,
    teamPoints: pointsEquipe,
    opponentPoints: pointsEnnemi,       
    } )

},

}


team.addPlayer('didier','michel',14);
team.addPlayer('Tristan','patrick',15);
team.addGames('Tiny',45,28);
team.addGames('Platiste',48,26);

//console.log(team.players);
//console.log(team.games);

let sumTeam = 0;
for (let game of team.games){
    sumTeam = sumTeam + game.teamPoints
}
console.log(sumTeam);


let sumOpponent=0;
for (let game of team.games){
    sumOpponent  = sumOpponent + game.opponentPoints
 
}
console.log(sumOpponent);


let total=0;
total=sumOpponent/team.games.length
console.log(total);


function oldGuy(){
let vieux=0;
        
    for (let ageMax of team.players){
            
         if (ageMax.age > vieux){
             vieux = ageMax.age
         }
        
      
     
    }
    console.log(vieux);

};
oldGuy();
```
## Petite révision des variables

```javascript
//1.1 Types simples

const name = 'Jacques';
let age = 80;
let useless = 'something';

console.log(name, age, useless);

age += 1;
useless = 14;

console.log(name, age, useless);

//----------------------//
//1.2 Tableaux

const fruits = ['apple', 'pear', 'cherry'];
const vegetables = ['potato', 'curlyflower', 'tomato'];

console.log(fruits, vegetables);

fruits.push('banana');
vegetables.pop();

console.log(fruits, vegetables);

//----------------------//
//1.3 Objets

const settings = {
    sound: true,
    music: false,
    graphics: 'high',
    resolution: [1920, 1080]
};

let savedGame = {
    time: 384,
    score: 47,
    opponent: 'Lolo'
};

console.log(settings, savedGame);

savedGame = {};
settings.music = true;
settings.resolution = [3840, 2160];

console.log(settings, savedGame);
```
## Revision pour les fonctions
```javascript 
//2.1 Fonctions simples
const sayHello = () => console.log('Hello');

const sayMyName = (first, last) => console.log(first, last);

const sayMyAge = (age) => console.log('You are ' + age + ' years old');

sayHello();
sayMyName('Odile', 'Crok');
sayMyAge(23);

//----------------------//
//2.2 this

const object = { // creation d'une variable constante de type objet
    color: 'red', // color = red
    shape: 'circle', // shape = circle
    threeDimensions: false, // threeDimensions = faux
    showThis: () => // showThis vaut une fonction qui console.log
        console.log(this)
}; 

object.showThis();

//----------------------//
//2.3 Application

const odile = {
    sayHello : () => console.log('Hello'),
    sayMyName: () =>  console.log({
        first: 'Odile',
        last: 'Crok'
    }),
    sayMyAge: ()=> console.log(23),
   
};

odile.sayHello()
odile.sayMyName()
odile.sayMyAge()
```
## Exercice en rapport avec le destructuring
```Javascript 
//4.1 Découverte

const [a, b, c,] = [1, 2, 3, 4];// Creation d'une variable qui est un tableau
console.log(a);
console.log(b);
console.log(c);

const {first, last, age} = {first: 'Paul', last: 'Henta', age: 35};
console.log(first);
console.log(last);
console.log(age);
//4.2 Application

const perturbations = Object.values(data);

for (const perturbation of perturbations) {
    const {texte: text, dateDebut: startDate, dateFin: endDate} = perturbation;
    console.log(startDate + ' - ' + endDate + ' : ' + text);
}

//4.3

function addPerturbation(key, {longitude, latitude, text: texte, startDate: dateDebut, endDate: dateFin,
    type = 'default', heureDebut = '00:00', heureFin = '12:00'} = {}) {
    data[key] = {longitude, latitude, texte, dateDebut, dateFin, type, heureDebut, heureFin};
}
addPerturbation('1234',
    {
        longitude: 23.34,
        latitude: 23.45,
        text: "123",
        startDate: "2021-01-02",
        endDate: "2023-01-02"
    });

console.log(data);



function testRest(){
const [a, b, ...rest] = [10, 20, 30, 40, 50];
console.log(rest);
};
testRest();
```
## Exercice sur les import/export
```Javascript
//5-1 Import

import {hello, showError} from './functions.js';
import anonyme from './functions.js';
import {sum, sub, multiply, divide, pow} from './math.js';
showError();
anonyme();
sum();
sub();
multiply();
divide();
pow();

hello();

// 5-2 Export
const [a, b] = [7, 9];

export const sum = (a, b) => a + b;
export const sub = (a, b) => a - b;
export const multiply = (a, b) => a * b;
export const divide = (a, b) => a / b;
export const pow = (a, b) => a ** b;

export const hello = () => console.log('hello');
export const showError = message => console.error(message);



/// C'est celle là, la fonction anonyme ///
export default () => {
    var _nyan = 0;
var __nyan = [[
"+      o     +              o      ",
"    +             o     +       +  ",
"o          +                       ",
"    o  +           +        +      ",
"+        o     o       +        o  ",
"-_-_-_-_-_-_-_,------,      o      ",
"_-_-_-_-_-_-_-|   /\\_/\\            ",
"-_-_-_-_-_-_-~|__( ^ .^)  +     +  ",
"_-_-_-_-_-_-_-\"\"  \"\"               ",
"+      o         o   +       o     ",
"    +         +                    ",
"o        o         o      o     +  ",
"    o           +                  ",
"+      +     o        o      +     "],
[
"+      o     +              +      ",
"    o             o     o       +  ",
"o          +                       ",
"    +  o           +        o      ",
"o        o     o       +        o  ",
"_-_-_-_-_-_-_-,------,      +      ",
"-_-_-_-_-_-_-_|   /\\_/\\            ",
"_-_-_-_-_-_-_-|__( ^ .^)  o     +  ",
"-_-_-_-_-_-_-_ \"\"  \"\"              ",
"+      +         o   +       o     ",
"    o         +                    ",
"+        +         +      +     o  ",
"    +           o                  ",
"+      o     o        o      +     "
]];

function nyan(){
    console.clear();
    console.log(__nyan[_nyan].join("\n"));
    if(_nyan === 0){ _nyan = 1; } else { _nyan = 0; }
};

window.setInterval(nyan, 300);
}
```
## Exercices sur les promesses

```Javascript
async function recuperationApi() {// creation d'une fonction asynchrone
  const recuperationTouteApi = await fetch("https://swapi.dev/api/")//creation d'une variable fetch pour recuperer une Api en ligne
  const recuperationTouteApiJson = await recuperationTouteApi.json();// transformation de API en Json
  console.log(recuperationTouteApiJson);// Pour afficher la variable recup dans la console
};
recuperationApi();

async function recuperationSpecies(id) {//creation  d'une fonction avec une variable en parametre 
  const recuperationEspeces = await fetch("https://swapi.dev/api/species/" + id)//creation d'une variable fetch pour recuperer les espece de l'api plus une ID en parametre
  const recuperationEspecesJson = await recuperationEspeces.json();// transformation de API en Json
  console.log(recuperationEspecesJson);// Pour afficher la variable recup dans la console
  return recuperationEspecesJson// Pour que la fonction valent recupP
};


async function recuperationHuman(recuperationEspecesJson)//Creation d'une fonction avec en parametre la variable recuperai dans la promesse
{
  const recuperationHuman = recuperationEspecesJson.people.map((url) => {//Transformation du tableau de string recuperationEspecesJson.people en promesses
    return fetch(url)//Return du tableau url en fetch
  });


  async function promiseExecution(){

    let promise = await Promise.all(recuperationHuman)
    return promise
  };
   const promise = await promiseExecution();
  console.log(promise);
   


  Promise.all(recuperationHuman)
    .then(async (people) => {
      const peopleJson = people.map(async (urlJson) => {
         return urlJson.json();
      });
      Promise.all(peopleJson)
        .then(async (peopleName) => {
          console.log(peopleName)
        }
        );

    });
};

recuperationSpecies(1)
  .then((recuperationEspecesJson) => recuperationHuman(recuperationEspecesJson))
  ```
