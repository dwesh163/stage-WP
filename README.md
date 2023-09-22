# stage-WP

Journal de bord pour le stage WordPress

## Qu’est-ce que [WordPress](https://wordpress.com/) ?

WordPress est un outil de gestion de contenu qui est **gratuit** et **open source**. Il est écrit principalement en **PHP** et est toujours accompagné d'une base de données, par exemple *MariaDB* ou alors *MySQL*. WordPress est très polyvalent et permet de créer une grande variété de site web différent. Ça peut être un e-commerce, un blog, un magasin en ligne, un site d'entreprise, etc. 



Un autre avantage de WordPress ce sont ses plugins. Les plugins WordPress sont une part importante de sa renommée ainsi que les nombreux thème disponible *gratuitement*. 


#### WordPress est-il beaucoup utilisé ?
Oui, WordPress est beaucoup utilisé. WordPress est le moyen le plus simple et le plus populaire pour créer votre propre site Web. WordPress gère plus de 43 % de tous les sites Web d'Internet et il a comme avantage de faciliter la construction de site Web via leur propre éditeur *Gutenberg* qui est intégré directement à WordPress et donc par extension votre site. Ce qui a pour effet de faciliter la construction d’un site Web et de la rendre accessible à tous, même aux personnes qui ne sont pas développeurs.

#### Combien coûte WordPress ?
Le logiciel WordPress en lui-même est gratuit, ce qui devient payant, c'est la mise en ligne au grand public de votre site WordPress via l'intermédiaire d'un hébergeur. WordPress et open source, ce qui signifie que vous pouvez le modifier et l'utiliser à votre guise. Par contre, l'utilisation de wordpress.com avec la version gratuite ne permet pas l'utilisation des plugins ou des thèmes, ce qui peut vous pousser à opter pour une version payante.

#### Quelle est la différence entre wordpress.com et wordpress.org ? 

- WordPress.org, est le logiciel WordPress gratuit et open source que vous pouvez installer sur votre propre hébergent ou même ordinateur.
- WordPress.com, est la partie commerciale de WordPress, Elle est reliée à WordPress, car elle l'utilise. Wordpress.com propose en plus de la plupart des fonctionnalités de wordpr4ess.org quelques nouvelles fonctionnalités comme : une bande passant non-réguler, un domaine gratuit pour un an, etc.

## Procédure d’installation de WordPress sur une Machine physique


```bash
sudo apt install apache2 mysql-server php-mysql libapache2-mod-php8.1
```
Installer les prérequis pour lamp Linux apache, MySQL et PHP.


```bash
sudo apt install lynx w3m
```
Installer un navigateur dans le terminal pour permettre le bon fonctionnement d'apache.


```bash
sudo mysql
```
Lancement de MySQL pour créer la base de donnée.

```SQL
CREATE database wordpress;
```
Crée la base de donnée pour WordPress.

```SQL
USE wordpress;
```
Choisir la base de donnée à utiliser pour les prochaines action.

```SQL
CREATE user 'wordpress'@'%' IDENTIFIED by 'wordpress';
```
Crée l'utilisateur **wordpress** avec le mot de passe *wordpress*.

```SQL
GRANT all on wordpress.* to 'wordpress'@'%';
```
Donner à l'utilisateur **wordpress** la permission pour modifier la base de donner *wordpress*.

```SQL
FLUSH PRIVILEGES;
```
Activer les privilèges pour l'utilisateur **wordpress**.  

<br>
<br>

Télécharger le package WordPress sur [wordpress.com](https://wordpress.org/). L'extraire dans le dossier téléchargement. 
```bash
cd /var/www/html
sudo mv ~/Downloads/wordpress .
```
Accéder à [http://localhost/wordpress/](http://localhost/wordpress/). Suivre les informations de connexion fournie par WordPress avec votre mot de passe et votre nom d'utilisateur, dans mon cas **wordpress**.

Et voilà, vous avez installé WordPress !

## Procédure d’installation de WordPress sur une VM distante

Il est prealbalemt nécessaire de se connecter a la vm distante grace a *ssh*

```bash
ssh root@vmurl 
```
Replacer vmurl par l'ip de votre vm et connecter vous

```bash
sudo apt install apache2 mysql-server php-mysql libapache2-mod-php8.1 php8.1
```
Installer les prérequis pour lamp Linux apache, MySQL et PHP.


```bash
sudo apt install lynx w3m
```
Installer un navigateur dans le terminal pour permettre le bon fonctionnement d'apache.


```bash
sudo mysql
```
Lancement de MySQL pour créer la base de donnée.

```SQL
CREATE database wordpress;
```
Crée la base de donnée pour WordPress.

```SQL
USE wordpress;
```
Choisir la base de donnée à utiliser pour les prochaines action.

```SQL
CREATE user 'wordpress'@'%' IDENTIFIED by 'wordpress';
```
Crée l'utilisateur **wordpress** avec le mot de passe *wordpress*.

```SQL
GRANT all on wordpress.* to 'wordpress'@'%';
```
Donner à l'utilisateur **wordpress** la permission pour modifier la base de donner *wordpress*.

```SQL
FLUSH PRIVILEGES;
```
Activer les privilèges pour l'utilisateur **wordpress**.  

<br>
<br>

Télécharger le package WordPress sur [wordpress.com](https://wordpress.org/). L'extraire dans le dossier téléchargement. 
```bash
cd /var/www/html
sudo mv ~/Downloads/wordpress .
```
Accéder à *l'url de votre serveur/wordpress* et suivez les informations de connexion fournie par WordPress avec votre mot de passe et votre nom d'utilisateur, dans mon cas **wordpress**.

Et voilà, vous avez installé WordPress !

![image](https://github.com/dwesh163/stage-WP/assets/142376542/fee5effc-8c78-4a52-b40b-42a5998fdb84)


## Docker 

#### Docker c'est quoi ?

Docker est une plateforme de conteneur qui a vu le jour en 2013 et qui a largement contribué à la conteneurisation. Elle permet de créer facilement des conteneurs et des applications basées sur les conteneurs. Docker n'est pas la seule plateforme de conteneur, mais elle est l'une des plus utilisées. Elle est plus facile à utiliser et à déployer que ses concurrentes.

En plus de sa facilité d'exécution, c'est une solution open source, sécurisée et économique. De nombreux entreprises et individus contribuent au développement de ce projet. Un large écosystème de produits, de services et de ressources est développé par cette vaste communauté.

#### conteneurisation vs virtualisation

##### virtualisation : 

La virtualisation est le fait de recréer un système d'exploitation complet et indépendant. Chaque machine virtuelle a sa propre OS, ses pilotes, etc. Cela signifie que la virtualisation offre une isolation complète entre la machine physique et la machine virtuelle, mais elle est plus gourmande en ressources, car chaque machine virtuelle doit inclure un système d'exploitation complet.

##### conteneurisation : 

La conteneurisation est le fait de partager la machine en gardant le même noyau d'OS et évitant ainsi la duplication des ressources. Chaque conteneur est une instance isolée d'une application avec ses propres bibliothèques et dépendances, mais elle n'a pas besoin d'un système d'exploitation complet. Cela la rend plus légère en termes de ressources par rapport à la virtualisation.



En résumé, la virtualisation isole les systèmes d'exploitation complets dans des machines virtuelles, tandis que la conteneurisation isole des applications individuelles dans des conteneurs légers. Chaque solution a ses avantages et ses inconvénients.

![Screenshot from 2023-09-15 10-16-46](https://github.com/dwesh163/stage-WP/assets/142376542/b67afd25-b26b-484a-a4c0-645a351e2941)

## Déploiement avec Docker (Ops)

#### Production :

- Se connecter à la machine distante en SSH
- Cloner le dépôt avec le fichier **docker-compose.yml**
- Exécuter la commande ```docker-compose up``` dans le dossier d'installation

Et voilà WordPress est installé avec docker

#### Mon déploiement en production est-il en tout point similaire à celui sur mon ordinateur ?

Oui, car se sont des packages docker qui sont facilement utilisable partout

## Wordpress@EPFL

## Alternative a WordPress
- Wix : l'alternative la plus populaire Affiliation.
- Squarespace : Meilleure alternative globale.
- Shopify : Meilleure alternative pour le e-commerce.

##  licence, prix et modèle commercial
#### wordpress est diviser en 2 filière 
- [wordpress.org](https://wordpress.org) est le logiciel WordPress gratuit et open source qui gère le système de site web
- [wordpress.com](https://wordpress.com) est la partie commerciale de WordPress, Elle est reliée à WordPress, car elle l'utilise.

## Site Connu qui utilise wordpress
- [EPFL.ch](https://EPFL.ch/)
- [thewaltdisneycompany.com](https://thewaltdisneycompany.com/)
- [whitehouse.gov](https://www.whitehouse.gov/)
- [www.bbc.com](https://www.bbc.com/)
- [www.renaultgroup.com](https://www.renaultgroup.com/)
- [LVMH.fr](https://www.lvmh.fr/)


## Avantages et inconvénients de WordPress

#### Quels sont les Avantages de WordPress ?

- Le logiciel est open-source et gratuit.
- Il est adaptable, de sorte que vous pouvez créer n'importe quel type de site Web.
- Il est facile à apprendre et il existe une vaste communauté.
- Vous pouvez mettre à jour et étendre votre site web à l'aide de thèmes et de plugins.

#### Quels sont les inconvénients de WordPress ?

- WordPress peut être lourd. 
- L'assistance WordPress est un forum.
- WordPress présente des risques de sécurité.

## WordPress est-il un bon choix pour l’EPFL

Oui, car il permet créer des gros sites très facilement avec beaucoup de contenu et en respectant la charte graphique de l'EPFL. Il permet grâce à la charte d'uniformiser les sites de toutes les facultés et il est assez simple  pour tous les collaborateurs de créer un site web.

## Bilan du stage

Durant ce stage, j'ai appris à connaitre WordPress et son fonctionnement. J'ai aussi appris à travailler sur une WM distante en SSH. J'ai découvert Docker que je ne connaissais pas du tout avant et que je trouve très utile. J'ai bien aimé la partie docker et moins bien aimer la partie WordPress@EPFL.


