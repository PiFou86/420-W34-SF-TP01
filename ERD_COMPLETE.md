# Version complétée de l'ERD et justifications

## Schéma (Équipier 1 et 2 : attention aux conflits de fusion)

Travaillez ici la version à compléter de l'ERD. (Débutez par un copier / coller de l'ERD du sujet)

---

## Justifications des clefs choisies par table (Équipier 1)

Pour chaque table, vous devez justifier le choix de la clef primaire.

Vous devez expliquer si vous avez choisi :

- une clef naturelle;
- une clef artificielle;
- une clef composée.

Dire qu’une colonne est unique n’est pas suffisant pour justifier une clef primaire. Vous devez expliquer pourquoi cette colonne est stable, obligatoire, simple à référencer et pertinente pour identifier une ligne dans le temps.

Une justification absente, trop courte ou purement descriptive ne sera pas suffisante.

### Exemples de justifications attendues

Ex. table `Etudiant` : nous avons choisi `matricule` comme clef primaire, car le matricule est attribué par l’établissement, il est obligatoire, unique et stable dans le temps. Le nom et le prénom ne sont pas de bonnes clefs, car plusieurs étudiants peuvent avoir le même nom.

Ex. table `Commande` : nous avons ajouté une colonne `commandeId` comme clef primaire, car aucune donnée fournie ne permet d’identifier naturellement une commande de manière simple et stable. La date de commande et le client ne suffisent pas, car un client peut passer plusieurs commandes la même journée.

Ex. table `InscriptionCours` : nous avons choisi la clef composée `(etudiantId, coursId, session)` parce qu’un étudiant ne peut être inscrit qu’une seule fois au même cours pour une même session. Cette clef représente directement la règle métier.

Ex. table `ReservationSalle` : nous avons ajouté `reservationId` comme clef primaire pour simplifier les références vers cette table. Nous avons aussi ajouté une contrainte d’unicité sur `(salleId, dateDebut, dateFin)` afin d’éviter deux réservations identiques pour la même salle au même moment.

Ex. table `Personne` : nous n’avons pas choisi le numéro de téléphone comme clef primaire, car une personne peut ne pas avoir de téléphone, changer de numéro ou partager un numéro avec une autre personne.

---

### Aeroport

Justification :

### Avion

Justification :

### Billet

Justification :

### CompagnieAerienne

Justification :

### DonneesTranspondeur

Justification :

### OccurrenceVol

Justification :

### Passager

Justification :

### Pays

Justification :

### RevisionAvion

Justification :

### Vol

Justification :

### Voyage

Justification :

---

## Justifications des types de colonnes choisis par table (Équipier 2)

Pour chaque table, vous devez justifier les types de données choisis pour les colonnes.

Une justification ne doit pas seulement répéter le type choisi. Elle doit expliquer pourquoi ce type est approprié pour la donnée représentée, les contraintes métier, les valeurs possibles et les requêtes attendues.

Vous devez aussi justifier les contraintes importantes, par exemple :

- `NOT NULL`;
- `NULL`;
- `CHECK`;
- `UNIQUE`;
- `DEFAULT`;
- colonne calculée;
- choix entre une colonne simple et une table de référence;
- choix entre une donnée stockée et une donnée calculée.

---

### Règles générales applicables sur plusieurs champs

Indiquez ici les règles que vous appliquez à plusieurs colonnes du modèle.

Ex. : les noms, prénoms, titres et descriptions utilisent `NVARCHAR`, car ils peuvent contenir des accents ou des caractères non latins.

Ex. : un montant d’argent est représenté par `DECIMAL(10,2)` plutôt que `FLOAT`, car il doit être stocké avec une précision fixe.

Ex. : une date de naissance utilise `DATE`, car l’heure n’est pas pertinente.

Ex. : une date de rendez-vous utilise `DATETIME2`, car l’heure est nécessaire.

Ex. : une colonne indiquant si un compte est actif utilise `BIT`, car elle représente une valeur vraie ou fausse.

Ex. : une quantité commandée utilise un type numérique entier et une contrainte `CHECK` pour empêcher les valeurs inférieures ou égales à zéro.

Ex. : un statut de commande peut être représenté par une colonne texte avec contrainte `CHECK`, ou par une clef étrangère vers une table de référence. Le choix doit être justifié selon le nombre de valeurs possibles, leur stabilité et les requêtes attendues.

Ex. : un total de facture peut être une colonne calculée ou être obtenu par requête à partir des lignes de facture, car il dépend d’autres données.

---

### Justifications pour les champs particuliers

Indiquez ici les choix qui nécessitent une justification particulière.

Ex. : nous avons choisi `VARCHAR(10)` pour un code court composé uniquement de caractères non accentués, car la longueur maximale est connue et les caractères Unicode ne sont pas nécessaires.

Ex. : nous avons choisi `NVARCHAR(100)` pour un nom affiché à l’utilisateur, car il peut contenir des accents, des espaces, des traits d’union ou d’autres caractères Unicode.

Ex. : nous avons choisi `DATE` pour une date de naissance, car l’heure n’a pas de signification dans ce contexte.

Ex. : nous avons choisi `DATETIME2` pour une date de début d’événement, car il faut conserver à la fois la date et l’heure.

Ex. : nous avons choisi `DECIMAL(10,2)` pour un montant d’argent, car une précision fixe est nécessaire. Le type `FLOAT` n’est pas approprié pour ce type de donnée.

Ex. : nous avons choisi `BIT` pour une colonne indiquant si une condition est vraie ou fausse.

Ex. : nous avons ajouté une contrainte `CHECK` sur une valeur numérique afin d’empêcher les valeurs impossibles selon les règles métier.

Ex. : nous avons choisi de ne pas stocker directement une donnée calculable, car elle peut être obtenue à partir d’autres colonnes et pourrait créer des incohérences si elle était modifiée manuellement.

Ex. : nous avons choisi de stocker une donnée calculée, mais uniquement sous forme de colonne calculée, afin de garantir que sa valeur reste cohérente avec les données dont elle dépend.

---

### Aeroport

Justification :

### Avion

Justification :

### Billet

Justification :

### CompagnieAerienne

Justification :

### DonneesTranspondeur

Justification :

### OccurrenceVol

Justification :

### Passager

Justification :

### Pays

Justification :

### RevisionAvion

Justification :

### Vol

Justification :

### Voyage

Justification :
