# 📊 Análisis DAR — Solución basada en Proxy-Caché para el GRID

Fuente LaTeX del **Análisis DAR (Decision Analysis and Resolution)** aplicado a las
tecnologías de **proxy-caché** y **almacenamiento de archivos**, en el marco del proyecto
*Marco operacional para una solución basada en proxy-caché en la infraestructura del
Grupo de Investigación GRID de la Universidad del Quindío*.

---

## 👥 Autores

- Santiago Quintero Uribe
- Juan Manuel Perdomo Cárdenas
- Andrés Felipe Zúñiga Zuluaga

Universidad del Quindío · Facultad de Ingeniería · Ingeniería de Sistemas y Computación
Armenia, Quindío, 2025

---

## 🧮 Contenido del análisis

El documento consolida la evaluación de 14 herramientas de proxy-caché y 22 de
almacenamiento, valoradas de forma independiente por cada integrante sobre siete
criterios ponderados:

| Criterio | Peso |
| --- | --- |
| Rendimiento técnico | 25 % |
| Escalabilidad | 20 % |
| Soporte y mantenimiento | 20 % |
| Adopción y madurez | 10 % |
| Observabilidad | 10 % |
| Adecuación al contexto GRID | 10 % |
| Riesgo tecnológico | 5 % |

Escala de valoración: 1 (bajo) a 3 (alto). La puntuación DAR es la suma ponderada.

---

## 📁 Estructura del repositorio

```
.
├── main.tex                     # Documento principal
├── portada.tex                  # Portada académica
├── config/
│   └── preambulo.tex            # Paquetes, colores y estilos de tabla
├── secciones/
│   ├── 01-plantilla-evaluacion.tex
│   ├── 02-analisis-por-integrante.tex
│   └── 03-consolidacion-resultados.tex
├── logos/
│   └── logo_uniquindio.png
├── imagenes/                    # Figuras del documento
├── .github/workflows/
│   └── compilar-latex.yml       # Compilación automática del PDF
└── .gitignore
```

---

## ⚙️ Compilación

**Local**

```bash
latexmk -pdf main.tex
```

o, sin `latexmk`:

```bash
pdflatex main.tex
pdflatex main.tex   # segunda pasada: resuelve las referencias cruzadas
```

**Overleaf**: sube el repositorio completo o impórtalo desde GitHub y fija `main.tex`
como documento principal.

**GitHub Actions**: cada `push` a `main` compila el documento y publica `main.pdf`
como artefacto descargable en la pestaña *Actions*.

---

## 🧾 Convenciones del documento

- Las leyendas de las tablas van **debajo** de cada tabla.
- Las tablas no se parten entre páginas: se colocan con `[H]` y pasan completas a la
  página siguiente si no caben.
- Cada tabla tiene su `\label{tab:...}` y se referencia en el texto con `\ref{}`.
