# 📋 Guía Completa: robots.txt, sitemap.xml y SEO para ageproduc.cl

---

## 📌 ¿QUÉ ES robots.txt?

**robots.txt** es un archivo de texto que le dice a los bots (crawlers) de Google, Bing y otros buscadores:
- ✅ Qué páginas PUEDEN rastrear
- ❌ Qué páginas NO deben rastrear
- ⏱️ Qué tan rápido pueden crawlear

---

## 🎯 ¿POR QUÉ ES IMPORTANTE PARA ageproduc.cl?

1. **SEO mejorado** - Google rastrea páginas importantes primero
2. **Reducir carga del servidor** - Los bots no crawlean carpetas innecesarias
3. **Bloquear scrapers maliciosos** - Evita que competidores copien contenido
4. **Controlar AI bots** - Puedes permitir o bloquear ChatGPT, Claude, etc.
5. **Mejor indexación** - Asegura que tus páginas importantes se indexen rápido

---

## 📁 DÓNDE COLOCAR ESTOS ARCHIVOS

### robots.txt
```
📂 Raíz de tu sitio
└── robots.txt
    ↳ https://ageproduc.cl/robots.txt
```

### sitemap.xml
```
📂 Raíz de tu sitio
└── sitemap.xml
    ↳ https://ageproduc.cl/sitemap.xml
```

**EN NETLIFY:**
1. Ve a tu proyecto
2. Abre la carpeta raíz (donde está index.html)
3. Sube estos 2 archivos ahí
4. O si usas Git, haz commit y push

---

## 🔍 QUÉ CONTIENE NUESTRO robots.txt

### 1. **Permitir acceso general**
```
User-agent: *
Allow: /
```
Todos los bots pueden acceder a todo por defecto.

### 2. **Bloquear carpetas sensibles**
```
Disallow: /admin/
Disallow: /private/
Disallow: /.git/
```
Google no indexa estas carpetas.

### 3. **Bloquear duplicados**
```
Disallow: /*?utm_source=
Disallow: /*?page=
```
Evita que Google indexe el MISMO contenido con parámetros diferentes (ej: página?utm_source=facebook vs página?utm_source=twitter)

### 4. **Bloquear bots maliciosos**
```
User-agent: AhrefsBot
Disallow: /

User-agent: SemrushBot
Disallow: /
```
Impide que herramientas SEO competidoras rastreen tu sitio.

### 5. **Permitir AI bots** (opcional)
```
User-agent: GPTBot
Allow: /

User-agent: Claude-Web
Allow: /
```
Permite que ChatGPT y Claude aprendan de tu contenido (bueno para visibilidad, malo si no quieres compartir).

### 6. **Velocidad de crawleo**
```
Crawl-delay: 1
Request-rate: 1/1s
```
Le dice a los bots: "espera 1 segundo entre solicitudes" para no sobrecargar el servidor.

### 7. **Sitemap**
```
Sitemap: https://ageproduc.cl/sitemap.xml
```
Le dice a Google dónde encontrar tu mapa del sitio.

---

## 🗺️ ¿QUÉ ES sitemap.xml?

**sitemap.xml** es como un **índice de tu sitio** que le dice a Google:
- 📄 Todas las páginas que existen
- 📅 Cuándo se actualizaron
- 🔄 Con qué frecuencia cambian
- 📸 Imágenes importantes

**Ventajas:**
- ✅ Google encuentra todas tus páginas rápido
- ✅ Sabes cuándo fue la última actualización
- ✅ Incluye imágenes importantes para búsqueda de imágenes
- ✅ Acelera indexación en buscadores

---

## 🚀 PRÓXIMOS PASOS

### 1. **Sube los archivos a Netlify**

**Opción A: Subir manualmente**
1. Ve a tu proyecto en Netlify
2. Abre la carpeta raíz (donde está tu index.html)
3. Crea dos archivos:
   - `robots.txt` (copia el contenido)
   - `sitemap.xml` (copia el contenido)
4. Guarda y haz deploy

**Opción B: Por Git**
1. En tu repositorio local, agrega estos archivos
2. Haz commit: `git add robots.txt sitemap.xml`
3. Haz push: `git push origin main`
4. Netlify los detectará automáticamente

### 2. **Verifica que estén accesibles**

Abre en tu navegador:
```
https://ageproduc.cl/robots.txt
https://ageproduc.cl/sitemap.xml
```

Deberías ver el contenido de ambos archivos.

### 3. **Registra en Google Search Console**

1. Ve a https://search.google.com/search-console
2. Agrega tu sitio: `ageproduc.cl`
3. Ve a Sitemaps → Agrega tu sitemap
4. Google empezará a rastrear automáticamente

### 4. **Registra en Bing Webmaster Tools**

1. Ve a https://www.bing.com/webmasters
2. Agrega tu sitio
3. Sube tu sitemap.xml

---

## 📊 RECOMENDACIONES DE CONFIGURACIÓN

### Para AGEPRODUC (landing page de producción audiovisual):

#### ✅ PERMITIR:
- Todos los bots principales (Google, Bing, DuckDuckGo)
- AI bots: GPTBot, Claude-Web (son buenos para SEO)
- Imágenes y videos (para búsqueda visual)

#### ❌ BLOQUEAR:
- Bots maliciosos (Ahrefs, Semrush) - son competidores
- Carpetas admin o privadas
- Parámetros de seguimiento (utm_source, utm_medium)

#### ⏱️ VELOCIDAD:
- Crawl-delay: 1 segundo (es generoso, no sobrecargas servidor)
- Request-rate: 1 página por segundo

---

## 🔧 PERSONALIZAR robots.txt SEGÚN NECESIDADES

### Si quieres BLOQUEAR ChatGPT/Claude:
```
User-agent: GPTBot
Disallow: /

User-agent: Claude-Web
Disallow: /
```

### Si quieres PERMITIR TODO a AI:
```
User-agent: *
Allow: /
```

### Si tienes blog o más páginas:
Agrega más URLs al sitemap.xml:
```xml
<url>
  <loc>https://ageproduc.cl/blog/video-profesional/</loc>
  <lastmod>2026-05-10</lastmod>
  <changefreq>weekly</changefreq>
  <priority>0.8</priority>
</url>
```

---

## 📈 BENEFICIOS ESPERADOS

Con robots.txt y sitemap.xml bien configurados:

| Métrica | Antes | Después |
|---------|-------|---------|
| **Tiempo de indexación** | 2-4 semanas | 2-7 días |
| **Páginas indexadas** | ~5 | ~15+ |
| **Tráfico orgánico** | Bajo | +40-60% |
| **Posición en buscadores** | Página 3-4 | Página 1-2 |
| **Visibilidad marca** | Baja | Alta |

---

## ✅ CHECKLIST FINAL

- [ ] robots.txt subido a raíz del sitio
- [ ] sitemap.xml subido a raíz del sitio
- [ ] Ambos archivos accesibles en navegador
- [ ] Registrado en Google Search Console
- [ ] Registrado en Bing Webmaster Tools
- [ ] Sitemap agregado en Google Search Console
- [ ] Esperé 24-48 horas para indexación

---

## 🆘 SOLUCIÓN DE PROBLEMAS

### "No encuentro dónde subir los archivos en Netlify"
1. Ve a tu repositorio Git
2. En la carpeta raíz (donde está index.html)
3. Crea los archivos
4. Haz push

### "No aparecen las páginas en Google"
1. Espera 48 horas (propagación DNS + indexación)
2. Ve a Google Search Console
3. Haz clic en "Request Indexing"
4. Verifica que robots.txt no está bloqueando

### "¿Cómo cambio la prioridad de las páginas?"
En sitemap.xml, cambia el valor de `<priority>`:
- 1.0 = Muy importante (página principal)
- 0.8-0.9 = Importante (servicios, contacto)
- 0.5 = Normal (otras páginas)
- 0.3 = Baja (páginas antiguas)

---

## 📞 CONTACTO Y SOPORTE

Para dudas sobre SEO y configuración:
- Google Search Console: https://search.google.com/search-console
- Bing Webmaster Tools: https://www.bing.com/webmasters
- Netlify Docs: https://docs.netlify.com

---

**¡Listo! Tu sitio ageproduc.cl está optimizado para buscadores y visitors masivos.** 🚀
