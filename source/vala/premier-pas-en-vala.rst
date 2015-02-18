********************
Premiers pas en Vala
********************

Un programme ?
==============

Avant de commencer à coder quoi que ce soit il serait déjà bien de savoir de quoi on parle, non ?

Alors un programme qu'est-ce que c'est ?

Un programme est un ensemble de **fonctions**. Chaque fonction regroupe une
suite d'**instructions** qui permettent de faire une chose précise: afficher
un bonjour, faire un calcul et j'en passe.
Une fois construite, une fonction peut être utilisée dans une autre fonction.
Pendant l'exécution de notre programme, celui ci lance automatiquement la
fonction "**main**", qui est la fonction principale du programme, c'est dans
celle-ci que se déroule la partie la plus attractive ! ;)

- Un programme en Vala est composé de fonctions.
- Chaque fonction est composée d'instructions.
- Chaque fonction est indépendante.
- La première fonction appelée dans un programme s'appelle "main".

.. code-block:: vala

   void main (){

   }

Structure d'une fonction
------------------------

Il y a plusieurs types de fonctions. On ne va pour le moment parler que des
trois basiques.

Une fonction est composée de deux parties:

* Son prototype qui est lui-même composé de 3 parties:
	* Le type de retour:
		* int qui retournera un entier.
		* char qui retournera un caractère ou une chaîne.
		* void qui ne demande pas de valeur de retour.

	* Le nom (pas d'espace entre le nom, pas de majuscule)
	* Les paramètres, entre parenthèses (dépend du type de la fonction)

           Exemple : ``int nom_de_la_fonction(int a, int b)``
* Son corps:
	* Délimité par des accolades
	* Un return, qui retourne le type de la fonction. Sauf pour la fonction void qui n'en demande pas.

.. code-block:: text

   int function_addition(int a, int b, int c)
   {
       c = a + b;
       return(c);
   }

**Tout ce qui va être exécuté se trouve dans le corps de la fonction.**

Ne pas oublier :
----------------

Voici une petite liste des choses importantes à ne pas oublier quand vous
allez coder. vous allez, au moins une fois, faire chacune des erreurs
listées ci-dessous :

* Ne surtout pas oublier le **point virgule ;** à la fin de vos ligne de
  code.
* N'oubliez pas le return quand votre fonction en demande un.
* Ouvrez et fermez vos parenthèses et accolades avant d'écrire quoi que ce
  soit dedans. Cela vous évitera d'en oublier une ou de vous perdre au moment
  de toutes les fermer.

La fonction main()
------------------

.. code-block:: vala

   int main  (string[] args) {
      print ("Salut le peuple de la Terre!\n");
      return(0);
   }

Voici un exemple avec le type de retour **void**:

.. code-block:: vala

   void main (string[] args) {
      print ("Je ne retourne rien ! Mais je suis très utile!\n");
   }

.. note::
   Le **\\n** permet de faire un retour à la ligne, cela évite d'avoir une phrase qui se colle dans le prompt du terminal.

Hello World en console
======================
La tradition veut que lorsqu'on apprend un nouveau langage de programmation,
on commence par écrire un programme qui affiche *Hello World!* dans la console.

On commence par créer un dossier Projets, avec un sous dossier
*console-hello*. Dans ce sous dossier, on va créer un fichier hello.vala et on
va l'ouvrir avec notre éditeur de texte.

.. code-block:: bash

   $ cd ~  # Permet de revenir dans notre dossier personnel.
   $ mkdir Projets # Crée le dossier Projets.
   $ mkdir Projets/console-hello # Crée le dossier console-hello dans Projets.
   $ cd Projets/console-hello # On se déplace dans le nouveau répertoire.
   $ touch hello.vala # On crée le fichier.
   $ xdg-open hello.vala # On ouvre le fichier avec le programme par défaut.

L'éditeur de text *Scratch* à dû s'ouvrir. Copiez dans le fichier le code
suivant:

.. code-block:: vala

   void main (){
      print("Hello world!\n");
   }

Ensuite, on retourne dans le terminal et on lance la compilation. Si
nécessaire, un appui sur la touche *enter* permet de créer une nouvelle ligne
de commande.

.. code-block:: bash

   $ valac hello.vala
   $ ./hello

La deuxième ligne lance notre premier programme. Si tout se passe bien, la
phrase *Hello World!* devrait s'être affichée dans le terminal.

.. note::
   Le code source des mini-projets de ce guide peut être consulté à l'adresse
   suivante : https://github.com/Elementary-fr/elementaryos-fr-exemple
