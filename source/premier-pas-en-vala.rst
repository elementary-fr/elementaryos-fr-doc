*******************
Premier pas en Vala
*******************

Présentation
=============

Vala est un langage de programmation apparu en 2006. Il a été créé en 2006
par Jürg Billeter.

Depuis toujours, le langage de prédilection de Gnome est le C. C'est un des
plus langage de programmation encors utilisés de nos jours. Le C est un
langage très puissant, pour preuvre, c'est le langage du noyau Linux.

Gnome avait décider d'utiliser le C pour construire son bureau libre. 
Cependant, lorsqu'il a fallut amélioré la librairie permetant de créer 
l'interface graphique, il se sont rendu compte qu'il devait réécrire le code
avec un style orienté objet.

Le C ne permettant pas de base la création d'objet, ils ont créé leur système,
appelé GObject, par dessus le C.

Ainsi, Gnome a obtenu pu faire de l'orienté objet et profiter des autres 
avantages du C.

Le principal avantage, les librairies Gnome peuvent être utilisée facilement
dans presque tous les autres langages, y compris les tous derniers langage
à la mode, les langages interprété comme le Python.

Les languages interprété ne sont pas directement convertit en language machine
par le dévellopeur mais seulement lors de l'execution, par l'interprêteur,
qui convertit le code à la volée.

Cette methode permet de faire des languages très flexibles et simple, mais en 
perdant un peu en performance.

Vala a été créer pour palier au problème de performance des languages
interprété. Le compilateur vala traduit le code en laguage C, puis le
compilateur C en laguage machine. De plus, le langage Vala amène toute
les principales nouveautés des languages moderne, ce qui permet d'écrire des
programme facilement, tous en gardant une vitesse proche du C.

Installation
============

Pour utiliser le langage Vala, nous devons installer le compilateur Valac, qui
va convertir nos fichier .vala en ficier .c. Il nous faut aussi le compilateur
Gcc qui va convertir les fichier .c en programme executable.

.. code-block:: bash

   $ sudo apt install valac build-essential

Hello World en console
======================

La tradition veux que lorsqu'on apprend un nouveau language de programmation,
on commence par écrire un programme qui affiche *Hello World!* dans la console.

On commence par créer un un dossier Projets, avec un sous dossiers
console-hello. Dans ce sous dossier, on va créer un fichier hello.vala et on
va l'ouvrir avec notre éditeur de texte.

.. code-block:: bash

   $ cd ~  # Permet de revenir dans notre dossier personnel
   $ mkdir Projets # Crée le dossier Projets
   $ mkdir Projets/console-hello # Crée le dossier console-hello dans Projets
   $ cd Projets/console-hello # On se déplace dans le nouveau répertoire
   $ touch hello.vala # On crée le fichier
   $ xdg-open hello.vala # On ouvre le fichier avec le programe par défaut

L'éditeur de text *Scratch* a du s'ouvrir. Copié dans le fichier le code
suivant:

.. code-block:: vala
   :linenos:
   
   void main (){
       print("Hello World!\n");
   }

Ensuite, on retourne dans le terminal est en lance la compilation. Si
nécéssaire, un appuis sur la touche *enter* permet de créer une nouvelle ligne
de commande.

.. code-block:: bash

   $ valac hello.vala
   $ ./hello

La deuxième ligne lance notre premier programme. Ci tous ce passe bien, la
phrase *Hello World!* devrait s'être affichée dans le terminal.

.. note::
   Le code source des mini-projets de ce guide peut être consulté à l'adresse
   suivante: https://github.com/Elementary-fr/elementaryos-fr-exemple






