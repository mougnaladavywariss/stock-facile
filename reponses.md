Comment stocke-t-on disponible et date_ajout dans SQLite ?

disponible : Stocké en entier (INTEGER), avec 0 pour faux et 1 pour vrai.

date_ajout : Stocké en texte (TEXT) au format standard (ex: YYYY-MM-DD HH:MM:SS).

Quel est le rôle de AUTOINCREMENT, de UNIQUE sur nom, et de CHECK (prix >= 0) ?

AUTOINCREMENT : Génère automatiquement un identifiant unique et croissant pour chaque nouvelle ligne.

UNIQUE sur nom : Empêche d'avoir deux enregistrements avec le même nom (évite les doublons).

CHECK (prix >= 0) : Interdit les prix négatifs.

Que signifie ON DELETE RESTRICT ?

Empêche de supprimer un élément parent s'il est encore utilisé par un élément enfant (bloque la suppression pour éviter les données orphelines).

2. Questions de réflexion

Pourquoi utilise-t-on ici un constructeur factory plutôt qu'un constructeur classique ?

Un constructeur factory permet de faire des traitements (comme parser du texte en DateTime ou convertir des types) avant de retourner l'instance, et il n'est pas obligé de créer systématiquement une nouvelle instance (utile pour le pattern Singleton ou le cache).

Pourquoi écrit-on (map['prix'] as num).toDouble() au lieu de map['prix'] as double ?

Parce que SQLite stocke les nombres entiers (ex: 5) sous forme d'int en Dart. Si on caste directement un int en double avec as double, Dart lève une erreur de type. Passer par num permet de récupérer un entier ou un décimal et de le convertir proprement en double.