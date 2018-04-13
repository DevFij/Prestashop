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

- /views/templates :  Dossier contenant les fichiers .tpl 

- /views/templates/admin : Dossier contenant les templates utilisés par les controleurs d'administration  du module

- /views/templates/front : Dossier contenant les templates utilisés par les controleurs du front

- /views/templates/hook :  Dossier contenat les templates utilisés par les hook du module

- /views/css :  Dossier de fichiers css du module

- /views/js : Dossier de fichiers js du module

- /views/img : Dossier des images du module

- /translations : Fichier de traduction du module.
On peut y trouver, des fichiers fr.php, it.php, nl.php

- /controllers : Dossier des controlleurs du module

- /override : dossier contenant les classes modifiant par défaut de PS.

En réalité pour l'écriture d'un module, seuls les trois premiers fichier sont essentiels. En fait deux, car le fichier : config.xml est généré automatiquement par PS.
## Création de votre premier module
### Le test
Le fichier source principal doit contenir le test suivant : 

       <?php    
        if(!defined('_PS_VERSION_')) {
         exit;
      }
### la classe principale
Elle a le même nom que le module en CamelCase et etend la classe Module ou ses classes dérivées. Imaginons que nous souhaitons créer un module qui souhaite la bienvenue sur notre page.
Le dossier contenant le fichier source principal est /modules/bienvenue

    <?php
    if (!defined('_PS_VERSION_')) {
      exit;
    }
    class Bienvenue extends Module
    {
      public function __construct()
      {
        $this->name = 'bienvenue';
        $this->tab = 'front_office_features';
        $this->version = '1.0.0';
        $this->author = 'G U2';
        $this->need_instance = 0;
        $this->ps_versions_compliancy = array('min' => '1.6', 'max' => _PS_VERSION_);  
        $this->bootstrap = true;
    }
    }
   Là on a deja un module prêt à l'emploi.
   ### Exercice 1
   1. Dans votre sous-domaine crée dans le domaine u2ktek.com, installer une boutique PS utilisant le thème par défaut.
   2. Charger le module bienvenue.
   3. Changer la valeur du champ Tab en administration, analytics_stats, market_place.
   4. Supprimer le module chargé precédement, recharger les modules.
   5. Bonus: Pouvez vous consulter les logs retraçant les diverses actions sur le serveur?
   ### Les méthodes d'installation et de suppresssion du module.
   Pour gestion back office du module, on rajoute des méthodes de suppression et d'installation du module.
   
        parent::__construct();
 
        $this->displayName = $this->l('Bienvenue');
        $this->description = $this->l('Je vous souhaite la bienvenue.');

        $this->confirmUninstall = $this->l('Etes vous sûre de vouloir supprimer le module?');

        if (!Configuration::get('BIENVENUE_NAME')) {
          $this->warning = $this->l('Le nom du module n'existe pas.');
   ### Exercice 2 
   Supprimer le module chargé précedemment. Et rajouter le ce qui précède. 
   1. Que constatez vous?
   2. Bonus : Pouvez vous accéder à la base de donnée de ps et voir lire les données des modules? Que représente le champ       
   BIENVENUE_NAME?
   #### Méthode d'installation
   Voici ce que contiendra au minimum un méthode d'installation. Elle fait appel à la methode d'installation de la classe parente.
   
           public function install()
            {
                 if (!parent::install()) {
                    return false;
                    }
           return true;
           }
   
   #### Méthode de suppression
 Pour la méthode de suppression, c'est en fait assez similiaire.
 
     public function uninstall()
     {
      if (!parent::uninstall()) {
        return false;
      }

      return true;
     }

      
