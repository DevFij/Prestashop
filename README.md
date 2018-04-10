# Prestashop
## Creation de module
Les modules permettent  d'ajouter des fonctionnalités à PrestaShop sans devoir modifier ses fichiers internes, rendant possible le fait de mettre la solution à jour sans devoir recopier toutes ses modifications
** Warning **
Toujours éviter de toucher au fichier interne de PrestaShop lorsque vous concevez un module, même si cela peut être difficile dans certaines situations.
### Organisation de fichiers d'un module
Tous les modules PrestaShop sont installés dans le dossier /modules. Tous les modules ayant la meme structure, on peut en apprendre beaucoup en lisant le code des modules existants.
- Le nom du module
- Le dossier contenant le module a créer de même nom que le module
Le nom tout en minuscule ne doit pas contenir d'espace. Il pourra contenir - et _.
- Le dossier doit contenir un fichier .php de même nom que le module
