# Dictionnaire de données - Base de données musicale

## Table: **joueurs**
Stocke les informations des utilisateurs de la plateforme musicale.

| Champ          | Type    | Contraintes                            | Description                   |
| -------------- | ------- | -------------------------------------- | ----------------------------- |
| joueurs_id     | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique du joueur  |
| joueurs_email  | VARCHAR | NOT NULL, UNIQUE                       | Adresse email du joueur       |
| joueurs_mdp    | VARCHAR | NOT NULL                               | Mot de passe (hashé)          |
| joueurs_pseudo | VARCHAR | NOT NULL, UNIQUE                       | Pseudo/nom d'utilisateur      |
| roles_id       | UUID    | FOREIGN KEY                            | Référence vers la table roles |

---

## Table: **roles**
Définit les différents rôles d'utilisateurs dans le système.

| Champ    | Type    | Contraintes                            | Description                            |
| -------- | ------- | -------------------------------------- | -------------------------------------- |
| roles_id | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique du rôle             |
| role_nom | VARCHAR | NOT NULL                               | Nom du rôle (admin, utilisateur, etc.) |

---

## Table: **historique**
Enregistre l'historique des actions des joueurs.

| Champ              | Type      | Contraintes                            | Description                               |
| ------------------ | --------- | -------------------------------------- | ----------------------------------------- |
| historique_id      | UUID      | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique de l'entrée historique |
| historique_contenu | TEXT      |                                        | Contenu/description de l'action           |
| historique_quand   | TIMESTAMP | NOT NULL                               | Date et heure de l'action                 |

---

## Table: **joueurs_historique**
Table de liaison entre joueurs et historique (relation many-to-many).

| Champ         | Type | Contraintes | Description               |
| ------------- | ---- | ----------- | ------------------------- |
| joueurs_id    | UUID | FOREIGN KEY | Référence vers joueurs    |
| historique_id | UUID | FOREIGN KEY | Référence vers historique |

---

## Table: **musiques**
Stocke les informations des morceaux de musique.

| Champ        | Type    | Contraintes                            | Description                      |
| ------------ | ------- | -------------------------------------- | -------------------------------- |
| musiques_id  | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique de la musique |
| musiques_nom | VARCHAR | NOT NULL                               | Titre de la musique              |

---

## Table: **favoris_musiques**
Gère les musiques favorites des joueurs.

| Champ       | Type | Contraintes | Description             |
| ----------- | ---- | ----------- | ----------------------- |
| joueurs_id  | UUID | FOREIGN KEY | Référence vers joueurs  |
| musiques_id | UUID | FOREIGN KEY | Référence vers musiques |

---

## Table: **vote**
Stocke les votes des joueurs sur les musiques.

| Champ           | Type | Contraintes | Description                         |
| --------------- | ---- | ----------- | ----------------------------------- |
| joueurs_id      | UUID | FOREIGN KEY | Référence vers joueurs              |
| prop_musique_id | UUID | FOREIGN KEY | Référence vers propositions_musique |

---

## Table: **propositions_musique**
Gère les propositions de musiques par les joueurs.

| Champ              | Type    | Contraintes                            | Description                          |
| ------------------ | ------- | -------------------------------------- | ------------------------------------ |
| prop_musique_id    | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique de la proposition |
| prop_musique_titre | VARCHAR | NOT NULL                               | Titre de la musique proposée         |
| musiques_id        | UUID    | FOREIGN KEY                            | Référence vers musiques              |

---

## Table: **joueurs_propositions**
Table de liaison entre joueurs et leurs propositions.

| Champ           | Type | Contraintes | Description                         |
| --------------- | ---- | ----------- | ----------------------------------- |
| joueurs_id      | UUID | FOREIGN KEY | Référence vers joueurs              |
| prop_musique_id | UUID | FOREIGN KEY | Référence vers propositions_musique |

---

## Table: **sources_proposition**
Définit les sources des propositions musicales.

| Champ           | Type | Contraintes | Description                         |
| --------------- | ---- | ----------- | ----------------------------------- |
| sources_id      | UUID | FOREIGN KEY | Référence vers sources              |
| prop_musique_id | UUID | FOREIGN KEY | Référence vers propositions_musique |

---

## Table: **sources**
Stocke les différentes sources de musique (plateformes, services).

| Champ        | Type    | Contraintes                            | Description                     |
| ------------ | ------- | -------------------------------------- | ------------------------------- |
| sources_id   | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique de la source |
| sources_lien | VARCHAR |                                        | Lien vers la source             |
| musiques_id  | UUID    | FOREIGN KEY                            | Référence vers musiques         |

---

## Table: **disponible**
Gère la disponibilité des musiques sur différentes sources.

| Champ        | Type | Contraintes | Description              |
| ------------ | ---- | ----------- | ------------------------ |
| bande_son_id | UUID | FOREIGN KEY | Référence vers bande_son |
| sources_id   | UUID | FOREIGN KEY | Référence vers sources   |

---

## Table: **bande_son**
Stocke les informations des bandes sonores.

| Champ         | Type    | Contraintes                            | Description                           |
| ------------- | ------- | -------------------------------------- | ------------------------------------- |
| bande_son_id  | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique de la bande sonore |
| bande_son_nom | VARCHAR | NOT NULL                               | Nom de la bande sonore                |

---

## Table: **bande_son_musiques**
Table de liaison entre bandes sonores et musiques.

| Champ        | Type | Contraintes | Description              |
| ------------ | ---- | ----------- | ------------------------ |
| bande_son_id | UUID | FOREIGN KEY | Référence vers bande_son |
| musiques_id  | UUID | FOREIGN KEY | Référence vers musiques  |

---

## Table: **doit_avoir**
Définit les relations obligatoires entre bandes sonores et tags.

| Champ        | Type | Contraintes | Description              |
| ------------ | ---- | ----------- | ------------------------ |
| bande_son_id | UUID | FOREIGN KEY | Référence vers bande_son |
| tag_id       | UUID | FOREIGN KEY | Référence vers tag       |

---

## Table: **tag**
Stocke les tags/étiquettes pour catégoriser le contenu.

| Champ   | Type    | Contraintes                            | Description               |
| ------- | ------- | -------------------------------------- | ------------------------- |
| tag_id  | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique du tag |
| tag_nom | VARCHAR | NOT NULL                               | Nom du tag                |

---

## Table: **tag_musiques**
Table de liaison entre tags et musiques.

| Champ       | Type | Contraintes | Description             |
| ----------- | ---- | ----------- | ----------------------- |
| musiques_id | UUID | FOREIGN KEY | Référence vers musiques |
| tag_id      | UUID | FOREIGN KEY | Référence vers tag      |

---

## Table: **bande_son_langues**
Gère les langues associées aux bandes sonores.

| Champ        | Type | Contraintes | Description              |
| ------------ | ---- | ----------- | ------------------------ |
| bande_son_id | UUID | FOREIGN KEY | Référence vers bande_son |
| langues_id   | UUID | FOREIGN KEY | Référence vers langues   |

---

## Table: **langues**
Stocke les différentes langues disponibles.

| Champ       | Type    | Contraintes                            | Description                     |
| ----------- | ------- | -------------------------------------- | ------------------------------- |
| langues_id  | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique de la langue |
| langues_nom | VARCHAR | NOT NULL                               | Nom de la langue                |

---

## Table: **langues_musiques**
Table de liaison entre langues et musiques.

| Champ       | Type | Contraintes | Description             |
| ----------- | ---- | ----------- | ----------------------- |
| musiques_id | UUID | FOREIGN KEY | Référence vers musiques |
| langues_id  | UUID | FOREIGN KEY | Référence vers langues  |

---

## Table: **bande_son_compositeur**
Table de liaison entre bandes sonores et compositeurs.

| Champ          | Type | Contraintes | Description                |
| -------------- | ---- | ----------- | -------------------------- |
| bande_son_id   | UUID | FOREIGN KEY | Référence vers bande_son   |
| compositeur_id | UUID | FOREIGN KEY | Référence vers compositeur |

---

## Table: **compositeur**
Stocke les informations des compositeurs.

| Champ          | Type    | Contraintes                            | Description                       |
| -------------- | ------- | -------------------------------------- | --------------------------------- |
| compositeur_id | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique du compositeur |
| nom            | VARCHAR | NOT NULL                               | Nom du compositeur                |
| groupe         | VARCHAR |                                        | Nom du groupe (si applicable)     |

---

## Table: **compositeur_musiques**
Table de liaison entre compositeurs et musiques.

| Champ          | Type | Contraintes | Description                |
| -------------- | ---- | ----------- | -------------------------- |
| musiques_id    | UUID | FOREIGN KEY | Référence vers musiques    |
| compositeur_id | UUID | FOREIGN KEY | Référence vers compositeur |

---

## Table: **bande_son_pochette**
Gère les pochettes des bandes sonores.

| Champ        | Type | Contraintes | Description              |
| ------------ | ---- | ----------- | ------------------------ |
| bande_son_id | UUID | FOREIGN KEY | Référence vers bande_son |
| pochette_id  | UUID | FOREIGN KEY | Référence vers pochette  |

---

## Table: **pochette**
Stocke les informations des pochettes/images.

| Champ       | Type    | Contraintes                            | Description                       |
| ----------- | ------- | -------------------------------------- | --------------------------------- |
| pochette_id | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique de la pochette |
| image_link  | VARCHAR |                                        | Lien vers l'image de la pochette  |

---

## Table: **pochette_musiques**
Table de liaison entre pochettes et musiques.

| Champ       | Type | Contraintes | Description             |
| ----------- | ---- | ----------- | ----------------------- |
| musiques_id | UUID | FOREIGN KEY | Référence vers musiques |
| pochette_id | UUID | FOREIGN KEY | Référence vers pochette |

---

## Tables liées aux jeux

### Table: **joueurs_jeux**
Table de liaison entre joueurs et jeux.

| Champ      | Type | Contraintes | Description            |
| ---------- | ---- | ----------- | ---------------------- |
| joueurs_id | UUID | FOREIGN KEY | Référence vers joueurs |
| jeux_id    | UUID | FOREIGN KEY | Référence vers jeux    |

---

### Table: **jeux**
Stocke les informations des jeux.

| Champ           | Type | Contraintes                            | Description                 |
| --------------- | ---- | -------------------------------------- | --------------------------- |
| jeux_id         | UUID | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique du jeu   |
| resume          | TEXT |                                        | Résumé/description du jeu   |
| date_sortie_of  | DATE |                                        | Date de sortie officielle   |
| developpeurs_id | UUID | FOREIGN KEY                            | Référence vers développeurs |

---

### Table: **jeux_publies**
Gère les jeux publiés par les développeurs.

| Champ         | Type | Contraintes | Description               |
| ------------- | ---- | ----------- | ------------------------- |
| jeux_id       | UUID | FOREIGN KEY | Référence vers jeux       |
| plateforme_id | UUID | FOREIGN KEY | Référence vers plateforme |

---

### Table: **genres_jeux**
Table de liaison entre genres et jeux.

| Champ     | Type | Contraintes | Description           |
| --------- | ---- | ----------- | --------------------- |
| jeux_id   | UUID | FOREIGN KEY | Référence vers jeux   |
| genres_id | UUID | FOREIGN KEY | Référence vers genres |

---

### Table: **genres**
Stocke les genres de jeux.

| Champ      | Type    | Contraintes                            | Description                 |
| ---------- | ------- | -------------------------------------- | --------------------------- |
| genres_id  | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique du genre |
| genres_nom | VARCHAR | NOT NULL                               | Nom du genre                |

---

### Table: **developpeurs**
Stocke les informations des développeurs de jeux.

| Champ                | Type    | Contraintes                            | Description                       |
| -------------------- | ------- | -------------------------------------- | --------------------------------- |
| developpeurs_id      | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique du développeur |
| developpeur_nom      | VARCHAR | NOT NULL                               | Nom du développeur                |
| developpeur_website  | VARCHAR |                                        | Site web du développeur           |
| developpeur_logo     | VARCHAR |                                        | Lien vers le logo                 |
| developpeur_desc     | TEXT    |                                        | Description du développeur        |
| developpeur_siglenom | VARCHAR |                                        | Sigle/acronyme                    |

---

### Table: **plateforme**
Stocke les plateformes de jeu.

| Champ             | Type    | Contraintes                            | Description                         |
| ----------------- | ------- | -------------------------------------- | ----------------------------------- |
| plateforme_id     | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique de la plateforme |
| plateforme_nom    | VARCHAR | NOT NULL                               | Nom de la plateforme                |
| plateforme_devnom | VARCHAR |                                        | Nom du développeur de la plateforme |

---

### Table: **plateforme_jv**
Table de liaison entre plateformes et jeux vidéo.

| Champ             | Type    | Contraintes                            | Description             |
| ----------------- | ------- | -------------------------------------- | ----------------------- |
| plateforme_jv_id  | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique      |
| plateforme_jv_nom | VARCHAR | NOT NULL                               | Nom de la plateforme JV |

---

### Table: **comptes_exterieur**
Gère les comptes externes des joueurs.

| Champ                | Type    | Contraintes                            | Description                          |
| -------------------- | ------- | -------------------------------------- | ------------------------------------ |
| comptes_ext_id       | UUID    | PRIMARY KEY, DEFAULT gen_random_uuid() | Identifiant unique du compte externe |
| comptes_ext_pseudo   | VARCHAR |                                        | Pseudo sur la plateforme externe     |
| comptes_ext_victoire | BOOLEAN |                                        | Indicateur de victoire               |
| plateforme_jv_id     | UUID    | FOREIGN KEY                            | Référence vers plateforme_jv         |

---

### Table: **commentaire**
Stocke les commentaires des joueurs.

| Champ               | Type | Contraintes | Description             |
| ------------------- | ---- | ----------- | ----------------------- |
| joueurs_id          | UUID | FOREIGN KEY | Référence vers joueurs  |
| musiques_id         | UUID | FOREIGN KEY | Référence vers musiques |
| commentaire_contenu | TEXT | NOT NULL    | Contenu du commentaire  |

---

## Relations principales

- **joueurs** ↔ **musiques** : Relations many-to-many via favoris_musiques
- **joueurs** ↔ **propositions_musique** : Relation one-to-many pour les propositions
- **bande_son** ↔ **musiques** : Relation many-to-many
- **compositeur** ↔ **musiques** : Relation many-to-many
- **jeux** ↔ **genres** : Relation many-to-many
- **developpeurs** ↔ **jeux** : Relation one-to-many
- **sources** ↔ **musiques** : Relation one-to-many