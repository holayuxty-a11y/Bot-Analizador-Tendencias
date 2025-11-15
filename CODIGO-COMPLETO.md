# 🚀 CODIGO COMPLETO COPY-PASTE

## INSTRUCCIONES:

1. Clonar repo
2. En terminal: `npm init -y`
3. Crear archivos abajo con contenido
4. `npm install` (instala dependencias de package.json)
5. `npm run setup` (crea base de datos)
6. `npm start` (inicia bot)

---

## ARCHIVO 1: package.json

Copia TODO el contenido abajo y pégalo en archivo `package.json` en raiz del proyecto:

```json
{
  "name": "bot-analizador-tendencias",
  "version": "1.0.0",
  "description": "Bot para analizar productos virales",
  "main": "server.js",
  "scripts": {
    "start": "node server.js",
    "setup": "node setup-db.js",
    "dev": "nodemon server.js"
  },
  "dependencies": {
    "express": "^4.18.2",
    "pg": "^8.11.3",
    "dotenv": "^16.3.1",
    "axios": "^1.6.5",
    "node-cron": "^3.0.3",
    "nodemailer": "^6.9.7",
    "cors": "^2.8.5",
    "helmet": "^7.1.0",
    "winston": "^3.11.0",
    "body-parser": "^1.20.2"
  }
}
```

---

## ARCHIVO 2: .env

Renombra `.env.example` a `.env` Y EDITA con TUS VALORES:

```env
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=tu_contraseña_postgresql
DB_NAME=bot_tendencias

OPENAI_API_KEY=sk-tu_openai_key
SMTP_USER=tu_email@gmail.com
SMTP_PASSWORD=tu_app_password

PORT=3000
NODE_ENV=development
```

---

## ARCHIVO 3: setup-db.js

Ver link en repositorio o crear manualmente.

**IMPORTANTE**: Ejecuta: `npm run setup` para crear tablas

---

## ARCHIVO 4: server.js (SIMPLIFICADO)

Ver repositorio o descargar de GitHub.

Luego: `npm start`

---

## PASOS SETUP FINAL:

### 1. Instalar PostgreSQL
https://www.postgresql.org/download/

### 2. Crear BD
```bash
psql -U postgres
CREATE DATABASE bot_tendencias;
\\q
```

### 3. Clonar Repo
```bash
git clone https://github.com/holayuxty-a11y/Bot-Analizador-Tendencias.git
cd Bot-Analizador-Tendencias
```

### 4. Setup
```bash
npm install
copy .env.example .env  # (editar con tus credenciales)
npm run setup
```

### 5. EJECUTAR
```bash
npm start
```

✅ Bot corriendo en http://localhost:3000

---

## TESTEAR API:

```bash
curl http://localhost:3000/api/health
curl http://localhost:3000/api/productos
curl http://localhost:3000/api/productos-rentables
```

✅ Si ves datos JSON = TODO OK!

---

Para ver el código completo de cada archivo, ve a:
https://github.com/holayuxty-a11y/Bot-Analizador-Tendencias
