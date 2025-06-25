# 🚀 Guía de Deployment

Esta guía describe las opciones de despliegue para **Bot WhatsApp Business**.

---

## 1. Despliegue Automático (CI/CD)

El backend está configurado con **GitHub Actions** para deployment automatizado:

- Build y test automáticos al hacer push a `main`.
- Deploy al servidor vía SSH.
- Restart de la app con PM2.
- Health checks automáticos.

### Ejemplo de flujo:
```yaml
# Push a main
git push origin main
# GitHub Actions ejecuta:
# - Tests
# - Build
# - Deploy
# - Restart
# - Health check
```

---

## 2. Despliegue Manual

1. Accede al servidor:
```bash
ssh usuario@tu-servidor.com
```
2. Ve a la carpeta del proyecto:
```bash
cd /ruta/al/proyecto
```
3. Actualiza el código:
```bash
git pull origin main
```
4. Instala dependencias:
```bash
npm install --omit=dev
```
5. Reinicia la app:
```bash
pm2 restart backend_botwp
```

---

## 3. Monitoreo y Logs

- **PM2** para logs y monitoreo en tiempo real:
```bash
pm2 logs backend_botwp
pm2 monit
pm2 status
```

---

## 4. Backup y Rollback

- Backups automáticos de base de datos.
- Rollback automático en caso de fallos críticos.

---

## 5. Recomendaciones de Producción

- Usar HTTPS obligatorio
- Configurar variables sensibles en `.env`
- Habilitar alertas de monitoreo
- Escalar horizontalmente con Nginx si es necesario

---

> Consulta la configuración de GitHub Actions y PM2 para personalizar el workflow de deployment.
