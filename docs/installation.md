# ⚙️ Guía de Instalación

Esta guía describe los pasos para instalar y configurar el sistema **Bot WhatsApp Business** en un entorno local o de producción.

---

## Prerrequisitos

- Node.js 18.x o superior
- NPM 8.x o superior
- MySQL 8.x
- PM2 (opcional, recomendado para producción)
- Git

---

## 1. Clonar los repositorios

```bash
git clone https://github.com/Krhix21/bot-wp-back.git
# Opcional: Clonar frontend si es público
git clone https://github.com/Krhix21/bot-wp-front.git
```

---

## 2. Instalar dependencias

### Backend
```bash
cd bot-wp-back
npm install
```

### Frontend (si aplica)
```bash
cd ../bot-wp-front
npm install
```

---

## 3. Configurar variables de entorno

Copia el archivo de ejemplo y edítalo:
```bash
cp .env.example .env
nano .env
```

Configura los parámetros de base de datos, JWT, correo, etc.

---

## 4. Configurar base de datos

Crea la base de datos y ejecuta migraciones:
```bash
mysql -u root -p
CREATE DATABASE bot_whatsapp;
EXIT;

# En el backend
npm run migrate
npm run seed # Opcional
```

---

## 5. Iniciar la aplicación

### Backend
```bash
npm run dev # Desarrollo
npm start   # Producción
pm2 start ecosystem.config.js # Con PM2
```

### Frontend
```bash
ng serve # Desarrollo
ng build --prod # Producción
```

---

## 6. Acceso y pruebas

- Frontend: http://localhost:4200
- Backend API: http://localhost:3001
- API Docs: http://localhost:3001/api-docs

---

> Consulta la documentación de cada repositorio para detalles avanzados de configuración y despliegue.
