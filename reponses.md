Comment stocke-t-on disponible et date_ajout dans SQLite ?

disponible : Stocké en entier (INTEGER), avec 0 pour faux et 1 pour vrai.

date_ajout : Stocké en texte (TEXT) au format standard (ex: YYYY-MM-DD HH:MM:SS).

Quel est le rôle de AUTOINCREMENT, de UNIQUE sur nom, et de CHECK (prix >= 0) ?

AUTOINCREMENT : Génère automatiquement un identifiant unique et croissant pour chaque nouvelle ligne.

UNIQUE sur nom : Empêche d'avoir deux enregistrements avec le même nom (évite les doublons).

CHECK (prix >= 0) : Interdit les prix négatifs.

Que signifie ON DELETE RESTRICT ?

Empêche de supprimer un élément parent s'il est encore utilisé par un élément enfant (bloque la suppression pour éviter les données orphelines).