# Laravel Boost SDK

Le **Laravel Boost SDK** est un lanceur standalone pour le serveur MCP [Laravel Boost](https://github.com/thumanics/laravel-boost). Il permet d'utiliser toute la puissance de Boost (génération de modules, introspection de base de données, exécution de commandes Artisan, etc.) sur n'importe quel projet Laravel sans avoir besoin d'installer le package Boost localement dans chaque projet.

## Fonctionnement (Bootstrap Hybride)

Le SDK utilise un mécanisme de "Bootstrap Hybride" : il embarque lui-même le moteur Boost et "s'attache" dynamiquement au projet Laravel cible en chargeant son environnement, son autoloader et son instance d'application.

## Prérequis

- PHP 8.2 ou supérieur
- Un projet Laravel (v10, v11 ou v12)

## Installation

### Installation Globale (Recommandé)

Pour pouvoir lancer Boost depuis n'importe quel dossier de projet :

```bash
composer global require thumanics/laravel-boost-sdk
```

### Installation Locale

```bash
composer require thumanics/laravel-boost-sdk --dev
```

## Utilisation

Une fois installé, placez-vous à la racine de n'importe quel projet Laravel et lancez :

```bash
laravel-boost-mcp
```

### Configuration dans un client MCP (ex: Claude Desktop)

Ajoutez la configuration suivante dans votre fichier `claude_desktop_config.json` :

```json
{
  "mcpServers": {
    "laravel-boost": {
      "command": "php",
      "args": ["/chemin/vers/votre/global/vendor/bin/laravel-boost-mcp"]
    }
  }
}
```

*Note : Remplacez `/chemin/vers/votre/global/vendor/bin/` par le chemin réel de vos binaires Composer globaux.*

## Avantages

- **Propres** : Ne pollue pas les dépendances de vos projets de production.
- **Universel** : Fonctionne sur tous vos projets locaux (Laragon, Herd, Docker).
- **Centralisé** : Mettez à jour le SDK une seule fois pour tous vos projets.

## License

MIT
