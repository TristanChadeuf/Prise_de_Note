# HTML/CSS Semaine 2
## Les balises utile HTML :

```HTML
La balise <title>

La balise <meta description>
Les balises titre <h1>, <h2>, <h3>, <h4>,<h5>, <h6>

La balise <strong> (mise en gras d'une partie de texte)

La balise <p> (paragraphe)

La balise <br> (saut de ligne)

La balise <ul> et <li> (liste à puces)

La balise <ol> et <li> (liste ordonnée)

La balise <a href> (la balise pour créer un lien hypertexte)
```
## Création de CV en HTML/CSS

* Penser à l'endatation
* Penser à ecrire des notes pour se retrouver


### Partie HTML
```HTML
<!DOCTYPE html>
<html lang="fr">
    
<head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="preconnect" href="https://fonts.googleapis.com">
        <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
        <link
            href="https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap"
            rel="stylesheet">
        <title>CV Tristan Chadeuf</title>
        <link rel="stylesheet" href="../css/style.css">
        <style>
            a {
                color: white
            }
        </style>
</head>

<body>
    <header class="Wrapper">
        <nav class="navBarT">
            <ul class="menuListeT">
                <li><a href="#idcarriere">Carriere</a></li>
                <li><a href="#idscolaire">Parcours Scolaire</a></li>
                <li><a href="#idcentreinteret"> Centre d'interet</a></li>
                <li><a href="#idcompetences">Competences</a></li>
                <li><a href="./hobby.html">hobby</a></li>
                <li><a href="./contact.html">Contact</a></li>
            </ul>
        </nav>
        <div id="hautT" class="header-T">
            <img id="photoProfilT" src="../photo/photodeprofile.jpg" alt="Photo de Profile Tristan Chadeuf">
            <div class="infoT">
                <h1>CV Tristan Chadeuf</h1>
                <div class="space-arround">
                    <img class="icone" src="../photo/geo-alt.svg" alt="Icones géocalisation">
                    <p>20 chemin des Pierriers</p>
                </div>
                <div class="space-arround">
                    <img class="icone" src="../photo/envelope.svg" alt="Icones envelope">
                    <p>Tristan.chadeuf@gmail.com</p>
                </div>
            </div>
        </div>

    </header>
    <main>
        <section class="resume">
            <h2>RÉSUMÉ</h2>
            <a id="fleche"href="#hautT"><img src="../photo/arrow-bar-up.svg" alt="fleche pour scroll horizontal" style="width:3em;"></a>
            <p>Ma vie professionnel a commencé en étant Commercial itinérant en alternance,<br>
                puis je souhaitez approfondir mes connaissances en poursuivant mes études<br>
                jusqu'à la licence de Community manager toujours en alternance.</p>
        </section>


        <div id="idcarriere" class="bloccarriere">
            <div>
                <div class="carriere">
                    <h2>CARRIÈRE</h2>
                    <div class="commercialItinerant">
                        <h3>COMMERCIAL ITINÉRANT</h3>
                        <P>2019-2021 <br>PATISAVEURS</P>
                        <div class="commercialItinerantListe">
                            <ul>
                                <li>Prise de commande</li>
                                <li>Prospection sur un secteur définit</li>
                                <li>Soutien à l'équipe commercial</li>
                                <li>Fidélisation de la clientèle</li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="carriere">
                    <h3>COMMUNITY MANAGER</h3>
                    <P>2021-2022 <br>PATISAVEURS</P>
                    <div class="communityManagerliste">
                        <ul>
                            <li>Création du site internet</li>
                            <li>Création de réseaux sociaux</li>
                            <li>Mise en place d'action de communication</li>
                        </ul>
                    </div>
                </div>
                <div class="saisonnier">
                    <h3>SAISONNIER STATION DE SKI</h3>
                    <P>2022-2024 <br>
                    <div class="saisonnierliste">
                        <ul>
                            <li>Vente de forfait</li>
                            <li>Agent des remontées mécaniques</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
        <div id=idscolaire class="parcoursScolaire">
            <div class="parcoursScolaireListe">
                <h3>PARCOURS SCOLAIRE</h3>
                <p>2016-2019 <br>BAC PRO VENTE</P>
                <p>2019-2021 <br>BTS NDRC</P>
                <p>2021-2022 <br>LICENCE COMMUNITY MANAGER</p>
            </div>
        </div>
        <div id="idcentreinteret" class="centreInteret">
            <h3>CENTRE D'INTÉRÊT</h3>
            <div class="centreInteretListe">
                <p>
                    PRATIQUE DU SKI<br>
                    LA MUSIQUE<br>
                    JEUX VIDÉOS<br>
                </p>
            </div>
        </div>
        <div id="idcompetences" class="competences">
            <h3>COMPÉTENCES</h3>
            <div class="competencestableau">
            <table>
                    <tr>
                        <td>WORD <br>EXCEL</td>
                        <td>CANVA <br>WORDPRESS</td>
                    </tr>

                    <tr>
                        <td>POWERPOINT</td>
                        <td>HTML/CSS</td>
                    </tr>
            </table>
            </div>
        </div>
    </main>
    <footer class="footer">
        <img src="../photo/telephone.svg"    alt="Icones de Telephone" style="width: 5em;">
        <p>06.08.36.16.18</p>
        <a href="https://www.linkedin.com/in/tristan-chadeuf-aa139b22b/"><img src="../photo/linkedin.svg"   alt="Logo linkedin"  style="width: 5em"></a>
    </footer>

</body>
</html>
```
### Partie CSS 
```CSS
* {
    margin: 0;
    padding: 0;
}

.competencestableau td {
    border: 1px solid black;
    padding: 15px;
}

table {
    border-collapse: collapse;
    margin: auto;
}

#photoProfilT {
    width: 300px;
    border-radius: 50px;
    margin: 120px 60px 70px 50px;
    box-shadow: 15px 15px #000000;
    padding: 10px 10px 10px 10px;
}
.icone {
    width: 60px
}

body {
    font-family: 'poppins', sans-sherif;
    margin: 0;
    width: 100%;
   

}

.header-T {
    display: flex;
    align-items: center;
    font-weight: 600;
    font-style: italic;
}

.infoT {
    margin-left: 150px;
}

.space-arround {
    display: flex;
    font-size: 2rem;
    margin: 30px 20px 30px 20px;
    align-content: center;
    padding: 10px 10px 10px 10px
}

h1 {
    font-size: 5rem;
    background-color: rgba(245, 245, 220, 0.382);
    border-radius: 20px;
    padding: 10px 20px 10px 20px;
    box-shadow: 15px 15px #000000;
    margin: 230px 200px 0px 200px;
    text-align: center;
}

.menuListeT {
    display: flex;
    justify-content: space-around;
    flex-direction: row;

}
.menuListeT li{
list-style-type: none;

}

.navBarT {
    width: 100%;
    font-size: 2rem;
    padding: 40px;
    margin: 0px 0px 0px 0px;
    background-color: #000000;
    color: white;
    position: fixed;


}

.resume {
    background-image: url(../photo/resume.jpg);
    background-size: cover;
    background-position: center;
    object-fit: cover;
    display: flex;
    font-size: 2rem;
    flex-direction: column;
    margin: 0px;
    padding: 300px;

}

.resume p {
    background-color: rgba(255, 255, 255, 0.461);
}

h2 {
    text-align: center;
    font-size: 5rem;
    background-color: rgba(245, 245, 220, 0.382);
    border-radius: 20px;
    padding: 10px 20px 10px 20px;
    box-shadow: 15px 15px #000000;
    margin: 0px 0px 60px 0px;

}

.bloccarriere {
    background-color: white;
    font-size: 2rem;
    padding: 100px;
}

.bloccarriere h3 {
    text-align: center;
    margin: 50px 50px 50px 50px;
}

.parcoursScolaire {
    background-image: url(../photo/school-work.jpg);
    background-size: cover;
    background-position: center;
    object-fit: cover;
    font-size: 3rem;
    margin: 0px;
    padding: 300px;

}

.parcoursScolaire h3 {
    text-align: center;
    color: white;
    background-color: rgba(0, 0, 0, 0.433);
}

.parcoursScolaireListe p {
    background-color: rgba(0, 0, 0, 0.402)
}

.centreInteret {
    font-size: 2rem;
    margin: 0px;
    padding: 400px;
    background-image: url(../photo/ski.jpg);
    background-size: cover;
    background-position: center;
    object-fit: cover;
}

.centreInteret h3 {
    text-align: center;
    background-color: rgba(255, 255, 255, 0.472);
}

.competences {
    background-image: url(../photo/competence.jpg);
    background-size: cover;
    background-position: center;
    object-fit: cover;
    font-size: 4rem;
    margin: 0px;
    padding: 200px;
}

.competences h3 {
    text-align: center;
}

.footer {
    display: flex;
    justify-content: space-around;
    margin: 20px 20px 20px 20px;
    padding: 30px;
    font-size: 2rem;

}

#fleche {
    position: fixed;
   bottom: 0;
    right: 90px;

}

.photocentre {
    height: 600px;
    width: 100%;
    background-image: no-repeat;
    object-fit: cover;

}

.parcoursScolaire {
    color: white;
}

.centreInteretListe  {
    background-color: rgba(255, 255, 255, 0.472);
}

table {
    background-color: white;
}

.competences h3 {
    background-color: white;
}
/* commencement Page hobbyT */
.menuHobbyTT {
    font-size: 2rem;
    padding: 40px;
    background-color: #000000;
    color: white;
    position: fixed;
    margin: 0;
    width: 100%;
    text-align: center
}

.hobbyT h2 {
    text-align: center;
    margin: 0px 0px 60px 0px;
    
}

.hobbyT p {
    text-align: center;
    font-size: 2rem;
    background-color: rgba(245, 245, 220, 0.567);
    border-radius: 0px 50px 0px 50px;
}

.mainhobbyTT {
    background-image: url(../photo/hobbies.jpg);
    background-size: cover;
    background-position: center;
    object-fit: cover;
    margin: 0px 0px 0px 0px;
    width: 100%;
    height: 1000px;
    padding-top: 200px;
}

.mainhobbyTT {
    display: flex;
    flex-direction: column;
    align-items: center;
}

a {
    color: white
}
/* commencement page contact */

.ficheContact {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-content: space-between;
    background-image: url(../photo/ski.jpg);
    background-image: no-repeat;
    background-size: cover;
    /* object-fit: cover; */
   }

.menuContact {
    font-size: 2rem;
    padding: 40px 0px 40px 0px;
    background-color: #000000;
    color: white;
    margin: 0;
    width: 100%;
    text-align: center
}
.mainContact h2{
 width: 50%;
 text-align: center;
 margin: 50px 0px 50px 0px;
}
.mainContact{
    display: flex;
    flex-direction: column;
    align-items: center;
}
form {
    width: 50%;
    display: flex;
    flex-direction: column;
    align-items: center;
    align-content: space-around;
    background-color: rgba(245, 245, 220, 0.382);
    border-radius: 0px 50px 0px 50px;
    font-size: 2rem;
    padding-left: 50px;
    
}
textarea{
    width: 100%;
    height: 6rem;
    font-size: 2rem;

}
.formdiv{
margin-bottom: 50px;
display: flex;
flex-direction: column;

}
.footerContact{
background-color: white;
width: 100%;
padding: 70px 0px 70px 0px;
margin: 130px 0px 0px 0px;
font-size: 2rem;
display: flex;
justify-content: space-around;
flex-direction: row;
align-items: center;
}

.texte{
    height: 60px;
    width: 700px;
    font-size: 2rem;
}
.select{
    height: 60px;
    width: 700px;
    font-size: 2rem;
}
button{
    height: 60px;
    width: 700px;
    background-color: rgb(245, 245, 220);
    font-size: 2rem;
    margin-top: 50px;
    margin-bottom: 50px;
    border-radius: 50px 50px 50px 50px;
    
}
iframe{
    border: none;
}


@media only screen and (max-width: 700px){
    
        .navBarT{
            display: none;
        
        }
    .header-T{
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 100%;
    }
    .infoT{
    margin-left: 0px;

    }
    #fleche {
        position: fixed;
        right: 90px;
        display: none;

    }


    body{
        width: 100%;
    }
    #photoProfilT{
        display: none;
    }
    .bloccarriere {
        background-color: white;
        font-size: 2rem;
        padding: 0px;
    }
    .resume {
        display: flex;
        font-size: 2rem;
        flex-direction: column;
        margin: 5px;
        padding: 5px;

    }
    h2 {
        font-size: 2rem;
    margin: 8px;
    box-shadow: 5px 5px;
    
    }
    .space-arround {
        
        font-size: 1rem;
        display:flex;
        flex-direction: column;
        align-items: center;
        padding: 10px 0px 10px 0px
    }
    .parcoursScolaire {
        background-image: url(../photo/school-work.jpg);
        background-size: cover;
        background-position: center;
        object-fit: cover;
        font-size: 2rem;
        margin: 0px;
        padding: 10px;
    
    }
    .centreInteret {
        font-size: 2rem;
        margin: 0px;
        padding: 10px;
        
    }
    .competences {
        background-image: url(../photo/competence.jpg);
        background-size: cover;
        background-position: center;
        object-fit: cover;
        font-size: 2rem;
        margin: 0px;
        padding: 10px;
    }
    .footer {
        display: flex;
        justify-content: space-around;
        margin: 0px;
        padding: 5px;
        font-size: 2rem;
    
    }
    img{
        width: 2em;
    }


}

@media only screen and (max-width: 1800px){
.menuListeT{
    font-size: 1rem;
}

#photoProfilT{
    display: none;
}

.header-T{
    display: flex;
    flex-direction: column;
    align-items: right;
    width: 100%;
}
h1 {
    font-size: 5rem;
    background-color: rgba(245, 245, 220, 0.382);
    border-radius: 20px;
    padding: 10px 5px 0px px;
    box-shadow: 15px 15px #000000;
    
    text-align: center;
}
h2 {
    font-size: 2rem;
margin: 8px;
box-shadow: 5px 5px;

}
.space-arround {
    
    display:flex;
    flex-direction: column;
    align-items: center;
    padding: 10px 0px 10px 0px
}
.parcoursScolaire {
    background-image: url(/photo/school-work.jpg);
    background-size: cover;
    background-position: center;
    object-fit: cover;
    font-size: 2rem;
    margin: 0px;
    padding: 10px;

}
.centreInteret {
    font-size: 2rem;
    margin: 0px;
    padding: 10px;
    
}
.competences {
    background-image: url(/photo/competence.jpg);
    background-size: cover;
    background-position: center;
    object-fit: cover;
    font-size: 2rem;
    margin: 0px;
    padding: 10px;
}

}
@media only screen and (max-width: 1150px){
    .navBarT{
        display: none;
    
    }
    .hobbyT p{
        font-size: 1rem;
    }
    .menuHobbyTT a{
        font-size: 1rem;
    }

    .header-T{
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 100%;
    }
    #photoProfilT {
        width: 250px;
        border-radius: 50px;
        margin: 0px 0px 20px 0px;
        box-shadow: 15px 15px #000000;
        padding: 0px 0px 0px 0px;
    }
    .menuContact a{
        font-size: 1rem;
    }
    .texte{
        height: 30px;
        width: 350px;
        font-size: 1rem;
    }
    .select{
        height: 30px;
        width: 350px;
        font-size: 1rem;
    }
    button{
        height: 30px;
        width: 350px;
        background-color: rgb(245, 245, 220);
        font-size: 1rem;
        margin-top: 50px;
        margin-bottom: 50px;
        border-radius: 50px 50px 50px 50px;
        
    }
    .footerContact{
        display: none;
    }
   
    
}
```