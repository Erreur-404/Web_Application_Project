# Serveur NestJS

Ce projet est une implémentation du serveur de départ utilisant le cadriciel [NestJS](https://nestjs.com/). Ceci est une alternative à serveur de base qui vous est fournie et qui utilise NodeJS/Express. Vous pouvez utiliser le serveur NodeJS/Express fourni ou ce serveur pour votre projet.

## NestJS

NestJS est un cadriciel de développement de serveurs web utilisant NodeJS et Expess avec une architecture très similaire à celle d'Angular. Vous remarquerez l'utilisation de termes tels que `service`,`module` et autres similaires à Angular.

NestJS utilise souvent les décorateurs (annotations avec le symbole `@`) pour attacher des fonctionnalités supplémentaires au code. Par exemple, la configuration d'un gestionnaire de route en NestJS :

```ts

```

est équivalente à la configuration suivante avec Express :

```ts


## Intégration avec les autres exemples du cours

Afin de vous aider, ce projet inclut également le code nécessaire pour présenter les fonctionnalités de communication avec une base de données `MongoDB` et la communication avec `SocketIO`. Le code se base sur les projets suivants disponibles sur GitLab :

-   [`MongoDB`](https://gitlab.com/nikolayradoev/mongodb-example) : la route `/api/docs` du serveur NodeJS offre une interface qui vous permet de tester la connexion avec la base de données. Notez que NestJS utilise la librairie `Mongoose` pour la communication avec MongoDB.

    **Important**: vous devez configurer la variable d'environnement `DATABASE_CONNECTION_STRING` disponible dans le fichier `.env` avant de pouvoir vous connecter à une base de données.

-   [`SocketIO`](https://gitlab.com/nikolayradoev/socket-io-exemple) : vous pouvez utiliser le site web (client) de cet exemple pour tester la communication par WebSocket avec le serveur NestJS.

NestJS utilise la librairie `Jest` pour ses tests. L'ensemble du code qui est fourni est déjà testé avec plusieurs exemples de tests unitaires. Vous pouvez vous baser sur ces exemples pour tester vos propres fonctionnalités.

# Choix de serveur à utiliser

Vous devez choisir le serveur à utiliser dans votre projet : NodeJS/Express de base ou NestJS. Dans les deux cas, vous devez apporter quelques changements à votre entrepôt.

Notez que les configurations pour le déploiement et le pipeline de validation assument qu'il a seulement un répertoire `/server` dans votre entrepôt. Peu importe votre choix, le répertoire de votre serveur doit porter ce nom.

### Serveur NodeJS de base

Si vous avez décidé de garder le serveur NodeJS de base, vous n'avez qu'à supprimer le répertoire `/server-nestjs` et pousser vos changements sur Git.

**Note : il est important de retirer le répertoire du serveur non utilisé pour ne pas avoir du _code mort_ qui n'est jamais utilisé dans votre entrepôt.**

### Serveur NestJS

Si vous avez décidé de prendre le serveur NestJS, vous devez :

- Supprimer le répertoire `/server` et renommer `/server-nestjs` à `/server`.
- Modifier la valeur du champ `entryFile` pour `server/app/index` dans le fichier `nest-cli.json`.
- Modifier la valeur du champ `@app` à `out/server/app` dans le fichier `/server/package.json`.

N'oubliez pas de pousser vos changements sur Git.

**Note : il est important de retirer le répertoire du serveur non utilisé pour ne pas avoir du _code mort_ qui n'est jamais utilisé dans votre entrepôt.**

