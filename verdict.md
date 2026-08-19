# Verdict — Recommandation Mistral Assurances

> **5 lignes maximum.** Document remis à Inès Tabet.
> Auteur : `Etienne` — Date : `18/08/2026`

**Recommandation** : Nous vous recommandons de changer de modèle pour aller vers le modèle HistGB

**Raison principale (chiffrée)** : Sur des données identiques, l'erreur moyenne passe de 114 a 52 locations par heure, soit une baisse de 55%, le R2 fait aussi un bond drastique et passe de 0.3 a 0.8, le modèle comprend désormais 80% des variations de la demande de location contre 32% aujourd'hui et on note une baisse de 48% sur les erreurs les plus critiques (notamment sur les pics d'activités)

**Condition de changement d'avis** : si l'explicabilité du modele pose problème alors je proposerais de le rendre plus transparent en implémentant la librairie tierce SHAP, qui permet de donner le "poids" de chaque variables dans le calcul. 

---

*Verdict produit par Etienne, 18/08/2026, dans le cadre du brief M4-B1 pas ATOS.*
