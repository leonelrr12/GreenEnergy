# Green Energy Technologies - Sitio Web

## Estructura
- **Ubicación**: `/var/www/apps/greenenergy/` (bind-mount a `/root/apps/greenenergy/`)
- **10 páginas HTML**: about, contact, index, privacy, project, quote, service, team, terms, testimonial
- **Nginx**: `greenenergytechnologie.com` con HTTPS (Let's Encrypt), proxy `/api/ → 127.0.0.1:3001`
- **Assets**: img/, js/main.js, lib/, assets/css/, scss/ (template Bootstrap)

## Endpoints
- Formulario contacto + chatbot envían a: `POST /api/public/lead` (CRM en puerto 3001)
- WhatsApp: `+507 6001-7560`
- Teléfono: `+507 6749-9134`

## Chatbot
Presente en todas las páginas. Flujo de 7 pasos (nombre, teléfono, email, monto recibo, tipo propiedad, plano, interés).
Al completar, envía los datos a `/api/public/lead`.

## Notas
- Los archivos HTML comparten header/navbar/footer/chatbot duplicados manualmente.
- SSI está habilitado en nginx (`ssi on;`), se pueden crear partials si se desea.
