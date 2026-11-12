# SPEAL · Apps para clientes

Fachadas web (dominio propio) de las apps que SPEAL opera para sus clientes.
Cada carpeta es un sitio independiente en **Cloudflare Pages**; el servidor y los datos
siguen en Google Apps Script + Sheets + Drive.

| Carpeta | Cliente | Dominio | Proyecto Cloudflare Pages |
|---|---|---|---|
| `orvit/` | ORVIT Corporate Center (Qro.) | orvit.speal.mx | `orvit` |

## Agregar un cliente nuevo
1. Copia la carpeta `orvit/` con el nombre del cliente.
2. Cambia `APPS_SCRIPT_URL` en `index.html`, los íconos y el `manifest.webmanifest`.
3. En Cloudflare → Workers & Pages → Create → Pages → Connect to Git → este repo.
   - Build command: *(vacío)*
   - Build output directory: `<carpeta-del-cliente>`
4. Custom domains → `<cliente>.speal.mx`.

## Cuando se publique una nueva versión en Apps Script
Si se usa **Gestionar implementaciones → Editar → Nueva versión**, la URL `/exec` no cambia
y aquí no hay que tocar nada. Solo si se crea una implementación **nueva** hay que
actualizar `APPS_SCRIPT_URL`.
