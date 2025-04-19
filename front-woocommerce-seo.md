# 📅 Jour 5 — Inscription front, CPT avancé, shortcodes, WooCommerce & sécurité CAPTCHA

## 🎯 Objectifs

- Ajouter un formulaire d’inscription utilisateur en frontend
- Créer un template custom pour un CPT
- Récupérer des données ACF dans un template
- Créer un shortcode pour afficher des éléments personnalisés
- Approfondir WooCommerce
- Renforcer la sécurité avec un CAPTCHA (Turnstile ou Recaptcha)

---

## 🔐 Étape 1 – Plugin d’inscription via le frontend

👉 Le plugin fourni sur le GDrive permet d’avoir un formulaire d’inscription simple sur une page WordPress.

1. Télécharge le plugin fourni via GDrive
2. Va dans **Extensions > Ajouter > Téléverser une extension**
3. Sélectionne le ZIP du plugin et installe-le
4. Active-le
5. Une fois activé, un shortcode est probablement disponible : `[user_registration_form]`

➡️ Colle ce shortcode dans une page “Inscription”

📸 **Capture suggérée :** Formulaire d’inscription visible côté frontend.

---

## 🧱 Étape 2 – Création d’un template custom pour un CPT

1. Va dans ton thème enfant
2. Crée un fichier nommé `single-nomducpt.php`  
   Exemple : `single-recette.php` si ton CPT est `recette`

### Exemple minimal de `single-recette.php` :

```php
get_header();

the_title(); 
the_content(); 

get_footer(); 
```

---

📥 Étape 3 – Récupération de données ACF dans un template

👉 get_field() – ACF`

Ajoute dans ton `single-recette.php` :

```php
if(get_field('temps_de_cuisson'))
  Temps de cuisson : the_field('temps_de_cuisson'); minutes
endif;
```

---

🧩 Étape 4 – Créer un `shortcode` pour afficher une liste de recettes

Dans `functions.php` de ton `thème enfant` :

```php
function shortcode_liste_recettes() {
    $args = array(
        'post_type' => 'recette',
        'posts_per_page' => 5
    );
    $query = new WP_Query($args);
    $output = '<ul>';
    while ($query->have_posts()) {
        $query->the_post();
        $output .= '<li><a href="'.get_permalink().'">'.get_the_title().'</a></li>';
    }
    $output .= '</ul>';
    wp_reset_postdata();
    return $output;
}
add_shortcode('recettes_recent', 'shortcode_liste_recettes');
```

➡️ Utilisation dans une page : `[recettes_recent]`

---


🛒 Étape 5 – Aller plus loin avec WooCommerce

👉 Documentation :

* [Getting Started](https://woocommerce.com/documentation/woocommerce/getting-started/)

1. Active le plugin WooCommerce

2. Explore :

    - Produits > Ajouter un nouveau produit

    - Réglages > Paiement / Livraison / Taxes

3. Ajoute une image produit, une description, un prix

📸 Capture suggérée : `Fiche produit WooCommerce`.

---

<p align="center">
  <a href="readme.md">Suivant</a>
</p>