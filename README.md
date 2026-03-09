# 🌍 Portal de Fichas Departamentales de Riesgo - UNGRD

Este proyecto centraliza y automatiza la generación de las **Fichas Departamentales de Caracterización de Escenarios de Riesgo** de la UNGRD. Convierte documentación técnica colaborativa (`.docx`) en un ecosistema web interactivo desarrollado con **Quarto**, permitiendo una consulta ágil y profesional de la información de riesgo en Colombia.

## 🚀 Flujo de Automatización (CI/CD)

El sistema opera mediante un pipeline integrado que asegura que la web siempre refleje la última versión de los documentos técnicos:

1.  **Origen de Datos (Google Drive):** Los especialistas técnicos mantienen las fichas en archivos Word (`.docx`) dentro de carpetas compartidas.
2.  **Extracción y Transformación (Google Colab):**
    - Un script especializado en **Google Colab** actúa como motor ETL.
    - Descarga los documentos de Drive y utiliza **Pandoc** para la conversión base a Markdown.
    - Realiza una limpieza profunda mediante Python (regex): elimina TOCs estáticos, estandariza tablas en formato Grid, y extrae imágenes a rutas locales.
    - **Segmentación:** El script divide el documento original en capítulos (`01_capitulo.qmd`, `02_capitulo.qmd`, etc.) para mejorar la navegación y carga del sitio.
3.  **Control de Versiones (GitHub):** El script de Colab realiza un `push` automático de los archivos procesados a este repositorio.
4.  **Generación de Sitio (GitHub Actions):** Al detectar cambios en `main`, un workflow dispara la compilación de Quarto, aplicando estilos SASS personalizados y generando el sitio estático en la carpeta `docs/`.
5.  **Despliegue:** El sitio se publica automáticamente en **GitHub Pages**.

## 📂 Estructura del Repositorio

La arquitectura del proyecto está optimizada para la publicación multilibro de Quarto:

```text
fichas-ungrd/
├── _quarto.yml               # Configuración global del sitio (menús, temas, búsqueda)
├── custom.scss               # Identidad visual corporativa (colores UNGRD, tipografías, tablas)
├── index.qmd                 # Página de inicio del portal
├── fichas/                   # Directorio raíz de contenido técnico
│   └── [departamento]/       # Carpeta por cada departamento (ej: cordoba)
│       ├── _metadata.yml     # Configuración específica del departamento
│       ├── index.qmd         # Portada de la ficha departamental
│       ├── 01_capitulo.qmd   # Secciones desglosadas (Ej: Caracterización General)
│       ├── ...               # Otros capítulos técnicos
│       └── media/            # Imágenes y mapas extraídos del Word original
├── .github/workflows/
│   └── publish.yml           # Pipeline de despliegue automático
├── docs/                     # Archivos finales renderizados (para GitHub Pages)
└── README.md                 # Documentación del sistema
```

## 🎨 Personalización y Estilo

El proyecto utiliza un sistema de estilos avanzado definido en `custom.scss` que incluye:

- **Diseño Premium:** Uso de la fuente _Source Sans Pro_ y banners dinámicos.
- **Cajas Especializadas:** Estilos para "Resumen", "Abstract" y "Callouts" de importancia.
- **Optimización de Medios:** Centrado automático de figuras, sombras elegantes y títulos en negrita.
- **Tablas Profesionales:** Formateo automático de tablas con encabezados destacados y tipografía Arial para máxima legibilidad.

## 🛠️ Tecnologías Core

- **Quarto:** Framework de publicación científica para el renderizado del sitio.
- **Python (Google Colab):** Para la automatización del procesamiento de texto y gestión de archivos.
- **SASS/SCSS:** Para la personalización profunda de la interfaz de usuario.
- **GitHub Actions:** Orquestación de la integración continua.
