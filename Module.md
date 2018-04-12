Un module est contitué de plusieurs fichiers et dossiers contenu dans un dossier du même nom que le module. Ce dossier est stocké dans le repertoire /modules à la racine de prestashop : /modules/nom_du_module
## Structure de fichier d'un module prestashop
Voici une structure possible des fichiers et repertoires d'un module prestashop (PS).
- nom_du_module.php : fichier source principal. 
Ce fichier aura le même nom que le module. Par exemple, un module FijCode, aura pour ficher source principal fijcode.php et sera stocké dans le repertoire /modules/fijcode/
- config.xml : fichier de configuration du cache.
Il est crée par PS s'il n'exite pas lors de l'installation du module.
- logo.png : Icone representant le module dans le back office.
Il est de dimension 32x32 pixels.
- /views : Ce repertoire contient les fichiers pour la vue (Front)
- /views/templates/ :  Dossier contenant les fichiers .tpl 
- /views/templates/admin : Dossier contenant les templates utilisés par les controleurs d'administration  du module
- /views/templates/front : Dossier contenant les templates utilisés par les controleurs du front
- /views/templates/hook :  Dossier contenat les templates utilisés par les hook du module
