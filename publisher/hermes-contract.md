# BE-004 - Contrat Hermès Publisher

## Objectif

Ce contrat definit comment Hermès doit lire, publier et classer les contenus Localia.

## Planning

Hermès doit tourner les lundis et jeudis a 10:00 heure de Paris.

## Source

Depot : TibTIBUS/localia-content-hub
Dossier source : /content/ready

## Selection des contenus

Hermès publie uniquement les fichiers JSON qui respectent toutes les conditions :

- status = ready
- scheduled_for inferieur ou egal a maintenant
- platforms contient facebook ou instagram
- id non deja publie
- visual.brief existe

## Publication Facebook

Utiliser :
- facebook.text
- visual.file si disponible
- sinon exploiter visual.brief pour generer ou recuperer le visuel final selon les capacites Hermès

## Publication Instagram

Utiliser :
- instagram.caption
- instagram.hashtags
- visual.file si disponible
- sinon exploiter visual.brief pour generer ou recuperer le visuel final selon les capacites Hermès

## Apres succes

Mettre a jour le JSON :
- status = published
- publication.published_at = date actuelle
- publication.facebook_post_url si disponible
- publication.instagram_post_url si disponible

Puis deplacer le fichier vers /content/published.

## En cas d erreur

Mettre a jour le JSON :
- status = failed
- error_message = message clair

Puis deplacer le fichier vers /content/failed.

## Rapport

Creer un rapport dans /reports avec :
- date
- fichiers traites
- publications reussies
- erreurs
- liens disponibles

## Regle absolue

Ne jamais publier deux fois le meme contenu.
