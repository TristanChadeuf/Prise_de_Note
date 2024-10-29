# Salut voila tes notes sur les tests

## Selon-vous, qu’est-ce un test ?

Les tests logiciels sont le processus d'évaluation et de vérification qu'un produit ou une application logicielle fait ce qu'il est censé faire . Les avantages de tests de qualité incluent la prévention des bugs et l'amélioration des performances.

## À quoi servent les tests ?

Son objectif principal est d'identifier un nombre maximal de comportements problématiques du logiciel. Il permet ainsi, dès lors que les problèmes identifiés seront corrigés, d'en augmenter la qualité. Une programmeuse écrivant du code Java avec JUnit.

## Y a-t-il plusieurs types de tests ? Si oui, quelle est leur différence ?

## 1. Tests unitaires
Les tests unitaires sont de très bas niveau, près de la source de votre application. Ils consistent à tester les méthodes et fonctions individuelles des classes, des composants ou des modules utilisés par votre logiciel. Les tests unitaires sont en général assez bon marché à automatiser et peuvent être exécutés très rapidement par un serveur d'intégration continue.

## 2. Tests d'intégration
Les tests d'intégration vérifient que les différents modules ou services utilisés par votre application fonctionnent bien ensemble. Par exemple, ils peuvent tester l'interaction avec la base de données ou s'assurer que les microservices fonctionnent ensemble comme prévu. Ces types de tests sont plus coûteux à exécuter, car ils nécessitent que plusieurs parties de l'application soient fonctionnelles.

## 3. Tests fonctionnels
Les tests fonctionnels se concentrent sur les exigences métier d'une application. Ils vérifient uniquement 
la sortie d'une action et non les états intermédiaires du système lors de l'exécution de cette action.

Il y a parfois une certaine confusion entre les tests d'intégration et les tests fonctionnels, car ils nécessitent tous les deux plusieurs composants pour interagir. La différence réside dans le fait qu'un test d'intégration peut simplement vérifier que vous pouvez interroger la base de données, tandis qu'un test fonctionnel s'attend à obtenir une valeur spécifique de la base de données, telle que définie par les exigences du produit.

## 4. Tests de bout en bout
Les tests de bout en bout reproduisent le comportement d'un utilisateur avec le logiciel dans un environnement applicatif complet. Ils vérifient que les différents flux d'utilisateurs fonctionnent comme prévu et peuvent être aussi simples que le chargement d'une page Web ou la connexion. Des scénarios beaucoup plus complexes peuvent aussi vérifier les notifications par e-mail, les paiements en ligne, etc.

Les tests de bout en bout sont très utiles, mais ils sont coûteux à réaliser et peuvent être difficiles à gérer lorsqu'ils sont automatisés. Il est recommandé d'avoir quelques tests clés de bout en bout et de s'appuyer davantage sur des tests de niveau inférieur (tests unitaires et d'intégration) pour être en mesure d'identifier rapidement les changements de dernière minute.

## 5. Tests d'acceptation
Les tests d'acceptation sont des tests formels exécutés pour vérifier si un système répond à ses exigences métier. Ils nécessitent que l'application soit entièrement opérationnelle et se concentrent sur la simulation du comportement des utilisateurs. Ils peuvent aussi aller plus loin, et mesurer la performance du système et rejeter les changements si certains objectifs ne sont pas atteints.

## 6. Tests de performance
Les tests de performance évaluent les performances d'un système sous une charge de travail spécifique. Ces tests permettent de mesurer la fiabilité, la vitesse, l'évolutivité et la réactivité d'une application. Par exemple, un test de performance peut observer les temps de réponse lors de l'exécution d'un nombre important de demandes ou déterminer le comportement du système face à une quantité élevée de données. Il peut déterminer si une application répond aux exigences de performances, localiser les goulots d'étranglement, mesurer la stabilité pendant les pics de trafic, et plus encore.

## 7. Smoke tests
Les smoke tests sont des tests simples qui vérifient le fonctionnement de base d'une application. Ils sont conçus pour être rapides à exécuter, et leur but est de vous donner l'assurance que les caractéristiques principales de votre système fonctionnent comme prévu.

Les « smoke tests » peuvent être utiles juste après la création d'un build afin de décider si vous pouvez exécuter des tests plus coûteux. Ils peuvent également être utiles après un déploiement afin de vous assurer que l'application s'exécute correctement dans l'environnement nouvellement déployé.

## Définir ce qu’est le TDD et quels sont les avantages de cette pratique.

Le test-driven development désigne une méthodologie de développement logiciel piloté par les tests. 
Cette technique est utilisée par les équipes agiles, elle est itérative et incrémentale. 
Le TDD pousse les développeurs à corriger les bugs en temps réel, au fur et à mesure de la programmation.

## Cahier de test

- Nom du test : Le titre qui décrit la fonctionnalité à tester.
- ID du test : Généralement un identifiant numérique ou alphanumérique que les testeurs utilisent pour regrouper les cas de test en suites de test.
- Objectif : Également appelé description, ce composant décrit ce que le test doit valider.
- Références : Liens vers vos « user stories » et les spécifications de conception ou les exigences que le test doit vérifier.
- Conditions préalables : Toutes les conditions nécessaires pour que le testeur puisse effectuer le test.
- Configurations : Ce composant identifie ce dont le scénario de test a besoin pour fonctionner correctement, comme la version de l'application, le système d'exploitation, les exigences en matière de date et d'heure et les spécifications de sécurité.
- Étapes de test : Des descriptions détaillées des actions séquentielles qui doivent être effectuées pour terminer le test.
- Résultat attendu : Une explication de la manière dont la fonctionnalité ou le système doit réagir.

## test 1 = 

- Nom = DislayedWord
- id = 1
- Objectif = Teste le bon affichage du mot à deviner en fonction des lettres trouvées


## test 2 = 
- Nom = Attemps
- id = 2
- Objectif = Teste le nombre d'essai

## test 3 =

- Nom = CompteurError
- id = 3
- Objectif = Teste si le compteur d'erreur marche

## test 4 = 

- Nom = AfficheMot
- id = 4 
- Objectif = Teste si un mot est bien afficher

## test 5 = 

- Nom = CheckWin
- id = 5
- Objectif = Tester si le message s'affiche si la personne gagne

## test 6 = 

- Nom = CheckLose
- id = 6
- Objectif = Tester si le message s'affiche si la personne perd


