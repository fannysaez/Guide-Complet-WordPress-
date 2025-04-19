# 📅 Jour 2 — Plugin custom : CSS + JS personnalisés

## 🎯 Objectif de la journée
- Utiliser un **plugin personnalisé** (fourni sur le Discord via GDrive)
- Injecter du **code CSS** et **JavaScript** personnalisé dans WordPress
- Comprendre comment intégrer ses propres scripts et styles dans un site WordPress proprement

---

## 🔧 Étape 1 – Récupération du plugin

1. Télécharge le plugin “Custom CSS + JS” via le lien GDrive partagé sur le Discord.
2. Vérifie que le fichier téléchargé est bien un `.zip` (ex: `custom-assets.zip`).

💡 Ne pas décompresser le fichier `.zip`, nous allons l’installer tel quel dans WordPress.

---

## 📥 Étape 2 – Installation du plugin

1. Va dans ton tableau de bord WordPress : `http://localhost/nomdusite/wp-admin`
2. Menu **Extensions > Ajouter**
3. Clique sur **Téléverser une extension**
4. Choisis le fichier `.zip`
5. Clique sur **Installer maintenant** puis sur **Activer**

📸 **Capture suggérée :** Interface WordPress, bouton “Téléverser une extension” avec le `.zip` sélectionné.

---

## 🧪 Étape 3 – Vérifier l’effet du plugin

1. Une fois activé, vérifie si le plugin :
   - Ajoute un menu dans l’administration (ex: “Custom Scripts”)
   - Fournit une interface pour ajouter du CSS ou JS directement

📸 **Capture suggérée :** Nouveau menu admin ou page du plugin avec champ d’édition de CSS/JS.

---

## 🧠 Étape 4 – Où est injecté le CSS/JS ?

Ce plugin injecte le CSS/JS dans le `head` ou le `footer` du site.

Tu peux :
- Ajouter du **CSS personnalisé** pour modifier l’apparence du thème
- Ajouter du **JS** pour ajouter des comportements (ex: animation, alertes, interactions)

Exemple CSS :

```css
body {
    background-color: #f0f0f0;
}
```
Exemple JS :

```js
document.addEventListener('DOMContentLoaded', function() {
    alert("Bienvenue sur notre site !");
});
```

---

⚙️ Étape 5 – Alternative via le code (`functions.php`)

Il est aussi possible d’ajouter ses fichiers dans le `thème enfant` via functions.php :

```php
function add_custom_assets() {
    wp_enqueue_style('custom-style', get_stylesheet_directory_uri() . '/assets/custom.css');
    wp_enqueue_script('custom-js', get_stylesheet_directory_uri() . '/assets/custom.js', [], false, true);
}
add_action('wp_enqueue_scripts', 'add_custom_assets');
```

🔐 Sécurité : bonnes pratiques

* Toujours filtrer/sanitiser le contenu dynamique en JS
* Ne pas inclure de bibliothèques JS/CDN externes sans vérification
* Tester ton code dans un environnement local avant de le pousser en production

✅ Résultat attendu

* ✅ Plugin installé et activé
* ✅ Code CSS et JS personnalisé visible sur le site
* ✅ Compréhension du fonctionnement de l’injection dans WordPress

📚 Ressources utiles

* 🔗 [Documentation officielle plugins WordPress](https://developer.wordpress.org/plugins/intro/)

---

<p align="center">
  <a href="...">Suivant</a>
</p>