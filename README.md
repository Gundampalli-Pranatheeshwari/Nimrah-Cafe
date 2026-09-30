# Nimrah Cafe & Bakery

Full-stack cafe ordering platform: HTML/CSS/JavaScript + Node.js/Express + MySQL + Flutter client.

## 1. Requirements
- Node.js 18+
- MySQL 8+
- Flutter 3+

## 2. Database
Run `database/schema.sql`, then `database/seed.sql` in MySQL.

## 3. Backend
Copy `.env.example` to `.env`, set DB credentials and JWT secret, then:
```bash
npm install
npm run dev
```
API: `http://localhost:5000/api`
Website: `http://localhost:5000`

The first admin can be created with `POST /api/auth/register` and then promoted with SQL:
`UPDATE users SET role='admin' WHERE email='admin@example.com';`

## 4. Frontend
The Express server serves `frontend/` directly. Open `/`.

## 5. Flutter
```bash
cd mobile
flutter pub get
flutter run
```
Set `ApiService.baseUrl` to your machine's LAN IP for a physical device, e.g. `http://192.168.1.10:5000/api`.

## 6. API
GET `/api/products`, GET `/api/products/:id`, GET `/api/categories`, GET `/api/offers`, POST `/api/orders`, POST `/api/contact`.
Admin endpoints use `Authorization: Bearer <JWT>`.

## 7. Production
Use HTTPS behind Nginx, strong secrets, managed MySQL, object storage/CDN for images, backups, monitoring, and a real payment provider. Never commit `.env`.
