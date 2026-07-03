# BE-004 - Flux de statut

## Etats autorises

### draft

Contenu en preparation. Ne doit jamais etre publie.

### ready

Contenu pret a publier. Hermès peut le lire si la date est atteinte.

### published

Contenu publie avec succes. Hermès doit l ignorer.

### failed

Contenu non publie a cause d une erreur. Hermès doit l ignorer sauf relance explicite.

## Transitions autorisees

- draft vers ready
- ready vers published
- ready vers failed
- failed vers ready uniquement apres correction humaine ou agent explicite

## Interdictions

- published vers ready
- published vers failed
- supprimer un contenu sans trace
- publier un contenu en draft
