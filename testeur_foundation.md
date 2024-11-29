# Tester - Foundation (ISTBQ)

[README.md](README.md)

## Fondamentaux des tests

### Analyse des causes racines

Effet ---> Défaillance ---> Défaut ---> Erreur ---> Cause racine

### Les 7 principes sur les tests 

1. Le test montre la présence des défauts, pas leur absence
2. Les tests exhaustifs sont impossibles
3. Tester tôt économise du temps et de l’argent
4. Regroupement des défauts
5. Paradoxe du pesticide
6. Les tests dépendent du contexte
7. L’absence d’erreurs est une illusion

### Le processus de test

- Planification des tests
- Suivi et contrôle des tests
- Analyse de test
- Conception des tests
- Implémentation des tests
- Exécution des tests
- Clôture des tests

### Glosaire

- **Base de test** : L'ensemble des connaissances utilisées comme base pour l'analyse et la conception des tests

- **Condition de test** : Un aspect des bases de test qui est pertinent pour atteindre des objectifs de test spécifiques 

- **Testware** : Produits d’activités réalisés au cours du processus de test pour la planification, la conception, l'exécution, l'évaluation et l'établissement de rapports sur les tests 

- **Validation** : Confirmation par l’examen et la fourniture de preuves objectives que les exigences, pour un usage ou une application voulue, ont été satisfaites (par rapport a un besoin)

- **Verification** : Confirmation par l’examen et la fourniture de preuves objectives que des exigences spécifiées ont été satisfaites (par rapport à une spécification)

## Tester pendant le cycle de vie du développement logiciel

### Modèles de cycle de développement

- **Séquentiel** : flux séquentiel d’activités (Cascade, Cycle en V)
- **Itératif et incrémental** : réalisation par morceaux (RUP, Scrum, Kanban, Spyral)

### Niveau de test
   - **Test Unitaire** (test de composant) : teste un composant unitairement
   - **Test d'Intégration** : teste les interfaces entre composants ou systèmes
   - **Test Système** : teste le système dans son intégralité
   - **Test d'acceptation** : teste le système dans son intégralité
     -  UAT - User Acceptance Testing
     -  OAT - Operational Acceptance Testing
     -  Tests d'acceptation contractuelle et réglementaire
     -  Tests alpha (interne) et bêta (externe)

### Types de test

- Fonctionnels (boite noire) : testent l’adéquation fonctionnelle du logiciel
- Non fonctionnels : testent des caractéristiques non fonctionnelles du système
- Structurels (boite blanche): testent le fonctionnement interne du logiciel
- Tests liés au changement
  - TEST DE CONFIRMATION (RE-TEST)
  - TEST DE (NON) REGRESSION
  
*Tous les types peuvent s’appliquer à chaque niveau*

### Test de maintenance

Facteurs déclencheurs : 
- Changements dans le système 
- Changements dans l’environnement
- Déclassement / fin de vie

*Analyse d’impact pour la maintenance*

### Tests statiques

***Le code n’est pas exécuté, à différence des tests dynamiques. On cherche des défauts, pas des défaillances***

**Test dynamique** : Exécution du logiciel. Provoquer des défaillances

**Test statique** : Trouver des défauts

- Revues : pour tous documents (manuel)
- Analyse statique : pour le code ou tous documents ayant une structure formelle (outillage possible)


### Les revues

#### Processus

1. Planification
2. Lancement
3. Revue individuelle (préparation individuelle)
4. Communication et analyse des problèmes
5. Correction et production de rapports

#### Rôles

- **Manager** : Est responsable de la planification des revues. Alloue les ressources et vérifie le retour sur investissement
- **Responsable de la revue** : Organise la revue en pratique (qui, quand…)
- **Auteur** : Crée le produit d’activité revu, Corrige les défauts
- **Réviseurs** : Experts représentants différentes perspectives. Identifient des défauts
- **Facilitateur (modérateur)** : Assure le bon déroulement et la médiation entre participants. Joue un rôle important dans le succès de la revue
- **Scribe (rapporteur)** : Recueille et enregistre les défauts

#### Types de revue

- **Informelle** : Pas de réel processus
- **Relecture technique** : Dirigée par l’auteur, scribe
- **Revue technique (par les pairs)** : Pairs techniques de l'auteur et des experts techniques
- **Inspection** : Checklist

#### Techniques de revue

- **Ad hoc** : Sans directives particulières
- **Basée sur les checklists** : Les réviseurs s’appuient sur une checklist
- **Scénarios et essais à blanc** : Utilisation d’un guide de relecture basé sur un scénario d’utilisation du produit final
- **Basée sur les rôles** : Evaluation selon différents rôles de l’organisation ou associée à des types d’utilisateur
- **Basée sur la perspective** : 
  - Les réviseurs adoptent différents points de vue
  - Avec Checklists
  - En essayant de « faire » des choses avec le document (par ex. concevoir des tests)

## Techniques de test

- **Techniques Boîte blanche ou Test structurel** : Procédure documentée utilisée pour dériver et sélectionner des cas de tests basée sur une analyse de la structure interne d’un composant ou système
  
  - Test et couverture des instructions
  - Test et couverture des décisions

- **Boîte noire** : Procédure documentée pour élaborer et sélectionner des cas de tests basée sur une analyse des spécifications fonctionnelles ou non-fonctionnelles d’un composant ou système sans faire référence à sa structure interne

  - Partitions d’équivalence
  - Analyse des valeurs limites
  - Test de tables de décision
  - Test des transitions d’états
  - Test des cas d’utilisation
  
- **Techniques basées sur l’expérience** : Procédure pour obtenir et/ou sélectionner des cas de test basée sur l'expérience du testeur, sa connaissance et son intuition

  - Estimation d’erreur
  - Tests exploratoires
  - Tests basés sur les checklists

*La couverture des décisions est plus forte de la couverture des instructions, 100% de couverture des décisions assure 100% de couverture des instructions, l’inverse n’est pas vrai*

## Gestion des tests

### L’organisation des tests

- **Independance du test** (plusieurs niveaux d’independance possibles)

- Les deux **rôles** dans le test :
   - **TESTEUR** : analyse, conception, implementation, execution des tests
   - **TEST MANAGER** : planification et pilotage

- **Plan de test**

  1. Identifiant
  2. Introduction
  3. Eléments à tester
  4. Caractéristiques à tester
  5. Caractéristiques à ne pas tester
  6. Approche
  7. Critères de passage ou échec
  8. Critères de suspension et
  conditions de reprise
  1. Livrables du test
  2.  Tâches de test
  3.  Besoins en environnements
  4.  Responsabilités
  5.  Ressources et besoins en
  formation
  1.  Planning
  2.  Risques et contingences
  3.  Approbations

- **Planification** : POLITIQUE de test (niveau entreprise) -> **STRATEGIE de test** (niveau entreprise) -> PLAN de test maître (niveau projet) -> PLAN de test de niveau(niveau projet)

### Stratégies de test 

- **Analytique**: Analyse des exigences, Analyse des risques
- **Basée sur des modèles**: Tests conçus à partir d’un modèle
- **Méthodique**: Utilisation d’un ensemble prédéfini de tests ou conditions de test (ex: taxonomie de défauts)
- **Conforme à un processus ou une norme**: Basée sur des règles et normes externe (ex: DO 178B)
- **Dirigée (ou consultative)**: Dictée par les parties prenantes
- **Anti-régressions**: Eviter les régressions (avec des tests automatisés)
- **Réactive**: Adaptée pendant l’exécution des tests

### DoR, DoD

- Critères d’entrée = disponibilité de ...
- Critères de sortie 

### Techniques d'estimation des tests

*Quelle quantité de test prévoir?*

- **Technique basée sur les métriques** : estimer l'effort de test sur la base de métriques d'anciens projets similaires ou sur la base de valeurs représentatives
- **Technique basée sur l’expertise** : estimation de l'effort de test sur la base de l'expérience des responsables des tâches de test ou par des experts

### Pilotage et contrôle des tests

*Réalisés par le Test Manager*

- **Pilotage** : 
  - recueillir des informations et fournir un retour et de la visibilité sur les activités de test 
  - évaluer l'avancement du test
  - mesurer si les critères de sortie du test sont satisfaits

- **Contrôle** : 
  - Prise de mesures correctives
  - Ex: reprioriser les tests, modifier le calendrier d’exécution des tests

*Afin de pouvoir piloter correctement un projet de test, il est indispensable d’identifier les bonnes métriques qui permettent de mesurer les informations retenues importantes*

- **Rapport d’avancement (suivi de l’avancement du projet)**
  - statut des activités de test et avancement par rapport au plan de test
   -facteurs qui freinent l'avancement
   - tests prévus pour la prochaine période
de suivi
   - qualité de l'objet de test

- **Rapport de synthèse (récapitulatif)**
  - récapitulatif des tests réalisés
  - Informations sur le déroulement de la période de test
  - écarts par rapport au plan
  - statut des tests et de la qualité du produit par rapport aux critères de sortie ou à la définition du terminé 
  - facteurs ayant bloqué ou bloquant l’avancement
  - métriques sur les défauts, les cas de test, la couverture de test, l’avancement de l'activité et la consommation de ressources
  - risques résiduels
  - produits d'activités de test réutilisables


### Métriques utilisées pour les tests

- Pourcentage du temps de travail prévu réalisé pour la préparation des cas de test (ou le pourcentage des cas de test prévus implémentés)
- Pourcentage du travail prévu réalisé pour la préparation de l'environnement de test
- Exécution des cas de test (p. ex. nombre de cas de test exécutés/non exécutés, cas de test réussis/échoués, et/ou conditions de test réussies/échouées)
- Informations sur les défauts (p. ex. densité des défauts, défauts trouvés et corrigés, taux de défaillance et résultats des tests de confirmation)
- Couverture des exigences, des User Stories, des critères d'acceptation, des risques ou du code par les tests
- Degré d'achèvement des tâches, affectation et utilisation des ressources, et temps passé
- Coût des tests, y compris en comparaison avec le bénéfice apporté par la découverte des défauts supplémentaires ou le coût par rapport au bénéfice de l'exécution de tests supplémentaires

### Risques et test

- **Risque** : possibilité d'un événement futur qui a des conséquences négatives. Le niveau de risque est déterminé par la probabilité de l'événement et son impact (le préjudice).
  
   - **Risque produit**
     - Risque directement lié à l’objet de test
   - **Risque projet**
     - Risque lié à la gestion et au contrôle du projet (de test), par  exemple manque d’encadrement, deadlines irréalistes, exigences changeantes 

- **Test Basé sur les Risques**:
  - Une approche de test, commençant dès le début du projet, destinée à réduire le niveau des risques produit et à informer sur leur statut. Elle implique l’identification des risques produit et  l’utilisation de niveaux de risque pour guider le processus de test

- **Réduction des risques** 
  - 4 options principales
    - Mesures préventives pour réduire probabilité et/ou impact du risque
    - Plan de contingence pour réduire l’impact si le risque se produit
    - Transfert du risque  
    - Acceptation du risque
  - Réduction avec le test
    - Associer des tests aux risques

### Gestion des défauts

Exemple d’attributs de description: 

- Identifiant unique
- Titre explicite
- Nom de la personne ayant découvert le défaut
- Nom de la personne travaillant sur le défaut
- Sévérité du défaut (selon une classification à définir)
- Priorité de la correction du défaut
- Numéro de livraison ou version logicielle dans laquelle le défaut a été trouvé
- Niveau de test auquel le défaut a été trouvé
- Description détaillée du défaut trouvé incluant les détails d’exécution du test.
  - La description doit fournir suffisamment de détail pour pouvoir reproduire le défaut de façon non ambigüe (elle devrait inclure un lien vers le résultat d’exécution du test correspondant).
- Statut du défaut. Le cycle de vie du défaut est basé sur cet attribut.

### Classification des outils de test

- Outils pour la gestion des tests et du testware
- Outils pour les tests statiques
- Outils pour la conception et l'implémentation des tests
- Outils pour l'exécution et les logs de tests
- Outils pour la mesure de la performance et l'analyse dynamique
- Outils pour des besoins de test spécifiques

