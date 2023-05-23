=> : indique une proposition

# Structure
- les packages sont nommés bizarrement 
  => On pourrait mettre com.adaptionsoft.games.triva qui contient GameRunner et un sous package services
- L'indentation n'est pas commune sur les différents fichiers
  => soit configurer IDE soit mettre en place une lib maven qui reformat le ficher, soit un hook via git
- Manque des commentaires
- Manque de couvertures de tests
- 

# Dépendances
- Dans le pom xml on pourrait utiliser la dernière version de Junit et Assertj pour vérifier nos champs (assertThat(monObjet).isNull())

# Fichier Game Runner
- L18 : Pourquoi on utilise une méthode static pour playGame ?
- L18 : Rand aurait pu être mis en attribut de la classe pour éviter d'appeler PlayGame avec la classe Random
- L21 : Comme c'est une application en ligne de commandes pourquoi ne pas utiliser directement les arguments au lancement du l'application ?
  => Si jamais args est vide, on utilise les 3 propositions (Chet, Pat, Sue) soit ce qu'on a mis
- L28 : Ici le premier joueur (numéro 0) ne joue pas
  ==> on pourrait créer une classe user avec un id et un nom pour faciliter la lisibilité et de savoir directement ce qu'on cherche à faire
- L30 : Ce n'est pas clair mais j'imagine qu' c'est pour générer un lancé de dés. On pour mettre ça dans une classe "thimble"
- L38 : Il serait préférable de ne pas faire une boucle infinie
==> rajouter une condition pour gérer le nombre de tours

# Fichier Game
- L7: Utiliser des Interfaces pour les listes et les instanciers quand on en a besoin
=> List player;
- L8: Préférable d'instancier le tableau avec le nombre max d'utilisateur dans le constructeur de Game si possible 
=> Si on avait créé un objet Player , on aurait pu mettre sa place, son purses et ses pénalités directement dedans
- L12: ==> On pourrait créer un objet Question avec un sujet et un type de question sous la forme d'un enum, et rajouter toutes les questions dans une seule list
- L23 & 24: double parenthèse inutile
- L25: sous fonction inutile
- L33: fonction non utilisée
- L45: dans System.out.println prévilégier String.format , faire un tour sur toute la page
- L78: préférable d'utiliser les accolades pour une condition
- L87: utiliser un switch case (avec java 17 c'est plus sympa)
- L99: un switch case c'est mieux
==> switch (places[currentPlayer]){
case 0, 4, 8 => return "Pop";
case ...
}

- L 124 : faire directement un return de didPlayerWin(); sans passer par une variable
