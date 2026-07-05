# Cursor-chat-gpt

Dépôt minimal pour utiliser **Cursor** comme un **chat type ChatGPT** — sans code, sans contexte de projet, sans dérive vers l'édition de fichiers.

> Ce README est destiné aux visiteurs GitHub. Il n'est **pas** injecté dans le contexte Cursor (voir `.cursorignore`).

---

## Principe

Ce repo ne contient presque rien : une règle Cursor (`.cursor/rules/Ask.mdc`) et un `.cursorignore` qui masque tout le reste. Quand vous ouvrez ce dossier dans Cursor, l'assistant se comporte comme un chat conversationnel — pas comme un agent de développement.

---

## Installation

```bash
git clone https://github.com/daugier/Cursor-chat-gpt.git
cd Cursor-chat-gpt
```

Ouvrir le dossier dans **Cursor** : `File → Open Folder…` → sélectionner `Cursor-chat-gpt`.

---

## Réglages Cursor recommandés

### 1. Mode de chat : **Ask**

Utilisez le mode **Ask** (pas Agent) pour une conversation proche de ChatGPT. Le mode Agent cherchera à modifier des fichiers ; ce n'est pas l'objectif ici.

### 2. Ouvrir uniquement ce dossier

Travaillez dans un workspace **limité à ce repo**. N'ouvrez pas un monorepo ou un autre projet en parallèle — sinon Cursor injectera du contexte indésirable.

### 3. Vérifier les règles du projet

Les règles sont dans `.cursor/rules/Ask.mdc` (`alwaysApply: true`). Elles imposent notamment :

- réponses en **français** ;
- ton conversationnel, sans todo list ni plan d'action automatique ;
- **pas d'outils par défaut** (pas d'exploration du repo, pas de terminal) ;
- recherche web **uniquement** si nécessaire (faits récents, ou demande explicite).

Si le comportement ne correspond pas : `Cursor Settings → Rules` et vérifier que les **Project Rules** sont actives pour ce workspace.

### 4. `.cursorignore`

Le fichier ignore tout (`*`) sauf `.cursor/rules/`. Conséquence :

- aucun fichier parasite dans le contexte ;
- ce `README.md` n'est **pas** lu par Cursor — c'est voulu.

Ne retirez pas le `*` global sauf si vous savez ce que vous faites.

### 5. Modèle

Choisissez le modèle qui vous convient dans le sélecteur de chat. Pour du brainstorming ou des questions générales, un modèle rapide suffit ; pour de l'analyse technique fine, prenez un modèle plus capable.

### 6. Nouveau chat

Démarrez un **nouveau chat** (`Ctrl+L` / `Cmd+L`) quand vous changez de sujet — l'historique long peut brouiller les réponses.

---

## Conseils pratiques

| Situation | Conseil |
|-----------|---------|
| Réponse trop « développeur » (code, fichiers, étapes) | Rappeler : *« réponds en mode conversation, sans outils »* |
| Besoin d'infos à jour | Demander explicitement : *« cherche sur le web »* ou `@web` |
| Sujet sans lien avec la tech | Fonctionne très bien — c'est le but |
| Veut coder pour de vrai | Ouvrir un **autre** repo, pas celui-ci |
| Règles ignorées | Vérifier que le dossier ouvert est bien la racine de ce clone |

---

## Contenu du dépôt

```
Cursor-chat-gpt/
├── .cursor/
│   └── rules/
│       └── Ask.mdc      ← règles de comportement (lu par Cursor)
├── .cursorignore        ← masque tout sauf les règles
└── README.md            ← ce fichier (lu par les humains sur GitHub)
```

---

## Modifier le comportement

Éditez `.cursor/rules/Ask.mdc` si vous voulez ajuster le ton, la langue ou la politique de recherche web. Commitez et poussez vos changements sur votre fork si besoin.

---

*Usage personnel · partagé tel quel · aucune garantie*
