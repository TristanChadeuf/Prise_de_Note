# Salut Tristan voila tes notes sur Spring boot

## Pour le contexte Spring boot est un framework de java avec le design patter MVC


## Code de création de classes User(Model)
```java
package com.ecommerce.microcommerce.model;

import jakarta.persistence.*;

//@JsonFilter("monFiltreDynamique")
@Entity
public class User {
    @Id
    @GeneratedValue(strategy= GenerationType.AUTO)

    @Column(nullable = false)
    private Long id;

    @Column(nullable = false)
    private String prenom;

    @Column(nullable = false)
    private String nom;

    @Column(nullable = false)
    private int dateNaissance;

    @Column(nullable = false)
    private int numeroPermis;

    //CONSTRUCTOR*******************************************************************************************************

    public User(Long id, String nom, String prenom, int dateNaissance, int numeroPermis) {

        this.id = id;

        this.nom = nom;

        this.prenom = prenom;

        this.dateNaissance = dateNaissance;

        this.numeroPermis = numeroPermis;

    }

    public User() {

    }

    //GETTER SETTER*****************************************************************************************************

    public long getId() {
        return this.id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getNom() {
        return nom;
    }

    public void setNom(String nom) {
        this.nom = nom;
    }

    public String getPrenom() {
        return prenom;
    }

    public void setPrenom(String prenom) {
        this.prenom = prenom;
    }

    public int getDateNaissance() {
        return dateNaissance;
    }

    public void setDateNaissance(int dateNaissance) {
        this.dateNaissance = dateNaissance;
    }
    public int getNumeroPermis() {
        return numeroPermis;
    }

    public void setNumeroPermis(int numeroPermis) {
        this.numeroPermis = numeroPermis;
    }

}
```


## Creation de la classes User Controller(Controller)
```java
package com.ecommerce.microcommerce.web.controlleur;

import com.ecommerce.microcommerce.dao.UserDao;
import com.ecommerce.microcommerce.model.User;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.*;

import java.util.List;


@RestController
public class UsersController {



   //CONSTRUCTOR*******************************************************************************************************
    private final UserDao userDao;
    @Autowired

    public UsersController(UserDao userDao) {
        this.userDao = userDao;

    }

    //ROUTE ALL USERS***************************************************************************************************
    @GetMapping("/user")
    public List<User> AllUsers() {
        return userDao.findAll();
    }

    //ROUTE USERS ID****************************************************************************************************

    @GetMapping(value = "/user/{id}")
    public User afficherUnProduit(@PathVariable Long id) {
        return userDao.findById(id).orElse(null);
    }

    //ROUTE CREATE USER*************************************************************************************************
    @PostMapping(value="/user")
    public User ajouterUnClient(@RequestBody User user) {

        return userDao.save(user);

    }
//ROUTE UPDATE USER***********************************************************
    @PutMapping(value = "/user/{id}")
   public User modifierUnClient(@PathVariable Long id , @RequestBody User user) {
        user.setId(id);
        return userDao.save(user);
    }

//ROUTE DELETE USER*************************************************************
    @DeleteMapping(value = "/user/{id}")
    public void supprimerUnClient(@PathVariable Long id) {
         userDao.deleteById(id);
    }

}
```
## Les micro-Services

- Qu’est ce qu’un micro service et comment est composé un micro service : 

Dans une architecture de microservices, chaque microservice est un service unique conçu pour accueillir une fonctionnalité d'application et gérer des tâches discrètes. Chaque microservice communique avec d'autres services via des interfaces simples afin de répondre à des problématiques métier.

- Pourquoi met on en place des micro services : 

Les microservices permettent aux développeurs, notamment ceux du secteur de la santé, de créer des applications qui sont constituées de services faiblement couplés, ce qui facilite les étapes de développement, de test, de déploiement et de mise à niveau.

- Quels sont les bienfaits d’une telle architecture : 

Les microservices stimulent vos équipes et vos routines grâce à un développement distribué. Vous pouvez aussi développer plusieurs microservices simultanément. Ainsi, davantage de développeurs peuvent travailler en même temps, sur la même application, ce qui réduit la durée du développement.

- Quels en sont les inconvénients : 

Cette flexibilité qui va de pair avec les microservices peut entraîner une précipitation dans le déploiement de changements, ce qui implique de créer de nouveaux modèles. En ingénierie logicielle, un modèle se réfère à toute solution algorithmique qui a fait ses preuves. Un anti-modèle se rapporte aux erreurs communément commises dans le cadre de la résolution d'un problème et qui engendrent plus de problèmes sur le long terme.

Outre la culture et les processus, la complexité et l'efficacité sont les deux défis majeurs liés aux architectures de microservices. Lorsque vous travaillez avec une architecture de microservices, faites attention à ces anti-modèles courants.






