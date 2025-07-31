# RBAC 

|                                       | Visiteur | Joueur | Modérateur | Administrateur |
| ------------------------------------- | -------- | ------ | ---------- | -------------- |
| Création de compte                    | V        | X      | X          | X              |
| Connexion                             | V        | X      | V          | V              |
| Consulter le contenu de la plateforme | V        | V      | V          | V              |
| Consulter un profil                   | V        | V      | V          | V              |
| Modifier son profil                   | X        | V      | X          | V              |
| Supprimer un joueur                   | X        | X      | X          | V              |
| Publier un commentaire                | X        | V      | V          | V              |
| Modifier un commentaire               | X        | V      | V          | V              |
| Supprimer un commentaire              | X        | V      | V          | V              |
| Signaler un contenu                   | X        | V      | V          | V              |

| Gérer les joueurs                     | X        | X      | X           | V              |
| Gérer les modérateurs                 | X        | X      | X           | V              |
| Gérer les administrateurs             | X        | X      | X           | V              |
| Gérer les contenus                    | X        | X      | V           | V              |
| Gérer les commentaires                | X        | X      | V           | V              |
| Gérer les signalements                | X        | X      | V           | V              |
| Gérer les permissions                 | X        | X      | X           | V              |
| Gérer les rôles                       | X        | X      | X           | V              |
| Gérer les logs                        | X        | X      | V (partiel) | V              |
| Gérer les paramètres de la plateforme | X        | X      | X           | V              |
| Gérer les événements                  | X        | X      | V           | V              |
| Gérer les notifications               | X        | X      | V           | V              |