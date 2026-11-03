#  Éco-conception et performance

L'**éco-conception** consiste à réduire l'impact environnemental d'un service numérique **pendant tout son cycle de vie** : Extraction, fabrication, usage, transport, fin de vie.

Pour ProxxiConnect, l'objectif est simple : **une application plus sobre, qui reste agréable à utiliser**.

>  **Le réflexe à garder :** chaque octet envoyé, chaque requête et chaque calcul inutile consomme de l'énergie, sur le serveur comme sur le téléphone de l'utilisateur. Moins on en envoie, mieux c'est, pour l'environnement comme pour la vitesse.

---

## 1. Les notions de base

### 1.1 Le cycle de vie d'un service numérique

Un service numérique ne se résume pas à l'application. Il comprend du **logiciel**, du **matériel** et de l'**infrastructure**. Son cycle de vie compte cinq phases :

1. Extraction des matières premières
2. Fabrication
3. Distribution (transport)
4. Utilisation
5. Fin de vie ou valorisation

**Règle générale : la fabrication pèse souvent plus lourd que l'utilisation.**

| Appareil | Phase la plus impactante |
|---|---|
| Smartphone | Fabrication (environ **85 %** de l'impact) |
| PC fixe | Utilisation (environ **75 %** de l'impact) |

>  Un PC fixe a moins d'impact qu'un portable, notamment parce qu'il n'embarque pas de batterie.

### 1.2 L'ACV : une analyse multicritère

L'**ACV** (Analyse du Cycle de Vie) évalue les impacts environnementaux d'un service sur **tout** son cycle de vie, avec une approche **multicritère** : gaz à effet de serre, eau, énergie, ressources minérales, etc.

> ⚠️ Un impact environnemental ne se résume **jamais à un seul chiffre**.

### 1.3 L'unité fonctionnelle (UF)

L'UF est le **périmètre précis de mesure**. Au lieu d'analyser le service entier, on mesure une **action reproductible**.

- **Forme attendue :** sujet + verbe + complément. Exemples : « réserver un billet Marseille → Nantes », « acheter un produit en ligne ».
- **Pourquoi la précision compte :** une UF vague donne une mesure peu fiable.
- **Correspondance :** une UF correspond en général à un **parcours utilisateur**.

Pour ProxxiConnect, trois UF possibles :

| UF | Acteur | Fréquence indicative |
|---|---|---|
| Consulter la liste de ses collaborateurs | Proxxi | *à estimer* |
| Remplir un questionnaire de suivi | Proxxi | *à estimer* |
| Consulter le tableau de bord des statistiques | Administrateur | *à estimer* |

### 1.4 Le flux de référence

Le **flux de référence** est le nombre d'utilisations du service sur une durée donnée (par exemple, le nombre de visiteurs par heure). Il permet de passer d'une mesure **par page** à une estimation **par jour** et **par mois**.

> Exemple : un flux de 320 visiteurs par heure donne **320 × 24** visites par jour.

---

## 2. Pourquoi c'est important ici ?

| Constat | Conséquence pour ProxxiConnect |
|---|---|
| L'application est utilisée **sur mobile**, parfois avec une connexion faible | Les pages doivent être légères et rapides |
| Les Proxxi consultent l'outil **souvent** | Chaque requête inutile se répète des centaines de fois |
| L'application tourne **en continu** sur un cluster | Un service plus léger consomme moins de serveurs |
| Les données sont **conservées 5 ans** | Stocker ce qui est inutile coûte de la place, donc de l'énergie |

---

## 3. Les 3 piliers du développement durable

| Pilier | Ce que ça veut dire | Pour ProxxiConnect |
|---|---|---|
| **Social** (*IT for Good*) | Le numérique doit être utile aux personnes : conditions de travail, accessibilité, éthique, vie privée | Accessibilité RGAA, protection des données personnelles |
| **Environnemental** (*IT for Green*) | Réduire l'impact du numérique | Sobriété des pages, serveurs et données |
| **Économique** | Économie de la fonctionnalité : louer plutôt qu'acheter, économie circulaire | Allonger la durée de vie des appareils des utilisateurs |

### Les « SOS » : les freins à l'éco-conception

- **S**urconsommation : le numérique pousse à consommer toujours plus de matériel et de services.
- **O**bsolescence programmée : des appareils de plus en plus difficiles à réparer, reconditionner ou recycler.
- **S**ensibilisation : beaucoup d'équipes ignorent l'impact carbone de leur organisation.

---

## 4. Les 5 actions appliquées à ProxxiConnect

La démarche d'éco-conception repose sur **cinq actions**. Voici comment elles se traduisent pour ce projet.

| # | Action | Application à ProxxiConnect |
|---|---|---|
| 1 | **Conduire une ACV numérique** | Définir les UF (section 1.3), puis analyser les phases matériel, hébergement et usage |
| 2 | **Cadrer le projet** | Sensibiliser l'équipe et les administrateurs, fixer une stratégie et des axes précis |
| 3 | **Élaborer un référentiel** | Choisir les bonnes pratiques retenues (section 5), fixer un "budget" environnemental |
| 4 | **Optimiser le service** | Appliquer les bonnes pratiques dans le code, puis les valider par des tests |
| 5 | **Mesurer l'empreinte** | Mesurer avant et après chaque optimisation, puis suivre l'évolution dans le temps |

>  **Mémo :** *Analyser → Cadrer → Référentiel → Optimiser → Mesurer.*

> ⚠️ **Piège :** l'éco-conception ne se fait pas seul. Elle demande la participation de toute l'équipe.

---

## 5. Référentiels et cadre réglementaire

### 5.1 Ne pas partir de zéro

Il existe déjà de nombreux référentiels. Il ne faut pas tous les lire en détail : on retient **4 à 5 bonnes pratiques par référentiel**, en s'appuyant sur leurs mots-clés.

| Référentiel | Ce que c'est |
|---|---|
| **RGESN** | Référentiel Général d'Écoconception de Services Numériques, mis en place par l'État |
| **115 bonnes pratiques GreenIT** | Bonnes pratiques d'éco-conception web, portées par le collectif GreenIT |
| **74 bonnes pratiques GreenIT** | Bonnes pratiques sur le matériel |
| **GR491** | Référentiel de l'INR sur l'éco-conception |
| **AFNOR Spec 2201** | Guide de référence pour écoconcevoir des services numériques |
| **RGAA** | Référentiel d'accessibilité numérique |
| **Checklists Opquast** | Bonnes pratiques de qualité numérique |

**Liens utiles :**
- [Référentiel général d'écoconception (RGESN)](https://ecoresponsable.numerique.gouv.fr/publications/referentiel-general-ecoconception/)
- [R-Web GreenIT](https://rweb.greenit.fr/)
- [GR491](https://gr491.isit-europe.org/)
- [Checklists Opquast](https://checklists.opquast.com/fr/qualite-numerique/)

### 5.2 Le cadre légal

| Loi | Contenu clé |
|---|---|
| **Loi transition énergétique** | Peines prévues pour l'obsolescence programmée |
| **Loi AGEC** | Indice de réparabilité (2022), indice de durabilité (2024), extension de garantie, pièces détachées disponibles |
| **Loi Climat et Résilience** (2021) | Affichage environnemental fondé sur une ACV multicritère |
| **Loi REEN** (2021) | Réduction de l'empreinte numérique, sensibilisation, formation à l'ACV, référentiel RGESN |

### 5.3 Le budget environnemental

Avant d'optimiser, on fixe un **"budget" environnemental** : la limite d'impact que le service s'engage à ne pas dépasser, puis un **plan d'action** pour s'en approcher.

---

## 6. Les bonnes pratiques appliquées au projet

| Domaine | Bonne pratique | Application concrète |
|---|---|---|
|  **Images** | Des images légères et au bon format | Compression, format moderne (WebP), dimensions adaptées à l'écran |
|  **Code** | N'envoyer que ce qui est utilisé | Découpage par écran (*code splitting*) et suppression du code mort (*tree shaking*), via Vite |
|  **Code** | Ne pas réécrire ce qui existe déjà | Principe **DRY** (*Don't Repeat Yourself*) : factoriser plutôt que dupliquer |
|  **Code** | Garder le code simple | Principe **KISS** (*Keep It Simple, Stupid*) : du code simple consomme moins de ressources |
|  **API** | Limiter les appels | Mise en cache d'environ **1 minute** pour les appels Google, pagination des listes, optimisation des requêtes |
|  **Données** | Ne garder que le nécessaire | Purge automatique après 5 ans (RG-05) |
|  **Interface** | Sobriété visuelle | Pas de vidéo ni d'animation lourde en arrière-plan |
|  **Responsive** | Une seule base de code adaptée à tous les écrans | Design responsive optimisé, *mobile-first* |
|  **Chargement** | Charger à la demande | *Lazy loading* des images hors écran |
|  **Réseau** | Compresser les échanges | Compression gzip ou Brotli côté Nginx *(à valider)* |
|  **Mémoire** | Ne pas laisser de ressources ouvertes | Surveillance de l'onglet Memory pour détecter les fuites |

>  **Règle simple :** avant d'ajouter une dépendance, demandez-vous : *« Est-ce que je peux faire la même chose avec le navigateur ou du code de quelques lignes ? »*

>  **Ordre de priorité conseillé :** commencer par les optimisations **légères à fort impact** (lazy loading, images, responsive), avant les refontes d'architecture.

---

## 7. Les principes du Green Software

Les principes ci-dessous sont issus de la formation (Microsoft Learn et Green Software Foundation). Ils donnent le « pourquoi » des bonnes pratiques.

| Principe | À retenir |
|---|---|
| **1. Efficacité carbone** | Émettre le moins de CO₂ possible pour une tâche donnée. Un ordinateur consomme dès qu'il est allumé |
| **2. Électricité** | L'électricité n'est pas « propre » par défaut. Énergie (kWh) = Puissance (W) × Temps |
| **3. Intensité carbone** | CO₂ émis par kWh, variable selon le lieu et l'heure. Des outils comme [Electricity Maps](https://www.electricitymaps.com/) la visualisent |
| **4. Carbone incorporé** | Pollution de la fabrication et de la fin de vie, même pour un appareil peu utilisé |
| **5. Proportionnalité énergétique** | Un serveur est plus efficace quand il est bien utilisé. Il consomme même à vide |
| **6. Réseau** | Chaque donnée transférée émet du CO₂. Le mobile consomme environ **deux fois plus** que le filaire |
| **7. Demand shaping** | Adapter la demande à l'énergie disponible (ex. : réduire la qualité vidéo en visio) |
| **8. Éco-modes** | Souvent des compromis entre performance et économie. L'éco-conception est une **somme** d'optimisations |

>  Dans le langage courant, « carbone » désigne ici le **CO₂ équivalent** (le gaz à effet de serre), et non l'élément chimique.

>  **Conséquence directe pour ProxxiConnect :** moins de données transférées et moins de calculs CPU signifient moins d'énergie consommée, et des appareils des utilisateurs qui durent plus longtemps.

---

## 8. Les outils de mesure

Pour éco-concevoir, il faut **mesurer pour mieux optimiser**. Les outils se répartissent en trois familles : les extensions de navigateur, les plateformes en ligne, et les outils intégrés au code.

### 8.1 GreenIT-Analysis : l'extension de référence

**GreenIT-Analysis** est la référence historique en France (collectif GreenIT). Elle fournit :

- un indice **EcoIndex**, noté de **A à G** ;
- des mesures de **gaz à effet de serre**, de **DOM** et de consommation d'eau ;
- la liste des **bonnes pratiques non respectées**.

### 8.2 L'onglet Network : le poids du réseau

Mesure l'impact sur le **réseau** (bande passante) et les serveurs. C'est le **premier levier**, car le transfert de données est très énergivore.

- **Traquer les images lourdes :** trier la colonne *Size* par ordre décroissant. Une image de **plus de 200 Ko** doit être optimisée.
- **Vérifier les requêtes inutiles :** repérer les scripts tiers (trackers, polices non utilisées) à supprimer.

### 8.3 L'onglet Performance : l'effort du processeur

Mesure l'effort demandé au **CPU** de l'utilisateur. Un site qui fait chauffer un smartphone pousse au renouvellement prématuré du matériel.

**Procédure :**
1. Lancer l'enregistrement, faire défiler la page ou cliquer sur un élément, puis arrêter ;
2. Analyser la piste **Main** : les blocs **jaunes** (*Scripting*) et **violets** (*Rendering*) ;
3. Lire le camembert **Summary** (en bas) : si le jaune domine alors que le site est statique, le JavaScript consomme trop.

Un JavaScript qui tourne en continu alors que l'utilisateur ne fait rien est une **« passoire énergétique »**.

**Options utiles :**

| Option | À quoi elle sert |
|---|---|
| **CPU Throttling** (« 4x » ou « 6x slowdown ») | Simule un smartphone d'entrée de gamme. Si le site rame, le code n'est pas éco-conçu |
| **Screenshots** | Relie un pic de CPU à un événement visuel (ex. : un carrousel qui défile) |
| **Memory** | Ajoute le graphique de la RAM pendant l'enregistrement |
| **Dim 3rd parties** | Grise les scripts externes (réseaux sociaux, analytics, bandeaux cookies). Permet de juger si ces scripts sont vraiment utiles |

### 8.4 L'onglet Memory : la mémoire vive

Surveille la RAM du terminal. Une application qui consomme trop de RAM ralentit l'appareil et réduit l'autonomie de la batterie.

**Détecter une fuite de mémoire :**
1. Prendre un **heap snapshot** (instantané) ;
2. Naviguer sur le site, puis revenir à la page de départ ;
3. Reprendre un instantané.

Si la mémoire a grimpé **sans redescendre**, du code mort reste stocké inutilement.

>  **Repère visuel :** une courbe qui monte en escalier sans jamais redescendre signale une fuite.

**Autre point :** un DOM trop complexe (trop de balises imbriquées) sature la mémoire.

### 8.5 Lighthouse : l'audit général

Lighthouse n'est pas purement « écologique », mais ses scores de **Performance** et de **Best Practices** sont directement liés à l'éco-conception.

- **Tester en mode Mobile :** le réseau est moins stable et le processeur plus faible.
- **Consulter la section Opportunities :** elle liste ce qu'il faut corriger pour économiser des ressources.
  - *Properly size images* : images trop grandes ;
  - *Defer offscreen images* : mettre en place le **lazy loading** ;
  - *Reduce unused JavaScript* : supprimer le **code mort**.
- **Vérifier le score d'accessibilité :** le RGESN et le RGAA partagent de nombreux critères. Un site accessible est souvent un site plus sobre.

---

## 9. Procédure de mesure pas à pas

Pour obtenir des résultats **comparables**, suivez toujours la même procédure.

**Mesure de chaque page (GreenIT-Analysis) :**
1. **Vider le cache** dans GreenIT-Analysis, via l'Inspector, pour simuler une première visite ;
2. Lancer l'analyse ;
3. **Sauvegarder** l'analyse, puis vérifier qu'elle apparaît dans l'historique ;
4. Répéter les étapes 1 à 3 pour **chaque étape** de l'UF (connexion, tableau de bord, questionnaire…).

**Mesures complémentaires :**
5. Ouvrir les DevTools (F12) : onglets Network, Performance et Memory, avec les options décrites en section 8 ;
6. Lancer **Lighthouse** en mode Mobile sur les pages principales ;
7. Reporter les résultats dans le tableur, par étape et dans l'ordre de l'UF.

**Calcul à partir du flux de référence :**
8. Définir le **flux de référence** (nombre de visiteurs par heure), à partir d'une estimation réaliste ;
9. Calculer les données **par jour** (flux × 24) et **par mois** ;
10. Calculer les **cumuls** (somme des GES et de l'eau), puis adapter les formules au flux retenu.

> ⚠️ **Important :** sans vider le cache, la deuxième mesure bénéficie des fichiers déjà téléchargés. Les chiffres ne sont alors pas comparables.

---

## 10. Tableau de suivi

Ce tableau est à compléter à chaque mesure. Il permet de voir si l'application s'améliore ou se dégrade.

| Date | Page | EcoIndex | Poids de la page | Requêtes | Images > 200 Ko | Lighthouse (performance) | Remarques |
|---|---|---|---|---|---|---|---|
| *JJ/MM/AAAA* | Connexion | *à mesurer* | *à mesurer* | *à mesurer* | *à mesurer* | *à mesurer* | |
| *JJ/MM/AAAA* | Tableau de bord | *à mesurer* | *à mesurer* | *à mesurer* | *à mesurer* | *à mesurer* | |
| *JJ/MM/AAAA* | Mes collaborateurs | *à mesurer* | *à mesurer* | *à mesurer* | *à mesurer* | *à mesurer* | |
| *JJ/MM/AAAA* | Questionnaire | *à mesurer* | *à mesurer* | *à mesurer* | *à mesurer* | *à mesurer* | |

>  **Objectifs chiffrés :** à fixer par l'équipe une fois les premières mesures disponibles.

>  **Mesure avant / après :** pour chaque optimisation, noter les valeurs avant et après, ainsi que le critère de réussite visé. C'est la seule façon de prouver qu'une optimisation a un effet.

---

## 11. Performance web : trois indicateurs clés

Les **Core Web Vitals** reflètent l'expérience réelle de l'utilisateur.

| Indicateur | Ce qu'il mesure | Question de l'utilisateur | Seuil « bon » recommandé par Google |
|---|---|---|---|
| **LCP** (*Largest Contentful Paint*) | Le temps d'affichage du contenu principal | *« Est-ce que la page s'affiche vite ? »* | ≤ 2,5 s |
| **INP** (*Interaction to Next Paint*) | Le temps de réaction après un clic ou une saisie | *« Est-ce que ça réagit vite quand je touche ? »* | ≤ 200 ms |
| **CLS** (*Cumulative Layout Shift*) | La stabilité visuelle pendant le chargement | *« Est-ce que les éléments bougent sous mes yeux ? »* | ≤ 0,1 |

>  **Exemple de CLS élevé :** vous voulez cliquer sur « Valider », mais une bannière apparaît au dernier moment et le bouton se décale. Vous cliquez sur autre chose. C'est très frustrant, surtout sur mobile.

**Points de vigilance :**
- temps de réponse de l'API ;
- poids des fichiers JavaScript, CSS et images ;
- code inutile ;
- traitements lourds sur le thread principal (ce qui fige l'écran) ;
- absence de cache et appels API non limités.

---

## 12. Obsolescence et durée de vie

Allonger la durée de vie des appareils est l'un des leviers les plus efficaces.

- Un ordinateur dure aujourd'hui **4 à 6 ans**, contre **10 à 15 ans** en 1985.
- Passer de **2 à 4 ans** d'utilisation améliore l'impact d'environ **+50 %**.
- Une page web est passée de **13 Ko en 1995** à environ **2 000 Ko en 2022**. Les logiciels trop lourds poussent au renouvellement.

**Les types d'obsolescence évoqués :** incompatibilité logicielle, fragilisation des composants, esthétique, cycles de renouvellement accélérés, panne programmée, désinformation, obsolescence logicielle (mises à jour qui ralentissent), suppression des pièces détachées.

>  **Question à se poser pour chaque écran :** cette page apporte-t-elle plus que la même information dans une version plus jolie ? Est-elle nécessaire ? Son impact sur la RAM est-il justifié ?

---

## 13. Éviter le greenwashing

Le **greenwashing** (« lessivage vert ») consiste à donner une image écologique à un produit ou un service sans que ce soit justifié.

Pour ProxxiConnect, on évite ce piège en :
- ne communiquant que sur des **mesures vérifiables** (EcoIndex, poids, requêtes, avant / après) ;
- **sourçant** chaque chiffre ;
- ne revendiquant pas d'être « vert » sans avoir mesuré.

---

## 14. Intégrer l'éco-conception dans le travail quotidien

L'éco-conception ne se fait pas à la fin. Elle fait partie de la **Definition of Done** : une fonctionnalité qui alourdit fortement une page n'est pas considérée comme terminée.

- [ ] La nouvelle page ou fonctionnalité a été mesurée avec GreenIT-Analysis ;
- [ ] Aucune image non optimisée n'a été ajoutée ;
- [ ] Aucune dépendance lourde n'a été ajoutée sans justification ;
- [ ] Les appels API sont limités (pas de requête répétée inutilement) ;
- [ ] Le code inutilisé a été supprimé ;
- [ ] Les mesures avant / après sont notées dans le tableau de suivi.

---

## 15. Accessibilité et sobriété : deux qualités liées

Une interface **sobre** est souvent plus **accessible** : moins d'éléments décoratifs, un contenu structuré, des libellés clairs. Les deux démarches se renforcent.

>  Les règles d'accessibilité sont détaillées dans le [plan de tests](../05-tests/plan-tests.md#5-les-tests-manuels) et dans la [sécurité](../04-securite/securite.md).

---

## 16. Points à retenir

1. **Unité fonctionnelle** = un parcours utilisateur précis et reproductible.
2. **Fabrication et extraction** pèsent souvent plus que l'utilisation.
3. **Réutiliser les référentiels existants** (RGESN, GreenIT, RGAA) plutôt que partir de zéro.
4. **Mesurer avant et après**, avec la même procédure à chaque fois.
5. **KISS et DRY** : un code simple et sans duplication consomme moins.
6. **Tests réguliers** pour valider les optimisations et suivre l'amélioration continue.

---

## 17. Ressources

- **GreenIT-Analysis** : extension Chrome, à rechercher par son nom sur le Chrome Web Store ;
- [impactco2.fr](https://impactco2.fr/outils/usagenumerique) : outil de sensibilisation à l'impact du numérique ;
- [Green Software Foundation : patterns](https://patterns.greensoftware.foundation/) : catalogue de patterns d'éco-conception logicielle ;
- [Electricity Maps](https://www.electricitymaps.com/) : intensité carbone de l'électricité par région ;
- **Cahier des charges**, section 16 : [cachier-des-charges.md](../01-contexte/cachier-des-charges.md#16-numérique-responsable).

---

>  **Pour aller plus loin :** [Spécifications](../03-conception/specifications.md) · [Architecture](../03-conception/architecture.md) · [Plan de tests](../05-tests/plan-tests.md)
