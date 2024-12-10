# Voila tes notes sur le modules Conception

### stacks techniques definition :

### LAMP :

Une pile LAMP est un ensemble de quatre technologies logicielles différentes que les développeurs utilisent pour créer des sites web et des applications web. LAMP est un acronyme du système d'exploitation Linux, du serveur web Apache, du serveur de base de données MySQL et du langage de programmation PHP.

### MEAN :

MEAN stack est une pile technologique full stack. Elle est utilisée par les programmeurs pour développer des applications Web ou encore des applications mobiles (hybrides et non natives).  Basée sur JavaScript, elle est open source et offre des outils et des plugins utiles. Elle réunit quatre des technologies les plus utilisées et appréciées pour le développement JavaScript :

- MongoDB
- Express
- AngularJS
- Node.js

 MEAN établit ainsi la base pour créer facilement des applications Web complexes.



### MERN 

La MERN stack est également une pile technologique utilisée par les développeurs full stack. Sa principale particularité c’est qu’elle permet de développer un site ou une application Web de A à Z (back-end et front-end). Ses composants sont comme suit :

 - MongoDB
- Express
- React
- Node.js

Le JavaScript côté client et le Node.js côté serveur.


## MongoDB ou PostgreSQL

### MongoDB et PostgreSQL sont des types de bases de données distincts qui possèdent des modèles de données distincts.

#### MongoDB

MongoDB est une base de données document qui stocke les données sous forme de paires clé-valeur dans des documents JSON. Chaque document peut contenir différents types de données, notamment des tableaux, des valeurs booléennes, des nombres, des chaînes et des documents imbriqués. Grâce à Binary JSON (BSON), MongoDB contient des types de données supplémentaires et traite les données de manière efficace. La flexibilité de stockage de données de MongoDB vous permet de stocker des données non structurées, évolutives et dynamiques.

MongoDB organise chaque document en collections, chacune ayant un ObjectId unique, que vous utilisez pour identifier un document. Le tableau suivant présente un exemple de données client dans MongoDB.

clients :[

{

  customer_id: "1",

  nom : “John Doe”,

  pays : "États-Unis"

},

{

  customer_id: "2",

  âge : “35”

  email: "jane_doe@example.com"

}]

#### PostgreSQL

En revanche, PostgreSQL est un système de gestion de base de données relationnelle objet (ORDBMS) qui combine des fonctionnalités orientées objet avec des fonctionnalités de base de données relationnelle. Dans un tableau, chaque ligne représente des points de données individuels et chaque colonne définit le type d'informations que vous y stockez. PostgreSQL prend en charge différents types de données, notamment les dates, le texte, les nombres entiers et les valeurs booléennes. 

Contrairement à MongoDB, PostgreSQL utilise un schéma prédéfini pour stocker les données. Un schéma garantit la cohérence et l'intégrité des données, car chaque colonne contient un type de données spécifique. Cependant, il est moins flexible. Le tableau suivant présente un exemple.

dbo.customers

customer_id

name

age

Amazon EC2

1

John Doe

24

john_doe@example.com

2

Jane Doe

35

jane_doe@example.com

![tableau comparaison mongoDB && PostreSQL](./image/Capture%20d’écran%20du%202024-12-09%2010-28-05.png)

