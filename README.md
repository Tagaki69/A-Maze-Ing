# A-Maze-ing 🧩

## 🎯 Description
Générateur et solveur de labyrinthes procéduraux en Python. Le projet génère des labyrinthes parfaits (ou imparfaits) basés sur une configuration stricte, incluant un motif "42" obligatoire au centre et un export au format hexadécimal.

## 🚀 Fonctionnalités
- **Génération Procédurale** : Algorithme DFS itératif pour des couloirs sinueux et complexes.
- **Shortest Path** : Résolution via BFS garantissant le chemin le plus court.
- **Validation Robuste** : Parsing de configuration via `Pydantic` pour un contrôle strict des entrées.
- **Interface UI** : Menu interactif en ASCII avec support de thèmes (Ghost, Cyberpunk, Hell, etc.).
- **Export Hex** : Sortie conforme au format 42 (murs codés sur 4 bits).

## 📁 Structure
```text
A-Maze-ing/
├── a_maze_ing.py        # Point d'entrée & Interface Menu
├── mazegen/
│   └── mazegen.py       # Coeur algorithmique (DFS/BFS/Logic)
├── config_parser.py     # Modèles Pydantic & Parsing
├── config.txt           # Configuration du labyrinthe
└── Makefile             # Automatisation (install, run, lint)

```

## 📝 Aperçu des Composants

### 🧠 Logique & Algorithmes (`mazegen.py`)

* **`generate()`** : Implémentation d'un **DFS Itératif** (Recursive Backtracker) avec pile pour éviter les `RecursionError` sur les grandes grilles.
* **`solve()`** : Algorithme **BFS** (Breadth-First Search) pour trouver le chemin optimal vers la sortie.
* **`setup_42_pattern()`** : Intégration mathématique du motif "42" statique au sein d'une grille dynamique.

### 🛠️ Validation & Données (`config_parser.py`)

* **`MazeConfig`** : Modèle de données utilisant des `field_validator` pour garantir des dimensions valides (5 à 100) et des coordonnées cohérentes.
* **`validate_maze_configs`** : Vérifie l'absence de chevauchement entre l'entrée/sortie et le motif central "42".

### 🎮 Interface & Système (`a_maze_ing.py`)

* **`MenuState`** : Gestionnaire d'état pour les thèmes, les animations et la régénération à la volée.
* **`get_single_key()`** : Capture de touches en temps réel via `termios` et `tty` sans bloquer le terminal.

## 🤝 Équipe & Rôles

* **`elarue`** : Logique algorithmique pure (DFS, BFS) et intégration du pattern "42".
* **`wakhazza`** : Architecture système, validation Pydantic, UI interactive et logique d'export Hex.

## 🏆 Note obtenue

**120/100** (bonus inclus) ✨

## 🛠️ Contraintes 42

✅ Validation Pydantic ✅ Typage statique (Mypy) ✅ Linting Flake8 ✅ Makefile complet

## 📚 Concepts clés

**DFS itératif** • **BFS** • **Data Validation** • **Architecture Modulaire** • **Terminal UI**

---

## ⚠️ Disclaimer 42

Ce dépôt est rendu public pour présenter mon code et servir de ressource pédagogique ; le plagiat est strictement interdit et vous devez être capable d'expliquer votre propre travail.

*Projet réalisé dans le cadre du cursus 42* 🎓
