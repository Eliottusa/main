# Changelog

## [2.1.0] — 2025-06-10
### Ajouté
- Cache météo in-memory (dure enviro,n 60s)
- Champ `carbon_footprint_g` dans la réponse
- Endpoint `GET /health` ajouté

### Modifié
- `calculate_best_route` nous retourne donc3 valeurs `(transport, durée, co2)`
- Erreur `503` explicite si le service météo est injoignable; avertissement pour l'utilisateur

## [2.0.0] — 2025-04-15
### Ajouté
- Authentification avec  clé API (`verify_api_key`) breaking change
- Support de Lyon dans le simulateur météo

### Modifié
- Refactorisation async/await
- Route renommée `/route` → `/api/v1/route`

### Supprimé
- Endpoint `/route` non versionné 

## [1.0.0] — 2025-01-20
- Version initiale : recommandation de transport via météo et trafic simulés
