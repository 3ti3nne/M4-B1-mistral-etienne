# Carte de décision personnelle — M4-B1

> **Ton ébauche perso** de la grille de décision C4, **avant** la
> restitution collective de mercredi. À confronter aux propositions des
> autres pour construire la grille commune.
> Auteur : `Etienne` — Date : `18/08/2026`

## Critères que je mobilise (mon ordre de priorité)

1. Précision sur les heures de pointes
2. Les jours exceptionnels où le modèle peut faire des erreurs notables
3. Précision sur le pic printemps-été
4. Savoir expliquer une prédiction

## Modèles que j'ai benchmarkés

> Liste rapide.

- Famille A : RandomForest
- Famille B : HistGradientBoosting
- Famille C : Ridge

## Pour quel cas je choisirais chaque famille ?

> Si Inès me demandait *« et pour un cas X, vous prendriez quoi ? »*.

| Cas                                                 | Famille recommandée | Pourquoi                                                                                                                                    |
|-----------------------------------------------------|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **Mistral Bike Sharing (saisonnalité forte)**       | HistGB              | Meilleure perception des cas non linéaires, sensiblement pareil que RandomForest mais est beaucoup plus rapide et pèse beaucoup moins lourd |
| **Cas similaire mais 100 lignes seulement**         | Ridge               | Forest probablement trop complexe pour des petits cas                                                                                       |
| **Cas avec exigence d'explicabilité réglementaire** | Ridge               | Les arbres sont trop "boîte noire"                                                                                                          |
| **Cas avec latence < 5 ms imposée**                 | HistGb / Ridge      | HistGb est à 4.7 donc à monitorer pour qu'il n'atteigne pas la limite, sinon fallback sur Ridge qui est à 1                                 | ...                                                                                                                                         |

## Analyse éthique et réglementaire (C2)

> ~5 lignes. Le geste : **évaluer s'il existe réellement des risques**, puis
> **conclure**. Conclure « risque faible » est une réponse valide et
> professionnelle — pas besoin d'inventer un problème.

- Le dataset contient-il des **données personnelles** ? Non
- Utilise-t-on un **attribut sensible** / y a-t-il un risque de **biais** envers une population ? Non
- Y a-t-il un enjeu **RGPD / confidentialité** ? Non
- Quel **impact sociétal** de l'usage du modèle (destinataires directs/indirects) ? Si le modèle calcule mal, les usagers seront impactés possiblement dans leur vie professionnelle
- **Conclusion** : Risque faible, données agrégées, pas de PII → risque faible ;
  si on exploitait des trajets individuels, il faudrait une analyse RGPD +
  minimisation + réidentification 

## Ouverture — Robustesse d'une solution d'IA (hors C2, prépare M7)

> Cette activité **ne relève pas de C2**. C'est un **complément à ta décision
> C4** et une ouverture vers **M7** (menaces sur les systèmes d'IA) : un réflexe
> pro = évaluer les limites d'un modèle au-delà de ses performances. Une ligne
> suffit. Cf. mini-cours `06_Menaces_robustesse_essentiel.md`.

- **Vulnérabilité identifiée** : le modèle accepte des entrées non valides, temperature_norm au dessus du seuil, et renvoie sans erreur un chiffre anormal
- **Garde-fou envisagé** en conception : validation des données avant entrée

## Ce que je veux apporter à la grille collective

> 1-2 contributions ou questions à pousser pendant la restitution.

- ...
- ...

---

*Carte personnelle à compléter avant la restitution collective mercredi 11h30.*
