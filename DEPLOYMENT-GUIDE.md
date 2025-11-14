# 🚀 DEPLOYMENT GUIDE - BOT ANALIZADOR DE TENDENCIAS

## ⚡ QUICK START (5 MINUTOS)

### Paso 1: Clonar Repositorio

```bash
git clone https://github.com/holayuxty-a11y/Bot-Analizador-Tendencias.git
cd Bot-Analizador-Tendencias
```

### Paso 2: Configurar Variables de Entorno

```bash
cp .env.example .env
# EDITAR .env CON TUS CREDENCIALES
```

### Paso 3: Instalar Dependencias

```bash
npm install
```

### Paso 4: Configurar Base de Datos PostgreSQL

```bash
# CREAR BASE DE DATOS
createdb bot_tendencias

# O usar PostgreSQL GUI y crear manually
# Luego ejecutar el script de setup:
npm run setup
```

### Paso 5: Iniciar el Servidor

```bash
npm start
# Servidor corriendo en http://localhost:3000
```

---

## 📋 ARCHIVOS NECESARIOS

Todos los archivos están listos en este repositorio. Si alguno falta, cópialos desde abajo:

### 1. `package.json` - COPIAR Y CREAR

Este archivo contiene TODAS las dependencias necesarias.

### 2. `.env.example` - COPIAR Y RENOMBRAR a `.env`

Configuración de variables de entorno.

### 3. `server.js` - BACKEND NODE.JS

Archivo principal del servidor. Contiene:
- API endpoints
- Integración con OpenAI
- Cron jobs para análisis automáticos
- Email alerts
- Database queries

### 4. `setup-db.js` - INICIALIZACIÓN DE BD

Script para crear tablas y datos de ejemplo.

### 5. `Dashboard.jsx` - REACT FRONTEND

Componente React para el dashboard interactivo.

---

## 📚 DESPLEGAR EN PRODUCCIÓN

### Opción 1: Heroku (RECOMENDADO)

```bash
# Instalar Heroku CLI
heroku login
heroku create tu-app-name
git push heroku main
```

### Opción 2: DigitalOcean

```bash
# Crear droplet Ubuntu 22.04
# SSH into droplet
cd /var/www
git clone <repo>
cd Bot-Analizador-Tendencias
npm install
npm run setup
npm start

# Usar PM2 para mantener el proceso vivo
npm install -g pm2
pm2 start server.js --name "bot-analizador"
pm2 save
```

### Opción 3: AWS EC2

```bash
# Launch EC2 instance (Ubuntu 22.04)
# Conectar por SSH
sudo apt update && sudo apt upgrade -y
sudo apt install nodejs npm postgresql postgresql-contrib

# Clonar y configurar
git clone <repo>
cd Bot-Analizador-Tendencias
npm install
sudo -u postgres createdb bot_tendencias
npm run setup
npm start
```

---

## 📞 API ENDPOINTS

### Health Check
```bash
GET /api/health
# Response: {"status": "OK", "timestamp": ".."}
```

### Obtener Productos
```bash
GET /api/productos?page=1&limit=20
```

### Top 10 Rentables
```bash
GET /api/productos-rentables
# Retorna: Margen > 30%, Viralidad > 50
```

### Estadísticas
```bash
GET /api/estadisticas
# Retorna: totales, promedios, máximos
```

### Iniciar Análisis Manual
```bash
POST /api/analizar
Body: {"plataforma": "TikTok", "keyword": "viral products"}
```

### Enviar Email
```bash
POST /api/enviar-email
Body: {"destinatario": "email@ejemplo.com", "tipo": "resumen_diario"}
```

---

## 💫 MONETIZACIÓN

### Plan Starter - $29/mes
- 50 análisis por mes
- 1 usuario
- Email diario
- Dashboard básico

### Plan Pro - $99/mes
- Análisis ilimitados
- 5 usuarios
- API access
- Integraciones N8N
- Soporte prioritario

### Plan Enterprise - Custom
- Custom deployments
- White-label
- Integraciones avanzadas
- Soporte 24/7

---

## 📈 ANALYTICS & MONITORING

Logs en:
- `error.log` - Errores
- `combined.log` - Todos los logs

Monitora con:
```bash
tail -f error.log
tail -f combined.log
```

---

## 🚧 TROUBLESHOOTING

### Error: "Cannot connect to database"
```bash
# Verificar PostgreSQL
sudo service postgresql status
# Reinstalar si es necesario
```

### Error: "Module not found"
```bash
rm -rf node_modules
npm install
```

### Error: "Port 3000 already in use"
```bash
# Encontrar proceso usando puerto 3000
lsof -i :3000
# Matar proceso
kill -9 <PID>
```

---

## 🎯 DASHBOARD REACT FRONTEND

Si necesitas un frontend React separado:

```bash
npx create-react-app frontend
cd frontend
npm install axios chart.js react-chartjs-2
# Copy Dashboard.jsx al src/
npm start
```

---

## 💫 N8N WORKFLOW AUTOMATION

Para automatizar análisis cada 6 horas:

1. Ir a [n8n.io](https://n8n.io)
2. Create workflow
3. Add HTTP node que llame a `/api/analizar`
4. Schedule con cron: `0 */6 * * *`
5. Deploy

---

## 🛠 MANTENIMIENTO

### Backup de BD
```bash
pg_dump bot_tendencias > backup.sql
```

### Restaurar BD
```bash
psql bot_tendencias < backup.sql
```

### Update dependencias
```bash
npm update
npm audit fix
```

---

## 🌟 ÉXITO!

Si todo funciona:
1. Bot está analizando productos
2. Dashboard accesible en http://localhost:3000
3. Recibirás emails diarios con Top 10 productos
4. API disponible para integraciones

**¡A monetizar! 💵**
