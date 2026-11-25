# Dashboard de Rendimiento de Influencer

Dashboard estático y adaptable para analizar el rendimiento de campañas de influencers en Instagram, TikTok y YouTube. La interfaz está construida con HTML semántico y Tailwind CSS v4; los gráficos se presentan con Chart.css.

> Este repositorio contiene una demostración de frontend con cifras de ejemplo escritas directamente en el HTML. No se conecta a redes sociales, bases de datos ni APIs de analítica en tiempo real.

## Contenido del dashboard

- KPIs: ingresos, tasa de conversión, engagement, margen y comisión acumulada.
- Gráfico de evolución de comisiones, comparación de ROAS por plataforma y funnel de conversión.
- Indicadores por producto y tablas operativas de productos y plataformas.
- Alertas, oportunidades y listados ordenados.
- Interfaz en español, diseño adaptable y navegación a las secciones del dashboard.

## Tecnologías

- **HTML5:** estructura y datos de ejemplo en `index.html`.
- **Tailwind CSS v4:** compilación local con `@tailwindcss/cli`; `src/input.css` es la entrada y `src/output.css` el archivo generado.
- **Chart.css:** estilos para gráficos basados en tablas HTML; se carga desde jsDelivr.
- **Google Fonts:** tipografías Manrope y Space Grotesk, cargadas remotamente.
- **Python 3 + Flask:** servidor de desarrollo en `server.py`, en el puerto 3000.
- **Node.js/npm:** instalación y ejecución de Tailwind CLI.

No hay un framework de aplicación JavaScript ni una capa de datos/API. Los filtros y valores del dashboard son contenido estático de muestra.

## Requisitos

- Node.js y npm
- Python 3
- Flask (`pip install flask`)
- Conexión a internet para cargar Google Fonts y Chart.css desde sus CDNs

## Ejecutar en local

Desde la raíz del repositorio:

```bash
npm install
npm run build
pip3 install flask
npm run serve
```

Abre **http://localhost:3000**. El servidor escucha en `0.0.0.0:3000`; según el entorno, el puerto también podría ser accesible desde un contenedor de desarrollo u otro dispositivo.

### Flujo de desarrollo

En una terminal, inicia Tailwind en modo observación:

```bash
npm run dev
```

En otra terminal, inicia el servidor:

```bash
npm run serve
```

Tailwind vuelve a generar `src/output.css` al detectar cambios en los archivos fuente. Detén el observador con `Ctrl+C`. Para generar una hoja minificada, ejecuta `npm run build`.

## Scripts npm

| Comando | Función |
| --- | --- |
| `npm run dev` | Compila Tailwind desde `src/input.css` a `src/output.css` y observa cambios. |
| `npm run build` | Genera `src/output.css` minificado. |
| `npm run serve` | Inicia el servidor Flask de desarrollo en el puerto 3000. |

## Estructura del proyecto

```text
.
├── index.html       # Estructura del dashboard y datos de muestra
├── server.py        # Servidor Flask para archivos estáticos
├── package.json     # Scripts npm y dependencias de Tailwind
└── src/
    ├── input.css    # Entrada de Tailwind v4
    └── output.css   # CSS generado y enlazado desde index.html
```

## Personalización

- Modifica el contenido y las cifras de ejemplo en `index.html`.
- Cambia allí las clases de Tailwind y recompila (o mantén `npm run dev` activo).
- Añade imports o CSS propio en `src/input.css`.
- Los gráficos de Chart.css (`charts-css line` y `charts-css bar`) y sus valores están definidos en el HTML.
- Para trabajar sin conexión o alojar los recursos localmente, sirve Chart.css y las fuentes desde el proyecto y actualiza sus etiquetas `<link>`.

## Consideraciones

- `server.py` está pensado para desarrollo local, no para producción; Flask se ejecuta con el modo debug activado.
- El dashboard es estático: no implementa filtrado funcional, autenticación, persistencia ni actualización de datos en vivo.
- `src/output.css` es un archivo generado; recompílalo después de modificar las clases de Tailwind.
