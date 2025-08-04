# Dictionnaire de données

### Joueurs
| Champ          | Type    | Contraintes                 | Description                   |
| -------------- | ------- | --------------------------- | ----------------------------- |
| joueurs_id     | UUID    | PRIMARY KEY, AUTO_INCREMENT | Identifiant unique du joueur  |
| joueurs_email  | VARCHAR | NOT NULL, UNIQUE            | Adresse email du joueur       |
| joueurs_mdp    | VARCHAR | NOT NULL                    | Mot de passe (hashé)          |
| joueurs_pseudo | VARCHAR | NOT NULL, UNIQUE            | Pseudo/nom d'utilisateur      |
| roles_id       | UUID    | FOREIGN KEY                 | Référence vers la table roles |

### Rôles
| Champ    | Type    | Contraintes                 | Description                            |
| -------- | ------- | --------------------------- | -------------------------------------- |
| roles_id | UUID    | PRIMARY KEY, AUTO_INCREMENT | Identifiant unique du rôle             |
| role_nom | VARCHAR | NOT NULL                    | Nom du rôle (admin, utilisateur, etc.) |

### Historique

| Champ              | Type      | Contraintes                 | Description                               |
| ------------------ | --------- | --------------------------- | ----------------------------------------- |
| historique_id      | UUID      | PRIMARY KEY, AUTO_INCREMENT | Identifiant unique de l'entrée historique |
| historique_contenu | TEXT      |                             | Contenu/description de l'action           |
| historique_quand   | TIMESTAMP | NOT NULL                    | Date et heure de l'action                 |

### joueurs_historiques

| Champ         | Type | Contraintes | Description               |
| ------------- | ---- | ----------- | ------------------------- |
| joueurs_id    | UUID | FOREIGN KEY | Référence vers joueurs    |
| historique_id | UUID | FOREIGN KEY | Référence vers historique |

