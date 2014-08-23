****************
Compte Launchpad
****************

Création d'un compte launchpad
==============================

Tout développeur elementary se doit d'avoir un compte sur Launchpad. Launchpad 
est la plateforme de Canonical pour l'hébergement de projet, suivi de bugs..etc.

Bien sûr si vous avez déjà un compte launchpad, vous pouvez passer cette partie.

.. figure:: _static/launchpad.png
    :align: center
    
    
Pour créer un compte cliquez en haut à droite sur Create account.ou aller 
directement sur https://login.launchpad.net/+login

.. figure:: _static/launchpad_login.png
    :align: center


Après rien de bien compliqué, vous pouvez compléter les infos de votre compte à votre guise.

Création d'une clé SSH et ajout au compte Launchpad
===================================================

Maintenant nous avons un compte Launchpad, nous allons en profiter pour lui ajouter une paire 
de clé ssh. Dans un premier nous allons générer ces clés. Ces clés sont une sorte de reconnaissance 
digitale de votre ordinateur et importer la clé publique à Launchpad assurera un gain de sécurité 
quand vous modifier votre code (de toute façon c'est obligatoire).

On vas installer l'outil nécessaire pour générer la clé et ensuite créer cette dernière, avec Terminal :

.. code-block:: bash

   sudo apt-get install openssh-client
   ssh-keygen -t rsa
￼
￼

