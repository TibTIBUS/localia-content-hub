# Routine Hermes - publication social media

Frequence recommandee : tous les jours a 06:00 Europe/Paris.

## Mission

Publier les contenus Localia stockes dans GitHub lorsque leur statut est ready et que leur date de publication est atteinte.

## Etapes

1. Lire les fichiers JSON dans content/ready.
2. Garder uniquement les contenus avec status ready, scheduled_for atteint, et platforms contenant facebook ou instagram.
3. Pour Facebook, lire facebook.text, recuperer visual.file, puis publier sur la Page connectee.
4. Pour Instagram, lire instagram.caption, ajouter les hashtags, recuperer visual.file, puis publier sur le compte professionnel connecte.
5. Apres succes, passer status a published, ajouter published_at, ajouter les liens si disponibles, puis deplacer le fichier vers content/published.
6. En cas d erreur, passer status a failed, ajouter error_message, puis deplacer le fichier vers content/failed.
7. Creer un rapport Markdown dans reports.

## Regles

- Ne jamais publier deux fois le meme contenu.
- Ignorer tout contenu deja en published.
- Ne jamais publier si le visuel manque et que la plateforme impose une image.
- Ne jamais modifier le sens du texte sans consigne explicite.
