# Dune · Contador de victorias

Página para registrar las partidas de Dune (2019): quién ganó, con qué facción, en alianza con quién. Incluye la expansión Ixianos y Tleilaxu.
La página se publica en GitHub Pages y las partidas quedan guardadas en una hoja de Google Sheets.

## 1. Hoja de Google y Apps Script
1. Crea una hoja de cálculo nueva en Google Sheets (por ejemplo "Dune partidas").
2. Ve a **Extensiones → Apps Script**, borra lo que haya y pega el contenido de `Code.gs`. Guarda.
3. (Opcional, recomendado) **Configuración del proyecto → Propiedades del script → Agregar**: `CLAVE` = la clave del grupo. Sin clave, cualquiera con el link puede editar.
4. **Implementar → Nueva implementación → Tipo: Aplicación web**
   - Ejecutar como: **Yo**
   - Quién tiene acceso: **Cualquier persona**
5. Autoriza los permisos y copia la URL que termina en `/exec`.

La pestaña `Partidas` se crea sola con la primera partida. Tiene una columna por facción, así que también puedes corregir datos a mano en la hoja.

## 2. Conectar la página
En `index.html`, pega la URL en la línea:
```js
const API_URL = 'https://script.google.com/macros/s/XXXX/exec';
```

## 3. GitHub Pages
En el repositorio: **Settings → Pages → Source: Deploy from a branch → main / (root)**. En un par de minutos queda en `https://<usuario>.github.io/<repo>/`.

## Notas
- Si cambias `Code.gs`, vuelve a publicar con **Implementar → Administrar implementaciones → Editar → Nueva versión**. Así la URL no cambia.
- La página se actualiza sola cada 30 segundos.
