# Bot Analizador de Tendencias de Productos

## 📊 Descripción

Bot automatizado que analiza productos virales de **TikTok, Instagram y Pinterest** para identificar oportunidades de dropshipping con alto potencial de rentabilidad.

### Características Principales:

- ✅ Análisis automático de viralidad y engagement
- 💰 Cálculo de márgenes de ganancia
- 📈 Seguimiento de tendencias en tiempo real
- 📧 Alertas diarias por email
- 🔍 Búsqueda de proveedores en AliExpress
- 🎯 Puntuación de riesgo y competencia
- 📊 Dashboard interactivo
- 🚀 N8N workflow para automatización

## 🏗️ Arquitectura

```
Bot-Analizador-Tendencias/
├── backend/              # Node.js/Express API
├── frontend/             # React Dashboard
├── n8n-workflow/         # Automatización N8N
├── landing-page/         # Página de venta
├── database/              # Scripts SQL
└── docs/                  # Documentación
```

## ⚡ Quick Start

### Requisitos:
- Node.js 18+
- PostgreSQL 14+
- npm o yarn

### Instalación (5 minutos):

```bash
# 1. Clonar repositorio
git clone https://github.com/holayuxty-a11y/Bot-Analizador-Tendencias.git
cd Bot-Analizador-Tendencias/backend

# 2. Instalar dependencias
npm install

# 3. Configurar variables de entorno
cp .env.example .env
# Editar .env con tus credenciales

# 4. Configurar base de datos
npm run setup

# 5. Iniciar servidor
npm start
```

## 📋 Archivos Clave

- `server.js` - API principal con endpoints
- `setup-db.js` - Inicialización de base de datos
- `.env.example` - Plantilla de variables de entorno
- `package.json` - Dependencias del proyecto

## 🔗 API Endpoints

- `GET /api/health` - Health check
- `GET /api/productos` - Obtener productos
- `GET /api/productos-rentables` - Top 10 rentables
- `GET /api/estadisticas` - Estadísticas generales
- `POST /api/analizar` - Iniciar análisis
- `POST /api/enviar-email` - Enviar reporte

## 💡 Variables de Entorno Importantes

```env
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=tu_contraseña
DB_NAME=bot_tendencias

OPENAI_API_KEY=sk-...
SMTP_USER=tu-email@gmail.com
SMTP_PASSWORD=tu-app-password
```

## 📚 Documentación Completa

Ver archivos en `/docs`

## 💰 Modelos de Monetización

- **Plan Starter** ($29/mes) - 50 análisis/mes
- **Plan Pro** ($99/mes) - Análisis ilimitado + API
- **Plan Enterprise** (custom) - Integraciones personalizadas

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Abre un issue o PR.

## 📞 Soporte

Contacta a: support@tudominio.com

---

**Bot Analizador de Tendencias** © 2024 - MIT License
