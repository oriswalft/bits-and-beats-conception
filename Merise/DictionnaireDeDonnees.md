# Dictionnaire de données

### Joueurs
| Champ          | Type    | Contraintes                            | Description                   |
| -------------- | ------- | -------------------------------------- | ----------------------------- |
| joueurs_id     | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique du joueur  |
| joueurs_email  | VARCHAR | NOT NULL, UNIQUE                       | Adresse email du joueur       |
| joueurs_mdp    | VARCHAR | NOT NULL                               | Mot de passe (hashé)          |
| joueurs_pseudo | VARCHAR | NOT NULL, UNIQUE                       | Pseudo/nom d'utilisateur      |
| roles_id       | UUID    | FOREIGN KEY                            | Référence vers la table roles |

### Rôles
| Champ    | Type    | Contraintes                            | Description                            |
| -------- | ------- | -------------------------------------- | -------------------------------------- |
| roles_id | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique du rôle             |
| role_nom | VARCHAR | NOT NULL                               | Nom du rôle (admin, utilisateur, etc.) |


### Historique

| Champ              | Type     | Contraintes                            | Description                               |
| ------------------ | -------- | -------------------------------------- | ----------------------------------------- |
| historique_id      | UUID     | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique de l'entrée historique |
| historique_contenu | TEXT     |                                        | Contenu/description de l'action           |
| historique_quand   | DATETIME | NOT NULL                               | Date et heure de l'action                 |  |

### joueurs_historiques

| Champ         | Type | Contraintes | Description               |
| ------------- | ---- | ----------- | ------------------------- |
| joueurs_id    | UUID | FOREIGN KEY | Référence vers joueurs    |
| historique_id | UUID | FOREIGN KEY | Référence vers historique |

### Musiques 
| Champ        | Type    | Contraintes                            | Description                      |
| ------------ | ------- | -------------------------------------- | -------------------------------- |
| musiques_id  | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique de la musique |
| musiques_nom | VARCHAR | NOT NULL                               | Titre de la musique              |


### Comptes_exterieurs
| Champ          | Type | Contraintes                 | Description                          |
| -------------- | ---- | --------------------------- | ------------------------------------ |
| comptes_ext_id | UUID | PRIMARY KEY, AUTO_INCREMENT | Identifiant unique du compte externe |
