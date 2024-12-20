// .gitignore
node_modules/
.env
.DS_Store
dist/
build/
*.log
database/*.db

// README.md
# Portal Firmowy z Integracją SharePoint

Portal do zarządzania formularzami firmowymi z integracją SharePoint.

## Wymagania
- Node.js (wersja LTS)
- npm lub yarn
- Git

## Szybki start

1. Klonowanie repozytorium:
```bash
git clone https://github.com/twoja-nazwa/portal-firmowy.git
cd portal-firmowy
```

2. Instalacja zależności:
```bash
# Frontend
cd frontend
npm install

# Backend
cd ../backend
npm install
```

3. Konfiguracja:
- Skopiuj `.env.example` do `.env`
- Uzupełnij zmienne środowiskowe

4. Uruchomienie:
```bash
# Terminal 1 - Frontend
cd frontend
npm run dev

# Terminal 2 - Backend
cd backend
npm run dev
```

## Dokumentacja
Pełna dokumentacja znajduje się w katalogu `/docs`.

## Licencja
MIT

// .env.example
NODE_ENV=development
PORT=3000
SP_USERNAME=uzytkownik@firma.com
SP_PASSWORD=haslo
DB_PATH=../database/portal.db

// package.json (główny)
{
  "name": "portal-firmowy",
  "version": "1.0.0",
  "private": true,
  "workspaces": [
    "frontend",
    "backend"
  ],
  "scripts": {
    "dev": "concurrently \"npm run dev:frontend\" \"npm run dev:backend\"",
    "dev:frontend": "cd frontend && npm run dev",
    "dev:backend": "cd backend && npm run dev",
    "build": "cd frontend && npm run build",
    "start": "cd backend && npm start"
  },
  "devDependencies": {
    "concurrently": "^8.0.1"
  }
}