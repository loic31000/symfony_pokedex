# Pokédex Symfony

![PHP](https://img.shields.io/badge/PHP-8.4-777BB4?style=flat&logo=php&logoColor=white)
![Symfony](https://img.shields.io/badge/Symfony-8.0-000000?style=flat&logo=symfony&logoColor=white)
![Doctrine](https://img.shields.io/badge/Doctrine-ORM-FC6A31?style=flat&logo=doctrine&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-336791?style=flat&logo=postgresql&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3-38BDF8?style=flat&logo=tailwindcss&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=flat&logo=docker&logoColor=white)
![License](https://img.shields.io/badge/license-proprietary-red?style=flat)

Application web Pokédex développée avec **Symfony 8**, permettant de lister et d'ajouter des Pokémon (nom + image) dans une base de données PostgreSQL.

---

## Fonctionnalités

- **Liste des Pokémon** — affichage de tous les Pokémon enregistrés avec leur ID, nom et image
- **Ajout de Pokémon** — formulaire pour ajouter un Pokémon (nom, URL d'image)
- Interface stylisée avec **Tailwind CSS**

---

## Stack technique

| Couche | Technologie |
|---|---|
| Framework | Symfony 8.0 |
| Langage | PHP 8.4 |
| ORM | Doctrine ORM 3 |
| Base de données | PostgreSQL 16 |
| Frontend | Twig + Tailwind CSS |
| Assets | Symfony Asset Mapper |
| Conteneurs | Docker Compose |

---

## Installation

### Prérequis

- PHP 8.4+
- Composer
- Docker & Docker Compose

### Étapes

```bash
# Cloner le projet
git clone https://github.com/loic31000/symfony_pokedex.git
cd symfony_pokedex

# Installer les dépendances PHP
composer install

# Démarrer la base de données PostgreSQL
docker compose up -d

# Créer la base de données et appliquer les migrations
php bin/console doctrine:database:create
php bin/console doctrine:migrations:migrate

# Lancer le serveur de développement
symfony server:start
```

L'application est accessible sur [http://localhost:8000](http://localhost:8000).

---

## Structure du projet

```
src/
├── Controller/
│   └── PokeController.php   # Routes : / (liste) et /add (ajout)
├── Entity/
│   └── Pokedex.php          # Entité Pokémon (id, name, imageURL)
├── Form/
│   └── PokedexType.php      # Formulaire d'ajout
└── Repository/
    └── PokedexRepository.php
templates/
└── poke/
    ├── index.html.twig      # Page liste
    └── add.html.twig        # Page ajout
migrations/                  # Migrations Doctrine
```

---

## Routes

| Méthode | URL | Description |
|---|---|---|
| GET | `/` | Liste de tous les Pokémon |
| GET/POST | `/add` | Formulaire d'ajout d'un Pokémon |
