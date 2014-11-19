*******************
elementaryos-fr-doc pour Prep'Etna
*******************
Liste des Modification a faire
==============================

01 - Premiers pas (ok)
02 - Fonction et variables (manque des notions)
03 - la compilation (ajouter les options disponible sur valac)
04 - le type char (manque)
05 - boucle et conditions (manque les boucles)
06 - les tableaux (manque le cours
07 - variable et fonctions (????)
08 - Usage avancee des variables (a voir)
09 - Les bibliotheque statiques (bonus)
10 - Le passage de parametres (a faire)
11 - Le makefile (pas obligatoire)
12 - Allocation Dynamique (bonus)
13 - Preprocesseur (bonus)
14 - Les structures de donnees (bonus)
15 - Les pointeurs sur fonction (bonus)
16 - Les listes chainees (bonus)

Objectif:
=========
1 - refaire la doc comme les cours de c ( voir les images des videos);
2 - faire 2 exercices type c (jours 3/4) en vala
3 - faire un exemple en gtk
4 - conception du power point simple avec quelque video (via eideite)

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
