********************************
Maîtrise des variables : avancée
********************************


Les différents types de variables
=================================

Nous avons vu juste au-dessus que la variable *nombre* pouvait être un entier
numérique grâce au mot clé *int*. Le langage Vala dispose de beaucoup de types
permettant de représenter beaucoup de choses différentes.

Par exemple, nous pouvons stocker une chaîne de caractères grâce au type *string*.

.. code-block:: vala

   string prenom = "nicolas";

ou encore un boolean (qui représente une valeur vraie ou fausse) avec :

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
int8       Entier de -128 à +127
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

Les nombres ci-dessus ont une taille qui varie en fonction de la plateforme
sur laquelle le code a été compilé. Les valeurs limitées sont données, à titre
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


Types spécifiques
-----------------

=========  ====================================================================
Type       Description
=========  ====================================================================
bool       Boolean, vrai ou faux
unichar    Un caractère (utilisant l'encodage *unicode*)
string     Une chaîne de caractère
=========  ====================================================================

Vous verrez plus loin qu'il existe encore d'autres types dans le langage
Vala et qu'on peut également construire les siens.
