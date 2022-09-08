<div align="center">
  <img src="https://user-images.githubusercontent.com/6887819/186343424-9262d753-1b96-410f-bd3d-5d3b3eea4518.svg" \>
  <img src="https://user-images.githubusercontent.com/6887819/186343452-a07e99be-9483-40ab-bf2a-5db76404a4b1.svg" \>
</div>

[StudyStorm](https://studystorm.net) est la meilleure plateforme d'apprentissage en ligne pour les étudiants.

[![](https://img.shields.io/badge/licence-MIT-blue.svg)](https://opensource.org/licenses/MIT)
![](https://img.shields.io/badge/version-1.0.0-blue.svg)

[![[Backend] Unit & Component tests](https://github.com/StudyStorm/api-backend/actions/workflows/test.yml/badge.svg)](https://github.com/StudyStorm/api-backend/actions/workflows/test.yml)
[![[Frontend] Unit & Component tests](https://github.com/StudyStorm/application/actions/workflows/test.yml/badge.svg)](https://github.com/StudyStorm/application/actions/workflows/test.yml)

[![DigitalOcean Referral Badge](https://web-platforms.sfo2.digitaloceanspaces.com/WWW/Badge%203.svg)](https://www.digitalocean.com/?refcode=935ca50df3d4&utm_campaign=Referral_Invite&utm_medium=Referral_Program&utm_source=badge)



## Contexte
StudyStorm est un projet de groupe, open source, réalisé dans le cadre du cours PDG du semestre d'été de la HEIG-VD.

## Auteurs

- Alen Bijelic
- Nicolas Crausaz
- Jonathan Friedli
- Lazar Pavicevic
- Maxime Scharwath

## Description du projet
### Conçu pour les étudiants, pensé par des étudiants
L’application StudyStorm permet aux utilisateurs de créer des collections de cartes de révision et de les partager avec d’autres utilisateurs de la plateforme. 

Vous souhaitez contribuer au savoir commun ? Créez une salle de classe !
Le créateur d’une salle de classe peut partager ses collections à tout le monde ou rendre la salle de classe privée, en invitant uniquement les utilisateurs qu’il souhaite, à rejoindre la salle de classe. Organisez votre salle de classe d’une manière semblable à un système de dossier afin de regrouper les cartes par sujet, chapitre, unité de cours, etc…

La communauté peut évaluer le contenu qu’elle a apprécié ou pas. Les collections avec le plus de votes positifs sont mises en avant sur la page d’accueil. Les cartes étant réalisées par des personnes, il est possible qu’il y ait des erreurs dans la réponse d’une carte, ou qu’il y ait une réponse plus pertinente. Les utilisateurs ont la possibilité de signaler une carte en proposant une meilleure réponse. C’est ensuite de la responsabilité du créateur de la carte d’appliquer le changement.

## Comment lancer le projet en local

### Base de données
Pour lancer la base de donnée vous aurez uniquement besoin de [Docker](https://docs.docker.com/engine/install/).  
Une fois docker installé, vous pouvez lancer la base de donnée en exécutant la commande suivante:
```bash
docker run --name sql-studystorm -p 5432:5432 -e POSTGRES_USER=user -e POSTGRES_PASSWORD=password123 -e POSTGRES_MULTIPLE_DATABASES=studystorm,studystorm_test gradescope/postgresql-multiple-databases:14.4
```
Cela aura pour effet de créer un container avec une PostgresSQL 14.4, avec deux bases de données: `studystorm` et `studystorm_test`. Nous pourrons ensuite communiquer avec elles via le port 5432.

> **Warning**  
> Si vous avez déjà une base de donnée en local sur le port 5432, vous devrez changer le port (celui à droite des " : " ) dans la commande ci-dessus.

### Frontend
Les préréquis et instructions pour lancer la partie frontend du projet sont dans la doc du repository, disponible [ici](https://github.com/StudyStorm/application#readme).

### Backend
Les préréquis et instructions pour lancer la partie backend du projet sont dans la doc du repository, disponible [ici](https://github.com/StudyStorm/api-backend#readme).

### Minio
TODO

### Mailgun 
TODO

### Supabase
TODO

## Contribuer au projet
 Afin de contribuer à ce projet, il vous suffit de clone le repository et de créer une nouvelle branche. Dès votre premier commit, il faut créer une Pull Request en mode "Draft". Ensuite, à chaque nouveau commit, une action github va s'occuper de lancer les tests unitaires et de vérifier que le code est bien formaté. 

 Chaque commit aura la forme suivante : Un préfixe, puis : et enfin un message rédigé en anglais.  
  Les préfixes sont les suivants : 
 * feat: pour une nouvelle fonctionnalité
 * fix: pour une correction de bug
 * docs: pour une modification de la documentation
 * refactor: pour une modification de code qui n'ajoute pas de fonctionnalité ni de bug
 * chore: pour une modification de configuration.

 Exemple de commit : ```feat: add register page for new users```

 Une fois la PR prête à être mergée, vous pouvez la mettre en mode "Ready for review" et un autre membres de l'équipe va s'occuper de la review. Si tout est bon, la PR sera mergée dans la branche dev et votre contribution sera ajoutée au projet. Vous pourrez ensuite supprimer votre branche.

 ## Déployer une fonctionnalité
Afin de déployer une fonctionnalité en production, il suffit de merge la branche dev (après s'être assuré qu'elle ne contient plus aucun bug et passe tous les tests) dans la branche main. DigitalOcean, qui watch notre branche main, va alors se charger de déployer la nouvelle version de l'application. Cela peut prendre entre 5 et 10 minutes.  
Vous pourrez ensuite voir vos nouvelles fonctionnalité directement sur le site [https://studystorm.net/](https://studystorm.net/).
