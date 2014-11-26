********************
Premiers pas en Vala
********************

Un programme ?
==============

Avant de commencer à coder quoi que ce soit il serait déjà bien de savoir de quoi on parle. Non ?
Alors un programme qu'est-ce que c'est ? Un programme est un emsemble de fonctions. 
Une fonction regroupe une suite d'instructions qui permettent de faire une chose précise: afficher un bonjour, faire un calcul et j'en passe.
Une fois construite, une fonction peut être utilisée dans une autre fonction. Pendant l'exécution de notre programme, celui ci lance automatiquement la fonction "main", qui est la fonction principale du programme, c'est dans celle ci que se déroule la partie la plus attractive ;)  

- Un code source en Vala est composé de fonctions.
- Chaque fonction est composée d'instructions.
- Chaque fonction est indépendante.
- La première fonction appelée dans un programme s'appelle "main".

.. code-block:: vala
   :linenos:
 
       void main (){
      
   }

Structure d'une fonction
------------------------

Une fonction est composée de deux parties:

* Son prototype qui est lui-même composé de 3 parties:
	1. Le type de retour (int)
	2. Le nom (pas d'espace entre le nom, pas de majuscules)
	3. Les paramètres, entre parenthèses: (int a, int b)
* Son corps:
	1. Délimité par des accolades
	2. Un return(), qui retourne le type de la fonction.

.. code-block:: vala
   :linenos:
 
       int addition (int a, int b){
       return(a + b);
   }

Corps d'une fonction
--------------------

Dans l'exemple plus haut, il n'y avait pas de déclaration de variable car "a" et "b" sont déjà initialisés.
Voici une autre façon de le faire pour vous montrez la création d'une variable:

.. code-block:: vala
   :linenos:
 
   int addition (int a,int b){
       int	result;
       
       result = a * b;
       return(result);
   }

.. note::
	Pour une meilleur lisibilitée, je vous conseil d'utiliser une partie déclarative et une partie instructions.

La fonction main()
------------------

 À FAIRE EN VALA!
 
 .. code-block:: vala
   :linenos:
 
   int main (int argc, char **argv){
       return(0);
   }

Notion de variable
==================

Hello World en console
======================
La tradition veut que lorsqu'on apprend un nouveau langage de programmation,
on commence par écrire un programme qui affiche *Hello World!* dans la console.

On commence par créer un dossier Projets, avec un sous dossier
*console-hello*. Dans ce sous dossier, on va créer un fichier hello.vala et on
va l'ouvrir avec notre éditeur de texte.

.. code-block:: bash

   $ cd ~  # Permet de revenir dans notre dossier personnel.
   $ mkdir Projets # Créer le dossier Projets.
   $ mkdir Projets/console-hello # Créer le dossier console-hello dans Projets.
   $ cd Projets/console-hello # On se déplace dans le nouveau répertoire.
   $ touch hello.vala # On créer le fichier.
   $ xdg-open hello.vala # On ouvre le fichier avec le programe par défaut.

L'éditeur de text *Scratch* a dû s'ouvrir. Copiez dans le fichier le code
suivant:

.. code-block:: vala
   :linenos:
 
       void main (){
       print("Hello world!\n");
   }

Ensuite, on retourne dans le terminal et on lance la compilation. Si
nécéssaire, un appui sur la touche *enter* permet de créer une nouvelle ligne
de commande.

.. code-block:: bash

   $ valac hello.vala
   $ ./hello

La deuxième ligne lance notre premier programme. Si tout ce passe bien, la
phrase *Hello World!* devrait s'être affichée dans le terminal.

.. note::
   Le code source des mini-projets de ce guide peut être consulté à l'adresse
   suivante : https://github.com/Elementary-fr/elementaryos-fr-exemple

