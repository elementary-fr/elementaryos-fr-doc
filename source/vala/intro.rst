
############
Introduction
############

Présentation
=============

Vala est un langage de programmation apparu en 2006. Il a été créé
par Jürg Billeter.

Depuis toujours, le langage de prédilection de Gnome est le C. C'est un des
langages de programmation les plus utilisés de nos jours. Le C est un
langage très puissant. Pour preuve: c'est le langage du noyau Linux.

L'équipe de Gnome avait décidée d'utiliser le C pour construire son bureau
libre. Cependant, lorsqu'il a fallut améliorer la librairie permettant de
créer l'interface graphique, ils se sont rendus compte qu'ils devaient
réécrire le code avec un style orienté objet.

Le C ne permettant pas de base la création d'objet, ils ont créés leur système,
appelé GObject, par dessus le C.

Ainsi, Gnome a pu faire de l'orienté objet et profiter des autres
avantages du C.

Le principal avantage: les librairies Gnome peuvent être utilisées facilement
dans presque tous les autres langages, y compris les tout derniers langages
à la mode, les langages interprétés comme le Python.

Les langages interprétés ne sont pas directement convertis en langage machine
par le dévelopeur mais seulement lors de l'exécution, par l'interpréteur,
qui convertit le code à la volée.

Cette methode permet de faire des langages très flexibles et simples, mais en
perdant un peu de performance.

Vala a été créé pour palier au problème de performances des langages
interprétés. Le compilateur Vala traduit le code en language C, puis le
compilateur C, en langage machine. De plus, le langage Vala amène toutes
les principales nouveautés des langages modernes, ce qui permet d'écrire des
programmes facilement tout en gardant une vitesse d'exécution proche du C.


Installation
============

Pour utiliser le langage Vala, nous devons installer le compilateur Valac, qui
va convertir nos fichiers .vala en ficier .c. Il nous faut aussi le compilateur
Gcc qui va convertir les fichier .c en programme exécutable.

.. code-block:: bash

   $ sudo apt-get install valac build-essential
   
Notre programme d'aprentisage
=============================


