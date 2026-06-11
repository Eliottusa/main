# README du TP Documentation "EcoRide"

Ce Projet, nommé "Ecoride" est tout simplement une API de recommandation de transport écoresponsable. Elle analyse en temps réel les conditions météorologiques et le traffic urbain afin d'optimiser le trajet, le tout en minimisant l'empreinte carbone!

## Pré-requis:

- Python **3.10+**
- pip **22+**

## Installation et mise en service de l'API

```bash
# 1. Cloner le dépôt
git clone https://github.com/votre-org/ecoride-api.git
cd ecoride-api

# 2. Créer l'environnement virtuel
python -m venv .venv

##Linux:
source .venv/bin/activate  

## Windows: 
source .venv\Scripts\activate

# 3. Installer les dépendances
pip install -r requirements.txt
```

## Démarrage rapide 

```bash
# Lancer le serveur de développement
uvicorn main:app --reload --port 8000
```

L'API est donc accessible sur `http://localhost:8000`.  
La documentation interactive Swagger est disponible sur `http://localhost:8000/docs`.

---


## Utilisation

### Vérifier l'état du service

```bash
curl http://localhost:8000/health
```

```json
{
  "status": "healthy",
  "timestamp": 1718100000.0
}
```

## Endpoints

| Méthode | Route | Auth | Description |
|---|---|---|---|
| GET | `/health` | Non | Statut du service |
| POST | `/api/v1/route` | Oui | Recommandation de trajet |

## GET /health

Vérifie l'état du service. Non protégé.

**Réponse 200 :**

```json
{ "status": "healthy", "timestamp": 1718100000.0 }
```

---

## POST /api/v1/route

Retourne la recommandation de transport optimale. **Authentification requise.**

**Corps de la requête :**

| Champ | Type | Description |
|---|---|---|
| `user_id` | string | Identifiant utilisateur |
| `city` | string | Ville de départ (ex : `"Paris"`, `"Lyon"`) |
| `destination` | string | Destination souhaitée |

**Réponse 200 :**

| Champ | Type | Description |
|---|---|---|
| `recommended_transport` | string | Mode de transport recommandé |
| `estimated_time_minutes` | integer | Durée estimée en minutes |
| `weather_condition` | string | Météo détectée (`Soleil`, `Pluie`, `Nuageux`) |
| `carbon_footprint_g` | float | Empreinte carbone en grammes de CO₂ |

**Codes d'erreur :**

| Code | Cause |
|---|---|
| `401` | Token invalide ou absent |
| `422` | Corps de requête invalide |
| `503` | Service météo indisponible |