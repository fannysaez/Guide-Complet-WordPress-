# 📅 Jour 3 — Environnement de développement WordPress & gestion avancée des rôles

## 🎯 Objectif de la journée

- Installer et utiliser **LocalWP** pour un environnement WordPress local facile
- Créer un **blueprint** pour réutiliser une configuration de site
- Approfondir la gestion des **rôles et permissions**
- Comprendre les **hooks** WordPress
- Découvrir l’éditeur **Gutenberg**
- Gérer les **médias**

---

## 🧰 Étape 1 – Installer LocalWP

### 🔗 Lien de téléchargement :
👉 [https://localwp.com](https://localwp.com)

1. Télécharge **Local** selon ton système (Windows / macOS / Linux).
2. Suis l’installation classique (suivant / suivant / installer).
3. Lance l’application.

📸 **Capture suggérée :** Interface de Local avec bouton “+ Create a new site”.

---

## 🛠️ Étape 2 – Créer un site local avec Local

1. Clique sur **+ Create a new site**
2. Donne un nom (ex: `mon-site-test`)
3. Choisis les réglages par défaut (Preferred)
4. Définis un identifiant admin et mot de passe

💡 Local crée automatiquement :
- Une base de données
- Un WordPress fonctionnel
- Une URL locale (ex: `http://mon-site-test.local`)

📸 **Capture suggérée :** Page de création d’un site avec configuration apparente.

---

## 📦 Étape 3 – Créer un Blueprint (modèle de site)

Un **blueprint** est un modèle de site que tu peux réutiliser avec :
- Thème personnalisé
- Plugins installés
- Pages déjà créées

### 🔗 Guide officiel :  
👉 [https://localwp.com/help-docs/local-features/how-to-use-blueprints](https://localwp.com/help-docs/local-features/how-to-use-blueprints/)

1. Clique droit sur un site dans Local > **“Save as Blueprint”**
2. Nomme ton blueprint
3. Il sera disponible lors de la création d’un nouveau site

📸 **Capture suggérée :** Option “Save as Blueprint” visible sur un site Local.

---

## 👥 Étape 4 – Gestion avancée des rôles avec le plugin "Members"

1. Va dans **Extensions > Ajouter**
2. Rechercher **Members**
3. Installe et active le plugin : [https://wordpress.org/plugins/members](https://wordpress.org/plugins/members/)

Il permet de :
- Créer des **rôles personnalisés**
- Modifier les **permissions** (capabilities)
- Attribuer des rôles à des utilisateurs

📸 **Capture suggérée :** Interface du plugin “Members” avec une liste des rôles.

---

## 🧑‍💻 Étape 5 – Créer un rôle en PHP

Extrait de code à ajouter dans un plugin custom ou dans le `functions.php` :

```php
function mon_role_personnalise() {
    add_role('test_editor', 'Test Editor', [
        'read' => true,
        'edit_posts' => true,
        'edit_others_posts' => true,
        'delete_posts' => false,
    ]);
}
add_action('init', 'mon_role_personnalise');
```

---

🔁 Étape 6 – Hooks WordPress

👉 https://developer.wordpress.org/plugins/hooks

## 🔄 Les Hooks dans WordPress

WordPress repose sur deux types de hooks :

| Type    | Exemple                                         | Description                                |
|---------|-------------------------------------------------|--------------------------------------------|
| Action  | `add_action('init', 'fonction')`                | Exécute une fonction à un moment donné     |
| Filter  | `add_filter('the_content', 'modifier_le_contenu')` | Modifie une donnée avant affichage         |

Exemple de filter :

```php
function ajouter_note_bas_article($content) {
    if (is_single()) {
        $content .= '<p><em>Merci pour votre lecture !</em></p>';
    }
    return $content;
}
add_filter('the_content', 'ajouter_note_bas_article');
```
---

✍️ Étape 7 – Utiliser l’éditeur Gutenberg

👉 https://wpmarmite.com/en/wordpress/gutenberg

* Crée une nouvelle page ou un nouvel article
* Utilise les blocs pour structurer ton contenu :
* Paragraphe, Titre, Image, Liste, Colonnes…
* Teste l’ajout de blocs réutilisables et la prévisualisation
---

✅ Résultat attendu

    ✅ Environnement local fonctionnel avec LocalWP
    ✅ Blueprint créé pour usage futur
    ✅ Plugin Members installé et testé
    ✅ Création et gestion de rôles personnalisés
    ✅ Hooks testés (action & filter)
    ✅ Utilisation de Gutenberg pour créer une page structurée
    ✅ Gestion de la bibliothèque de médias

---

📚 Ressources utiles

* 🔗 [LocalWP – Installer](https://localwp.com/help-docs/getting-started/installing-local/)
* 🔗 [Créer des rôles en PHP](https://nettsmed.no/creating-custom-user-role-inwordpress/#example-1-adding-a-author-pro-custom-user-role-in-word-press)
* 🔗 [Plugin Members – WordPress](https://developer.wordpress.org/plugins/intro/)
* 🔗 [Hooks WordPress – Developer doc](https://developer.wordpress.org/plugins/hooks/)
* 🔗 [Gutenberg – WPMarmite](https://wpmarmite.com/en/wordpress/gutenberg/)

---

<p align="center">
  <a href="cpt-acf.md">Suivant</a>
</p>