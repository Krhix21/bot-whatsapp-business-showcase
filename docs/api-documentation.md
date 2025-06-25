# 📡 Documentación de API

Esta sección describe los endpoints principales del backend de **Bot WhatsApp Business**.

---

## Autenticación

```
POST /api/auth/login
POST /api/auth/register
POST /api/auth/refresh
GET  /api/auth/profile
```

---

## Proveedores

```
- **GET /api/providers**
  - Headers: `Authorization: Bearer <token>`
  - Descripción: Lista todos los proveedores.

- **POST /api/providers**
  - Body: `{ "name": "Proveedor X", "phone": "+573001234567" }`
```

---

## Mensajes

```
- **GET /api/messages**
  - Query params: `providerId`, `dateFrom`, `dateTo`
  - Descripción: Lista mensajes filtrados.

## Analytics

```
GET /api/analytics/overview
GET /api/analytics/messages
GET /api/analytics/users
GET /api/analytics/performance
GET /api/analytics/export
```

---

## Errores comunes

- `401 Unauthorized`: Token inválido o expirado.
- `400 Bad Request`: Parámetros incorrectos.
- `500 Internal Server Error`: Error inesperado del servidor.

---

> Para más detalles, consulta la documentación Swagger en `/api-docs` una vez desplegado el backend.
