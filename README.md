## Projet dbt de test : `jaffle_shop`

`jaffle_shop` est une boutique de commerce électronique fictive. Ce projet dbt transforme des données brutes issues d'une base de données d'application en modèles de clients et de commandes prêts pour l'analyse.

### Qu'est-ce que ce dépôt ?
Ce que ce dépôt **est** :
- Un terrain de jeu autonome pour le projet dbt, utile pour tester des scripts et expliquer certains concepts fondamentaux de dbt.

Ce que ce dépôt **n'est pas** :
- Un tutoriel — pour cela, consultez le [Tutoriel de démarrage](https://docs.getdbt.com/tutorial/setting-up). Notamment, ce dépôt contient certains anti-modèles pour rester autonome, à savoir l'utilisation de graines au lieu de sources.
- Une démonstration des meilleures pratiques — consultez plutôt le dépôt [dbt Learn Demo](https://github.com/dbt-labs/dbt-learn-demo). Nous souhaitons garder ce projet aussi simple que possible. Ainsi, nous avons choisi de ne pas implémenter :
    - nos modèles de nommage de fichiers standards (qui ont plus de sens sur des projets plus grands, plutôt que sur ce projet de cinq modèles)
    - un flux de pull requests
    - des intégrations CI/CD
- Une démonstration de l'utilisation de dbt pour un projet de haute complexité, ou une démo de fonctionnalités avancées (par exemple, macros, packages, hooks, opérations) — nous essayons juste de garder les choses simples ici !

### Qu'y a-t-il dans ce dépôt ?
Ce dépôt contient des [graines](https://docs.getdbt.com/docs/building-a-dbt-project/seeds) qui incluent des données brutes fictives provenant d'une application.

Les données brutes comprennent des clients, des commandes, et des paiements, avec le diagramme relationnel d'entités suivant :

![Diagramme ER du Jaffle Shop](/etc/jaffle_shop_erd.png)

### Exécuter ce projet
Pour démarrer avec ce projet :
1. Installez dbt en suivant [ces instructions](https://docs.getdbt.com/docs/installation).

2. Clonez ce dépôt.

3. Changez de répertoire pour `jaffle_shop` depuis la ligne de commande :
```bash
$ cd jaffle_shop
```

4.Configurez un profil appelé jaffle_shop pour vous connecter à un entrepôt de données en suivant ces instructions. Si vous avez accès à un entrepôt de données, vous pouvez utiliser ces identifiants – nous recommandons de définir votre schéma cible comme un nouveau schéma (dbt créera le schéma pour vous, tant que vous avez les bons privilèges). Si vous n'avez pas accès à un entrepôt de données existant, vous pouvez également configurer une base de données locale PostgreSQL et vous y connecter dans votre profil.

5.Assurez-vous que votre profil est correctement configuré depuis la ligne de commande :
```bash
$ dbt debug
```

6.Chargez les CSV avec l'ensemble de données de démonstration. Cela matérialise les CSV en tables dans votre schéma cible. Notez qu'un projet dbt typique ne nécessite pas cette étape puisque dbt suppose que vos données brutes sont déjà dans votre entrepôt.
```bash
$ dbt seed
```
7.Exécutez les modèles :
```bash
$ dbt run
```
> **REMARQUE:** Si cette étape échoue, cela peut signifier que vous devez apporter de petites modifications au SQL dans le dossier des modèles pour ajuster au type de SQL de votre base de données cible. Envisagez cela si vous utilisez un adaptateur contribué par la communauté.
8.Testez la sortie des modèles :
```bash
$ dbt test
```
9.Générez la documentation pour le projet :
```bash
$ dbt docs generate
```
10.Consultez la documentation pour le projet :
```bash
$ dbt docs serve
```
### Qu'est-ce qu'un jaffle ?
Un jaffle est un sandwich grillé avec des bords pincés et scellés. Inventé à Bondi en 1949, le modeste jaffle est un classique australien. Les bords scellés permettent aux consommateurs de jaffle de profiter de garnitures liquides à l'intérieur du sandwich, qui atteignent des températures proches du noyau de la terre lors de la cuisson. Souvent consommé à la maison après une soirée, la garniture la plus classique est les spaghettis en conserve, tandis que ma préférée personnelle est le ragoût de bœuf restant avec du fromage fondu.

---
Pour plus d'informations sur dbt :
- Lisez l'[introduction à dbt](https://docs.getdbt.com/docs/introduction).
- Lisez le [point de vue dbt](https://docs.getdbt.com/docs/about/viewpoint).
- Rejoignez la [communauté dbt](http://community.getdbt.com/).
---
