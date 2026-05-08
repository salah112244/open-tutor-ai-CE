# Guide d'installation sur Windows (Environnement Natif)

> Contribution par : Yassine EL BAITE & Salaheddine EL QUATLLI  
> Stagiaires CRMEEF Agadir — 2024/2025

## Prérequis

- Windows 10/11 64-bit
- Git : https://git-scm.com/downloads
- Python 3.11 : https://www.python.org/downloads/release/python-3110/
- Conda (Miniconda) : https://docs.conda.io/en/latest/miniconda.html
- Node.js v18+ : https://nodejs.org/

## Étape 1 — Cloner le projet

```bash
git clone https://github.com/Open-TutorAi/open-tutor-ai-CE.git
cd open-tutor-ai-CE
```

## Étape 2 — Backend

```bash
cd backend
conda create -n tutorai-env python=3.11 -y
conda activate tutorai-env
pip install -r requirements.txt
python -m uvicorn open_tutorai.main:app --reload --host 0.0.0.0 --port 8080
```

## Étape 3 — Frontend

Ouvre un deuxième terminal :

```bash
cd open-tutor-ai-CE
npm install
npm run dev
```

## Étape 4 — Correction vite.config.ts

Dans `vite.config.ts`, remplace :target: 'http://open-tutor-backend:8080'
par :target: 'http://localhost:8080'



## Accès

- Frontend : http://localhost:5173
- Backend : http://localhost:8080

## Dépannage

| Erreur                   |Solution |
|--------                  |----------|
| Python 3.10 incompatible | Utiliser Python 3.11 obligatoirement |
| Backend Required error   | Corriger vite.config.ts |
| conda non reconnu        | Utiliser Anaconda Prompt |
