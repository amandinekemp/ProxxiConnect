# Expression du besoin

> **En une phrase :** les Proxxi doivent pouvoir suivre facilement les collaborateurs qui leur sont attribués, pour repérer les situations à risque **avant qu'il ne soit trop tard**.

Ce document explique **pourquoi** ProxxiConnect existe, **pour qui**, et **quelles contraintes** il doit respecter. Il ne décrit pas *comment* l'outil fonctionne : c'est le rôle des [spécifications](../03-conception/specifications.md) et du [cahier des charges complet](cachier-des-charges.md).

---

## 1. Le problème aujourd'hui

Les échanges entre les Proxxi et les collaborateurs existent déjà, mais ils sont **informels et dispersés**. Résultat :

| Situation actuelle | Conséquence concrète |
|---|---|
| Pas de rappel pour les Proxxi | Un rendez-vous obligatoire peut être oublié |
| Informations dispersées | Impossible de retrouver l'historique d'un échange |
| Aucune vision globale | Les administrateurs ne voient pas l'état du dispositif |
| Pas de statistiques fiables | Le pilotage RH repose sur des impressions |

> **Pourquoi c'est grave ?** Un collaborateur qui n'est pas suivi peut se retrouver isolé, démotivé, voire en situation de burn-out, sans que personne ne s'en aperçoive assez tôt.

---

## 2. Le besoin

Le besoin est formulé du point de vue de l'utilisateur, en une phrase :

> *« Suivre facilement ses collaborateurs, pour détecter les situations à risque avant qu'il ne soit trop tard. »*

Pour y répondre, l'outil doit permettre de :

- **enregistrer** chaque échange ;
- **historiser** les rencontres ;
- **centraliser** les comptes rendus ;
- **prioriser** les collaborateurs à suivre ;
- **suivre** les obligations annuelles (au minimum 3 rencontres par exercice fiscal) ;
- **suivre** les obligations internes liées aux primes.

---

## 3. Les personnes concernées

ProxxiConnect a **trois profils** d'utilisateurs. Un seul d'entre eux se connecte réellement à l'application.

| Profil | Qui ? | Ce qu'il fait dans l'outil | Accès |
|---|---|---|---|
| **Administrateur** | Sunita, Christophe, Cédric | Pilote le dispositif, gère les affectations, consulte les statistiques |  Global |
| **Proxxi** | Par exemple Laura | Organise les rendez-vous, remplit les questionnaires |  Ses collaborateurs uniquement |
| **Collaborateur** | Par exemple Julien | **Ne se connecte pas.** Il est suivi, et ses informations sont saisies par le Proxxi |  Aucun |

Pour mieux comprendre ces profils, trois personas ont été rédigés :

- [Persona 1 : Sunita](../00-/Personas/Persona_1_Sunita.md), responsable du suivi, qui pilote les indicateurs globaux ;
- [Persona 2 : Laura](../00-/Personas/Persona_2_Laura.md), Proxxi pour qui **l'accessibilité** est un enjeu clé ;
- [Persona 3 : Julien](../00-/Personas/Persona_3_Julien.md), collaborateur suivi, qui n'utilise pas l'application.

> Pour une fonctionnalité, se demander *« pour quel persona est-ce ? »*. Cela évite de construire des écrans que personne n'utilisera.

---

## 4. Les contraintes à respecter

Certaines contraintes ne sont pas négociables. Elles conditionnent toutes les décisions techniques.

| Contrainte | Ce que cela signifie concrètement |
|---|---|
|  **Accès mobile** | L'outil doit fonctionner correctement sur téléphone (approche *mobile-first*) |
|  **Simplicité d'utilisation** | Un Proxxi doit pouvoir saisir un questionnaire sans formation lourde |
|  **Centralisation des données** | Une seule source de vérité, pas de fichiers Excel parallèles |
|  **Historisation des échanges** | Rien n'est écrasé : on garde la trace de ce qui a été fait, et quand |
|  **Notifications automatiques** | Rappels et alertes envoyés sans intervention humaine |
|  **Conservation des données** | Les données sont conservées pendant **5 ans** |

---

## 5. Ce qui est hors périmètre (pour l'instant)

Le MVP (*Minimum Viable Product*, la première version utile) se limite volontairement au strict nécessaire. Les autres fonctionnalités sont classées avec la méthode **MoSCoW** :

| Priorité | Signification | Éléments |
|---|---|---|
| **Must Have** | Indispensable à la mise en production | Connexion Google, gestion des Proxxi et collaborateurs, questionnaire, alertes, rappels, suivi des 3 RDV |
| **Should Have** | Important, à faire après le MVP | Conservation des données, tableau de bord, statistiques |
| **Could Have** | Souhaitable si le temps le permet | Export PowerPoint `.pptx` |
| **Won't Have** | Pas pour l'instant | Gestion des actions traitées / non traitées, comparaison entre exercices fiscaux |

---

## 6. Glossaire rapide

| Terme | Définition simple |
|---|---|
| **Proxxi** | Personne qui assure le suivi humain d'un ou plusieurs collaborateurs |
| **Collaborateur** | Salarié en mission chez un client ou au centre de services (CDS). Il n'utilise pas l'application |
| **Rendez-vous (RDV)** | Rencontre entre un Proxxi et un collaborateur (restaurant, site client ou visio) |
| **Questionnaire** | Formulaire standardisé rempli après un rendez-vous. Il est verrouillé une fois validé |
| **Météo du suivi** | Ressenti déclaratif du collaborateur : Ensoleillé, Pluvieux, Tornade ou Glacial |
| **Exercice fiscal** | Période du **1er août N-1 au 31 juillet N** |
| **MVP** | Première version livrable, limitée au strict nécessaire |

---

> **Pour aller plus loin :** [Cahier des charges complet](cachier-des-charges.md) · [Spécifications fonctionnelles](../03-conception/specifications.md) · [Organisation du projet](../02-gestion-projet/organisation.md)
