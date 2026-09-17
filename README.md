# Briefing Matutino Planta 2 (SPA)

Aplicación web responsiva de una sola página (Single Page Application) optimizada para smartphones con apariencia y comportamiento de app nativa. Diseñada para registrar las novedades de la junta operativa de las **08:00 AM en menos de 3 minutos** y emitir el reporte ejecutivo formal antes de la junta directiva de las **09:00 AM**.

---

## 🚀 Inicio Rápido

1. **Abrir la Aplicación**:
   - En tu computadora o smartphone, simplemente abre el archivo [`index.html`](./index.html) en tu navegador preferido (Google Chrome, Safari, Edge, Firefox).
   - No requiere instalaciones de Node, Python, ni configuración de servidores: es 100% autónoma y funcional fuera de la caja.

2. **Acceso como App Nativa en Smartphone (Recomendado)**:
   - **En iPhone (Safari)**: Toca el botón de **Compartir** (icono de cuadro con flecha hacia arriba) y selecciona **"Agregar a pantalla de inicio"**.
   - **En Android (Google Chrome)**: Toca el menú de los tres puntos verticales y presiona **"Instalar aplicación"** o **"Agregar a la pantalla principal"**.
   - *Ventaja*: Se abrirá en pantalla completa sin barra de direcciones del navegador, lista en tu bolsillo para la junta de las 8:00 AM.

---

## 🛠️ Características Principales

### 1. Captura en Menos de 3 Minutos
- **Bala para Dirección**: Campo superior destacado con contador de caracteres y botones de inserción rápida ("🟢 100% Nominal", "🟡 Con Monitoreo", "🔴 Paro Crítico") para resumir el estado general en 1 o 2 oraciones.
- **Tarjetas Dinámicas de Máquina**:
  - Máquina / Línea (input ágil).
  - Selector de Estatus estilo píldora de 1 toque (**🟢 OK**, **🟡 Monitoreo**, **🔴 Paro**).
  - Falla o síntoma detectado.
  - Solución o acción tomada en piso.
  - Tiempo muerto acumulado en minutos (`inputmode="numeric"` para desplegar teclado numérico directo en celular).
- **Indicadores en Tiempo Real**: Tarjetas métricas superiores con conteo de eventos, máquinas OK, en monitoreo, en paro y sumatoria de minutos de paro.

### 2. Generación de PDF Formal en 1 Página Exacta
- Integra `html2pdf.js` (con `html2canvas` y `jsPDF`).
- Formato **Carta / Letter (8.5 x 11 pulg)** calibrado milimétricamente para **nunca desbordar a una segunda página**.
- Diseño industrial sobrio de alto contraste:
  - Membrete institucional con fecha y hora de emisión.
  - Bloque destacado de la "Bala para Dirección".
  - Métricas flash del turno.
  - Tabla operativa: Máquina/Línea, Estatus con badges cromáticos, Falla, Solución y Tiempo Muerto.

### 3. Enlace con WhatsApp (Doble Vía)
- **Vía 1 (Web Share API Móvil)**: Al pulsar *"Enviar por WhatsApp"*, la app genera el archivo PDF y utiliza `navigator.share({ files: [pdf] })`. En Android y iOS se abrirá la hoja de compartir nativa permitiendo enviar directamente el documento PDF a WhatsApp.
- **Vía 2 (Fallback / wa.me directo)**: Si el navegador no permite compartir archivos binarios por API, genera y abre automáticamente un enlace a `https://wa.me/[TELEFONO]?text=...` con el resumen ejecutivo estructurado con negritas, viñetas, emojis y tiempos muertos listo para enviarse con 1 toque.

### 4. Persistencia y Configuración Local
- **Teléfono Guardado**: Haz clic en el engranaje superior para guardar el número de WhatsApp de tu jefe o dirección (con clave de país, ej. `5218112345678`). Se guarda en `localStorage` y no tendrás que volver a teclearlo.
- **Auto-guardado Continuo**: Si minimizas el navegador durante la junta, tomas una llamada o se recarga la pestaña, **no pierdes nada**; el borrador se restaura al instante.
- **Botón "Limpiar Formato"**: Icono de papelera en la barra superior para vaciar los campos del día anterior e iniciar fresco para el día siguiente (con confirmación de seguridad).

---

## 📱 Paleta de Diseño
- **Fondo**: `Slate-950` (#020617) y `Slate-900` (#0f172a).
- **Acentos Industriales**: `Sky-500` (#0284c7) y `Blue-700` (#0369a1).
- **Estatus Operativo**:
  - 🟢 **OK**: `Emerald-400` / `Emerald-500`
  - 🟡 **Monitoreo**: `Amber-400` / `Amber-500`
  - 🔴 **Paro**: `Rose-500` con reborde activo.
- **Botón de Acción WhatsApp**: Verde oficial de la marca (`#25D366`).
