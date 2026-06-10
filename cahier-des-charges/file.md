# Cahier des Charges Simplifié — Projet My Curly

## 1. C'est quoi My Curly ?

### 1.1 Le But

My Curly est une plateforme web dédiée aux personnes ayant les cheveux bouclés. Elle permet de découvrir des produits adaptés, réserver des services capillaires et consulter des conseils pour mieux prendre soin de leurs cheveux.

### 1.2 Pour qui ?

**Les Utilisateurs :**

* Créer un compte et se connecter.
* Consulter les produits.
* Passer des commandes.
* Réserver des services.
* Lire les articles du blog.
* Gérer leur profil.

**Les Administrateurs :**

* Gérer les utilisateurs.
* Gérer les produits et catégories.
* Gérer les commandes.
* Gérer les réservations.
* Gérer les articles et commentaires.

---

## 2. Que fait la plateforme ? (Fonctionnalités)

### 2.1 Pour les Utilisateurs

**Inscription et Connexion**

* Création de compte.
* Connexion sécurisée.
* Gestion du profil.

**Catalogue Produits**

* Consultation des produits.
* Recherche par catégorie.
* Affichage des détails des produits.

**Panier et Commandes**

* Ajout au panier.
* Validation des commandes.
* Consultation de l'historique des commandes.

**Réservation de Services**

* Consultation des services disponibles.
* Réservation en ligne.
* Suivi des réservations.

**Blog**

* Consultation des articles.
* Ajout de commentaires.

### 2.2 Pour les Administrateurs

**Tableau de bord**

* Vue globale des activités du site.

**Gestion des Produits**

* Ajouter, modifier ou supprimer des produits.

**Gestion des Catégories**

* Organiser les produits par catégories.

**Gestion des Commandes**

* Consulter et gérer les commandes.

**Gestion des Réservations**

* Valider ou annuler les réservations.

**Gestion du Blog**

* Ajouter, modifier ou supprimer des articles.
* Gérer les commentaires.

---

## 3. Design et Expérience Utilisateur (UI/UX)

### Interface Moderne

* Design moderne et professionnel.
* Navigation simple et intuitive.
* Couleurs adaptées à l'identité visuelle de My Curly.

### Responsive Design

* Compatible ordinateur.
* Compatible tablette.
* Compatible smartphone.

### Expérience Utilisateur

* Navigation rapide.
* Accès facile aux produits et services.
* Interface claire et ergonomique.

---

## 4. Technique et Sécurité

### 4.1 Sécurité

* Mots de passe sécurisés et chiffrés.
* Gestion des sessions utilisateurs.
* Protection contre les injections SQL grâce à PDO.
* Protection CSRF des formulaires.
* Contrôle des accès administrateur.

### 4.2 Technologies Utilisées

* PHP 8
* MySQL
* HTML5
* CSS3
* JavaScript
* AJAX
* XAMPP (développement local)

### 4.3 Base de Données

Tables principales :

* users
* categories
* products
* blog_posts
* comments
* likes
* cart_items
* orders
* order_items
* reservations
* services

---

## 5. Livrables Attendus

* Cahier des charges.
* Maquettes de l'application.
* MCD et MLD.
* Base de données MySQL.
* Code source complet.
* Rapport final.
* Présentation du projet.
