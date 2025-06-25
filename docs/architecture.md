# 🏗️ Arquitectura del Proyecto

## Visión General

El sistema **Bot WhatsApp Business** está diseñado bajo una arquitectura desacoplada y escalable, separando claramente el backend (API y lógica de negocio) del frontend (dashboard y administración).

---

## Diagrama de Arquitectura

```
[ Usuario ]
     |
     v
[ Frontend Angular ] <-----> [ Backend Node.js/Express ] <-----> [ PostgresSql ]
                                         |
                                         v
                                [ WhatsApp Web.js ]
```

- **Frontend**: Aplicación Angular SPA para administración y visualización en tiempo real.
- **Backend**: API RESTful en Node.js/Express, maneja lógica, autenticación y conexión con WhatsApp.
- **Base de datos**: PostgresSql para persistencia de datos.
- **Socket.io**: Comunicación en tiempo real entre frontend y backend.
- **WhatsApp Web.js**: Integración directa con WhatsApp Web para envío/recepción de mensajes.

---

## Componentes Clave

- **API REST**: Endpoints seguros para gestión de proveedores, mensajes, analytics, etc.
- **Websockets**: Actualización en tiempo real de métricas y mensajes.
- **Autenticación JWT**: Seguridad robusta para usuarios y proveedores.
- **CI/CD**: Deploy automatizado con GitHub Actions y PM2.

---

## Flujo de Datos

1. El usuario interactúa con el dashboard (Angular).
2. Las acciones disparan peticiones al backend (Express).
3. El backend procesa la lógica, consulta la base de datos y/o interactúa con WhatsApp Web.js.
4. Las respuestas se envían al frontend y/o se actualizan en tiempo real vía Socket.io.

---

## Seguridad

- Autenticación y autorización JWT.
- Validación de entradas y sanitización.
- Rate limiting y CORS.

---

## Escalabilidad

- Arquitectura desacoplada: permite escalar backend y frontend de forma independiente.
- Uso de PM2 y Nginx para balanceo y alta disponibilidad.

---

## Diagrama de Carpetas (Backend)

```
bot-wp-back/
├── routes/
├── services/
├── middleware/
├── utils/
├── uploads/
├── app.js
├── database.js
└── ...
```

## Diagrama de Carpetas (Frontend)

```
bot-wp-front/
├── src/
│   ├── app/
│   ├── assets/
│   ├── environments/
│   └── ...
└── ...
```

---

> Para detalles técnicos consulta la documentación de cada módulo en este repositorio.
