## Architecture

```
ecoride-api/
├── main.py              # Point d'entrée, définition des routes FastAPI
├── requirements.txt     # Dépendances Python
├── docs/
│   ├── architecture.md  # Schéma d'architecture et flux de données
│   ├── api-reference.md # Référence complète des endpoints
│   └── sequence.md      # Diagrammes de séquence
├── README.md
└── CHANGELOG.md
```

Voir [docs/architecture.md](./docs/architecture.md) pour le détail des composants.

---

## Documentation technique

| Document | Description |
|---|---|
| [API Reference](./docs/api-reference.md) | Endpoints, paramètres, codes d'erreur |
| [Architecture](./docs/architecture.md) | Composants, flux de données, dépendances |
| [Diagramme de séquence](./docs/sequence.md) | Flux d'appel complet de `/api/v1/route` |
| [CHANGELOG](./CHANGELOG.md) | Historique des versions |

---