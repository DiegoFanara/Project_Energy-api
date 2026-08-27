# Energy API

API REST de gestion de données énergétiques pour des bâtiments.

`energy-api` fournit un point d’entrée central pour enregistrer, consulter et exploiter les informations nécessaires au suivi énergétique. Le projet est développé avec [NestJS](https://nestjs.com/) et TypeScript.

> Le projet est en développement actif. Le contrat d’API peut évoluer avant la première version stable.

## Fonctionnalités

- vérification de l’état du service;
- gestion des bâtiments;
- réponses HTTP au format JSON;
- architecture modulaire par domaine;
- tests unitaires et tests de bout en bout;
- contrôles de qualité avec ESLint et Prettier.

## Technologies

- Node.js;
- TypeScript;
- NestJS;
- Jest;
- Supertest;
- ESLint;
- Prettier.

## Prérequis

- une version de Node.js compatible avec le fichier `package.json`;
- npm;
- Git.

Vérifier l’environnement local :

- npm install
- node --version
- npm --version
- git --version

## Installation

Cloner le dépôt :

git clone <URL_DU_DEPOT>
cd energy-api
```

Installer les dépendances :

npm install

## Configuration

L’application attend la variable d’environnement suivante :

| Variable | Obligatoire | Description | Exemple local |
|---|---|---|---|
| `PORT` | Oui | Port d’écoute du serveur HTTP | `3000` |

Le numéro `3000` est seulement un exemple de configuration locale. L’application ne doit pas imposer silencieusement ce port dans son code.

Sous Linux ou macOS :

```bash
PORT=3000 npm run start:dev
```

Sous PowerShell :

```powershell
$env:PORT=3000
npm run start:dev
```

Si le projet utilise un fichier `.env`, créer celui-ci à partir du modèle versionné :

cp .env.example .env
```

Le fichier `.env` ne doit jamais être ajouté au dépôt.

## Exécution

### Développement

```bash
npm run start:dev

### Production

```bash
npm run build
npm run start:prod
```

Avec `PORT=3000`, l’API est accessible à l’adresse suivante :

http://localhost:3000/api
```

## API

Toutes les routes sont exposées sous le préfixe global `/api`.

| Méthode | Route | Statut attendu | Description |
|---|---|---:|---|
| `GET` | `/api/health` | `200 OK` | Vérifie l’état du service |
| `GET` | `/api/buildings` | `200 OK` | Retourne les bâtiments |
| `POST` | `/api/buildings` | `201 Created` | Crée un bâtiment |

### Vérifier l’état du service

```bash
curl -i http://localhost:3000/api/health

Exemple de réponse :

```json
{
  "status": "ok"
}
```

### Obtenir les bâtiments

```bash
curl -i http://localhost:3000/api/buildings
```