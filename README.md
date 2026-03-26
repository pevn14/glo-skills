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
├── CLAUDE.md                  ← contexte et règles globales pour Claude Code
├── README.md
├── .claude/
│   └── commands/              ← skills disponibles en slash commands
│       ├── grill-me.md
│       └── soft-skills-eval.md
├── livrables/                 ← fichiers générés (md, docx)
└── notes/                     ← notes de travail brutes
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
> /grill-me voici mon plan : ...
```

### `/soft-skills-eval`

Évalue les 16 savoir-être professionnels du référentiel France Travail adaptés à une activité donnée.
Claude mène une interview puis produit :
- un tableau d'évaluation de chaque savoir-être (note 0 à 5)
- un top 5 des savoir-être critiques avec cas d'usage concrets
- les angles morts à surveiller
- un fichier de restitution dans `livrables/` (format md ou docx au choix)
```
> /soft-skills-eval
```

---

## Ajouter un skill

Crée un fichier `.md` dans `.claude/commands/` avec le format suivant :
```markdown
---
name: nom-du-skill
description: Description courte — quand utiliser ce skill.
---
Instructions détaillées pour Claude...
```

Le skill est immédiatement disponible comme `/nom-du-skill` dans toute session Claude Code lancée depuis ce projet.