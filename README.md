# Brandyali — MVP

Plateforme web qui connecte créateurs de marques de vêtements et prestataires textiles locaux.

## Prérequis
- Node.js
- MongoDB local ou distant

## Installation
1. Backend
   - `cd backend`
   - `npm install`
2. Config
   - Copier `backend/.env.example` vers `backend/.env`
   - Renseigner `MONGO_URI` et `JWT_SECRET`

## Seed des prestataires
- `node backend/scripts/seed.js`
- Réinitialiser: `node backend/scripts/seed.js --reset`

## Lancer en local (un seul serveur)
1. Démarrer MongoDB
2. Lancer l'API:
   - `cd backend`
   - `npm run dev`
3. Ouvrir:
   - `http://localhost:4000`

Les fichiers frontend sont servis par Express depuis `frontend/pages`.
Les appels API se font sur `/api`.

## Endpoints principaux
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/users/me`
- `GET /api/providers`
- `GET /api/providers/:id`
- `POST /api/requests`

## Tests manuels MVP
1. Inscription valide (créateur + prestataire)
2. Inscription avec email déjà utilisé
3. Inscription avec champ vide
4. Connexion valide
5. Connexion invalide
6. Liste prestataires accessible
7. Détail prestataire (id valide)
8. Détail prestataire (id invalide) -> 404
9. Envoi demande en tant que créateur
10. Envoi demande sans token -> 401
11. Envoi demande avec prestataire -> 403
12. Envoi demande sans message -> 400

