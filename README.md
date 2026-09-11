# IRON Facilities — Master Security S.A.S.

**Propiedad de:** Master Security S.A.S. · NIT 900583611-6  
**Desarrollado por:** IRON APPS  
**Versión:** 1.0 · Septiembre 2026  
**URL producción:** https://erp.mastersecuritys.com

---

## ¿Qué es este sistema?

ERP de gestión de mantenimiento locativo para el contrato con el Grupo Aval (OBA2600005).
Gestiona solicitudes Verona, técnicos, ARL, compras, facturación y reportes.

---

## Archivos incluidos

```
master-security/
├── frontend/
│   └── index.html          ← Sistema web completo (abrir en navegador)
├── backend/
│   ├── server.js           ← Servidor API principal
│   ├── sheets.js           ← Conector Google Sheets
│   ├── auth.js             ← Módulo de autenticación y usuarios
│   ├── email-reader.js     ← Lector automático de emails Verona (cada 15 min)
│   ├── setup-sheets.js     ← Inicializar Google Sheet (correr UNA vez)
│   ├── package.json        ← Dependencias Node.js
│   └── .env.example        ← Variables de entorno (copiar como .env)
└── README.md
```

---

## Usuarios del sistema

| Usuario | Contraseña | Rol |
|---|---|---|
| yesenia@mastersecuritys.com | Yesenia2026* | Superadmin |
| wendy@mastersecuritys.com | Wendy2026* | Superadmin |
| keiny@mastersecuritys.com | Keiny2026* | Superadmin |
| roberto@mastersecuritys.com | Roberto2026* | Watcher (solo lectura) |

Técnicos: acceso por link único de WhatsApp generado desde el sistema.

---

## Instalación rápida (Opción A — pruebas locales)

Abrir `frontend/index.html` directamente en Chrome. Login funciona sin servidor.

## Instalación completa (Opción B — producción con automatizaciones)

Ver guía: `guia-despliegue-produccion.html`

Pasos resumidos:
1. Subir código a GitHub (repositorio privado)
2. Activar Gmail API + Sheets API en Google Cloud Console
3. Crear Web Service en Render.com (gratis o $7 USD/mes)
4. Agregar registro CNAME en GoDaddy → erp.mastersecuritys.com
5. Correr `node setup-sheets.js` una sola vez

---

## Reglas de negocio implementadas

- ARL vencida = técnico bloqueado (no se puede asignar)
- ARL mensual: alerta 5 días antes del vencimiento
- Técnico no ve valores — solo reporta ítems de trabajo
- Compras requieren aprobación de coordinación antes de ejecutarse
- Facturas siempre a nombre de Master Security S.A.S. NIT 900583611-6
- Al cerrar servicio → sincronización automática con Drive de Seguimiento
- Emails de Verona → lectura automática cada 15 minutos

---

## Renovación de dominio

mastersecuritys.com vence el **8 de noviembre de 2026** en GoDaddy.  
Renovar en octubre antes de que expire (~$20 USD/año).

---

*© Master Security S.A.S. · Desarrollado por IRON APPS*
