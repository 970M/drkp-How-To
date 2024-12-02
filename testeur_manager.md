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

- **Politique de test** : Décrit les objectifs et les finalités du test pour l’organisation
  - Résume la valeur que l’organisation dégage du test
  - Définit les objectifs du test, tels qu’acquérir de la confiance dans le logiciel, détecter des défauts dans le logiciel, et réduire le niveau de risque qualité
  - Décrit comment évaluer l’efficacité et la rentabilité des tests pour atteindre ces objectifs
  - Décrit le processus de test typique, éventuellement en utilisant comme base les processus de test fondamentaux de l’ISTQB
  - Spécifie comment l’organisation améliorera ses processus de test 
  
- **Stratégie de test** : Décrit les méthodes de test générales et indépendantes des projets au sein de l’organisation
  - **Analytique**: Analyse des exigences, Analyse des risques
  - **Basée sur des modèles**: Tests conçus à partir d’un modèle (type d'utilisation ...)
  - **Méthodique**: Utilisation d’un ensemble prédéfini de tests ou conditions de test (ex: taxonomie de défauts)
  - **Conforme à un processus ou une norme**: Basée sur des règles et normes externe (ex: DO 178B, processus Agile ...)
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


- **Plan de test maître (ou plan de test projet)** : Décrit l’implémentation de la stratégie de test sur un projet particulier
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
  
- **Plan de test de niveau (ou plan de test de phase)** : Décrit les activités précises à mettre en œuvre pour chaque niveau de test

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


## Techniques d'estimation des Tests

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

Les revues possibles sur un projet incluent:
-  Les revues contractuelles, initialisées au démarrage du projet et aux jalons majeurs
-  Les revues d’exigences, initialisés lorsque les exigences sont disponibles pour être revues, ce qui idéalement couvre les exigences fonctionnelles et non fonctionnelles
-  Les revues de conception de haut niveau, initiées quand la conception d’architecture est disponible pour revue
-  Les revues de conception détaillée, initiées lorsque la conception détaillée est disponible
-  Les revues de code, effectuées lorsque les modules individuels sont créés, et pouvant inclure les tests unitaires et leurs résultats de même que le code lui-même
-  Les revues de livrables de test, qui peuvent inclure le ou les plan(s) de test, les conditions de test, les résultats de l’analyse des risques qualité (produit), les tests, les données de test, les environnements de test, et les résultats de test
-  Les revues de démarrage des tests (disponibilité des tests) et les revues de sortie des tests pour chaque niveau de test, qui vérifient respectivement les critères d’entrée des tests avant de commencer leur exécution et les critères de sortie avant d’arrêter le test 
-  Les revues d’acceptation, utilisées pour obtenir l’acceptation d’un système par un client ou une partie prenante
  

### Gérer les Revues

**Pré-requis** :

- Ce qui doit être revu (produit et processus)
- Qui devrait être impliqué dans chaque revue spécifique
- Quels facteurs de risque importants couvrir ?

**Déterminer le temps optimal pour exécuter une revue, dépend de** :
- La disponibilité des éléments à revoir dans un état suffisamment avancé
- La disponibilité des bonnes personnes pour la revue
- Le moment où la version finale de l’élément devrait être disponible
- Le temps nécessaire pour le processus de revue de cet élément particulier

**Lors du déroulement de revues formelles, le responsable de la revue doit s’assurer que** :
- Des mesures appropriées sont fournies par les participants aux revues pour permettre d’évaluer l’efficacité d’une revue
- Des check-lists sont créées et maintenues pour améliorer les revues futures
- L’évaluation de la sévérité et de la priorité des défauts est définie pour utilisation par la gestion des anomalies trouvées durant les revues

**Après chaque revue, le responsable de revues devrait** :
- Collecter les métriques de revue et s’assurer que les problèmes identifiés sont traités pour atteindre les objectifs de la revue
- Utiliser des métriques de revues comme entrées pour déterminer le retour sur investissement (ROI) des revues
- Fournir des informations en retour aux parties prenantes pertinentes
- Fournir des informations en retour aux participants aux revues

### Métriques pour les Revues

**Objectif des métriques** :
- Évaluer la qualité de l’élément revu
- Evaluer le coût de réalisation de la revue
- Evaluer le bénéfice engendré par la conduite de revue

**Métriques pour l'évaluation du produit** :
- Taille des livrables (pages, lignes de codes, etc.)
- Temps de préparation nécessaire (avant la revue)
- Temps nécessaire pour mener la revue
- Temps nécessaire pour corriger les défauts
- Durée du processus de revue
- Nombre et sévérité des défauts trouvés
- Identification des agrégats de défauts (c.à.d., parties ayant une plus forte densité de défauts)
- Type de revue (revue informelle, relecture technique, revue technique ou inspection)
- Densité de défauts moyenne (par ex., défauts par page ou par millier de lignes de code)
- Estimation du nombre de défauts résiduels (densité de défauts résiduelle)

**Métriques pour l'évaluation du processus** :
- Efficacité de détection des défauts (prenant en compte les défauts trouvés ultérieurement dans le cycle de vie)
- Amélioration de la charge et du temps alloués au processus de revue
- Pourcentage de couverture des livrables prévus
- Types et sévérité des défauts détectés
- Enquêtes réalisées auprès des participants sur la rentabilité et l’efficacité du processus de revue
- Métrique sur le coût de la qualité pour les défauts identifiés lors de revues, versus coût des défauts trouvés lors des tests dynamiques et des défauts trouvés en production
- Corrélation sur l’efficacité des revues (type de revues versus efficacité de la détection de défauts)
- Nombre de relecteurs
- Nombre de défauts trouvés par heure consacrée à la revue
- Estimation du temps économisé pour le projet
- Effort moyen par défaut (c.à.d., temps total consacré à la détection et à la résolution des défauts divisé par le nombre de défauts

### Gérer des Revues Formelles

**Les principales caractéristiques des revues formelles sont** :
- Critères d’entrée et de sortie définis
- Check-lists utilisées par les relecteurs
- Livrables tels que des rapports, des notes d’évaluation et tout autre document résumant les résultats de la revue
- Métriques pour un reporting sur la rentabilité, l’efficacité et la progression des revues

## Gestion des Anomalies

### Cycle d’une Anomalie et États
- L’état **initial**
  - Dans cet état, un ou plusieurs testeurs collectent l’information qui sera nécessaire à la personne responsable de la résolution du défaut pour reproduire l’anomalie (voir section 4.3 pour l’information à inclure dans le rapport d’anomalie).
  - Cet état peut aussi être appelé “ouvert” ou “nouveau”.
- L’état **retourné**
  - Dans cet état, le destinataire du rapport a rejeté ce rapport ou a demandé au testeur de fournir davantage d’informations. Cet état peut indiquer un manque dans le processus initial de recueil d’informations ou dans le test lui-même, et les Test Managers devraient mesurer les taux de retour excessifs. Le(s) testeur(s) doi(ven)t fournir l’information complémentaire, ou confirmer que le rapport devrait en effet être rejeté.
  - Cet état peut aussi être appelé “rejeté” ou “clarification”.
- L’état **test de confirmation**
  - Dans cet état, le testeur va exécuter un test de confirmation (généralement, en suivant les étapes indiquées dans le rapport d’anomalie pour reproduire la défaillance) pour déterminer si la correction a bien résolu le problème. Si le test de confirmation indique que le défaut est réparé, le testeur devrait clôturer le rapport. Si le test de confirmation indique que le défaut n’est pas réparé, le testeur devrait ré-ouvrir le rapport, déclenchant sa réaffectation au porteur précédent, qui pourra alors compléter le travail nécessaire pour réparer le défaut.
  - Cet état peut aussi être appelé “résolu” ou “vérification”.

### Données d’un Rapport d’Anomalie
- La gestion de l’anomalie selon le cycle de vie des anomalies
- Une évaluation du statut du projet, spécifiquement en termes de qualité produit et avancement du test
- L’évaluation de la capacité du processus

### Données collectées sur les anomalies
- Le nom de la personne ayant découvert le défaut
- Le rôle de la personne (par ex., utilisateur final, analyste métier, développeur, personne du support technique)
- Le type de test réalisé (par ex., utilisabilité, performance, non-régression)
- Un résumé du problème
- Une description détaillée du problème
- Les étapes nécessaires pour reproduire la défaillance (pour un défaut), ainsi que les résultats attendus et obtenus (mettant en évidence l’anomalie), intégrant des copies d’écran, des extraits de bases de données et de logs là où c’est possible
- Les phases du cycle de vie durant lesquelles le défaut a été introduit, détecté et supprimé, y compris le niveau de test si c’est applicable
- Le livrable dans lequel le défaut a été introduit
- La sévérité de l’impact sur le système et/ou les parties prenantes produit (en général déterminé par le comportement technique du système)
- La priorité de correction du problème (généralement déterminé par l’impact métier de la défaillance)
- Le sous-système ou composant auquel le défaut est attaché (pour l’analyse des agrégats de défauts)
- L’activité en cours sur le projet lorsque le problème a été détecté
- La méthode d’identification qui a révélé le problème (par ex., revue, analyse statique, test dynamique, utilisation en production)
- Le type de défaut (correspondant en général à la taxonomie utilisée)
- La caractéristique qualité affectée par le défaut
- L’environnement de test dans lequel le défaut a été observé (pour le test dynamique)
- Le projet et produit dans lesquels le problème se trouve
- Le propriétaire actuel; c.à.d., la personne actuellement affectée au problème, à condition que le rapport ne soit pas dans un état final
- L’état courant du rapport (en général géré par l’outil de suivi des anomalies dans le cycle de vie de l’anomalie)
- Les livrables spécifiques (par ex., éléments de test avec leur numéro de version) dans lesquels le problème a été observé, ainsi que le livrable spécifique où le problème a été définitivement résolu
- L’impact sur les intérêts des parties prenantes du projet et du produit
- Les conclusions, recommandations et approbations des actions prises ou non pour résoudre le problème
- Les risques, coûts, opportunités, et bénéfices associés à la correction ou non du défaut
- Les dates de transitions d’état du défaut dans son cycle de vie, le propriétaire du défaut au moment de chaque transition, et les actions prises par l’équipe projet pour isoler, réparer et vérifier la correction
- Une description de la façon de résoudre le défaut et des recommandations pour le test de la correction (si le défaut a été résolu par un changement dans le logiciel)
- D’autres références, comme le test qui a mis en évidence le défaut et le risque, l’exigence, ou tout autre élément relié au défaut (pour le test dynamique)

### Évaluer l’Efficacité d’un Processus avec l’Information des Rapports d’Anomalie
- Utiliser l’information sur la phase d’introduction, de détection, et de suppression, pour évaluer, phase par phase le confinement par phase et suggérer des manières d’améliorer l’efficacité de détection des défauts dans chaque phase
- Utiliser l’information sur la phase d’introduction pour une analyse, selon la loi de Pareto, des phases dans lesquelles le plus grand nombre de défauts sont introduits, afin d’identifier des améliorations ciblées visant à réduire le nombre total de défauts
- Utiliser les informations de cause racine des défauts de l’analyse des causes racines des défauts pour déterminer les raisons sous-jacentes à l’introduction d’un défaut afin d’améliorer le processus pour réduire le nombre total de défauts
- Utiliser l’information sur les phases d’introduction, de détection, et de suppression, pour réaliser une analyse du coût de la qualité afin de minimiser le coût associé aux défauts
- Utiliser l’information sur les composants défaillants pour effectuer une analyse des agrégats de défauts afin de mieux comprendre les risques techniques (pour du test basé sur les risques) et permettre une ré-ingénierie des composants problématiques
