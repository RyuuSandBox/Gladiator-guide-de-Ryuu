# Guide Gladiator — AION 2

Guide de classe pour la Saison 1 globale d'AION 2 (5 octobre 2026). Une page HTML
autonome, sans dépendance ni build : on l'ouvre dans un navigateur, ou on la pose sur
GitHub Pages.

---

## Ce qu'il y a dans le dossier

| Fichier | Rôle |
|---|---|
| `index.html` | Le guide. 19 chapitres, ~195 Ko, tout est dedans (CSS, JS, avatar). |
| `icons/` | Les 35 icônes officielles des sorts. Vérifiées une par une. |
| `README.md` | Ce fichier. |

L'avatar est encodé directement dans la page : rien à copier à côté.
Les seules ressources externes sont les trois polices Google (Cinzel, Archivo,
JetBrains Mono). Sans connexion, la page reste lisible avec les polices système.

---

## Mettre en ligne sur GitHub Pages

Même dispositif que le guide Assassin :

1. Nouveau dépôt public, par exemple `Gladiator-guide-de-Ryuu`.
2. Déposer `index.html` **à la racine** du dépôt, et le dossier `icons/` à côté.
3. `Settings` → `Pages` → Source : `Deploy from a branch`, branche `main`, dossier `/ (root)`.
4. L'adresse est `https://<pseudo>.github.io/<nom-du-depot>/`
   — pas `https://<pseudo>.github.io/` tout court, qui ne répond que si un dépôt
   `<pseudo>.github.io` existe.

Compter une à deux minutes après chaque push avant que la page se rafraîchisse.

---

## Les icônes

La page fonctionne **sans** le dossier `icons/` : chaque sort a un pictogramme dessiné
à la main en SVG qui s'affiche par défaut. Quand une icône officielle est présente, elle
remplace le pictogramme partout où ce sort est cité — et **si le fichier est absent, la
page garde le pictogramme** au lieu d'afficher une image cassée. Vous pouvez donc
remplir le dossier progressivement.

### Où ça se règle

Tout en bas d'`index.html`, dans le bloc `SKILL_ICONS`. Une ligne par sort :

```js
"overhead-slam":  "icons/Overhead%20Slam.png",
```

Pour changer une icône : remplacer le fichier, ou modifier le chemin. Pour en désactiver
une : mettre `""`.

### Les 35 fichiers, vérifiés

Tous présents, tous en PNG 256×256, et **tous contrôlés image par image** contre les
vignettes du planner : chaque fichier porte bien l'icône du sort dont il a le nom.

**Actifs (12)** — `Keen Strike`, `Rending Blow`, `Leaping Slam`, `Mocking Blade`,
`Overhead Slam`, `Sword Aura Rampage`, `Ankle Slice`, `Crushing Wave`, `Rush Strike`,
`Aerial Snare`, `Ruinous Blow`, `Defiance`

**Passifs (10)** — `Survival Stance`, `Protection Armor`, `Blood Absorption`,
`Identify Weakness`, `Attack Preparation`, `Impact Hit`, `Destructive Impulse`,
`Experienced Counterstrike`, `Survival Willpower`, `Murderous Burst`

**Stigmas (13)** — `Wrath Wave`, `Lunge Stance`, `Zikel's Blessing`, `Focused Block`,
`Armor of Balance`, `Blade Toss`, `Tenaciousness`, `Lifestealing Blade`, `Rage Burst`,
`Wave Armor`, `Forced Restraint`, `Assault Strike`, `Fracturing Rush`

> Les noms de fichiers contiennent des **espaces**, et le code les échappe en `%20`
> (`icons/Overhead%20Slam.png`). `Zikel's Blessing.png` devient
> `icons/Zikel%27s%20Blessing.png`. C'est normal, ne pas « corriger » en enlevant les
> échappements : sans eux, GitHub Pages ne sert pas les fichiers.

### Si vous renommez un fichier

Modifier le chemin dans `SKILL_ICONS`, pas la clé de gauche. La clé (`"overhead-slam"`)
est ce qui relie l'icône aux 194 endroits où ce sort est cité dans la page ; le chemin de
droite est la seule chose qui doit suivre vos fichiers.

---

## Bon à savoir

**Les checklists du chapitre 17** se cochent et restent cochées, mais c'est stocké dans
le navigateur du lecteur, sur sa machine à lui. Chacun a la sienne, et vous ne voyez pas
celles des autres.

**Le thème** suit le réglage clair/sombre du système. On peut le forcer en ajoutant
`data-theme="dark"` ou `data-theme="light"` sur la balise `<html>`.

**Sans JavaScript**, la page reste entièrement lisible : sommaire, chapitres et tableaux
s'affichent normalement. Seuls l'animation d'apparition, la barre de progression et les
checklists demandent JS.

---

## Ce que le guide dit de lui-même

Trois choses à connaître avant de le partager, parce qu'elles sont assumées dans le
texte plutôt que cachées :

- **La classe n'a pas été jouée par l'auteur.** C'est une compilation vérifiée, pas un
  retour d'expérience — contrairement au guide Assassin. Le chapitre 2 expose la méthode
  et les quatre niveaux de fiabilité utilisés.
- **Six désaccords entre sources sont documentés** au chapitre 18, avec ce que dit chaque
  camp et l'arbitrage retenu. Le nombre de slots de stigma n'est volontairement pas tranché.
- **Le chapitre 12 (macro) est incomplet** et le dit : la seule vidéo qui la détaille
  n'a pas pu être transcrite.

---

## Mettre à jour après la sortie

Les points à reprendre en priorité une fois les serveurs ouverts sont listés à la fin de
l'annexe. Les plus structurants :

1. Le nombre réel de slots de stigma (chapitres 8 et 18).
2. Si un sort au niveau 8, avec un seul node, peut aller chercher sa cinquième option
   (chapitres 4 et 9).
3. Les noms français officiels du kit, si la version globale les traduit.

---

Habillage graphique original. Les icônes de compétences sont celles du jeu ;
AION 2 et ses visuels sont la propriété de NCSOFT Corporation.
