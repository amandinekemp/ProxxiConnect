# ProxxiConnect

1. Présentation du projet
2. Besoin fonctionnel
3. Public cible
4. Personas
5. Périmètre fonctionnel
6. MVP
7. Parcours utilisateurs
8. Use Cases
9. Règles métier
10. Modélisation des données
11. Dictionnaire de données
12. MCD
13. MLD
14. MPD
15. Contraintes du projet
16. Architecture envisagée
17. Stack technique
19. Charte graphique
20. Wireframes
21. Conclusion

# 1. Présentation du projet

## Nom du projet : ProxxiConnect

### Contexte

L’entreprise souhaite améliorer le suivi humain des collaborateurs en mission chez les les clients ainsi qu’au centre de services (CDS).

Aujourd’hui, les échanges entre les Proxxi et les salariés existent déjà, mais les informations sont dispersées et difficilement exploitables.  
Le suivi est principalement réalisé de manière informelle, ce qui limite :

- la visibilité globale sur l’état des collaborateurs ;
- le pilotage des actions de suivi ;
- la détection précoce des situations à risque ;
- la centralisation des comptes rendus ;
- la production de statistiques et de reportings fiables.

Le projet consiste donc à développer une application web permettant de centraliser les échanges entre les Proxxi et les collaborateurs afin de faciliter le suivi humain et le pilotage global du dispositif.

---

## Problématique ciblée

L’entreprise ne dispose actuellement d’aucun outil centralisé permettant :

- de suivre les échanges réalisés entre les Proxxi et les collaborateurs ;
- de détecter les situations de démotivation, d’isolement ou de burnout ;
- de visualiser les statistiques globales de suivi ;
- de garantir le respect des obligations liées aux rencontres annuelles ;
- de faciliter le reporting auprès des administrateurs et de la direction.

Le manque de centralisation rend également plus complexe :

- le suivi des actions à mettre en place ;
- l’historisation des échanges ;
- le pilotage des campagnes de suivi sur l’exercice fiscal.

---

## Objectif du projet

Créer une plateforme web mobile-first permettant :

- aux Proxxi de suivre les collaborateurs qui leur sont attribués ;
- de saisir des comptes rendus après chaque échange ;
- de remplir des questionnaires standardisés ;
- d’identifier rapidement les situations sensibles ;
- de centraliser les informations ;
- de générer des statistiques et reportings globaux ;
- de suivre les obligations internes liées aux primes.

---

## Valeur principale apportée

ProxxiConnect apporte une vision centralisée et structurée du suivi humain des collaborateurs.

L’application permet :

- d’améliorer la proximité entre l’entreprise et les salariés ;
- de détecter plus rapidement les situations à risque ;
- de faciliter la communication interne ;
- de suivre les obligations de rencontres annuelles ;
- d’automatiser les rappels et notifications ;
- de produire des statistiques exploitables pour le pilotage RH et managérial.

---

## Fonctionnalité centrale du MVP

La fonctionnalité principale du MVP est :

> le suivi des échanges entre les Proxxi et les collaborateurs via des questionnaires standardisés associés à des rendez-vous.

Cette fonctionnalité inclut :

- la gestion des collaborateurs ;
- la gestion des rendez-vous ;
- la saisie des questionnaires ;
- le suivi des statistiques principales ;
- les rappels automatiques ;
- les alertes administrateurs.

Le MVP doit rester volontairement simple afin de garantir :

- une réalisation réaliste ;
- une maintenance facilitée ;
- une bonne évolutivité du projet.

---

# 2. Formalisation du besoin fonctionnel

## Besoin utilisateur

Les Proxxi doivent pouvoir suivre facilement les collaborateurs qui leur sont attribués afin de maintenir une relation régulière et détecter rapidement les situations problématiques.

Aujourd’hui, les informations sont éparpillées entre différents supports et ne permettent pas d’obtenir une vision globale du suivi humain.

L’entreprise souhaite donc disposer d’un outil permettant :

- d’enregistrer chaque échange ;
- de conserver un historique des rencontres ;
- de centraliser les comptes rendus pour les administrateurs;
- de produire des statistiques globales ;
- d’identifier rapidement les collaborateurs nécessitant une attention particulière ;
- de suivre les obligations liées aux primes internes.

Le besoin doit également répondre à plusieurs contraintes :

- accès mobile ;
- simplicité d’utilisation ;
- centralisation des données ;
- historisation des échanges ;
- notifications automatiques ;
- conservation des données pendant 5 ans.

---

# 3. Public cible

## Les administrateurs

Les administrateurs disposent d’un accès global à la plateforme.

Ils peuvent :

- gérer les affectations des collaborateurs ;
- consulter l’ensemble des questionnaires ;
- suivre les statistiques globales ;
- recevoir les alertes importantes ;
- suivre les actions traitées ou non traitées ;
- exporter les reportings.

Administrateurs identifiés :

- Sunita
- Christophe
- Cédric

---

## Les Proxxi

Les Proxxi assurent le suivi humain des collaborateurs.

Leur rôle consiste à :

- organiser les rencontres ;
- maintenir une proximité avec les salariés ;
- remplir les questionnaires après chaque échange ;
- remonter les éventuelles difficultés rencontrées ;
- relayer les informations de l’entreprise.

Chaque Proxxi possède uniquement accès aux collaborateurs qui lui sont attribués.

---

## Les salariés

Les salariés n’utilisent pas directement l’application.

Toutes les informations sont saisies uniquement par :

- les Proxxi ;
- les administrateurs.

---

# 3.1 Persona du projet

Afin de mieux comprendre les besoins des futurs utilisateurs, plusieurs persona ont été définis.  
Ces profils représentent les principaux acteurs concernés par l’application et permettent de mieux orienter les choix fonctionnels et ergonomiques du projet.

[Persona #1 Sunita](/docs/00-/Personas/Persona_1_Sunita.md)

[Persona #2 Laura](/docs/00-/Personas/Persona_2_Laura.md)

[Persona #3 Julien](/docs/00-/Personas/Persona_3_Julien.md)

---

# 3.2 User Journey Global du projet

![User_journey_Global_du_projet](/docs/00-/User_journey/User_journey_Global.png)

---

# 4. Définition du périmètre fonctionnel

## Priorisation des fonctionnalités — méthode MoSCoW

| Niveau      | Fonctionnalité                                        |
|-------------|-------------------------------------------------------|
| Must Have   | Connexion via Google OAuth                            |
| Must Have   | Gestion des Proxxi                                    |
| Must Have   | Gestion des collaborateurs                            |
| Must Have   | Attribution des collaborateurs à un Proxxi            |
| Must Have   | Création d’un rendez-vous                             |
| Must Have   | Saisie du questionnaire                               |
| Must Have   | Historique des échanges                               |
| Must Have   | Notifications email                                   |
| Must Have   | Alertes administrateurs                               |
| Must Have   | Tableaux de bord statistiques                         |
| Must Have   | Tableau récapitulatif avancé pour les administrateurs |
| Must Have   | Suivi des 3 rendez-vous obligatoires                  |
| Must Have   | Conservation des données 5 ans                        |
| Should Have | Export PowerPoint (.pptx)                             |
| Should Have | Gestion des actions traitées / non traitées           |
| Should Have | Comparaison entre exercices fiscaux                   |
| Could Have  | Notifications temps réel                              |
| Could Have  | Statistiques détaillées par client                    |
| Won’t Have  | Application mobile native                             |
| Won’t Have  | Création dynamique des questions                      |

---

# 5. MVP

Le MVP se concentre sur :

- l’authentification Google ;
- la gestion des collaborateurs ;
- la gestion des rendez-vous ;
- les questionnaires fixes ;
- les alertes administrateurs ;
- les statistiques globales ;
- Le tableau récapitulatif des retours Proxxis pour les administrateurs ;
- les rappels automatiques.

Le MVP doit permettre une première mise en production rapide tout en couvrant les besoins métiers essentiels.

---

# Diagramme UML - Use Case

![Diagramme_UML_Cas_d_utilisation_ProxxiConnect](/Ressources/Diagramme_UML-Use_Case_ProxxiConnect.png)

---

# 6. Parcours utilisateurs

## Parcours — Connexion

### Acteur

Proxxi / Administrateur

### Étapes

1. L’utilisateur accède à l’application ;
2. Il se connecte via Google OAuth ;
3. Le système vérifie son rôle ;
4. L’utilisateur accède à son espace.

### Résultat attendu

Connexion sécurisée avec accès adapté au rôle utilisateur.

---

## Parcours — Création d’un compte rendu

### Acteur

Proxxi

### Étapes

1. Sélection du collaborateur ;
2. Création du rendez-vous ;
3. Choix du format (restaurant, site client, visio) ;
4. Remplissage du questionnaire ;
5. Validation définitive du formulaire.

### Résultat attendu

Le questionnaire est enregistré et verrouillé définitivement.

---

## Parcours — Consultation des statistiques

### Acteur

Administrateur

### Étapes

1. Accès au dashboard ;
2. Consultation des indicateurs ;
3. Filtrage par exercice fiscal ;
4. Analyse des graphiques ;
5. Export éventuel du reporting.

### Résultat attendu

Visualisation claire des données globales de suivi.

---

# 7. Règles métier

- Un collaborateur appartient à un seul Proxxi à la fois ;
- Les questionnaires sont fixes ;
- Un questionnaire validé ne peut plus être modifié ;
- Les salariés n’ont pas accès à l’application ;
- Les données doivent être conservées pendant 5 ans ;
- Chaque collaborateur doit être vu au minimum 3 fois par exercice fiscal ;
- L’exercice fiscal va du 1er août N-1 au 31 juillet N ;
- Les rappels sont envoyés automatiquement tous les 3 mois ;
- Un rappel supplémentaire est envoyé 2 mois après une rencontre ;
- Les administrateurs reçoivent une alerte lorsqu’un questionnaire est soumis ;
- Les alertes peuvent être marquées comme traitées ;
- Les Proxxi ne peuvent consulter que leurs propres collaborateurs ;
- Les administrateurs disposent d’un accès global.

---

# MCD (Modèle Conceptuel de Données)

![MCD_ProxxiConnect](/docs/03-conception/mcd/1.MCD_ProxxiConnect.drawio.png)

---

# 8. Contraintes du projet

## Contraintes fonctionnelles

- application web responsive ;
- approche mobile-first ;
- simplicité d’utilisation ;
- accessibilité minimale ;
- performance correcte sur mobile.

---

## Contraintes techniques

- authentification Google OAuth ;
- stockage sécurisé des données ;
- export PowerPoint ;
- architecture évolutive ;
- API REST ;
- hébergement cloud.

---

## Contraintes réglementaires

- conservation des données pendant 5 ans ;
- respect du RGPD ;
- sécurisation des accès ;
- protection des données personnelles.

---

# 9. Architecture envisagée

L’application reposera sur une architecture web fullstack séparée :

- un frontend Vue.js ;
- une API backend Spring Boot ;
- une base de données PostgreSQL.

## Communication

Le frontend communiquera avec le backend via une API REST sécurisée.

Le backend sera responsable :

- de l’authentification ;
- de la logique métier ;
- des notifications ;
- de l’accès aux données.

La base PostgreSQL stockera :

- les collaborateurs ;
- les rendez-vous ;
- les questionnaires ;
- les statistiques ;
- les alertes.

---

# 10. Stack technique détaillée

## Frontend

| Élément | Choix | Version | Justification |
|---|---|---|---|
| Langage | TypeScript | 5.x | Technologie déjà utilisée dans l’entreprise permettant de continuer à monter en compétence sur un environnement typé |
| Framework | Vue.js | 3.x | Framework déjà présent dans l’écosystème technique de l’entreprise et adapté à la création d’interfaces modernes |
| Build Tool | Vite | 6.x | Outil moderne offrant de bonnes performances de développement et déjà utilisé sur certains projets internes |
| CSS | Tailwind CSS | 4.x | Permet de développer rapidement une interface responsive et maintenable |
| UI Components | Shadcn Vue | dernière version stable | Accélère la création d’une interface cohérente et moderne |

---

## Backend

| Élément | Choix | Version | Justification |
|---|---|---|---|
| Runtime | Java | 21 LTS | Langage déjà utilisé dans l’entreprise permettant de rester cohérent avec l’environnement technique existant |
| Framework | Spring Boot | 3.x | Framework maîtrisé et utilisé en interne pour développer des APIs robustes et maintenables |
| Sécurité | Spring Security | 6.x | Intégration naturelle avec Spring Boot pour sécuriser l’application |
| Auth | Google OAuth2 | dernière version stable | Simplifie l’authentification grâce aux comptes Google professionnels déjà utilisés par les collaborateurs |
| API | REST | - | Architecture simple, standardisée et adaptée à une application web moderne |

---

## Base de données

| Élément | Choix | Version | Justification |
|---|---|---|---|
| SGBD | PostgreSQL | 17.x | Base de données robuste et déjà utilisée dans plusieurs projets de l’entreprise |
| ORM | Spring Data JPA | dernière version stable | Simplifie les accès aux données et s’intègre naturellement avec Spring Boot |

---

## Outils de développement

| Élément | Choix | Version | Justification |
|---|---|---|---|
| Gestionnaire de paquets | pnpm | 10.x | Plus rapide et optimisé pour les projets JavaScript modernes |
| Versioning | Git | dernière version stable | Standard utilisé dans l’entreprise pour la gestion du code source |
| Conteneurisation | Docker | dernière version stable | Facilite la reproductibilité des environnements de développement et de déploiement |

---

# 11. Librairies importantes

## Frontend

- Vue Router
- Pinia
- Axios
- Zod
- VueUse
- TailwindCSS
- Chart.js

---

## Backend

- Spring Security
- Spring Data JPA
- MapStruct
- Jakarta Validation
- Java Mail Sender

---

# 12. Notifications & reporting

## Notifications prévues

### Pour les Proxxi

- rappel après 2 mois sans rencontre ;
- informations liées aux collaborateurs.

### Pour les administrateurs

- alerte lors d’un questionnaire soumis ;
- suivi des alertes traitées ;
- remontée des situations sensibles.

---

## Reporting

Les administrateurs pourront consulter :

- nombre de réponses par météo ;
- nombre d’échanges par Proxxi ;
- évolution des suivis ;
- comparaison entre exercices fiscaux ;
- répartition des formats de rendez-vous.

Export prévu :

- PowerPoint (.pptx)

---

# 13. Charte graphique

## Identité visuelle

L’interface devra respecter l’identité graphique de Nextoo afin de conserver une cohérence avec l’écosystème de l’entreprise.

![Charte_graphique_ProxxiConnect](TODO lien)

---

## Couleurs principales

| Couleur | Usage |
|---|---|
| Bleu Galactique | Texte, sous-titres, fonds secondaires |
| Rouge T65 | Titres, éléments importants |
| Blanc Stormtrooper | Fonds principaux |

---

## Typographies

| Typographie | Usage |
|---|---|
| Montserrat Regular | Paragraphes et contenus |
| Montserrat Semi-Bold | Boutons et mise en avant |
| Krona One | Titres et sous-titres |

---

# Wireframes

Ecran de connexion :
![Wireframe_ProxxiConnect_connexion](/docs/03-conception/maquettes/Wireframes_ProxxiConnect/1wireframe_ProxxiConnect.png)

Tableau de bord :
![Wireframe_ProxxiConnect_taleau de bord](/docs/03-conception/maquettes/Wireframes_ProxxiConnect/2wireframe_ProxxiConnect_tableau_de_bord.png)

Mes collaborateurs :
![Wireframe_ProxxiConnect_mes_collaborateurs](/docs/03-conception/maquettes/Wireframes_ProxxiConnect/3wireframe_ProxxiConnect_mes_collaborateurs.png)

Mes rendez-vous :
![Wireframe_ProxxiConnect_mes_rendez-vous](/docs/03-conception/maquettes/Wireframes_ProxxiConnect/4wireframe_ProxxiConnect_mes_rdv.png)

Retour Proxxi :
![Wireframe_ProxxiConnect_retour_proxxi](/docs/03-conception/maquettes/Wireframes_ProxxiConnect/5wireframe_ProxxiConnect_retour_proxxi.png)

Assigner à un Proxxi :
![Wireframe_ProxxiConnect_assigner_a_un_proxxi](/docs/03-conception/maquettes/Wireframes_ProxxiConnect/6wireframe_ProxxiConnect_assigner_a_un_proxxi.png)

Synthése retour Proxxi :
![Wireframe_ProxxiConnect_synthese_retour_proxxi](/docs/03-conception/maquettes/Wireframes_ProxxiConnect/7wireframe_ProxxiConnect_synthese_retour_proxxi.png)

---

# 14. Conclusion

ProxxiConnect répond à un besoin concret de centralisation du suivi humain des collaborateurs.

Le projet vise à fournir un outil :

- simple ;
- structuré ;
- mobile-first ;
- évolutif ;
- exploitable par les Proxxi et les administrateurs.

Le MVP permettra de couvrir les besoins essentiels :

- suivi des échanges ;
- questionnaires ;
- statistiques ;
- alertes ;
- reporting.

---

## 👤 Contact

**Amandine Delbouve(Kemp)** – Développeuse

[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/amandinekemp)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/amandinedelbouve/)
