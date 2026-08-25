# Mise à jour du portfolio — mode d'emploi

## Ce que contient le dossier

| Fichier | Où le placer | Pourquoi |
|---|---|---|
| `index.html` | à la racine de `mon_portfolio/` (remplace l'ancien) | nouvelle page complète |
| `cv/index.html` | dans le dossier `cv/` (nouveau fichier) | l'ancien `cv/indexCV` n'a pas d'extension : GitHub Pages le **télécharge** au lieu de l'ouvrir. Le lien du CV était donc cassé pour tout visiteur. |
| `projets/rapport-alm/index.html` | nouveau dossier `projets/rapport-alm/` | même problème avec `projets/rapport ALM/indexrapportALM` (pas d'extension + espace dans le nom) |

Tu peux garder les anciens fichiers, ils ne gênent pas.

## Publier

```bash
cd chemin/vers/mon_portfolio

# copie les 3 fichiers du zip en respectant l'arborescence, puis :
git add -A
git commit -m "Refonte du portfolio : design sombre, bilingue FR/EN, resultats chiffres"
git push
```

GitHub Pages met environ 1 minute à se mettre à jour. Vide le cache (Ctrl+F5) pour voir le résultat.

## Vérifier avant de pousser

Ouvre simplement `index.html` dans ton navigateur depuis ton dossier local :
la photo, les icônes et le bouton FR/EN doivent fonctionner.

---

# Ce qui a changé

## Bugs corrigés

1. **`lang="en"` alors que le texte est en français.** Chrome traduisait automatiquement ta page : un recruteur voyait « Exceller » à la place d'Excel et « Maison » à la place d'Accueil. Corrigé, et l'attribut suit maintenant la langue choisie.
2. **Les deux boutons « Download CV » ne faisaient rien** (aucun lien). Ils pointent maintenant vers `cv/index.html`.
3. **Lien du CV et du rapport ALM cassés** (fichiers sans extension) — voir tableau ci-dessus.
4. **Deux gestionnaires JavaScript sur le formulaire.** Le second affichait « message envoyé » même quand Formspree échouait. Un seul gestionnaire désormais, avec un vrai message d'erreur.
5. **Liens Instagram et GitHub morts** (`href="#"`). Instagram retiré (aucun intérêt pour un recruteur actuariat), GitHub pointe vers ton profil.
6. **Virgules parasites** visibles dans le texte de la page (`<section id="contact">,`).
7. **Balises invalides** : `<h3 v>`, icône `fas fas-home-shield` inexistante.
8. **Titre incohérent** : la carte « Analyse ORSA » décrivait en réalité un exercice IFRS 17 / BBA. Renommée.
9. **Pas de description ni d'aperçu** : ajout des balises meta et Open Graph. Quand tu partages ton lien sur LinkedIn, l'aperçu affiche maintenant ta photo et une accroche.

## Ce qui a été ajouté

- **Bilingue FR / EN** via le sélecteur en haut à droite. Chaque texte porte `data-fr` et `data-en` — pour modifier une phrase, édite les deux attributs.
- **Bandeau de disponibilité** en haut : « Disponible immédiatement — Belgique, Luxembourg & remote ».
- **Quatre chiffres clés** sous l'accroche : 4 ans en compagnie, 15+ projets, 13 ans d'enseignement, IABE.
- **Section Parcours** : deux frises (expérience / formation) reprises de ton CV.
- **Résultats chiffrés sur chaque projet** au lieu d'un simple paragraphe : +3,6 % à +9,2 % de surcharge, 5 modèles comparés, Chain-Ladder, Pareto/GPD, etc. C'est ce qu'un recruteur lit en premier.
- **Deux projets récupérés** qui n'étaient pas affichés : le rapport ALM et les analyses de marché (NVIDIA, AAPL, immobilier US).
- **Bloc « Autres travaux »** : freMTPL2, bmspy, détection de fraude, risque de crédit, crédibilité Bühlmann-Straub, QuantLab, etc.
- **Design sombre premium** : navy + ambre, la même identité que tes documents de candidature.
- **Menu mobile** entièrement refait (l'ancien débordait de l'écran).
- **Plus de dépendance à typed.js ni scrollReveal** : l'animation de frappe et les apparitions sont écrites en JavaScript simple et commenté en français, dans le fichier. Deux scripts externes en moins à charger.

---

# À faire ensuite (par ordre d'impact)

1. **Ajouter un vrai CV en PDF.** Une page HTML ne se glisse pas dans un dossier de candidature. Dépose `cv/CV-Steve-SIMO-TCHEMO.pdf` dans le dépôt et remplace les trois `href="cv/index.html"` par ce chemin. C'est le point le plus important.
2. **Décrire tes dépôts GitHub.** `closing-actuariel` et `reassurance-xl-mtpl-pricing` n'ont ni description ni README visible. Un recruteur qui clique « Voir le projet » tombe sur une liste de fichiers nue. Un README avec le contexte, la méthode et deux graphiques change tout.
3. **Publier les projets du bloc « Autres travaux »** (freMTPL2, bmspy, fraude, crédit) et les transformer en vraies cartes avec lien.
4. **Photo.** La tienne est correcte mais le fond blanc tranche sur un fond sombre. Une photo sur fond neutre gris ou en extérieur flou passerait mieux.
5. **Domaine personnalisé** (facultatif) : `steve-simo.be` fait plus sérieux que `steve-gerald.github.io` et se configure en 10 minutes dans les réglages GitHub Pages.
