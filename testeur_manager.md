# Tester - Manager (ISTBQ)

[README.md](README.md)

## Processus de Test

- **Planification des Tests** : Identification des activités et ressources nécessaires à la réalisation de la mission et des objectifs définis dans la stratégie de tes
- **Pilotage et Contrôle des Tests** : Un planning des tests et un cadre de mesure doivent être établis pour permettre le suivi des livrables et des ressource
- **Analyse des Tests** : Définit “ce qu’il faut” tester, sous la forme de conditions de test
- **Conception des Tests** : Définit “comment” quelque chose doit être test
- **Implémentation des Tests** : Activité durant laquelle les tests sont organisés et priorisés
- **Exécution des Tests** : Commence dès que l’objet de test est livré et que les critères d’entrée pour l’exécution des tests sont satisfaits
- **valuation des Critères de Sortie et Reporting** : Suivi et le contrôle de l’avancement des tests 
- **Activités de Clôture des Tests** : 
  - Vérification de la complétude des tests
  - Transmission des artefacts de test
  - Leçons apprises
  - Archiver les résultats


## Gestion des Tests

### Parties-prenantes du Test

- Développeurs
- Les architectes de bases de données
- Les analystes métier et Marketing
- Les responsables de produit
- Les gestionnaires de projet
- Le support technique
- Les utilisateurs 

### Chaque niveau de test devrait avoir les éléments suivants clairement définis

- Objectifs de test, avec des buts atteignables
- Périmètre du test et éléments de test
- Base de test, avec un moyen de mesurer la couverture de cette base (c.à.d., la traçabilité)
- Critères d’entrée et de sortie
- Livrables du test, incluant le rapport des résultats de test
- Techniques de test applicables, ainsi qu’une manière pour assurer un degré de couverture avec ces techniques
- Mesures et métriques adaptées aux objectifs de test, aux critères d’entrée et de sortie, et reporting des résultats (y compris mesures de couverture)
- Outils de test à appliquer pour certaines tâches de test (si et où applicable)
- Ressources (par ex., environnements de test)
- Personnes et groupes responsables, à la fois au sein et hors de l’équipe de test
- Conformité avec les standard de l’organisation, les standards légaux et d’autres standards (lorsque cela est possible)


### Test Basé sur les Risques

#### Quatre activités principales:

1. **Identification des Risques**

     - Entretiens avec des experts
    - Évaluations indépendantes
    - Utilisation de templates de risque
    - Rétrospectives de projets
    - Groupe de travail sur les risques
    - Brainstorming
    - Check-lists
    - Rappel d’expérience passées

2. **Evaluation des risques** [ISO25000]
3. **Mitigation des Risques**
4. **Gestion des Risques**

#### Techniques
- **Informelle** : les testeurs analysent les risques qualité pendant du test exploratoire
- **Formelle** : 
  - Approches allégées:
    - Analyse et Gestion Pragmatique des Risques (Pragmatic Risque Analysis and Management ouPRAM)
    - Test Logiciel Systématique (Systematic Software Testing ou SST)
    - Gestion du Risque Produit (Product Risk Management ou PRisMa)
  - Analyse des Modes de Défaillances et Effets (AMDE)
  - Déploiement Qualité de Fonctions (DQF)
  - Analyse par Arbre de Défaillance (Fault Tree Analysis ou FTA)


#### Activités de clôture des test

- L’équipe de test a-t-elle détecté un pourcentage plus élevé de défauts importants que de
défauts peu importants?
- L’équipe de test a-t-elle trouvé les défauts les plus importants au début de la période
d’exécution des tests?
- L’équipe de test a-t-elle été en mesure d’expliquer aux parties prenantes les résultats de test
en termes de risques?
- Les tests sautés par l’équipe de test (s’il y en a) avaient-ils un niveau de risque associé plus
bas que ceux exécutés?

### Autres Techniques de Sélection des Tests

- Test basé sur les exigences
- Les graphes de cause à effet
- Approche basée sur les modèles
- Approches méthodiques 
- Approche réactive

## Documentation des Tests

- **Politique de test** : décrit les objectifs et les finalités du test pour l’organisation
  - Résume la valeur que l’organisation dégage du test
  - Définit les objectifs du test, tels qu’acquérir de la confiance dans le logiciel, détecter des défauts dans le logiciel, et réduire le niveau de risque qualité
  - Décrit comment évaluer l’efficacité et la rentabilité des tests pour atteindre ces objectifs
  - Décrit le processus de test typique, éventuellement en utilisant comme base les processus de test fondamentaux de l’ISTQB
  - Spécifie comment l’organisation améliorera ses processus de test 
  
- **Stratégie de test** : décrit les méthodes de test générales et indépendantes des projets au sein de l’organisation
  - **Analytique**: Analyse des exigences, Analyse des risques
  - **Basée sur des modèles**: Tests conçus à partir d’un modèle
  - **Méthodique**: Utilisation d’un ensemble prédéfini de tests ou conditions de test (ex: taxonomie de défauts)
  - **Conforme à un processus ou une norme**: Basée sur des règles et normes externe (ex: DO 178B)
  - **Dirigée (ou consultative)**: Dictée par les parties prenantes
  - **Anti-régressions**: Eviter les régressions (avec des tests automatisés)
  - **Réactive**: Adaptée pendant l’exécution des tests
  
```
La stratégie de test peut aussi décrire les points suivants:
  - Procédures d’intégration
  - Techniques de spécification des tests
  - Indépendance du test (qui peut varier selon le niveau)
  - Standards obligatoires ou optionnels
  - Environnements de test
  - Automatisation des tests
  - Outils de test
  - Réutilisabilité des livrables de développement et des livrables de test
  - Test de confirmation (re-test) et test de non-régression
  - Contrôle des tests et reporting
  - Mesure du test et métriques
  - Gestion des défauts
  - Approche de gestion en configuration des articles de test
  - Rôles et responsabilités
```


- **Plan de test maître (ou plan de test projet)** : décrit l’implémentation de la stratégie de test sur un projet particulier

  - Les éléments à tester et à ne pas tester
  - Les attributs qualité à tester et à ne pas tester
  - Le calendrier des tests et le budget (qui devrait être aligné sur le budget du projet ou opérationnel)
  - Les cycles d'exécution des tests et leurs liens avec le plan de livraison du logiciel
  - Les relations et livrables au sein de l’équipe de test et entre le test et les autres personnes ou départements
  - La définition de quels articles de test sont dans le périmètre ou hors du périmètre de chaque niveau de test décrit
  - Les critères spécifiques d’entrée, les critères de continuation (suspension/reprise) et les critères de sortie pour chaque niveau et les relations entre les niveaux
  - Les risques du projet de test
  - La gouvernance globale de l’effort de test
  - Les responsabilités pour l’exécution de chacun des niveaux de test
  - Les entrées et sorties de chaque niveau de test
  
- **Plan de test de niveau (ou plan de test de phase)** : décrit les activités précises à mettre en œuvre pour chaque niveau de test

- **Gestion des Risques Projet** :

  - Disponibilité des environnements et des outils de test
  - Disponibilité et compétence de l’équipe de test
  - Manque de standards, de règles et de techniques pour l’effort de test

 ```
Une fois un risque identifié et analysé, il existe quatre options principales pour gérer ce risque:
    1. Mitiger le risque par des mesures préventives pour diminuer sa probabilité et/ou son impact
    2. Faire des plans de contingence pour réduire l’impact si le risque se produit
    3. Transférer la gestion du risque à une autre entité
    4. Ignorer ou accepter le risque
 ```                                 

- **Autres Livrables du Test** :
  - Rapports d’anomalies
  - Les spécifications de cas de test
  - Les logs de test


## Techniques d'éstimation des Tests


- Intuition, supposition et expérience passée
- Structure de la répartition du travail (WBS Work-breakdown-structure)
- Sessions d’estimation en équipe (par ex., Delphi à Large Bande)
- Règles et normes de la société
- Pourcentages de l'effort pour l’ensemble du projet ou du niveau des effectifs (par exemple, les ratios testeurs / développeurs)
- Historique et métriques de l'organisation, y compris les modèles dérivés de métriques qui estiment le nombre de défauts, le nombre de cycles de test, le nombre de cas de test, l'effort moyen estimé de chaque test, et le nombre de cycles de non-régression impliqués
- Des moyennes issues de l’industrie et des modèles prédictifs tels que les points de fonction, les lignes de code, l'effort de développement estimé, ou d'autres paramètres du projet 


```
Si les développeurs ont adopté de bonnes pratiques comme le test unitaire automatisé et l’intégration continue, alors jusqu’à 50% des défauts seront supprimés avant la livraison du code à l’équipe de test
```


## Métriques de Test

### Catégories de métrique de test
- **Métriques projet**, qui mesurent le progrès au regard des critères de sortie du projet, telles que les pourcentages de cas de test exécutés, passés avec succès et en échec
- **Métriques produit**, qui mesurent certains attributs du produit, telles que l’étendue de ce qui a été couvert par des tests ou la densité des défauts
- **Métriques processus**, qui mesurent la capacité des processus de développement ou de test, telles que le pourcentage de défauts découverts par le test
- **Métriques liées aux personnes**, qui mesurent la capacité des individus ou groupes, telles que l’implémentation des cas de test selon un planning donné


### L’avancement est principalement mesuré selon cinq dimensions

- Risques produit (qualité)
- Défauts
- Tests
- Couverture
- Confiance

*La confiance est souvent aussi rapportée de façon subjective*

### Définition de métriques                                

**Les métriques liées au risque produit incluent** :
  - Pourcentage de risques entièrement couverts par des tests passés avec succès
  - Pourcentage de risques pour lesquels certains ou tous les tests sont en échec
  - Pourcentage de risques n’étant pas encore complètement testés
  - Pourcentage des risques couverts, triés par catégories de risques
  - Pourcentage des risques identifiés après l’analyse de risque qualité initiale
  
**Les métriques liées aux défauts incluent** :
 - Nombre cumulé de défauts rapportés (trouvés) versus nombre total de défauts résolus (corrigés)
 - Temps moyen entre les défaillances ou taux de nouvelles défaillances
 - Répartition du nombre ou du pourcentage de défauts classés par:
   - Élément ou composant de test particulier
   - Causes racines
   - Source du défaut (par ex., spécification d’exigences, nouvelle fonctionnalité, régression, etc.)
   - Version de livraison en test
   - Phase d’introduction, de détection et de résolution du défaut
   - Priorité/sévérité
   - Rapports d’anomalie rejetés ou en doublon
 - Tendances en termes de durée moyenne entre découverte et résolution des défauts
 - Nombre de défauts corrigés ayant introduit de nouveaux défauts (parfois appelés défauts dépendants)

**Les métriques liées aux tests incluent** :
 - Nombre total de tests planifiés, spécifiés (implémentés), exécutés, passés avec succès, en échec, bloqués, et sautés
 - Statut des tests de non-régression et de confirmation, y compris les tendances et les volumétries relatives aux défaillances lors des tests de non-régression et de confirmation
 - Nombre d’heures de test prévues par jour versus nombre d’heures réellement passées à tester
 - Disponibilité de l’environnement de test (pourcentage d’heures de disponibilité de l’environnement de test pour l’équipe de test)

**Les métriques liées à la couverture incluent** :
  - Couverture des exigences et des éléments de conception
  - Couverture du risque
  - Couverture des environnements et des configurations
  - Couverture du code


**Les métriques pour mesurer la planification et le suivi des tests peuvent inclure** :
- La couverture des risques, des exigences et des autres éléments de la base de test
- La découverte de défauts
- Le nombre d’heures prévues versus passées pour développer le testware et exécuter les cas de test

**Les métriques pour mesurer les activités d’analyse de test peuvent inclure**:
- Le nombre de conditions de test identifiées
- Le nombre de défauts trouvés lors de l’analyse des tests (par ex., en identifiant les risques ou les autres conditions de test en utilisant la base de test) 

**Les métriques pour mesurer les activités de conception de tests peuvent inclure**:
- Pourcentage des conditions de test couvertes par des cas de tests
- Nombre de défauts trouvés lors de la conception des tests (par ex., en développant des tests à partir de la base de test)

**Les métriques pour mesurer les activités d’implémentation des tests peuvent inclure** :
- Pourcentage d’environnements de test configurés
- Pourcentage de données de test chargées
- Pourcentage de cas de tests automatisés

**Les métriques pour mesurer les activités d’exécution des tests peuvent inclure** :
- Pourcentage de cas de tests exécutés, passés avec succès et en échec
- Pourcentage de conditions de test couvertes par des cas de test exécutés (et/ou passés avecsuccès)
- Nombre prévu versus réel de défauts trouvés/résolus
- Couverture prévue versus réalisée.


**Les métriques contrôlant l’avancement du test peuvent inclure les éléments suivants** :
- Nombre de conditions de test, cas de tests ou spécifications de test prévus et ceux ayant été exécutés, répartis par statut (passés ou en échec)
- Nombre total de défauts, souvent classés par sévérité, priorité, état actuel, sous-système concerné, ou autre classification (voir Chapitre 4)
- Nombre de changements demandés, acceptés, implémentés et testés  Coût prévu versus réel
- Durée prévue versus réelle
- Dates de passage des jalons de test prévues versus réelles 
- Dates de passage prévues versus dates réelles pour les jalons du projet ayant un lien avec le test (par ex., fin des développements)
- Statut des risques produit (qualité), souvent classés par, risques mitigés versus non-mitigés, domaines de risques, nouveaux risques découverts après l’analyse des tests, etc.
- Pourcentage d’effort de test, de coût ou de temps perdus suite à des évènements bloquants ou des changements de planning
- Statuts des tests de confirmation et de non-régression

**Les métriques pour mesurer les activités de clôture des tests peuvent inclure** :
- Le pourcentage de cas de test exécutés, passés avec succès, en échec, bloqués, et sautés pendant l’exécution des tests
- Le pourcentage de cas de test identifiés comme réutilisables dans le référentiel de test
- Le pourcentage de cas de test devant être automatisés versus le pourcentage de cas de test réellement automatisés
- Le pourcentage de cas de test intégrés aux tests de non-régression
- Le pourcentage de rapports de défauts résolus/non résolus
- Le pourcentage de livrables du test identifiés et archivés


## Revues 

