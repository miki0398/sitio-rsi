# Instrucciones paso a paso para publicar (para usuarios SIN experiencia técnica)

A continuación la guía para publicar esta carpeta en **GitHub Pages** (opción simple) y luego apuntar tu dominio en GoDaddy.

## 0) Preparativos
1. Si no tenés cuenta en GitHub, creá una en https://github.com.
2. (Opcional) Registrate en Formspree https://formspree.io y crea un formulario para obtener tu endpoint. Reemplaza el atributo `action` en contact.html por el endpoint que te den (algo como `https://formspree.io/f/abcdxyz`).
3. Rellená los datos de contacto en contact.html (teléfono, dirección).

## 1) Subir los archivos a GitHub (sin usar programación)
1. Iniciá sesión en GitHub.
2. Hacé clic en el botón **New repository** (nuevo repositorio).
3. Nombre sugerido: `sitio-rsi` (puede ser privado o público).
4. Creá el repositorio. En la página del repo, hacé clic en **Add file → Upload files**.
5. Arrastrá todos los archivos y carpetas de esta plantilla y luego clic en **Commit changes**.

## 2) Activar GitHub Pages
1. En el repo, ir a **Settings** → **Pages** (o **Code and automation → Pages**).
2. En "Build and deployment" elegir branch `main` (o `master`) y carpeta `/ (root)`. Guardar.
3. En "Custom domain" ingresá tu dominio (ejemplo: `tudominio.com`) y guardar. GitHub generará un archivo `CNAME` en el repo (si no lo hiciste manualmente).
4. GitHub te indicará si necesita registros DNS.

## 3) Configurar DNS en GoDaddy (manteniendo GoDaddy como registrador)
1. Iniciá sesión en tu cuenta de GoDaddy y abrí el panel de DNS del dominio.
2. Crear **4 registros A** apuntando al IPs de GitHub Pages (reemplazá TTL por 1 hora si te lo pide):
   - `@` → `185.199.108.153`
   - `@` → `185.199.109.153`
   - `@` → `185.199.110.153`
   - `@` → `185.199.111.153`
   (fuente: GitHub Pages docs). 
3. Crear un registro **CNAME**:
   - `www` → `yourusername.github.io`  (reemplazá `yourusername` por tu usuario de GitHub).
4. Guardá los cambios. La propagación DNS puede tardar desde minutos hasta 24 horas.

**Fuentes útiles**: GitHub Pages (custom domains), GoDaddy (cambiar nameservers o editar DNS). Consultá estos documentos si necesitás ayuda:  
- Cloudflare Pages - custom domains. citeturn0search0  
- GitHub Pages - custom domains y A records. citeturn2search0  
- Netlify - configurar dominio / DNS (opcional). citeturn0search13  
- GoDaddy - editar nameservers / DNS. citeturn0search3

## 4) Verificar y HTTPS
- GitHub Pages habilita HTTPS automáticamente una vez que los registros DNS estén correctos. Si no aparece, esperá la propagación y luego forzá la opción HTTPS en GitHub Pages settings.

## 5) Alternativa: Cloudflare Pages (recomendado por rendimiento)
- Si preferís usar Cloudflare Pages, podés crear una cuenta en Cloudflare, conectar el repositorio y usar Pages. En ese caso podés delegar nameservers a Cloudflare (GoDaddy → cambiar nameservers) y Cloudflare te guiará. (ver docs de Cloudflare Pages). citeturn0search0turn0search7

---

Si querés, yo puedo:
1) Personalizar los textos (yo los edito por ti).  
2) Subir los archivos a **tu** GitHub (necesitaré acceso — la forma más segura es que yo te entregue los archivos y vos los subas).  
3) Preparar instrucciones exactas con capturas para GoDaddy (podés pedírmelas).

----

Fin de las instrucciones. Si querés, te dejo ahora mismo los archivos listos para descargar y subir a GitHub.
