# Kotlin Apps

Dépôt de projets Android développés avec Kotlin et Jetpack Compose. Chaque application démontre des concepts spécifiques du développement Android moderne avec Material Design 3.

## Vue d'ensemble

Ce dépôt comprend dix applications Android, organisées par catégories selon les concepts abordés :
- **Bases** : Gestion d'état basique, layout et composition
- **Gestion d'état** : États multi-étapes, saisie utilisateur et calculs
- **Listes et données** : Affichage de listes, classes de données et chargement paresseux
- **Architecture** : Cycle de vie Android, Architecture Components (ViewModel, StateFlow)
- **Coroutines** : Programmation asynchrone avec Kotlin Coroutines
- **Réseau** : Appels réseau REST, sérialisation JSON et chargement d'images depuis Internet

## Structure du dépôt

Les projets sont organisés dans les dossiers suivants :

```
ktolin-apps/
├── 00-works/              # Ressources pédagogiques et révision
│   ├── Kotlin-Android.md  # Cours de révision complet pour QCM
│   ├── lessons/           # Supports de cours (PDF)
│   └── quizz/             # Quiz de révision (PDF)
├── 01-basics/              # Projets de base
│   ├── DiceRoller/
│   └── HappyBirthday/
├── 02-state-management/   # Gestion d'état avancée
│   ├── Lemonade/
│   └── TipTime/
├── 03-lists-and-data/     # Listes et données
│   ├── Affirmations/
│   └── Woof/
├── 04-architecture/       # Architecture Android
│   ├── Dessert Clicker/
│   └── Unscramble/
├── 05-coroutines/         # Coroutines Kotlin
│   └── Race Tracker/
└── 06-network/            # Réseau et API
    └── Mars Photos/
```

## Ressources pédagogiques

### 00-works/ - Révision et supports de cours

Ce dossier contient toutes les ressources pédagogiques pour réviser et préparer les examens :

#### Kotlin-Android.md

Cours de révision complet et concis pour QCM couvrant tous les concepts du développement Android avec Kotlin et Jetpack Compose.

**Contenu :**
- **Bases de Kotlin** : Opérateurs, types de données, nullabilité, fonctions, classes et objets
- **Première application Android** : Structure de projet, Activity, cycle de vie, Jetpack Compose
- **Gestion d'état** : `remember`, `mutableStateOf`, `rememberSaveable`
- **Listes et données** : Data classes, `LazyColumn`, composants Material
- **Architecture** : ViewModel, StateFlow, cycle de vie Android
- **Coroutines** : Fonctions suspendues, `launch`, `LaunchedEffect`, exécution concurrente
- **Réseau** : Retrofit, sérialisation JSON, Coil, gestion d'erreurs
- **Points clés pour QCM** : Résumé des concepts essentiels
- **Formulaire rapide** : Syntaxe essentielle avec exemples

**Format :** Chaque concept est accompagné d'exemples courts et concrets pour faciliter la compréhension et la mémorisation.

**Emplacement :** `00-works/Kotlin-Android.md`

#### lessons/

Contient les supports de cours originaux au format PDF :
- Introduction au développement Android
- Bases de Kotlin (opérateurs, fonctions, classes)
- Création d'applications Android
- Interfaces avancées avec Compose
- Architecture Android
- Accès Internet et coroutines
- Persistance de données

**Emplacement :** `00-works/lessons/`

#### quizz/

Contient les quiz de révision au format PDF pour chaque module :
- Quiz sur les bases de Kotlin
- Quiz sur la première application Android
- Quiz sur les interfaces avancées
- Quiz sur l'architecture Android
- Quiz sur l'accès Internet et le chargement d'images

**Emplacement :** `00-works/quizz/`

## Projets inclus

### 01-basics/ - Projets de base

#### DiceRoller

Application de lancer de dé interactive démontrant la gestion d'état basique dans Jetpack Compose.

- **Fonctionnalités** : Lancer un dé à 6 faces avec retour visuel, génération de nombres aléatoires
- **Concepts clés** : Gestion d'état avec `remember` et `mutableStateOf`, composables Image, interactions de boutons
- **Technologies** : Kotlin, Jetpack Compose, Material Design 3
- **Min SDK** : 24 | **Target SDK** : 36 | **Compile SDK** : 36
- **Emplacement** : `01-basics/DiceRoller/`

#### HappyBirthday

Application de carte d'anniversaire personnalisée illustrant la composition d'images et la mise en page de texte dans Compose.

- **Fonctionnalités** : Message d'anniversaire personnalisable, image de fond avec superposition, style de texte
- **Concepts clés** : Composables Image, style de texte, composition de layout (Box, Column), mise à l'échelle du contenu
- **Technologies** : Kotlin, Jetpack Compose, Material Design 3
- **Min SDK** : 24 | **Target SDK** : 36 | **Compile SDK** : 36
- **Emplacement** : `01-basics/HappyBirthday/`

### 02-state-management/ - Gestion d'état avancée

#### Lemonade

Application de simulation de fabrication de limonade démontrant la gestion d'état multi-étapes et les flux d'interaction utilisateur.

- **Fonctionnalités** : Processus de fabrication de limonade étape par étape (sélectionner, presser, boire, redémarrer), nombre de pressions aléatoire, retour visuel
- **Concepts clés** : Gestion d'état multi-étapes, composables Clickable, transitions d'état, Scaffold et TopAppBar
- **Technologies** : Kotlin, Jetpack Compose, Material Design 3
- **Min SDK** : 24 | **Target SDK** : 35 | **Compile SDK** : 35
- **Emplacement** : `02-state-management/Lemonade/`

#### TipTime

Application de calculateur de pourboire démontrant la gestion de la saisie utilisateur et les calculs en temps réel dans Compose.

- **Fonctionnalités** : Saisie du montant de la facture, pourcentage de pourboire personnalisable, option d'arrondi, calcul de pourboire en temps réel, formatage monétaire
- **Concepts clés** : Gestion de la saisie TextField, gestion d'état, calculs, formatage de nombres, composant Switch
- **Technologies** : Kotlin, Jetpack Compose, Material Design 3
- **Min SDK** : 24 | **Target SDK** : 35 | **Compile SDK** : 35
- **Emplacement** : `02-state-management/TipTime/`

### 03-lists-and-data/ - Listes et données

#### Affirmations

Application de liste défilante démontrant les classes de données, les listes et le chargement paresseux dans Jetpack Compose.

- **Fonctionnalités** : Liste défilante de 10 cartes d'affirmations, chacune avec une image et un texte motivationnel, défilement fluide avec LazyColumn
- **Concepts clés** : Composables LazyColumn, composants Card, classes de données, listes dans Compose, composables Image, gestion des ressources
- **Technologies** : Kotlin, Jetpack Compose, Material Design 3
- **Min SDK** : 24 | **Target SDK** : 33 | **Compile SDK** : 33
- **Emplacement** : `03-lists-and-data/Affirmations/`

#### Woof

Application de galerie de chiens mettant en valeur les composants Material Design 3 avec des cartes extensibles et des animations.

- **Fonctionnalités** : Liste défilante de cartes de chiens avec photos, noms, âges et activités favorites, cartes extensibles avec animations fluides, TopAppBar Material 3
- **Concepts clés** : Composables LazyColumn, composants Card avec fonctionnalité d'expansion/réduction, Scaffold et CenterAlignedTopAppBar, animations (animateContentSize), classes de données, layouts Row et Column, icônes Material
- **Technologies** : Kotlin, Jetpack Compose, Material Design 3
- **Min SDK** : 24 | **Target SDK** : 35 | **Compile SDK** : 35
- **Emplacement** : `03-lists-and-data/Woof/`

### 04-architecture/ - Architecture Android

#### Dessert Clicker

Jeu interactif de clic démontrant la gestion du cycle de vie Android et la persistance d'état dans Jetpack Compose.

- **Fonctionnalités** : Jeu de clic pour gagner des desserts avec déverrouillage progressif, suivi des revenus, fonctionnalité de partage via intents, retour visuel
- **Concepts clés** : Cycle de vie de l'Activity Android (onCreate, onStart, onResume, onPause, onStop, onDestroy), journalisation avec Logcat, gestion d'état avec `rememberSaveable`, gestion des intents (ACTION_SEND), Scaffold et TopAppBar, classes de données et logique de progression
- **Technologies** : Kotlin, Jetpack Compose, Material Design 3
- **Min SDK** : 24 | **Target SDK** : 35 | **Compile SDK** : 35
- **Emplacement** : `04-architecture/Dessert Clicker/`

#### Unscramble

Application de jeu de mots affichant des mots mélangés à déchiffrer, démontrant les Architecture Components Android avec ViewModel et StateFlow.

- **Fonctionnalités** : Jeu de déchiffrement de mots, suivi du score, fonctionnalité de saut de mot, dialogue de fin de partie, validation de saisie avec retour d'erreur, gestion des actions du clavier
- **Concepts clés** : Composant d'architecture ViewModel, StateFlow et MutableStateFlow pour la gestion d'état réactive, classes de données pour l'état de l'UI, composables AlertDialog, OutlinedTextField avec validation, actions du clavier (ImeAction), affichage edge-to-edge, gestion d'état avec coroutines Flow, tests unitaires avec JUnit
- **Technologies** : Kotlin, Jetpack Compose, Material Design 3, Android Architecture Components (ViewModel, StateFlow), JUnit 4
- **Tests** : Tests unitaires complets pour GameViewModel couvrant l'initialisation, les suppositions correctes/incorrectes, le saut de mots et les scénarios de fin de partie
- **Min SDK** : 24 | **Target SDK** : 34 | **Compile SDK** : 34
- **Emplacement** : `04-architecture/Unscramble/`

### 05-coroutines/ - Coroutines Kotlin

#### Race Tracker

Application de simulation de course démontrant les concepts fondamentaux des coroutines Kotlin pour la programmation asynchrone dans Jetpack Compose.

- **Fonctionnalités** : Simulation de course entre deux joueurs avec progression en temps réel, contrôles de démarrage/pause/réinitialisation, indicateurs de progression visuels, mise à jour asynchrone de l'état
- **Concepts clés** : Coroutines Kotlin (`suspend`, `delay`, `coroutineScope`, `launch`), fonctions suspendues, exécution concurrente de tâches, `LaunchedEffect` pour déclencher des coroutines depuis Compose, gestion d'état avec `mutableStateOf`, composables LinearProgressIndicator
- **Technologies** : Kotlin, Jetpack Compose, Material Design 3, Kotlin Coroutines
- **Tests** : Tests unitaires pour RaceParticipant avec kotlinx-coroutines-test
- **Min SDK** : 24 | **Target SDK** : 35 | **Compile SDK** : 35
- **Emplacement** : `05-coroutines/Race Tracker/`

### 06-network/ - Réseau et API

#### Mars Photos

Application de galerie de photos de Mars démontrant l'intégration d'API REST, la sérialisation JSON et le chargement d'images depuis Internet dans Jetpack Compose.

- **Fonctionnalités** : Affichage de photos réelles de la surface de Mars capturées par les rovers de la NASA, récupération de données depuis un service web REST, chargement d'images par URL, gestion des états de chargement et d'erreur, grille défilante avec LazyVerticalGrid
- **Concepts clés** : Appels réseau REST avec Retrofit, sérialisation/désérialisation JSON avec kotlinx.serialization, chargement d'images avec Coil, architecture Repository, ViewModel avec coroutines, gestion d'état UI (Loading, Success, Error), composables LazyVerticalGrid, gestion des erreurs réseau (IOException, HttpException), affichage edge-to-edge
- **Technologies** : Kotlin, Jetpack Compose, Material Design 3, Retrofit, kotlinx.serialization, Coil, OkHttp, Android Architecture Components (ViewModel)
- **Min SDK** : 24 | **Target SDK** : 34 | **Compile SDK** : 34
- **Emplacement** : `06-network/Mars Photos/`

## Technologies utilisées

### Technologies principales
- **Langage** : Kotlin
- **Framework UI** : Jetpack Compose
- **Système de design** : Material Design 3
- **Système de build** : Gradle (Kotlin DSL)

### Bibliothèques et dépendances
- AndroidX Core KTX
- AndroidX Lifecycle Runtime KTX
- AndroidX Activity Compose
- AndroidX Lifecycle ViewModel Compose
- Jetpack Compose BOM
- Compose UI, UI Graphics, UI Tooling
- Material 3 Components
- Kotlin Coroutines Flow
- Retrofit (pour les appels réseau REST)
- kotlinx.serialization (pour la sérialisation JSON)
- Coil (pour le chargement d'images)
- OkHttp (client HTTP)
- JUnit 4 (pour les tests unitaires)

### Outils de développement
- Android Studio
- Gradle
- Git

## Démarrage

### Prérequis
- Android Studio (dernière version recommandée)
- JDK 11 ou supérieur
- Android SDK (niveau API 24+)
- Connaissances de base de la syntaxe Kotlin
- Compréhension des fondamentaux du développement Android

### Installation

1. Cloner ce dépôt :
```bash
git clone <repository-url>
cd ktolin-apps
```

2. Ouvrir un projet dans Android Studio :
   - File → Open → Sélectionner le dossier du projet (par exemple, `01-basics/DiceRoller`, `02-state-management/Lemonade`, `05-coroutines/Race Tracker`, `06-network/Mars Photos`, etc.)

3. Synchroniser les dépendances Gradle

4. Exécuter l'application sur un émulateur ou un appareil physique

## Structure du dépôt

Le dépôt est organisé en catégories pour faciliter la navigation :

```
ktolin-apps/
├── 00-works/               # Ressources pédagogiques
│   ├── Kotlin-Android.md   # Cours de révision pour QCM
│   ├── lessons/            # Supports de cours (PDF)
│   └── quizz/              # Quiz de révision (PDF)
├── 01-basics/              # Concepts de base
│   ├── DiceRoller/         # Gestion d'état basique
│   └── HappyBirthday/      # Layout et composition
├── 02-state-management/    # Gestion d'état avancée
│   ├── Lemonade/           # États multi-étapes
│   └── TipTime/            # Saisie utilisateur et calculs
├── 03-lists-and-data/      # Listes et données
│   ├── Affirmations/       # Listes simples
│   └── Woof/               # Cartes extensibles et animations
├── 04-architecture/        # Architecture Android
│   ├── Dessert Clicker/    # Cycle de vie Android
│   └── Unscramble/         # ViewModel et StateFlow
├── 05-coroutines/          # Coroutines Kotlin
│   └── Race Tracker/       # Programmation asynchrone
├── 06-network/             # Réseau et API
│   └── Mars Photos/        # Appels réseau REST et chargement d'images
└── README.md
```

Chaque projet suit une structure Android standard :
```
ProjectName/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/projectname/
│   │   │   │   ├── MainActivity.kt
│   │   │   │   └── ui/theme/
│   │   │   ├── res/
│   │   │   └── AndroidManifest.xml
│   │   ├── test/
│   │   └── androidTest/
│   └── build.gradle.kts
├── gradle/
├── build.gradle.kts
└── settings.gradle.kts
```

## Parcours d'apprentissage

### Révision et préparation aux examens

Avant de commencer les projets pratiques, consultez le cours de révision dans `00-works/Kotlin-Android.md` pour une vue d'ensemble complète de tous les concepts, avec des exemples concrets et un format optimisé pour la révision de QCM.

### Projets pratiques

Ces projets sont conçus pour enseigner progressivement les concepts de Jetpack Compose :

### Niveau 1 : Bases (`01-basics/`)
1. **DiceRoller** - Gestion d'état basique et interface utilisateur
2. **HappyBirthday** - Layout et composition d'images

### Niveau 2 : Gestion d'état (`02-state-management/`)
3. **Lemonade** - Gestion d'état multi-étapes
4. **TipTime** - Saisie utilisateur et calculs

### Niveau 3 : Listes et données (`03-lists-and-data/`)
5. **Affirmations** - Listes, classes de données et chargement paresseux
6. **Woof** - Composants Material Design 3, cartes extensibles et animations

### Niveau 4 : Architecture (`04-architecture/`)
7. **Dessert Clicker** - Gestion du cycle de vie Android, journalisation et gestion des intents
8. **Unscramble** - Architecture Components Android avec ViewModel et StateFlow pour la gestion d'état réactive, et tests unitaires avec JUnit

### Niveau 5 : Coroutines (`05-coroutines/`)
9. **Race Tracker** - Programmation asynchrone avec Kotlin Coroutines, exécution concurrente de tâches, fonctions suspendues et intégration avec Jetpack Compose

### Niveau 6 : Réseau (`06-network/`)
10. **Mars Photos** - Appels réseau REST avec Retrofit, sérialisation JSON avec kotlinx.serialization, chargement d'images avec Coil, architecture Repository et ViewModel avec coroutines

## Licence

Chaque projet peut avoir sa propre licence. Consultez les fichiers README individuels de chaque projet pour les informations de licence.

## Contribution

Chaque projet est autonome et peut être exécuté indépendamment. Les contributions sont les bienvenues.
