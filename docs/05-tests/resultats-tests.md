# Résultats des tests

Ce document **enregistre ce qui a été réellement testé**, par qui, sur quelle version, et avec quel résultat. C'est la preuve que l'application a été vérifiée avant chaque mise en production.

> ⚠️ **État actuel :** aucune campagne n'a encore été exécutée. Le dépôt ne contient pas encore le code applicatif. Les tableaux ci-dessous sont des **modèles prêts à remplir**.

---

## 1. Légende des statuts

| Statut | Signification |
|---|---|
| **À faire** | Le test n'a pas encore été exécuté |
| **Validé** | Le résultat est conforme au résultat attendu |
| **Partiel** | Le résultat est globalement conforme, avec une réserve notée |
| **Échec** | Le résultat n'est pas conforme. Une anomalie doit être ouverte |

---

## 2. Gravité des anomalies

| Gravité | Définition | Exemple | Bloque la mise en production ? |
|---|---|---|---|
| **Bloquante** | L'application ne peut pas être utilisée, ou une donnée est exposée | Un Proxxi voit les collaborateurs d'un autre | Oui |
| **Majeure** | Une fonctionnalité essentielle ne marche pas correctement | Le questionnaire ne s'envoie pas | Oui |
| **Mineure** | Un défaut gênant, mais contournable | Un message d'erreur mal formulé | Non |
| **Cosmétique** | Un défaut visuel sans impact sur l'usage | Un décalage de quelques pixels | Non |

> **Règle du cahier des charges :** la mise en production n'est possible que si **aucun bug n'est présent**, ou si les anomalies détectées ont été corrigées.

---

## 3. Campagne de tests

### 3.1 Informations générales

| Champ | Valeur |
|---|---|
| **Numéro de campagne** | `CAMP-01` |
| **Date d'exécution** | *JJ/MM/AAAA* |
| **Version testée** | *tag GitLab, par exemple `v0.1.0`* |
| **Environnement** | Recette / Local |
| **Testeur** | *Nom de la personne* |
| **Navigateur et appareil** | *Ex. : Chrome 130, Windows 11 / Android 15* |

### 3.2 Résultats par scénario

| ID | Scénario | Statut | Commentaire | Anomalie |
|---|---|---|---|---|
| T-01 | Connexion avec un compte du domaine autorisé |  | | |
| T-02 | Connexion avec un compte hors domaine |  | | |
| T-03 | Un Proxxi consulte sa liste de collaborateurs |  | | |
| T-04 | Accès direct à un collaborateur non attribué |  | | |
| T-05 | Attribution d'un collaborateur à un Proxxi |  | | |
| T-06 | Un seul Proxxi actif par collaborateur |  | | |
| T-07 | Saisie complète d'un questionnaire |  | | |
| T-08 | Validation avec champ obligatoire manquant |  | | |
| T-09 | Validation définitive d'un questionnaire |  | | |
| T-10 | Modification d'un questionnaire validé |  | | |
| T-11 | Alerte envoyée aux administrateurs |  | | |
| T-12 | Doublon refusé (même date, même personne) |  | | |
| T-13 | Alerte pour un collaborateur sans Proxxi |  | | |
| T-14 | Relance 2 mois après une rencontre |  | | |
| T-15 | Statistiques par exercice fiscal |  | | |
| T-16 | Parcours complet sur téléphone |  | | |
| T-17 | Questionnaire utilisable au clavier |  | | |

### 3.3 Synthèse

| Indicateur | Résultat |
|---|---|
| Scénarios exécutés | *0 / 17* |
| Validés | *0* |
| Partiels ⚠️ | *0* |
| Échecs | *0* |
| Anomalies ouvertes | *0* |
| **Décision** | *En attente d'exécution* |

> **Décision de mise en production :** elle n'est possible que si tous les scénarios sont validés et qu'aucune anomalie bloquante ou majeure n'est ouverte.

---

## 4. Journal des anomalies

Chaque anomalie reçoit un identifiant, est liée à son ticket Jira et à son scénario de test.

| ID | Jira | Scénario | Gravité | Description | Statut de correction |
|---|---|---|---|---|---|
| *BUG-001* | *PROXXI-XXX* | *T-xx* | */ / / * | *Ce qui est observé, et ce qui était attendu* | *Ouverte / En cours / Corrigée / Vérifiée* |

### Comment bien décrire une anomalie

Une bonne anomalie permet à quelqu'un d'**autre** de la reproduire sans vous poser de question. Elle contient :

1. **Le contexte** : version, navigateur, appareil, compte utilisé ;
2. **Les étapes** : ce qu'il faut faire, dans l'ordre ;
3. **Le résultat observé** : ce qui se passe ;
4. **Le résultat attendu** : ce qui devrait se passer, avec la référence à la [spécification](../03-conception/specifications.md) ;
5. **Une capture d'écran** ou le message d'erreur exact.

> **Exemple :**
> *Contexte : version v0.1.0, Chrome sur Android, compte Proxxi.*
> *Étapes : ouvrir le questionnaire de Julien, laisser « Météo » vide, cliquer sur « Valider ».*
> *Observé : le formulaire est envoyé et une erreur 500 s'affiche.*
> *Attendu : le formulaire n'est pas envoyé et le champ « Météo » est signalé (T-08, réf. F-06).*

---

## 5. Historique des campagnes

| Campagne | Date | Version | Validés | Échecs | Décision |
|---|---|---|---|---|---|
| CAMP-01 | *à venir* | *à venir* | | | |

---

> **Pour aller plus loin :** [Plan de tests](plan-tests.md) · [Spécifications](../03-conception/specifications.md) · [Déploiement](../06-deploiement/deploiement.md)
