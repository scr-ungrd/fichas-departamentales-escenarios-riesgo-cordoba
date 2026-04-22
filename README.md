# 🌍 Ficha Departamental de Caracterización de Escenarios de Riesgo - Córdoba

![Quarto](https://img.shields.io/badge/Quarto-v1.4+-0078D4?style=for-the-badge&logo=quarto&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)

Este repositorio contiene la **Ficha Departamental de Caracterización de Escenarios de Riesgo para el departamento de Córdoba**. Es un documento técnico interactivo desarrollado con **Quarto**, que permite una consulta ágil y profesional de la información de riesgo territorial y ambiental.

Para consultar el portal nacional con el mapa interactivo de todos los departamentos, por favor visite nuestra nueva **[Landing Page Global](https://portal-riesgo-colombia.ungrd.gov.co)**.

## ✨ Características de la Ficha

- **Navegación Intuitiva:** Estructura de libro con tabla de contenidos dinámica.
- **Contenido Técnico Detallado:** Incluye aspectos legales, presentación institucional y capítulos especializados de riesgo.
- **Diseño Corporativo:** Estilos SASS (`custom.scss`) que garantizan la identidad visual de la UNGRD.
- **Automatización:** Procesado automáticamente desde fuentes técnicas para asegurar la integridad de la información.

## 🚀 Flujo de Actualización

1.  **Origen:** Los especialistas técnicos mantienen la información en documentos Word estructurados.
2.  **Procesamiento:** Un script ETL transforma el contenido a formato Markdown compatible con Quarto.
3.  **Despliegue:** GitHub Actions compila el libro y lo publica automáticamente.

## 📂 Estructura del Repositorio

```text
fichas-ungrd/
├── _quarto.yml                 # Configuración del libro de Córdoba
├── custom.scss                 # Estilos institucionales (SASS)
├── index.qmd                   # Portada de la ficha de Córdoba
├── 00_legal.qmd                # Marco legal y créditos
├── 00_presentacion.qmd         # Presentación institucional
├── 01_introduccion.qmd         # Introducción a la caracterización
├── 02_capitulo.qmd             # Capítulos técnicos...
├── ...                         # (03 al 07_capitulo.qmd)
├── media/                      # Mapas, gráficos y figuras del departamento
├── .github/workflows/
│   └── publish.yml             # Pipeline de despliegue
└── docs/                       # Sitio web renderizado final
```

## 🛠️ Tecnologías Core

- **Quarto:** Framework de publicación técnica para el renderizado del libro.
- **Python:** Gestión y limpieza de datos técnicos.
- **SASS/SCSS:** Personalización de la interfaz de usuario.
- **GitHub Actions:** Automatización de la integración y despliegue continuo.

---

© 2024 UNGRD - Unidad Nacional para la Gestión del Riesgo de Desastres.
