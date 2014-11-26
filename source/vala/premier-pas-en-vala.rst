********************
Premiers pas en Vala
********************

Un programme ?
==============

Avant de commencer à coder quoi que ce soit il serait déjà bien de savoir de quoi on parle, non ?

Alors un programme qu'est-ce que c'est ? 

Un programme est un emsemble de **fonctions**. Chaque fonction regroupe une suite d'**instructions** qui permettent de faire une chose précise: afficher un bonjour, faire un calcul et j'en passe.
Une fois construite, une fonction peut être utilisée dans une autre fonction. Pendant l'exécution de notre programme, celui ci lance automatiquement la fonction "**main**", qui est la fonction principale du programme, c'est dans celle ci que se déroule la partie la plus attractive ;)  

- Un programme en Vala est composé de fonctions.
- Chaque fonction est composée d'instructions.
- Chaque fonction est indépendante.
- La première fonction appelée dans un programme s'appelle "main".

.. code-block:: vala
  :linenos:
       void main (){
      
   }

Structure d'une fonction
------------------------

Il y a plusieurs types de fonctions. On ne va pour le moment parler que des trois basiques. 

Une fonction est composée de deux parties:

* Son prototype qui est lui-même composé de 3 parties :
	1. Le type de retour :
		int qui retournera un entier.
		char qui retournera un caractère ou une chaîne.
		void qui ne demande pas de valeur de retour.
	2. Le nom (pas d'espace entre le nom, pas de majuscules)
	3. Les paramètres, entre parenthèses (dépend du type de la fonction)
        4. Exemple : ``int nom_de_la_fonction(int a, int b)``
* Son corps:
	1. Délimité par des accolades
	2. Un return, qui retourne le type de la fonction.  Sauf pour la fonction void qui n'en demande pas.
	3. Exemple :
.. code-block::

	int    function_addition(int a, int b, int c)
	 {
          c = a + b;
          return(c);
         }
 
**Tout ce qui va être exécuté se trouve dans le corps de la fonction.**

Ne pas oublier :
----------------

Voici une petite liste des choses importantes à ne pas oublier quand vous aller coder. vous allez, au moins une fois, faire chaqu'une des erreurs listée si dessous :
 \-Ne surtout pas oublier le **point virgule ;** à la fin de vos ligne de code. \
 \-N'oubliez pas le return quand votre fonction en demande un. \
 \-Ouvrez et fermez vos paranthèses et accollades avant d'écrire quoi que ce soit dedans. Cela vous évitera d'en oublier une ou de vous perdre au moment de toutes les fermer.

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

