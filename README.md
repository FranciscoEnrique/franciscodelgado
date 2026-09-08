# franciscodelgado.dev

Landing personal de una sola página. Sitio estático generado con [Astro](https://astro.build/),
sin backend ni base de datos. Se despliega en **Cloudflare Pages**. La dirección de
contenido y diseño está en [`BRIEF.md`](BRIEF.md).

## Desarrollo

```sh
npm install
npm run dev      # http://localhost:4321
npm run build    # genera dist/
npm run preview  # sirve dist/ localmente
```

Todo el sitio vive en [`src/pages/index.astro`](src/pages/index.astro): el contenido
(proyectos, stack, contacto) está en las constantes al inicio del archivo y los estilos
en el bloque `<style>` al final.

## Antes de publicar — revisar

- **`contact.linkedin`** en `src/pages/index.astro`: cambiar por el perfil real.
- **`contact.email`**: ahora apunta a un correo de Gmail. Cambiar si prefieres uno
  del dominio.
- **CV**: colocar el PDF en `public/cv-francisco-delgado.pdf` (o ajustar `contact.cv`).
- **Proyecto RFID**: el array `projects[0].links` está vacío. Agregar el repo y/o el
  PDF de arquitectura cuando estén listos, p. ej.:
  ```js
  links: [
    { label: "Repositorio", href: "https://github.com/usuario/rfid-access" },
    { label: "Arquitectura (PDF)", href: "/rfid-arquitectura.pdf" },
  ]
  ```

## Despliegue — Cloudflare Pages

El dominio `franciscodelgado.dev` usa los nameservers de Cloudflare, así que Pages
gestiona DNS y certificado automáticamente.

**Proyecto (una vez):**

1. Cloudflare → **Workers & Pages → Create → Pages → Connect to Git** → repo
   `FranciscoEnrique/franciscodelgado`.
2. Build command: `npm run build` · Output directory: `dist`.
   Versión de Node vía [`.nvmrc`](.nvmrc) (`22`).
3. Deploy. Cada push a `main` republica.

**Dominio:**

4. En el proyecto de Pages → **Custom domains → Set up a domain** →
   `franciscodelgado.dev` (y opcionalmente `www.franciscodelgado.dev`).
5. Como el dominio está en Cloudflare, se crean los registros y el certificado
   solos, en ~1 min.

Alternativa sin Git (subida directa):

```sh
npm run build
npx wrangler pages deploy dist --project-name franciscodelgado
```

> El certificado del `.dev` es obligatorio: los navegadores fuerzan HTTPS (HSTS
> preload) y no dejan entrar sin él. Cloudflare lo emite al instante.
