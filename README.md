# Cheatsheet Markdown — prête à l’emploi (GitHub Pages / Jekyll)

> Tout ce qu’il te faut pour écrire vite et propre dans des fichiers `.md`. Compatible GitHub Pages (Jekyll + kramdown) et GitHub.

## Front matter (en-tête YAML pour les pages du site)
```md
---
layout: single         # gabarit
title: "Titre de la page"
permalink: /ma-page/   # URL finale
author_profile: false  # pas de colonne auteur (Minimal Mistakes)
sidebar: null          # pas de sidebar
classes: wide          # colonne plus large
toc: false             # ou true si tu veux un sommaire automatique (thème)
---
```

## Titres, emphase, code, citation
```md
# Titre H1
## Titre H2
### Titre H3

Texte **gras**, *italique*, ~~barré~~, `code inline`.

> Citation, avec évent. plusieurs lignes
> et un rendu distinct.
```

## Listes
```md
- Puce 1
- Puce 2
  - Sous-puce

1. Étape 1
2. Étape 2
```

## Liens & images
```md
[Lien inline](https://exemple.com)
[Lien de référence][id]
[id]: https://exemple.com "Titre"

![Texte alternatif](/assets/img.png "Titre (optionnel)")
[![Alt](/assets/vignette.png)](https://exemple.com)  # image cliquable

<!-- HTML si tu veux contrôler la taille -->
<img src="/assets/img.png" alt="Alt" width="420">
```

## Sauts de ligne & séparateurs
```md
Ligne 1··
Ligne 2  ← (deux espaces à la fin pour un vrai retour à la ligne)

---
```

## Blocs de code (avec coloration)
<pre><code>```python
def f(x):
    return x**2
```</code></pre>

## Tableaux (alignements)
```md
| Colonne | Droite | Centre |
|--------|-------:|:------:|
| A      |    123 |  milieu |
| B      |     45 |  67     |
```

## Listes de tâches (checkboxes)
```md
- [x] Fait
- [ ] À faire
```

## Notes de bas de page
```md
Du texte avec une note[^1] dans la phrase.

[^1]: Détail de la note en bas de page.
```

## Définitions, abréviations (kramdown / Jekyll)
```md
Terme
: Définition du terme (peut contenir du **Markdown**).

*[HTML]: HyperText Markup Language
```

## Exposants / indices (kramdown)
```md
E = mc^2^
H~2~O
```

## Ancrages & liens internes
```md
## Section utile {#section-utile}

Aller vers la [section utile](#section-utile).
```

## Classes & IDs sur des éléments (kramdown)
```md
**Important**{: .rouge}  <!-- applique une classe CSS au texte -->

> Bloc mis en avant
{: .surligne }            <!-- applique une classe au bloc précédent -->
```
*Définis les classes dans un CSS global (ex. `_includes/head/custom.html`).*

## HTML inline (pratique pour surligner/couleur)
```md
Du texte <mark>mis en évidence</mark> et
<span style="color:#e11d48">en rouge</span>.
```

## Math (si MathJax est inclus dans ton layout)
```md
Inline : \( a^2 + b^2 = c^2 \)

Bloc :
$$
\forall\,G,\ |G|\ \text{premier} \Rightarrow G \simeq \mathbb{Z}/|G|\mathbb{Z}.
$$
```

## Images locales & PDF (conseil de structure)
- Mets tes PDF dans `files/` → lien : `[Mon PDF](/files/monfichier.pdf)`
- Mets tes images dans `assets/` → `![Alt](/assets/photo.jpg)`

## Échappements utiles
```md
\*affiche un astérisque\*, \_un underscore\_, \`backticks\`, \[crochets\]
```

## Sommaire (selon thème Minimal Mistakes)
Dans le front matter :
```yaml
toc: true
toc_label: "Sommaire"
toc_sticky: false
```

## Liquid/Jekyll (petit rappel pratique)
```md
<!-- URL relative au site, robuste -->
[CV]({{ "/files/cv.pdf" | relative_url }})

<!-- Variables utiles -->
Site : {{ site.title }} — URL : {{ site.url }}
```

## Raccourcis typiques “page simple”
**Créer une nouvelle page** dans `_pages/ma-page.md` :
```md
---
layout: single
title: "Ma page"
permalink: /ma-page/
author_profile: false
sidebar: null
classes: wide
---
Contenu **Markdown** avec [lien](/files/cv.pdf), image ![](/assets/img.png) et équation \( e^{i\pi}+1=0 \).
```

---

### Mini-CSS prêt à coller (si tu veux 3 classes utiles)
Crée `_includes/head/custom.html` :
```html
<style>
.rouge{color:#dc2626}
.surligne{background:#fff3b0;padding:0 .2em;border-radius:.2em}
.note{font-size:.95em;color:#475569}
</style>
```
