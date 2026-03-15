# 💍 Álbum de Matrimonio

Sitio web para compartir las fotos de tu boda con los invitados.  
Las fotos se alojan en **GitHub** y se descargan en calidad original.

---

## Estructura de archivos

```
album-matrimonio/
├── index.html        ← El álbum (lo ven los invitados)
├── admin.html        ← Panel para subir y gestionar fotos
├── config.json       ← Nombres y fecha (se actualiza desde admin)
└── fotos/
    ├── lista.json    ← Lista de fotos (se actualiza automáticamente)
    └── foto1.jpg     ← Las fotos van aquí
```

---

## Paso 1 — Crear el repositorio en GitHub

1. Ve a [github.com](https://github.com) e inicia sesión
2. Clic en **"New repository"** (botón verde)
3. Nombre: `album-matrimonio` (o el que prefieras)
4. Marca **"Public"** (necesario para GitHub Pages)
5. Clic **"Create repository"**

---

## Paso 2 — Subir estos archivos

**Opción A — Desde la web de GitHub (más fácil):**
1. En tu repositorio, clic en **"uploading an existing file"**
2. Arrastra todos los archivos y carpetas
3. Escribe un mensaje como "Subir álbum inicial"
4. Clic **"Commit changes"**

**Opción B — Con Git:**
```bash
git init
git add .
git commit -m "Subir álbum inicial"
git remote add origin https://github.com/TU-USUARIO/album-matrimonio.git
git push -u origin main
```

---

## Paso 3 — Activar GitHub Pages

1. Ve a tu repositorio → **Settings** → **Pages**
2. En "Source" selecciona **"Deploy from a branch"**
3. Branch: **main** / Folder: **/ (root)**
4. Clic **Save**
5. En 1-2 minutos tu sitio estará en:
   `https://TU-USUARIO.github.io/album-matrimonio/`

---

## Paso 4 — Crear el Personal Access Token

Necesitas un token para que `admin.html` pueda subir fotos a GitHub.

1. GitHub → foto de perfil → **Settings**
2. Scroll abajo → **Developer settings**
3. **Personal access tokens** → **Tokens (classic)**
4. **Generate new token (classic)**
5. Nombre: `album-matrimonio`
6. Expiración: 90 días (o sin expiración)
7. Permisos: marca solo ✅ **repo**
8. Clic **Generate token**
9. **¡Cópialo ahora!** Solo se muestra una vez

---

## Paso 5 — Configurar el panel de admin

1. Abre `https://TU-USUARIO.github.io/album-matrimonio/admin.html`
2. La primera vez entra sin contraseña
3. Completa los campos:
   - **Usuario de GitHub**: tu nombre de usuario
   - **Repositorio**: `album-matrimonio`
   - **Token**: el que copiaste en el paso 4
   - **Contraseña admin**: elige una contraseña para proteger el panel
4. Clic **Guardar**
5. Clic **Probar conexión** para verificar que todo funciona

---

## Cómo subir fotos

### Desde el panel de admin (recomendado)
1. Abre `admin.html`
2. Arrastra las fotos al área de carga
3. Clic **"Subir al repositorio"**
4. Las fotos aparecen automáticamente en el álbum

### Manualmente desde GitHub
1. Ve a tu repositorio → carpeta `fotos/`
2. Clic **"Add file"** → **"Upload files"**
3. Arrastra las fotos
4. Commit changes
5. **Importante:** luego debes actualizar `fotos/lista.json` manualmente  
   (agrega el nombre de cada foto al array JSON)
   ```json
   ["foto1.jpg", "foto2.jpg", "foto3.jpg"]
   ```

---

## Compartir el álbum

Comparte este enlace con tus invitados:
```
https://TU-USUARIO.github.io/album-matrimonio/
```

Los invitados pueden:
- Ver todas las fotos en galería
- Abrir cada foto en pantalla completa
- Descargar fotos individuales (calidad original)
- Descargar todas las fotos de una vez

---

## Preguntas frecuentes

**¿Las fotos pierden calidad?**  
No. Los archivos se suben como binarios sin ninguna compresión ni recodificación. GitHub los almacena exactamente como los subiste.

**¿Cuántas fotos puedo subir?**  
GitHub permite repositorios de hasta 1 GB gratis. Para fotos de bodas (aprox. 5-8 MB cada una) caben unas 150-200 fotos cómodamente.

**¿El álbum es privado?**  
El repositorio debe ser público para que GitHub Pages funcione gratuitamente. Cualquiera con el enlace puede verlo, pero si no tienes el enlace no es fácil encontrarlo.

**¿El token es seguro?**  
El token se guarda solo en tu navegador (localStorage) y nunca se sube al repositorio. Nadie más puede verlo.
