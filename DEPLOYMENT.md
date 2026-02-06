# Déploiement du Dashboard sur Streamlit Cloud

## Étapes pour publier votre dashboard en public

### 1. **Préparer le repository GitHub**
- Poussez votre code sur GitHub (s'il ne l'est pas déjà)
- Assurez-vous que le repository contient :
  - `streamlit_app.py` (fichier principal)
  - `requirements.txt` (dépendances)
  - `data/` (dossier avec les données)
  - `.streamlit/config.toml` (configuration)

```bash
git add .
git commit -m "Préparation pour déploiement"
git push origin main
```

### 2. **Déployer sur Streamlit Cloud**

**Option A : Via l'interface Streamlit Cloud (Recommandée - Plus simple)**

1. Allez sur https://share.streamlit.io/
2. Cliquez sur **"New app"**
3. Connectez-vous avec votre compte GitHub
4. Sélectionnez :
   - Repository : `gdp-dashboard`
   - Branch : `main`
   - Main file path : `streamlit_app.py`
5. Cliquez sur **"Deploy"**

**Option B : Via la CLI (Ligne de commande)**

```bash
pip install streamlit
streamlit deploy
```

### 3. **URL publique générée**

Après le déploiement, vous recevrez une URL publique de la forme :
```
https://share.streamlit.io/Alexis2mlt/gdp-dashboard/main/streamlit_app.py
```

Cette URL sera accessible publiquement ! 🌍

### 4. **Partager votre dashboard**
- Partagez le lien unique avec vos collègues
- Le dashboard se met à jour automatiquement à chaque `push` sur GitHub

## Alternatives de déploiement

### **Heroku** (Gratuit mais limité)
1. Créez un compte sur https://www.heroku.com/
2. Créez une application
3. Connectez GitHub et sélectionnez votre repo
4. Ajoutez un fichier `Procfile` :
```
web: streamlit run streamlit_app.py --server.port=$PORT --server.address=0.0.0.0
```

### **Railway.app** (Gratuit et rapide)
1. Connectez votre GitHub sur https://railway.app/
2. Sélectionnez ce projet
3. L'URL publique est générée automatiquement

### **Replit** (Gratuit avec lien public)
1. Importez votre GitHub repo
2. Installez les dépendances
3. Lancez `streamlit run streamlit_app.py`

## Configuration de domaine personnalisé

Si vous avez un domaine personnalisé :
- **Streamlit Cloud** : Accédez à "Settings" > "Custom Domain"
- **Autres plateformes** : Configurez les enregistrements DNS

## Troubleshooting

**Le dashboard demande de l'authentification ?**
- Streamlit Cloud ne demande rien par défaut
- Vérifiez que le repo est public

**Les données ne se chargent pas ?**
- Assurez-vous que le chemin `data/gdp_data.csv` est correct dans `streamlit_app.py`

**L'app s'arrête après quelques secondes ?**
- Vérifiez les logs de déploiement pour les erreurs
- Assurez-vous que toutes les dépendances sont dans `requirements.txt`
