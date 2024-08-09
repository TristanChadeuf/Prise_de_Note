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