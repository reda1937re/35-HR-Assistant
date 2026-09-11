# 35-HR-Assistant

Assistant RH interne. Backend Flask (`rhAgent.py`) exposant des endpoints `/chat`, `/text` et d'approbation de congés, adossé à une équipe de 3 agents IA (solde/demandes de congés, affectations projet, traitement des approbations) qui lisent/écrivent dans Airtable, envoient des emails d'approbation aux RH, et exposent le flux d'approbation publiquement via un tunnel ngrok. `app.py` est une interface de chat Streamlit séparée qui appelle l'API Flask `/chat` par identifiant employé.

## Tech stack

Flask, flask-cors, streamlit, agno (Agent, Team, OpenAIChat, FileTools, CalculatorTools, EmailTools, SqliteStorage), pyairtable, pyngrok, requests, python-dotenv

## Lancer le projet

```bash
pip install -r requirements.txt
```

Créer un `.env` avec `OPENAI_API_KEY`, `AIRTABLE_TOKEN`, `AIRTABLE_BASE_ID`, `NGROK_AUTH_TOKEN`, `HR_EMAIL`

```bash
python rhAgent.py        # backend Flask (port 5000) + tunnel ngrok
streamlit run app.py     # interface de chat (dans un autre terminal)
```
