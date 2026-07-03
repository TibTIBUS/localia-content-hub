# BE-006 - Gestion des visuels

## Decision d architecture

ChatGPT est responsable de la creation des visuels.
Hermes est responsable de la publication.

Hermes ne doit pas inventer le visuel. Il doit utiliser le visuel final fourni par ChatGPT.

## Sorties attendues par ChatGPT

Pour chaque contenu, ChatGPT doit produire :

1. Le fichier JSON dans `/content/ready`.
2. Le brief visuel dans `/assets/visual-briefs`.
3. Le prompt source dans `/assets/image-prompts`.
4. Le visuel final dans `/assets/images`, ou une version encodee si le connecteur ne permet pas l upload binaire direct.

## Regle ready

Un contenu ne doit passer en `ready` que si :

- le texte Facebook existe ;
- le texte Instagram existe ;
- le brief visuel existe ;
- le prompt image existe ;
- le visuel final est disponible ou recuperable ;
- la checklist qualite est validee.

## Fallback technique

Si le connecteur GitHub ne permet pas d envoyer directement un PNG, ChatGPT peut stocker :

`/assets/images/<id>.png.b64`

Hermes devra alors :

1. Lire le fichier `.png.b64`.
2. Le decoder en PNG localement.
3. Utiliser ce PNG pour publier.

## Interdiction

Hermes ne doit pas publier si :

- le PNG est absent ;
- le fichier `.png.b64` est absent ;
- le brief existe mais aucun visuel final n est disponible ;
- le visuel ne respecte pas le Brand Engine.
