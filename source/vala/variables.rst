**************
Les variables
**************

Dans ce chapitre nous allons apprendre ce que sont les variables et comment ces
éléments indispensables vont nous rendre bien des services pour traiter de
l'information susceptible de changer dans nos programmes informatiques.

Nous continuerons en découvrant les différents types de variables et nous
ferons nos premières manipulations avec elles.

Soyez attentifs à ce chapitre, il est vraiment fondamental de bien comprendre à
quoi servent les variables lors du développement d'une application informatique.


Qu’est-ce qu’une variable ?
===========================

Comme tous les langages de programmations, le Vala va pouvoir conserver des
données grâce à des variables. Ce sont en fait des blocs de mémoire qui vont
contenir des nombres, des chaines de caractères, des dates ou plein d’autres
choses.

Les variables vont nous permettre d’effectuer des calculs mathématiques,
d’enregistrer l’âge du visiteur, de comparer des valeurs, ...etc.

On peut les comparer à des petits classeurs possédant une étiquette.
On va pouvoir mettre des choses dans ces classeurs, par exemple, je mets 30 dans
le classeur étiqueté *âge de Nicolas* et *20* dans le classeur
*âge de Jérémie*. Si je veux connaitre l’âge de Nicolas, je n’ai qu’à regarder
dans ce classeur pour obtenir 30. Je peux également remplacer ce qu’il y a dans
mon classeur par autre chose, par exemple changer 30 en 25. Je ne peux par
contre pas mettre deux choses dans mon classeur, il n’a qu’un seul emplacement.

Une variable est représentée par son nom, caractérisée par son type et contient
une valeur.

.. note::

   Le type correspond à ce que la variable représente : un entier, une chaîne
   de caractères, une date, ...etc.

Par exemple, l’âge d’une personne pourrait être stocké sous la forme d’un
entier et accessible par la variable *age*. Ce qui s’écrit en Vala :

.. code-block:: vala


   int age;

On appelle ceci la déclaration de la variable *age*.

Le mot clé *int* permet d’indiquer au compilateur que la variable *age* est un
entier numérique. *int* correspond au début d’ "integer" qui veut dire
"entier" en anglais.

Ici, la variable *age* n’a pas été initialisée. Elle ne pourra pas être 
utilisée car le compilateur ne sait pas quelle valeur il y a dans la variable
*age*.

Pour l’initialiser (on parle également d’affecter une valeur) on utilisera
l’opérateur égal (*=*). 

.. code-block:: vala

   int age;
   age = 30;


Notre variable *age* possède désormais l’entier numérique *30* comme valeur.

L’initialisation d’une variable peut également se faire au même moment que sa
déclaration. Ainsi, on pourra remplacer le code précédent par :

.. code-block:: vala


   int age = 30;

Pour déclarer une variable en Vala, on commence toujours par indiquer son type
(int, ici un entier) et son nom (age). Il faudra impérativement affecter une
valeur à cette variable avec l’opérateur *=*, soit sur la même instruction que
la déclaration, soit un peu plus loin dans le code, mais dans tous les cas, 
avant l’utilisation de cette variable.

Nous pouvons à tout moment demander la valeur contenue dans la variable *age*, par
exemple :

.. code-block:: vala



   int age = 10;
   print("%d \n", age); // Écrit 10 sur la console


.. note::
   
   Les caractères *%d* sont la pour indiquer que *age* est un chiffre entier
   décimal.
   
   Les caractères *\n*, eux, indiquent à la console de faire un saut de ligne.
   
Il est possible de modifier la valeur de la variable à n’importe quel moment
grâce à l’emploi de l’opérateur *=* que nous avons aperçu :

.. code-block:: vala
   :linenos:

   int age = 30;
   print("%d \n", age); // Écrit 30 sur la console
   age = 20;
   print("%d \n", age); // Écrit 20 sur la console


Vous pouvez nommer vos variables à peu près n’importe comment, à quelques
détails près. Les noms de variables ne peuvent pas avoir le même nom qu’un type.
Il sera alors impossible d’appeler une variable *int*.

Il est également impossible d’utiliser des caractères spéciaux, comme des
espaces, des tirets, des lettres accentuées ou des caractères de ponctuation.

De même, on ne pourra pas nommer une variable en commençant par des chiffres.

.. note:: 
   Il est souvent recommandé de nommer ses variables en anglais (langue
   qui ne contient pas d'accent). Vous aurez noté que je ne le fais pas
   volontairement dans ce tutoriel afin de ne pas rajouter une contrainte 
   supplémentaire lors de la lecture du code. Mais libre à vous de le faire.

En général, une variable commence par une minuscule et si son nom représente
plusieurs mots, on les séparera par des tirets "en bas". Par exemple :


.. code-block:: vala

   int age_du_visiteur;


.. important::

   A noter un détail qui peut paraitre évident, mais toutes les variables sont
   réinitialisées à chaque nouvelle exécution du programme. Dès qu’on démarre le
   programme, les classeurs sont vidés, comme si on emménageait dans des
   nouveaux locaux à chaque fois.

   Il est donc impossible de faire persister une information entre deux
   exécutions du programme en utilisant des variables. Pour ceci, on utilisera
   d’autres solutions, comme enregistrer des valeurs dans un fichier ou dans une
   base de données. Nous y reviendrons ultérieurement.


Les différents types de variables
=================================

Nous avons vu juste au-dessus que la variable *age* pouvait être un entier
numérique grâce au mot clé *int*. Le langage Vala dispose de beaucoup de types
permettant de représenter beaucoup de choses différentes.

Par exemple, nous pouvons stocker une chaine de caractères grâce au type *string*.

.. code-block:: vala


   string prenom = "nicolas";

ou encors un boolean (qui représente une valeur vraie ou fausse) avec

.. code-block:: vala

   bool est_vrai= true;
   bool est_faux = false;

.. warning::

   Il est important de stocker des données dans des variables ayant le bon type.

   On ne peut par exemple pas stocker le prénom "Nicolas" dans un entier.


Les principaux types de base du langage Vala sont :


Nombre décimal à taille garantie:
---------------------------------

=========  ====================================================================
Type       Description
=========  ====================================================================
int8       Entier de -127 à +127
int16      Entier de -32768 à 32767
int32      Entier de -2147483648 à 2147483647
int64      Entier de -9223372036854775808 à 9223372036854775807

uint8      Entier non-signé (uniquement positif) de 0 à 255
uint16     Entier non-signé de 0 à 65535
uint32     Entier non-signé de 0 à 4294967295
uint64     Entier non-signé de 0 à 18446744073709551615
=========  ====================================================================


Nombre décimal à taille variable:
---------------------------------

Les nombres ci-dessus ont une taille qui varie ont fonction de la plateforme
sur laquelle le code a été compilé. Les valeurs limites sont données, à titre
indicatif, pour un ordinateur 32 bits.


=========  ====================================================================
Type       Description
=========  ====================================================================
short      Entier de -32768 à 32767
int        Entier de -2147483648 à 2147483647
long       Entier de -9223372036854775808 à 9223372036854775807
=========  ====================================================================


Nombre à virgule
----------------

=========  ====================================================================
Type       Description
=========  ====================================================================
float      Nombre simple précision de -3,402823e38 à 3,402823e38
double     Nombre double précision de -1,79769313486232e308 à
           1,79769313486232e308
=========  ====================================================================


Type spéciphiques
-----------------

=========  ====================================================================
Type       Description
=========  ====================================================================
bool       Boolean, vrai ou faux
unichar    Un caractère (utilisant l'encodage *unicode*)
string     Une chaine de caractère
=========  ====================================================================
   
Vous verrez plus loin qu'il existe encore d'autres types dans le langage
Vala et qu'on peut également construire les siens.


Affectations, opérations, concaténation
=======================================

Il est possible d’effectuer des opérations sur les variables et entre les
variables. Nous avons déjà vu comment affecter une valeur à une variable grâce
à l’opérateur *=*.

.. code-block:: vala

   int age = 30;
   string prenom = "nicolas";

.. note::

   Dans ce paragraphe, je vais vous donner plusieurs exemples d’affectations.
   Ces affectations seront faites sur la même instruction que la déclaration
   pour des raisons de concision. Mais ces exemples sont évidemment
   fonctionnels pour des affectations qui se situent à un endroit différent de 
   la déclaration.

En plus de la simple affectation, nous pouvons également faire des opérations, 
par exemple :

.. code-block:: vala

   int resultat = 2 * 3;

ou encore

.. code-block:: vala
   :linenos:

   int age1 = 20;
   int age2 = 30;
   int moyenne = (age1 + age2) / 2;

Les opérateurs *+*, *``*``*, */* ou encore *-* (que nous n’avons pas
encore utilisés) servent bien évidemment à faire les opérations mathématiques
qui leur correspondent, à savoir respectivement l’addition, la multiplication,
la division et la soustraction.

Vous aurez donc surement deviné que la variable *resultat* contient 6 et que
la moyenne vaut 25.

Il est à noter que les variables contiennent une valeur qui ne peut évoluer
qu’en affectant une nouvelle valeur à cette variable.

Ainsi, si j’ai le code suivant :

.. code-block:: vala
   :linenos:
   
   int age1 = 20;
   int age2 = 30;
   int moyenne = (age1 + age2) / 2;
   age2 = 40;
   

La variable moyenne vaudra toujours 25 même si j’ai changé la valeur de la 
variable *age2*.

En effet, lors du calcul de la moyenne, j’ai rangé dans mon classeur la valeur
25 grâce à l’opérateur d’affectation *=* et j’ai refermé mon classeur. Le
fait de changer la valeur du classeur *age2* n’influence en rien le classeur
*moyenne* dans la mesure où il est fermé.

Pour le modifier, il faudrait ré-exécuter l’opération d’affectation de la
variable moyenne, en écrivant à nouveau l’instruction de calcul, c’est-à-dire :

.. code-block:: vala
   :linenos:
   
   int age1 = 20;
   int age2 = 30;
   int moyenne = (age1 + age2) / 2;
   age2 = 40;
   moyenne = (age1 + age2) / 2;

D’autres opérateurs particuliers existent que nous ne trouvons pas dans les
cours de mathématiques. Par exemple, l’opérateur ++ qui permet de réaliser une
incrémentation de 1, ou l’opérateur -- qui permet de faire une décrémentation
de 1.

De même, les opérateurs que nous avons déjà vus peuvent se cumuler à l’opérateur
= pour simplifier une opération qui prend une variable comme opérande et
cette même variable comme résultat.

Par exemple :

.. code-block:: vala
   :linenos:
   
   int age = 20;
   age = age + 10; // age contient 30 (addition)
   age++; // age contient 31 (incrémentation de 1)
   age--; // age contient 30 (décrémentation de 1)
   age += 10; // équivalent à age = age + 10 (age contient 40)
   age /= 2; // équivalent à age = age / 2 => (age contient 20)

Comme nous avons pu le voir dans nos cours de mathématiques, il est possible de
grouper des opérations avec des parenthèses pour agir sur leurs priorités.

Ainsi, l’instruction précédemment vue :

.. code-block:: vala
   
   int moyenne = (age1 + age2) / 2;
   
effectue bien la somme des deux âges avant de les diviser par 2, car les
parenthèses sont prioritaires.

Cependant, l’instruction suivante :

.. code-block:: vala
   
   int moyenne = int moyenne = age1 + age2 / 2;
   
aurait commencé par diviser l’age2 par 2 et aurait ajouté l’age1, ce qui 
n’aurait plus rien à voir avec une moyenne.
 
En effet, la division est prioritaire par rapport à l’addition.
 
.. important::
   Attention, la division ici est un peu particulière.

Prenons cet exemple :

.. code-block:: vala
   
   int moyenne = 5 / 2;
   print("%d \n", moyenne);
   
Si nous l'exécutons, nous voyons que moyenne vaut 2.

.. hint::
   2 ? Si je me rappelle bien de mes cours de math ... c'est pas plutôt 2.5 ?

Oui et non.

Si nous divisions 5 par 2, nous obtenons bien 2.5.

Par contre, ici nous divisons l'entier 5 par l'entier 2 et nous stockons le
résultat dans l'entier moyenne.

Le Vala réalise en fait une division entière, c'est-à-dire qu'il prend la partie
entière de 2.5, c'est-à-dire 2.

De plus, l'entier moyenne est incapable de stocker une valeur contenant des 
chiffres après la virgule. Il ne prendrait que la partie entière.

Pour avoir 2.5, il faudrait utiliser le code suivant :

.. code-block:: vala
   
   double moyenne = 5.0 / 2.0;
   print("%f \n", moyenne);
   
Ici, nous divisons deux « doubles » entre eux et nous stockons le résultat
dans un « double ». (Rappelez-vous, le type de données « double » permet de
stocker des nombres à virgule.)

.. note::
   Le Vala comprend qu'il s'agit de double car nous avons ajouté un .0 derrière.
   Sans ça, il considère que les chiffres sont des entiers.
   
Les caractères spéciaux dans les chaines de caractères
======================================================

En ce qui concerne l’affectation de chaines de caractères, vous risquez 
d’avoir des surprises si vous tentez de mettre des caractères spéciaux dans
des variables de type string.

En effet, une chaine de caractères étant délimitée par des guillemets " ",
comment faire pour que notre chaine de caractères puisse contenir des guillemets ?

C’est là qu’intervient le caractère spécial \ qui sera à mettre juste devant le
guillemet, par exemple le code suivant :

.. code-block:: vala
   :linenos:
   
   string phrase = "Mon prénom est \"Nicolas\" \n";
   print(phrase);

affichera :

.. code-block:: text
   
   Mon prénom est "Nicolas"

Si vous avez testé par vous-même, vous avez pu remarquer que le caractère
spécial *\n* effectue un saut de ligne. 

Ainsi, le code suivant :

.. code-block:: vala
   :linenos:
   
   string phrase = "Mon prénom est \"Nicolas\"\n";
   print(phrase);
   print("Passe\nà\nla\nligne\n");

affichera:


.. code-block:: text
   
   Mon prénom est "Nicolas"
   Passe
   à
   la
   ligne
   
où nous remarquons bien les divers passages à la ligne.
 
On peut aussi utiliser le caractère spécial *\t* pour effectuer une tabulation.
Le code suivant:
 
.. code-block:: vala
   :linenos:
   
   print("Choses à faire :");
   print("\t - Arroser les plantes");
   print("\t - Laver la voiture");
   
permettra d’afficher des tabulations, comme illustré ci-dessous :
   
.. code-block:: text
   
   Choses à faire :
           - Arroser les plantes
           - Laver la voiture

Nous avons vu que le caractère \ était un caractère spécial et qu’il permettait
de dire au compilateur que nous voulions l’utiliser combiné à la valeur qui le
suit, permettant d’ avoir une tabulation ou un retour à la ligne.

Comment pourrons-nous avoir une chaine de caractères qui contienne ce fameux
caractère ?

Le principe est le même, il suffira de faire suivre ce fameux caractère spécial
de lui-même. Exemple:

.. code-block:: vala
   :linenos:
   
   print("Le caractère backslash \\");
   
En résumé
=========

- Une variable est une zone mémoire permettant de stocker une valeur d'un type
  particulier.
- Le Vala possède plein de types prédéfinis, comme les entiers (int), les
  chaînes de caractères (string), etc.
- On utilise l'opérateur = pour affecter une valeur à une variable.
- Il est possible de faire des opérations entre les variables.



