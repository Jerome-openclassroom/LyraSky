# 🌩️ Workflow d’Extraction de Données Météorologiques – Make + OpenAI + Google Sheets

Ce dépôt documente un workflow d’automatisation pleinement opérationnel conçu pour extraire des données météorologiques à partir d’un bulletin météo librement rédigé et remplir un Google Sheet avec des valeurs structurées.  
Le workflow est propulsé par l’API Assistants d’OpenAI et implémenté sur la plateforme Make.

---

## 🧠 Vue d’ensemble

Ce pipeline permet de :  
1. Déclencher le système manuellement via un webhook (ex. avec Postman).  
2. Récupérer le texte brut du bulletin météo depuis un Google Document.  
3. Envoyer le contenu à un Assistant OpenAI via `message an assistant`.  
4. Parser le JSON structuré renvoyé par l’Assistant.  
5. Injecter les données météo structurées dans un Google Sheet.  

---

## 🔧 Pile technique

- **Make (Integromat)** : orchestration du scénario, modules webhook, Docs, OpenAI, JSON, Sheets.  
- **Assistant OpenAI (gpt-4-0613)** : extraction texte → JSON via instruction système personnalisée.  
- **Google Docs** : contient le bulletin météo brut.  
- **Google Sheets** : reçoit les données météo nettoyées et parsées.  
- **Postman** : utilisé pour envoyer des webhooks de test et simuler des appels externes.  

---

## 🧩 Modules du workflow

1. **Webhook manuel**  
   Simule un déclencheur de rapport météo entrant (ex. depuis un système de prévision ou un opérateur).  
2. **Google Docs : Get Document Content**  
   Récupère le texte du bulletin depuis un Google Document spécifique.  
3. **OpenAI Assistant (Message an Assistant)**  
   Envoie le texte à un assistant GPT-4 configuré avec des instructions système précises.  
4. **JSON Parser**  
   Convertit la sortie structurée en paires clé-valeur.  
5. **Google Sheets : Add Row**  
   Enregistre les paramètres météo extraits dans un tableur.  

---

## 🔍 Paramétrage de l’Assistant

- **Modèle** : `gpt-4-0613`  
- **Top P** : 0,69  
- **Température** : 0,66  

---

## ✅ Exemple de sortie (champs Google Sheet)

| Ville    | Heure (UTC) | Temp (°C) | Vent  | Humidité (%) | Pression (hPa) | Observations visuelles                               | Phénomènes météorologiques        | Commentaire                                                               |
|----------|-------------|-----------|-------|---------------|----------------|------------------------------------------------------|-----------------------------------|---------------------------------------------------------------------------|
| Avignon  | 9h          | 21        | calme | 57            | 1010           | cumulonimbus menaçants NW, congestus, cumulus       | goutte froide, marais barométrique | risque orageux accru dans la journée d’après la croissance verticale visible |

---

## 📁 Structure du dépôt

```
Workflow_Météo/
├── README.md                 # Documentation principale (version anglaise)
├── README_fr.md              # Documentation en français
│
├── screenshots/              # Captures d’écran du workflow et des sorties
│   ├── Google_sheet_data.jpg       # Sortie structurée dans Google Sheet
│   ├── OpenAI_platform.jpg         # Configuration de l’assistant OpenAI (modèle, température, top_p)
│   ├── Weather_comment.jpg         # Exemple d’analyse météo générée
│   └── Workflow_Make_assistant_IA.jpg # Diagramme du workflow Make.com (webhook → assistant → sortie)
│
└── system_instruction/       # Prompt système et configuration du parsing
    └── system_instruction.txt     # Prompt système complet (parsing + formatage)
└── code/       # code et blueprints
    └── Integration Webhooks.blueprint.json    #  blueprint pour reproduire le Workflow


```

---

## 🎯 Objectif

Ce workflow fait partie d’un projet plus large visant à automatiser l’interprétation des données environnementales via des assistants IA.  
Il sert de prototype pour :  
- Une **intégration LLM fluide dans des pipelines météo réels**  
- Une utilisation en **éducation scientifique**, **météorologie opérationnelle** ou **science citoyenne**  
- De futurs **routines de parsing environnemental compatibles AGI**  

---

## 🧠 Auteur

**Jérôme Frasson (Jerome-X1)**  
Explorateur de la cognition post-AGI & des systèmes écologiques  
📫 jerome.frasson.vsi@gmail.com  
🔗 [GitHub – Jerome-X1]

---
