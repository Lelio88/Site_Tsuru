# Site Tsuru — Contexte d'Opération

## I. Finalité

Pages web publiques de Tsuru (app d'apprentissage du japonais) : accueil, confidentialité, suppression des données, mentions légales. Elles fournissent les URL que la fiche Google Play exige. Le code de l'app est dans le dépôt privé `Tsuru`.

## II. Architecture

Site statique pur (HTML/CSS, aucun build, aucun JavaScript), servi par GitHub Pages depuis la racine de `main`. `legal.css` est la seule feuille de style ; `icone.png` est l'icône Play (copie de `Tsuru/store/visuels/icone-512.png`).

## III. Pile Technologique

HTML5 et CSS3 vanilla. Aucune dépendance.

## IV. Garde-Fous non négociables

1. **Zéro ressource tierce, zéro JavaScript, aucun style en ligne.**
2. **La politique de confidentialité dit vrai** : toute fonction de Tsuru qui contacte un service ou collecte une donnée la met à jour **dans le même commit** (et change sa date). Aujourd'hui : rien n'est collecté ni transmis.
3. **Chaque page porte** `<meta name="tdm-reservation" content="1" />` et la navigation légale.
4. **Crédits tiers à jour** (KanjiVG, Zen Maru Gothic, VOICEVOX) en cohérence avec `Tsuru/CREDITS.md`.
5. **Contact public unique** : `heianenterpriseyt@gmail.com`.

## V. Flux de Travail (Explore → Plan → Code → Verify)

Modifier le HTML, ouvrir la page dans un navigateur isolé, vérifier mobile (320 px) et contraste, committer, pousser ; Pages publie en une minute (cache navigateur jusqu'à 10 min).

## VI. Commandes de Développement

Aucune. `python -m http.server` pour prévisualiser.

## VII. Maintenance documentaire

| Modification | Fichier à mettre à jour |
|---|---|
| Donnée collectée, permission, service tiers dans l'app | `confidentialite.html` + date |
| Crédit ou licence tierce | `index.html`, `mentions-legales.html` |

## VIII. Contexte de Session

- **Dernier focus** : création du site pour la publication Play de Tsuru.
- **Focus immédiat** : activer Pages, vérifier les URL, les saisir dans la Play Console.
