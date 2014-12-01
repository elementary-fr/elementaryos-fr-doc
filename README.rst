*******************
elementaryos-fr-doc
*******************

Guide non officiel du développeur elementary OS

Téléchargement et Accès
=======================

La dernière version de ce guide est disponible à l'adresse http://elementaryos-fr-doc.readthedocs.org/ sous format
WEB, PDF et ePub.

Dépendances
===========

La documentation est construite avec Sphinx, en utilisant le thème "sphinx_rtd_theme".

Sur elementary OS, il faut installer les paquets suivants:

.. code-block:: bash

   sudo apt-get install python3 python3-pip
   sudo pip3 install sphinx
   sudo pip3 install sphinx_rtd_theme
   
Construction
============

Pour lancer la compilation de la documentation, et créer un site web statique complet, il faut lancer la commande suivante
à la racine du projet:

.. code-block:: bash

   make html
   
Les fichiers sont créés dans le repertoire build/html.
