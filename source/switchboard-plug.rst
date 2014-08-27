Les Plugs Switchboard
==========

Les plugs (pligins) pour Switchboard se retrouvent dans Paramètres Système.

Les fichiers sont stockés dans `/usr/lib/x86_64-linux-gnu/switchboard/` puis dans un dossier selon la catégorie.

Il est possible de les coder directement dans un fichier vala et à la compilation le fichier .plug sera crée.

Il existe un template ici: http://bazaar.launchpad.net/~elementary-pantheon/pantheon-plugs/plug-template-isis/files

Format des fichiers .plug
=============================

Exemple ici avec About Plug (À Poropos)

.. code-block::

    [Plugin]
    Module=about
    IAge=2
    Name=About
    Description=About
    Authors=Switchboard Developers
    Copyright=Copyright © 2013 Switchboard Developers
    Website=http://launchpad.net/switchboard
    Icon=help-info
    X-Category=system
    X-GNOME-Gettext-Domain=about-plug

On retrouve des similitudes avec les fichiers desktop avec le nom, la description du module, l'icone...

.. figure:: _static/switchboard-plug/aboutplug.png
    :align: center