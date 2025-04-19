# 🧩 Formation WordPress — Guide Complet Étape par Étape

## 📚 Sommaire

1. [Jour 1 – Custom Roles (Plugin)](#jour-1--custom-roles-plugin)
2. [Jour 2 – Custom JS + CSS](#jour-2--custom-js--css)
3. [Jour 3 – Environnement Dev avec LocalWP](#jour-3--environnement-dev-avec-localwp)
4. [Jour 4 – Custom Post Types + ACF](#jour-4--custom-post-types--acf)
5. [Jour 5 – Front-end, CPT, WooCommerce, SEO & Éco-conception](#jour-5--front-end-cpt-woocommerce-seo--éco-conception)

---

## 📅 Jour 1 — Custom Roles (Plugin)

### ▶️ Objectif
Découverte de la gestion des rôles utilisateurs via un plugin personnalisé.

### 🔧 Étapes

1. Télécharger le plugin fourni via le lien GDrive (ex: `custom-roles.zip`).
2. Aller dans **Extensions > Ajouter > Téléverser une extension**.
3. Activer l’extension.

📸 _Exemple capture : Interface d’activation plugin_

---

## 📅 Jour 2 — Custom JS + CSS

### ▶️ Objectif
Ajouter du JS et CSS personnalisé via un plugin.

### 🔧 Étapes

1. Télécharger le plugin fourni via GDrive (`custom-js-css.zip`).
2. Installer et activer comme en jour 1.
3. Le plugin ajoute un champ dans le back-office pour intégrer votre CSS et JS.
4. Vérifier sur le front-end si les styles et scripts sont appliqués.

📸 _Exemple capture : Interface du plugin JS/CSS_

---

## 📅 Jour 3 — Environnement Dev avec LocalWP

### ▶️ Objectif
Créer un environnement de développement local pour WordPress.

### 🔧 Installer LocalWP

- Télécharger LocalWP : [https://localwp.com/](https://localwp.com/)
- Guide d’installation : [Voir ici](https://localwp.com/help-docs/getting-started/installing-local/)

📸 _Exemple capture : Interface LocalWP_

### 🧪 Créer un site avec Local

1. Lancer Local > "Create a new site".
2. Remplir le nom du site, choisir la configuration PHP/MySQL.
3. Installer WordPress automatiquement.

### 📦 Utiliser les Blueprints

- Guide officiel : [How to Use Blueprints](https://localwp.com/help-docs/local-features/how-to-use-blueprints/)
- Permet de réutiliser un site pré-configuré.

📸 _Exemple capture : Blueprints dans Local_

---

### 🔑 Rôles et Permissions

- Extension recommandée : [Members](https://wordpress.org/plugins/members/)
- Permet de gérer finement les rôles et leurs permissions.

📸 _Exemple capture : Interface Members_

---

### 🧠 Créer un rôle personnalisé en PHP

Source : [Créer un rôle](https://nettsmed.no/creating-custom-user-role-inwordpress/#example-1-adding-a-author-pro-custom-user-role-in-word-press)

```php
function add_custom_author_role() {
    add_role('author_pro', 'Auteur Pro', [
        'read' => true,
        'edit_posts' => true,
        'delete_posts' => false,
    ]);
}
add_action('init', 'add_custom_author_role');
```

---

<p align="center">
  <a href="customRoles.md">Suivant</a>
</p>