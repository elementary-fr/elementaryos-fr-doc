********************
Premiers pas en Vala
********************

Présentation
=============

Vala est un langage de programmation apparu en 2006. Il a été créé
par Jürg Billeter.

Depuis toujours, le langage de prédilection de Gnome est le C. C'est un des
langages de programmation le plus utilisé de nos jours. Le C est un
langage très puissant; pour preuvre, c'est le langage du noyau Linux.

L'équipe de Gnome avait décidé d'utiliser le C pour construire son bureau
libre. Cependant, lorsqu'il a fallut amélioré la librairie permettant de
créer l'interface graphique, ils se sont rendus compte qu'ils devaient
réécrire le code avec un style orienté objet.

Le C ne permettant pas de base la création d'objet, ils ont créé leur système,
appelé GObject, par dessus le C.

Ainsi, Gnome a pu faire de l'orienté objet et profité des autres
avantages du C.

Le principal avantage, les librairies Gnome peuvent être utilisées facilement
dans presque tous les autres langages, y compris les tous derniers langages
à la mode, les langages interprétés comme le Python.

Les langages interprétés ne sont pas directement convertis en langage machine
par le dévelopeur mais seulement lors de l'exécution, par l'interpréteur,
qui convertit le code à la volée.

Cette methode permet de faire des langages très flexibles et simples, mais en
perdant un peu en performance.

Vala a été créé pour palier au problème de performance des langages
interprétés. Le compilateur Vala traduit le code en language C, puis le
compilateur C, en langage machine. De plus, le langage Vala amène toutes
les principales nouveautés des langages modernes, ce qui permet d'écrire des
programmes facilement tout en gardant une vitesse d'exécution proche du C.


Installation
============

Pour utiliser le langage Vala, nous devons installer le compilateur Valac, qui
va convertir nos fichiers .vala en ficier .c. Il nous faut aussi le compilateur
Gcc qui va convertir les fichier .c en programme executable.

.. code-block:: bash

   $ sudo apt-get install valac build-essential


Hello World en console
======================
La tradition veut que lorsqu'on apprend un nouveau langage de programmation,
on commence par écrire un programme qui affiche *Hello World!* dans la console.

On commence par créer un un dossier Projets, avec un sous dossier
*console-hello*. Dans ce sous dossier, on va créer un fichier hello.vala et on
va l'ouvrir avec notre éditeur de texte.

.. code-block:: bash

   $ cd ~  # Permet de revenir dans notre dossier personnel
   $ mkdir Projets # Crée le dossier Projets
   $ mkdir Projets/console-hello # Crée le dossier console-hello dans Projets
   $ cd Projets/console-hello # On se déplace dans le nouveau répertoire
   $ touch hello.vala # On crée le fichier
   $ xdg-open hello.vala # On ouvre le fichier avec le programe par défaut

L'éditeur de text *Scratch* a dû s'ouvrir. Copié dans le fichier le code
suivant:

.. code-block:: vala
   :linenos:
 
       void main (){
       print("Hello World!\n");
   }

Ensuite, on retourne dans le terminal et on lance la compilation. Si
nécéssaire, un appui sur la touche *enter* permet de créer une nouvelle ligne
de commande.

.. code-block:: bash

   $ valac hello.vala
   $ ./hello

La deuxième ligne lance notre premier programme. Ci tous ce passe bien, la
phrase *Hello World!* devrait s'être affichée dans le terminal.

.. note::
   Le code source des mini-projets de ce guide peut être consulté à l'adresse
   suivante : https://github.com/Elementary-fr/elementaryos-fr-exemple

