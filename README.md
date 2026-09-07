# franciscodelgado.dev

Landing personal de una sola página. Sitio estático generado con [Astro](https://astro.build/),
sin backend ni base de datos. La dirección de contenido y diseño está en [`BRIEF.md`](BRIEF.md).

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

## Despliegue — GitHub Pages

1. Crear un repositorio en GitHub y subir este proyecto.
2. En el repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. El workflow [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) construye
   y publica en cada push a `main`.
4. El dominio personalizado se sirve vía [`public/CNAME`](public/CNAME)
   (`franciscodelgado.dev`), que Astro copia a `dist/`.
5. En el proveedor del dominio, apuntar el DNS a GitHub Pages:
   - `A` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - o `CNAME` de `www` → `<usuario>.github.io`
6. GitHub emite el certificado HTTPS automáticamente (unos minutos tras verificar el DNS).

Alternativa: conectar el repo a **Cloudflare Pages** (build command `npm run build`,
output `dist`) y configurar el dominio en su panel.
