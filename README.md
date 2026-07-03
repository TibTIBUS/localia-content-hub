# Localia Content Hub

Dépôt éditorial automatisé pour Localia.

Objectif :
- ChatGPT crée les contenus Facebook et Instagram.
- Les contenus sont stockés dans GitHub avec un statut clair.
- Hermès récupère les contenus prêts.
- Hermès publie sur Facebook et Instagram.
- Hermès écrit un rapport après publication.

## Structure

```txt
/content
  /drafts       Contenus non validés
  /ready        Contenus prêts à publier
  /published    Contenus publiés
  /failed       Contenus en erreur
/assets
  /images       Visuels source ou fichiers visuels associés
  /visual-briefs Briefs visuels détaillés
/reports        Rapports de publication Hermès
/config         Schémas, règles éditoriales et consignes
/routines       Prompts de routine ChatGPT et Hermès
```

## Règle principale

Ne jamais publier deux fois le même contenu.

Un contenu publiable doit avoir :
- `status: "ready"`
- une date `scheduled_for`
- au moins une plateforme dans `platforms`
- un texte Facebook ou une caption Instagram
- un visuel associé ou un brief visuel exploitable

## Important sur les visuels

Les visuels doivent rester cohérents avec les visuels déjà publiés sur la page Facebook Localia.

Le lien de référence est :
https://www.facebook.com/profile.php?id=61588767745281&sk=photos

Si l’accès direct à la galerie Facebook est bloqué, ne pas improviser :
- utiliser uniquement les règles validées dans `config/brand-guardrails.md` ;
- produire un brief visuel ou un SVG source sobre ;
- attendre validation ou fournir un visuel conforme aux codes Localia déjà connus.
