# Vigie Centre d'Appel

Centre d'appel interne pour C.T Informatique, séparé de Vigie Billets mais partageant sa base de données (employés) et son jeton de connexion (même `JWT_SECRET`).

## Phase 1 (en place)

- Appels internes entre employés, voix de poste à poste (WebRTC), aucun serveur média
- Clavier numérique avec postes personnalisés par employé, sonnerie et musique d'attente (fichier audio, licence CC BY-SA, crédit dans index.html)
- Mise en attente et transfert d'appel

## Phase 2 (pas commencée)

- Ligne téléphonique externe réelle via un fournisseur de voix infonuagique (Telnyx), pour recevoir des appels de l'extérieur
- Files d'attente, création automatique de billets à partir d'un appel

## Technique

- Node.js + Express, PostgreSQL (`tickets_db`, partagée avec Vigie Billets)
- Port 3504 (HTTP), 3505 (HTTPS - certificat via `generer-certificat-https.ps1`, requis pour l'accès au micro hors `localhost`)
- Pas encore d'installateur (déploiement manuel pour l'instant)
