# 📅 Jour 4 — Custom Post Types, ACF, WooCommerce, optimisation

## 🎯 Objectifs du jour

- Créer un **Custom Post Type (CPT)**
- Afficher un CPT avec un **template personnalisé**
- Utiliser les **champs personnalisés ACF**
- Créer un **shortcode**
- Installer et découvrir **WooCommerce**
- Aborder les bases de l’**éco-conception web**

---

## 📁 Étape 1 – Créer un Custom Post Type

👉 Documentation officielle : [learn.wordpress.org - Custom Post Types](https://learn.wordpress.org/lesson/custom-post-types/)

1. Installe et active l’extension gratuite **CPT UI**
2. Va dans **CPT UI > Ajouter un nouveau type de publication**
3. Exemple :
   - Slug : `recette`
   - Pluriel : `Recettes`
   - Singulier : `Recette`
4. Active l’option “Public” et “Afficher dans REST API”

📸 **Capture suggérée :** Interface du plugin CPT UI avec configuration d’un CPT “Recette”.

---

## 🗂️ Étape 2 – Créer un template custom pour le CPT

👉 Tu peux le faire manuellement dans ton **thème enfant**.

1. Crée un **thème enfant** (si pas encore fait)  
👉 Guide : [Créer un thème enfant WordPress](https://developer.wordpress.org/themes/advanced-topics/child-themes/)

2. Crée un dossier `templates` dans ton thème enfant  
3. Crée un fichier nommé : `single-recette.html` ou `single-recette.php`

### Exemple de contenu `single-recette.php`

```php
get_header();


the_title();
the_content();

get_footer();
```
---

🧩 Étape 3 – Créer un Shortcode personnalisé

👉 [Documentation officielle – add_shortcode()](https://developer.wordpress.org/reference/functions/add_shortcode/)

Ajoute dans `functions.php` ou un plugin custom :

```php
function afficher_annee() {
    return date('Y');
}
add_shortcode('annee', 'afficher_annee');
```
➡️ Dans un article, tu peux ensuite écrire : [annee] pour afficher “2025”.

---

🧠 Étape 4 – Ajouter des champs personnalisés avec ACF

👉 [Documentation ACF](https://www.advancedcustomfields.com/resources/)

1. Installe et active le plugin ACF

2. Crée un groupe de champs :

    * Exemple : `Détails Recette`

    * Ajoute un champ Temps de cuisson (type : nombre)

    * Affecte le groupe au post type recette

3. Dans single-recette.php, ajoute :

```php
Temps de cuisson : the_field('temps_de_cuisson'); minutes
```

---


🛍️ Étape 5 – Installer et découvrir WooCommerce

👉 Documentation :

* [WooCommerce Setup Wizard](https://woocommerce.com/document/woocommerce-setup-wizard/)

* [WooCommerce Getting Started](https://woocommerce.com/documentation/woocommerce/getting-started/)

1. Va dans Extensions > Ajouter

2. Rechercher WooCommerce

3. Installer & activer

4. Suis l’assistant de configuration : devise, paiement, transport…

`Page de configuration WooCommerce, vue boutique.`

---

✅ Résultat attendu

    ✅ Custom Post Type “Recette” fonctionnel
    ✅ Template personnalisé single-recette.php opérationnel
    ✅ Champs ACF visibles et récupérés
    ✅ Shortcode fonctionnel
    ✅ WooCommerce installé et testé
    ✅ Audit écologique effectué via Ecoindex ou Lighthouse

---

📚 Ressources utiles

* 🔗 [Créer un thème enfant WordPress](https://developer.wordpress.org/themes/advanced-topics/child-themes/)
* 🔗 [Documentation Custom Post Types](https://learn.wordpress.org/lesson/custom-post-types/)
* 🔗 [Shortcodes – WordPress](https://developer.wordpress.org/reference/functions/add_shortcode/)
* 🔗 [ACF – Récupérer les données](https://www.advancedcustomfields.com/resources/get_field/)
* 🔗 [WooCommerce Setup Wizarde](https://woocommerce.com/document/woocommerce-setup-wizard/)

---

<p align="center">
  <a href="front-woocommerce-seo.md">Suivant</a>
</p>