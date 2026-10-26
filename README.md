# focus-site

Les pages publiques de l'app, servies par GitHub Pages à
`https://inglow.github.io/focus-site/`. Le dépôt de l'app, `inglow/focus`, est
privé : ce qui doit être lu par un navigateur passe par ce dépôt public.

| Fichier | Rôle |
|---|---|
| `invitation/index.html` | La page de repli du lien d'invitation (PLAN, étape 3, option B) |
| `index.html` | Un accueil neutre, pour ne pas laisser l'adresse vide |
| `.nojekyll` | GitHub Pages sert les fichiers tels quels, sans Jekyll |

## La page d'invitation

- C'est la **copie exacte** de `web/invitation/index.html`, dans le dépôt de
  l'app. Le déploiement de l'app (`deploy-uat`, `deploy-main`) télécharge la
  page publiée et la compare à ce fichier, octet par octet : si elles diffèrent,
  il retire l'adresse et le lien d'invitation repasse par `accept-invitation`.
  Le run le signale, sans s'arrêter.
- Son adresse est dans la variable GitHub `FOCUS_INVITE_PAGE_URL` du dépôt de
  l'app : `https://inglow.github.io/focus-site/invitation/`.
- Après toute modification de `web/invitation/index.html`, recopier le fichier
  puis le publier :

  ```bash
  cp ~/Documents/workspace/applicationMobile/focus/web/invitation/index.html invitation/index.html
  ```

## Règles

- Aucun secret, aucun jeton, aucune donnée : le dépôt est public.
- Les pages ne chargent rien d'extérieur (politique de sécurité dans chaque
  page) et ne portent pas le nom de l'app, qui est provisoire.
- Branche `main` protégée, compte GitHub en double authentification.
