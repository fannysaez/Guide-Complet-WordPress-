# 📅 Jour 1 — Gestion des Rôles personnalisés (Plugin)

## 🎯 Objectif de la journée
Mettre en place et comprendre la gestion des rôles utilisateurs dans WordPress via :
- Un **plugin personnalisé** fourni sur le Discord (via Google Drive)
- L’installation et l’activation d’un plugin via l’interface d’administration
- L'exploration des rôles WordPress existants
- La création de rôles personnalisés via du code PHP

---

## 🔧 Étape 1 – Récupération du plugin

1. Télécharger le plugin "Custom Roles" fourni sur le Discord (lien GDrive).
2. Vérifie qu’il s’agit bien d’un fichier `.zip`.

💡 Astuce : Ne décompresse pas le fichier `.zip`, on va l’installer directement tel quel.

---

## 📥 Étape 2 – Installation du plugin

1. Accède à ton back-office WordPress : `http://localhost/nomdusite/wp-admin`
2. Va dans **Extensions > Ajouter**
3. Clique sur **Téléverser une extension**
4. Sélectionne le fichier `.zip` du plugin
5. Clique sur **Installer maintenant**
6. Puis **Activer**

📸 **Capture d'écran suggérée :** Interface WordPress avec l’onglet “Ajouter une extension” + bouton de téléversement du `.zip`.

---

## 🔍 Étape 3 – Vérification dans le menu

1. Une fois activé, vérifie que le plugin ajoute un menu personnalisé dans l’admin (ex : "Gestion des rôles").
2. Explore les fonctionnalités offertes : création, modification, suppression de rôles.

📸 **Capture d'écran suggérée :** Nouveau menu ajouté par le plugin dans la sidebar de l’admin WordPress.

---

## 👥 Étape 4 – Comprendre les rôles WordPress

WordPress propose par défaut plusieurs rôles utilisateur :

| Rôle             | Capacités principales                          |
|------------------|-------------------------------------------------|
| Administrateur   | Tous les droits, y compris l'installation de plugins |
| Éditeur          | Gère tous les articles, y compris ceux des autres |
| Auteur           | Gère uniquement ses propres articles            |
| Contributeur     | Rédige des articles sans pouvoir les publier    |
| Abonné           | Peut seulement lire et commenter                |

Source : [Documentation officielle des rôles](https://wordpress.org/documentation/article/roles-and-capabilities/)

---

## 🧪 Étape 5 – Créer un rôle personnalisé via PHP

Tu peux aussi créer un rôle personnalisé avec du code, à placer dans un fichier `.php` (ex: `functions.php` de ton thème enfant ou dans un plugin custom).

```php
function add_custom_author_role() {
    add_role('author_pro', 'Auteur Pro', [
        'read' => true,
        'edit_posts' => true,
        'delete_posts' => false,
        'publish_posts' => true,
    ]);
}
add_action('init', 'add_custom_author_role');
```

---

✅ Résultat attendu

    ✅ Plugin installé et activé
    ✅ Nouveau rôle visible ou créé
    ✅ Compréhension de la gestion des permissions
    ✅ (Bonus) Utilisation de l’interface visuelle avec le plugin Members

📚 Ressources utiles

    [🔗 Documentation officielle WordPress](https://wordpress.org/documentation/)
    [🔗 Créer un rôle personnalisé – nettsmed.no](https://nettsmed.no/creating-custom-user-role-inwordpress/#example-1-adding-a-author-pro-custom-user-role-in-word-press)
    [🔗 Plugin Members – WordPress.org](https://wordpress.org/plugins/members/)

---

<p align="center">
  <a href="customJs-et-CSS.md">Suivant</a>
</p>