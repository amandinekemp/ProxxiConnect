# ProxxiConnect

Plateforme web mobile-first de suivi humain des collaborateurs en mission chez les clients et au centre de services (CDS), développée pour Nextoo.

ProxxiConnect centralise les échanges entre les Proxxi et les collaborateurs : comptes rendus, questionnaires standardisés, rendez-vous, rappels automatiques, alertes et statistiques de pilotage.

## Sommaire

1. [Fonctionnalités](#1-fonctionnalités)
2. [Rôles](#2-rôles)
3. [Stack technique](#3-stack-technique)
4. [Architecture](#4-architecture)
5. [Prérequis](#5-prérequis)
6. [Installation en local](#6-installation-en-local)
7. [Configuration](#7-configuration)
8. [Tests](#8-tests)
9. [Qualité et sécurité](#9-qualité-et-sécurité)
10. [Accessibilité et éco-conception](#10-accessibilité-et-éco-conception)
11. [Workflow Git et merge requests](#11-workflow-git-et-merge-requests)
12. [CI/CD et déploiement](#12-cicd-et-déploiement)
13. [Documentation](#13-documentation)
14. [Contribuer](#14-contribuer)
15. [Contact](#15-contact)

---

## 1. Fonctionnalités

Fonctionnalités du MVP :

- connexion via Google OAuth, avec accès adapté au rôle ;
- gestion des Proxxi et des collaborateurs ;
- attribution d'un collaborateur à un Proxxi (un collaborateur n'a qu'un Proxxi à la fois) ;
- gestion des rendez-vous, dont le suivi des 3 rendez-vous obligatoires par exercice fiscal ;
- saisie de questionnaires standardisés, verrouillés après validation ;
- rappels automatiques : rendez-vous à planifier, questionnaires à remplir, relance 2 mois après une rencontre ;
- alertes par email : administrateurs (questionnaire soumis, collaborateur sans Proxxi) et collaborateurs (nouveau Proxxi attribué) ;
- tableau de bord et statistiques (Should Have).

Hors MVP : export PowerPoint (.pptx) en Could Have, comparaison entre exercices fiscaux et gestion des actions traitées / non traitées (Won't Have).

## 2. Rôles

- Administrateur : accès global. Gère les affectations, consulte les questionnaires et les statistiques, reçoit les alertes, exporte les reportings.
- Proxxi : accède uniquement à ses propres collaborateurs. Organise les rencontres, remplit les questionnaires, remonte les difficultés.
- Collaborateur : n'utilise pas l'application. Les informations sont saisies par les Proxxi et les administrateurs.

## 3. Stack technique

Frontend : TypeScript 5.x, Vue.js 3.x, Vite 6.x, Tailwind CSS 4.x, Shadcn Vue, Pinia, Vue Router, Axios, Zod, VueUse, Chart.js. Gestionnaire de paquets : pnpm 10.x.

Backend : Java 25 LTS, Spring Boot 3.x, Spring Security 6.x, Spring Data JPA, MapStruct, Jakarta Validation, Java Mail Sender. Authentification : Google OAuth2.

Données : PostgreSQL 17.x, migrations avec Liquibase.

Outils : Git, Docker, Maven, JIB, Trivy, SonarQube, ESLint, Prettier, Vitest, JUnit, Playwright, axe-core.

## 4. Architecture

Architecture web fullstack séparée :

- le frontend Vue.js consomme une API REST sécurisée ;
- le backend Spring Boot gère l'authentification, la logique métier, les notifications et l'accès aux données ;
- PostgreSQL stocke collaborateurs, affectations, rendez-vous, questionnaires, notifications et alertes.

Backend, en couches : Controller (API REST), Service (logique applicative), Repository / Infra (base et API externes), Mapper (conversions), DTO / Model / Entity (séparation API, métier et persistance). Les entités JPA ne sont jamais exposées au frontend.

Frontend : pages, composants réutilisables, stores Pinia, clients API centralisés, router avec routes protégées, styles Tailwind CSS et Shadcn Vue.

API Google utilisées : Google Identity (authentification).

## 5. Prérequis

- Java 25 (LTS)
- Maven, ou le wrapper Maven fourni dans le dépôt
- Node.js (version LTS) et pnpm 10.x
- Docker Compose
- Un projet Google Cloud avec des identifiants OAuth 2.0 configurés

## 6. Installation en local

Cloner le dépôt :

git clone <url-du-depot>
cd proxxiconnect


Lancer la base de données (exemple à adapter) :

docker compose up -d postgres


Lancer le backend :

cd backend
./mvnw spring-boot:run


Lancer le frontend :

cd frontend
pnpm install
pnpm dev


L'application frontend est ensuite accessible sur l'adresse indiquée par Vite (par défaut http://localhost:5173).

## 7. Configuration

Les secrets ne doivent jamais être committés ni intégrés aux images Docker. Ils passent par des variables d'environnement.

| Variable | Rôle | Exemple |
|---|---|---|
| SPRING_DATASOURCE_URL | URL de la base PostgreSQL | jdbc:postgresql://localhost:5432/proxxiconnect |
| SPRING_DATASOURCE_USERNAME | Utilisateur de la base | proxxi |
| SPRING_DATASOURCE_PASSWORD | Mot de passe de la base | <secret> |
| GOOGLE_CLIENT_ID | Identifiant client OAuth Google | <secret> |
| GOOGLE_CLIENT_SECRET | Secret client OAuth Google | <secret> |
| ALLOWED_DOMAIN | Domaine Google autorisé à se connecter | nextoo.com |
| MAIL_HOST / MAIL_PORT | Serveur SMTP pour les alertes | <à définir> |

Les cookies de session sont sécurisés (HttpOnly, Secure, SameSite). Le CORS est restreint aux origines autorisées.

## 8. Tests

Tests unitaires backend :

cd backend
./mvnw test


Tests unitaires frontend :

cd frontend
pnpm test


Tests end-to-end et accessibilité (Playwright avec axe) :

cd frontend
pnpm test:e2e


La couverture minimale obligatoire est de 80 %, vérifiée par SonarQube dans la pipeline.

## 9. Qualité et sécurité

Qualité :

- SonarLint dans l'IDE, avant commit ;
- ESLint (règles Vue / TypeScript et règles d'accessibilité), Prettier pour le formatage ;
- SonarQube en CI, avec Quality Gate bloquante.

Sécurité :

- scan des dépendances Maven / npm et des secrets avec Trivy, en pipeline ;
- validation des entrées, rate limit sur les endpoints, erreurs sans stack trace ;
- revue de code : chaque MR vérifie les accès, secrets, dépendances, données, API et erreurs.

## 10. Accessibilité et éco-conception

Accessibilité : l'interface suit les bonnes pratiques du référentiel RGAA (HTML sémantique, navigation au clavier, focus visible, labels explicites, alternatives textuelles, contrastes lisibles). Contrôles : ESLint a11y en local, Playwright avec axe et Lighthouse en CI, puis WAVE et Accessibility Insights avec contrôle humain avant recette.

Éco-conception : l'application est conçue pour être sobre. Les mesures s'appuient sur GreenIT-Analysis (EcoIndex), l'onglet Network, Performance et Memory des outils de développement, et Lighthouse. Pour des mesures comparables, vider le cache du navigateur avant chaque analyse.

## 11. Workflow Git et merge requests

Branches :

- main : production ;
- develop : développement et recette ;
- feature/* : créées depuis develop.

Règles :

- toute évolution passe par une Merge Request dont la cible est develop ;
- pas de commit direct sur main ou develop (sauf hotfix) ;
- la recette se fait sur develop avant la fusion vers main.

Titre de MR : référence Jira en tête, par exemple `PROXXI-123-Add-authentication`. La description renvoie au ticket Jira et contient les captures d'écran avant / après pour les modifications front-end.

Definition of Ready : ticket Jira existant, besoin compris, critères d'acceptation définis, informations disponibles, aucune question bloquante.

Definition of Done : code conforme aux standards (qualité, sécurité, accessibilité, éco-conception), testé sur ordinateur et téléphone, MR revue, déployée et validée en recette, documentation à jour.

## 12. CI/CD et déploiement

Pipeline CI (GitLab CI) : lint et type-check, tests unitaires et e2e, accessibilité, analyse SonarQube avec Quality Gate, scan Trivy.

Déploiement : construction des images avec JIB (backend) et Nginx (frontend), publication, puis synchronisation par ArgoCD sur Kubernetes à partir de Helm Charts. Un déploiement est déclenché par un tag GitLab, créé une fois les tests OK et Trivy sans faille critique. Back et front se synchronisent indépendamment.

En cas d'échec visible dans les logs : corriger sur une branche dédiée, fusionner dans develop, puis créer un nouveau tag. Les tentatives automatiques du Build peuvent retarder l'affichage de l'erreur de quelques minutes.

## 13. Documentation

- Cahier des charges complet : [cachier-des-charges.md](docs/01-contexte/cachier-des-charges.md)
- Personas : dossier [Personas](docs/00-/Personas)
- Modèle de données (MCD, MLD, MPD) : [MLD_MCD_MPD](docs/03-conception/MLD_MCD_MPD)
- Maquettes et wireframes : [maquettes](docs/03-conception/maquettes)
- Documentation d'équipe et onboarding : espace Confluence

## 14. Contribuer

1. Créer ou récupérer un ticket Jira qui respecte la Definition of Ready.
2. Créer une branche `feature/` depuis develop.
3. Développer en respectant la Definition of Done.
4. Ouvrir une Merge Request vers develop avec le titre et la description attendus.
5. Attendre la validation de la pipeline.

## 15. Contact

Amandine Delbouve (Kemp), développeuse

- GitHub : https://github.com/amandinekemp
- LinkedIn : https://www.linkedin.com/in/amandinedelbouve/
