# Dictionnaire de données

### Joueurs
| Champ          | Type    | Contraintes                 | Description                   |
| -------------- | ------- | --------------------------- | ----------------------------- |
| joueurs_id     | INT     | PRIMARY KEY, AUTO_INCREMENT | Identifiant unique du joueur  |
| joueurs_email  | VARCHAR | NOT NULL, UNIQUE            | Adresse email du joueur       |
| joueurs_mdp    | VARCHAR | NOT NULL                    | Mot de passe (hashé)          |
| joueurs_pseudo | VARCHAR | NOT NULL, UNIQUE            | Pseudo/nom d'utilisateur      |
| roles_id       | INT     | FOREIGN KEY                 | Référence vers la table roles |