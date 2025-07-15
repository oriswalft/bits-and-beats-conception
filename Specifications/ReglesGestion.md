# Joueur
- RG¤ : Un joueur doit avoir un pseudonyme
- RG¤ : Un joueur doit avoir une adresse email unique
- RG¤ : Un joueur doit avoir un mot de passe
- RG¤ : Un joueur doit avoir un rôle
- RG¤ : Un joueur peut avoir une photo de profil
- RG¤ : Un joueur peut avoir une bibliothèque
- RG¤ : Un joueur peut avoir des jeux favoris
- RG¤ : Un joueur peut avoir des musiques favorites
- RG¤ : Un joueur peut avoir des bande-sons favorites
- RG¤ : Un joueur peut faire des playlist
- RG¤ : Un joueur peut avoir des playlists
- RG¤ : Un joueur peut proposer des musiques 
- RG¤ : Un joueur peut faire des recherches
- RG¤ : Un joueur peut donner son vote sur la correspondance d'une musique
- RG¤ : Un joueur peut avoir un historique de recherche
- RG¤ : Un joueur peut poster un commentaire sur une proposition de musique qui lui appartient ou celle d'un autre joueur
- RG¤ : Un joueur peut modifier son profil
- RG¤ : Un joueur peut effacer son profil
- RG¤ : Un joueur peut avoir des comptes extérieur
- RG¤ : Un joueur peut synchroniser sa bibliothèque avec un compte extérieur
- RG¤ : Un joueur peut afficher ou non ses comptes extérieur
- RG¤ : Un joueur peut révoquer l'accès au compte extérieur

# Rôle
- RG¤ : Un rôle doit avoir un nom unique
- RG¤ : Un rôle doit avoir des permissions
- RG¤ : Un rôle peut être attribué à un ou plusieurs joueurs

# Bibliothèque 
- RG¤ : Une bibliothèque doit appartenir à un joueur
- RG¤ : Une bibliothèque doit contenir un ou plusieurs jeux
- RG¤ : Une bibliothèque peut être importée par un compte extérieur

# Jeu
- RG¤ : Un jeu doit avoir un titre
- RG¤ : Un jeu doit avoir un développeur
- RG¤ : Un jeu doit avoir un genre
- RG¤ : Un jeu doit avoir une année de sortie
  
# Développeur
- RG¤ : Un développeur doit avoir un nom
- RG¤ : Un développeur peut être une personne ou un groupe
- RG¤ : Un développeur doit être attribué au minimum sur un jeu
  
# Genre
- RG¤ : Un genre doit avoir un nom
- RG¤ : Un genre peut être spécifié à un ou plusieurs jeux

# Plateforme
- RG¤ : Une plateforme doit avoir un nom
- RG¤ : Une plateforme peut être attribuée à un ou plusieurs jeux
  
# Bande-son
- RG¤ : Une bande-son doit être tiré d'un jeu
- RG¤ : Une bande-son doit avoir un titre
- RG¤ : Une bande-son doit avoir une ou plusieurs musiques
- RG¤ : Une bande-son doit avoir un compositeur
- RG¤ : Une bande-son doit avoir au minimum un tag
- RG¤ : Une bande-son doit avoir une source
- RG¤ : Une bande-son peut avoir une pochette d'album
- RG¤ : Une bande-son peut être en favoris d'un ou plusieurs joueurs

# Musique 
- RG¤ : Une musique doit avoir une source principale
- RG¤ : Une musique peut avoir plusieurs sources secondaires
- RG¤ : Une musique doit avoir un titre
- RG¤ : Une musique doit avoir un compositeur
- RG¤ : Une musique doit avoir au minimum un tag
- RG¤ : Une musique peut avoir une pochette d'album

# Compositeur
- RG¤ : Un compositeur doit avoir un nom ou un pseudonyme
- RG¤ : Un compositeur peut avoir un prénom
- RG¤ : Un compositeur peut être une personne ou un groupe
- RG¤ : Un compositeur doit avoir composé au minimum une musique
- RG¤ : Un compositeur peut avoir participé à la composition d'une musique
  
# Tag
- RG¤ : Un tag doit avoir un nom unique
- RG¤ : Un tag peut être attribué à une ou plusieurs musique
- RG¤ : Un tag peut être attribué à une ou plusieurs bande-son

# Langue
- RG¤ : Une langue doit avoir un nom unique
- RG¤ : Une langue peut être réelle ou fictive
- RG¤ : Une langue peut avoir des variations
- RG¤ : Une langue doit avoir au minimum une musique

# Source
- RG¤ : Une source doit être un lien valide
- RG¤ : Une source peut-être une bande-son
- RG¤ : Une source peut être une musique

# Playlist
- RG¤ : Une playlist doit appartenir à un joueur
- RG¤ : Une playlist doit contenir au minimum une musique
- RG¤ : Une playlist doit avoir un nom unique

# Recherche
- RG¤ : Une recherche doit avoir un contenu
- RG¤ : Une recherche peut concerner une musique
- RG¤ : Une recherche peut concerner une bande-son
- RG¤ : Une recherche peut concerner un jeu
- RG¤ : Une recherche peut concerner un ou plusieurs tags

# Historique
- RG¤ : Un historique doit appartenir à un joueur
- RG¤ : Un historique doit avoir au minimum une recherche
- RG¤ : Un historique doit avoir un temps de conservation

# Commentaire
- RG¤ : Un commentaire doit être publié par un joueur
- RG¤ : Un commentaire doit avoir un contenu
- RG¤ : Un commentaire peut être publié sur une musique
- RG¤ : Un commentaire peut être publié sur une bande-son
- RG¤ : Un commentaire peut être lié à un autre commentaire

# Vote
- RG¤ : Un vote peut être donné par un joueur
- RG¤ : Un vote doit être positif ou négatif
- RG¤ : Un vote dépend d'une proposition de musique

# Proposition de musique
- RG¤ : Une proposition de musique doit être réalisée par un joueur
- RG¤ : Une proposition de musique doit avoir une source
- RG¤ : Une proposition de musique doit avoir un titre
- RG¤ : Une proposition de musique doit avoir au minimum un tag
- RG¤ : Une proposition doit être en rapport avec une musique déjà présente
- RG¤ : Une proposition peut recevoir des commentaires
- RG¤ : Une proposition peut recevoir des votes

# Favoris
- RG¤ : Un favoris doit appartenir à un joueur
- RG¤ : Un favoris peut concerner une musique
- RG¤ : Un favoris peut concerner une playlist
- RG¤ : Un favoris peut concerner une bande-son
- RG¤ : Un favoris ne peut pas être ajouté deux fois
- RG¤ : Un favoris peut être supprimé

# Synchronisation 
- RG¤ : Un joueur peut synchroniser une bibliothèque d'un compte extérieur
  
# Compte extérieur
- RG¤ : Un compte extérieur doit être lié au profil du joueur
- RG¤ : Un compte extérieur doit provenir d'une plateforme reconnue