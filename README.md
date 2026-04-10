# Espace de travail personnel — Business, Organisation & Conseils

Environnement de travail personnel propulsé par Claude Code, orienté business, organisation et conseils.
Les skills permettent de mener des interviews structurées et de produire des livrables directement depuis le terminal.

---

## Prérequis

- Un compte Claude Pro, Max, Teams ou Enterprise
- Claude Code installé sur ta machine
```bash
curl -fsSL https://claude.ai/install.sh | bash
claude --version
```

---

## Structure du projet
```
.
├── CLAUDE.md                        ← contexte et règles globales pour Claude Code
├── README.md
├── .claude/
│   └── skills/                      ← skills disponibles en slash commands
│       ├── grill-me/
│       │   └── SKILL.md
│       └── soft-skills-eval/
│           ├── SKILL.md
│           ├── referentiel-france-travail.md
│           └── referentiel-world-economic-forum.md
├── livrables/                       ← fichiers générés (ignorés par git)
└── notes/                           ← notes de travail brutes
```

---

## Utilisation des skills

Lance Claude Code depuis la racine du projet :
```bash
claude
```

### `/grill-me`

Interview méthodique pour challenger un plan ou une conception.
Claude parcourt chaque branche de l'arbre de décision et fournit sa recommandation pour chaque question.
```
> /grill-me
```

### `/soft-skills-eval`

Évalue les soft skills professionnels adaptés à une activité donnée, en s'appuyant sur deux référentiels croisés :
- **France Travail** — 16 savoir-être professionnels
- **World Economic Forum** — Future of Jobs 2025 (10 compétences)

Deux modes d'entrée :
- **Interview** — Claude pose 10 à 15 questions une par une
- **Fiche de poste** — colle directement une fiche de poste, Claude extrait les informations automatiquement

Claude produit :
- un tableau consolidé avec origine de chaque compétence (FT / WEF / FT+WEF / FT≈WEF)
- un top 5 des compétences critiques avec cas d'usage concrets et pistes de développement
- les angles morts à surveiller
- un fichier de restitution dans `livrables/`

```
> /soft-skills-eval
```

---

## Ajouter un skill

Crée un dossier dans `.claude/skills/` avec un fichier `SKILL.md` :
```
.claude/skills/
└── nom-du-skill/
    └── SKILL.md
```

Format du fichier `SKILL.md` :
```markdown
---
name: nom-du-skill
description: Description courte — quand utiliser ce skill.
---

Instructions détaillées pour Claude...
```

Le skill est immédiatement disponible comme `/nom-du-skill` dans toute session Claude Code lancée depuis ce projet.
