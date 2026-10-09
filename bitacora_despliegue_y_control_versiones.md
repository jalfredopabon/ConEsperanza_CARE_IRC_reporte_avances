# 📋 Bitácora de Proyecto, Despliegue y Control de Versiones

> **Proyecto:** Consorcio Humanitario CARE & IRC &mdash; Respuesta de Emergencia OCHA Colombia  
> **Lienzo / Dashboard:** Resumen Ejecutivo MEAL (Fondo Humanitario RHPF LAC)  
> **Fecha de Actualización:** Octubre 2026  
> **Ubicación Local:** `C:\Users\JosePabon\Music\Power BI - recursos\carpeta_prueba\`  

---

## 🚀 1. Repositorio Remoto y Despliegue Online (GitHub Pages)

| Recurso | Detalle / Enlace |
| :--- | :--- |
| **Repositorio GitHub** | [jalfredopabon/ConEsperanza_CARE_IRC_reporte_avances](https://github.com/jalfredopabon/ConEsperanza_CARE_IRC_reporte_avances) |
| **Rama de Producción (`main`)** | `main` (Única rama troncal y fuente de verdad oficial) |
| **Directorio de Publicación** | `/` (Raíz del repositorio) |
| **URL Demo Online (GitHub Pages)** | **[https://jalfredopabon.github.io/ConEsperanza_CARE_IRC_reporte_avances/](https://jalfredopabon.github.io/ConEsperanza_CARE_IRC_reporte_avances/)** |

---

## 🌿 2. Definición y Reglas de la Rama `main`

### ¿Qué representa `main` en este proyecto?
1. **Rama Troncal de Producción (*Single Source of Truth*):**  
   Todo cambio que se fusiona o se hace *push* en la rama `main` dispara automáticamente el pipeline de despliegue continuo de GitHub Pages.
2. **Entorno Visible al Donante y Socios:**  
   La URL pública de GitHub Pages consume directamente el archivo `index.html` ubicado en la raíz de `main`. Cualquier revisión del donante OCHA o los directores de CARE e IRC se evalúa sobre esta versión.
3. **Gemelo Digital del Reporte PBIP:**  
   El `index.html` en `main` actúa como la referencia arquitectónica y visual exacta (layout, paleta, tipografía, espaciado de 8px) que luego se traslada a las medidas DAX con visuales *HTML Content* en Power BI (`power_bi_prueba.pbip`).

---

## 🛠️ 3. Registro de Cambios Recientes (Changelog)

### Versión Actual (Desplegada en `main`):
- **Estandarización de Grilla Espacial de 8px:**  
  Alineación perfecta entre las tarjetas superiores de KPI (`minmax(0, 1fr)`), el gráfico de tendencia y las barras sectoriales, eliminando desbordamientos de borde y márgenes residuales.
- **Micro-interacciones y Feedback Háptico:**  
  Efectos hover adaptados a la organización activa (Azul OCHA, Naranja CARE, Amarillo IRC).
- **Corrección Crítica en Power BI TMDL (`_Measures.tmdl`):**  
  Solventado el error de indentación en la medida base `Color Hover Activo` que provocaba la caída en cascada de los visuales HTML Content ("Hubo un problema con uno o más campos").
- **Publicación a GitHub Pages:**  
  Sincronización confirmada mediante commit y push directo a la rama `main` del repositorio remoto.

---

## 🔄 4. Flujo de Trabajo para Actualizaciones Futuras

1. **Desarrollo y prueba local:**  
   Editar `index.html` en `carpeta_prueba` y verificar en navegador.
2. **Sincronización a `main`:**  
   Subir cambios mediante commit descriptivo a la rama `main`:
   ```bash
   git commit -am "tipo: descripción de la mejora visual o funcional"
   git push origin main
   ```
3. **Verificación en vivo:**  
   Esperar la notificación de build en GitHub Pages (~30 segundos) y recargar con `Ctrl + F5` en:  
   `https://jalfredopabon.github.io/ConEsperanza_CARE_IRC_reporte_avances/`
