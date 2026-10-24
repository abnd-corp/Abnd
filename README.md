# Abnd

Abnd.io : un catalogue communautaire de modules web. Chaque module a un nom, un lien et une image. Les utilisateurs créent un compte, parcourent les modules par tag, les ajoutent à leurs favoris, suivent d'autres utilisateurs, signalent un contenu et reçoivent des notifications. Une interface d'administration permet de modérer.

## Fonctionnalités

- **Comptes** : inscription, connexion, vérification de l'adresse e-mail, mot de passe oublié, profil
- **Modules** : création, recherche et filtres, page de profil d'un module, suppression
- **Tags** : classement des modules et navigation par tag
- **Favoris et historique** : modules aimés, modules visités
- **Communauté** : suivre un utilisateur, notifications
- **Modération** : signalement d'un module, tableau de bord d'administration
- **Pages légales** : conditions d'utilisation, politique de confidentialité, contact

## Stack

| | |
|---|---|
| Client | Vue 3, Vue Router, Pinia, Tailwind CSS, Vite |
| Serveur | Node.js, Express, TypeScript, Sequelize |
| Base de données | MySQL, avec Redis |
| Authentification | JWT, bcrypt |
| Envoi d'e-mails | Nodemailer |
| Images | Multer, Sharp |
| Infrastructure | Docker Compose (dev, test, prod), Traefik |

## Démarrage rapide

Prérequis : Docker et Docker Compose.

```bash
make up          # démarre tout en mode développement (docker-compose.dev.yml)
make down        # arrête
make test        # lance la suite de tests (docker-compose.test.yml)
```

En développement, le client est sur `http://localhost:5173`, l'API sur `http://localhost:5000` et phpMyAdmin sur `http://localhost:8080`. La production utilise `docker-compose.prod.yml` derrière Traefik.

## Structure

```
client/     Application Vue 3 (pages dans src/views)
server/     API Express : routes, contrôleurs, modèles Sequelize
traefik/    Configuration du reverse proxy
docker-compose.{dev,test,prod}.yml
```

## Contribuer

Les règles sont dans [CONTRIBUTING.md](CONTRIBUTING.md) et la [charte Abnd](https://github.com/abnd-corp/gouvernance/blob/main/CHARTE.md).

## Licence

AGPL-3.0-or-later : voir [LICENSE](LICENSE).
