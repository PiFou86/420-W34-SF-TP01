# Version complétée de l'ERD et justifications

## Schéma

L'ERD ici.

## Justifications des clefs choisies par table

Ex. table `Etudiant` : nous avons choisi le numéro de matricule comme clef primaire car elle est unique à travers le système et représente bien un étudiant du point de vu métier.

### Aeroport

### Avion

### Billet

### CompagnieAerienne

### DonneesTranspondeur

### OccurrenceVol

### Passager

### Pays

### RevisionAvion

### Vol

### Voyage

## Justifications des types de colonnes choisis par table

### Règles générales applicables sur plusieurs champs

- Ex. : Règle 1 : les couleurs sont des références à la table couleur qui a pour FK un entier alors toutes les références sont des entiers

### Justifications pour les champs particuliers

- Ex. : une note est une valeur décimale en pourcent, donc nous allons utiliser le type NUMBER(4,1). Nous allons aussi ajouter une validation unitaire pour que note soit NULL ou ait une valeur entre 0 et 100.
