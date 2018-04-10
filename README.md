# Prestashop
## Creation de module
Les modules permettent  d'ajouter des fonctionnalités à PrestaShop sans devoir modifier ses fichiers internes, rendant possible le fait de mettre la solution à jour sans devoir recopier toutes ses modifications
## **Warning**
Toujours éviter de toucher au fichier interne de PrestaShop lorsque vous concevez un module, même si cela peut être difficile dans certaines situations.
### Organisation de fichiers d'un module
Tous les modules PrestaShop sont installés dans le dossier /modules. Tous les modules ayant la meme structure, on peut en apprendre beaucoup en lisant le code des modules existants.
- Le nom du module
- Le dossier contenant le module a créer de même nom que le module
Le nom tout en minuscule ne doit pas contenir d'espace. Il pourra contenir - et _.
- Le dossier doit contenir un fichier .php de même nom que le module
- La partie publique du module doit être définie dans un fichier .tpl placé à la racine du dossier du module. Les fichiers TPL peuvent prendre n'importe quel nom, s'il n'y en a qu'un seul, une bonne pratique consiste à lui donner le même nom que le dossier et le fichier principal
### le fichier .php
Ce fichier doit commencer par 

    if (!defined('_PS_VERSION_'))
    exit;
    
De plus, il doit contenir une classe donc le nom sera le meme en CamelCase que le module et son dossier.
cette classe doit étendre la classe Module


    if (!defined('_PS_VERSION_'))
    exit;
    class MyModule extends Module
    {
    public function __construct()
    }
