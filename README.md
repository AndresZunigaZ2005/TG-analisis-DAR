# 📊 Resumen de la caracterización de las Tecnologías Proxy-Caché y Almacenamiento de Archivos

Fuente LaTeX del análisis **DAR (Decision Analysis and Resolution)** del modelo CMMI
aplicado a la selección de tecnologías de proxy-caché y almacenamiento de archivos de
gran tamaño, en el marco del proyecto *Marco operacional para una solución basada en
proxy-caché en la infraestructura del Grupo de Investigación GRID de la Universidad del
Quindío*.

---

## 👥 Autores

- Santiago Quintero Uribe
- Juan Manuel Perdomo Cárdenas
- Andrés Felipe Zúñiga Zuluaga

Universidad del Quindío · Facultad de Ingeniería · Ingeniería de Sistemas y Computación
Armenia, Quindío, 2026

---

## 🧮 Alcance del análisis

Se evaluaron **14 tecnologías de proxy-caché** y **22 de almacenamiento**, valoradas de
forma independiente por cada integrante sobre siete criterios ponderados:

| Criterio | Peso |
| --- | --- |
| Rendimiento técnico | 25 % |
| Escalabilidad | 20 % |
| Soporte y mantenimiento | 20 % |
| Adopción y madurez | 10 % |
| Observabilidad | 10 % |
| Adecuación al contexto GRID | 10 % |
| Riesgo tecnológico | 5 % |

Escala: 1 (muy limitado), 2 (aceptable), 3 (excelente / líder). La puntuación DAR es la
suma ponderada, y los 26 criterios individuales se detallan en la sección 4.

---

## 📁 Estructura del repositorio

```
.
├── main.tex                            # Documento principal (aquí se unifica todo)
├── portada.tex                         # Portada académica (datos parametrizados)
├── config/
│   └── preambulo.tex                   # Paquetes, colores y estilo de tablas
├── secciones/
│   ├── 01-metodologia-evaluacion.tex
│   ├── 02-criterios-evaluacion.tex     # 7 subsecciones, 26 criterios
│   ├── 03-analisis-dar.tex             # Tablas 3-10
│   ├── 04-plantilla-evaluacion.tex     # Tablas 1-2
│   ├── 05-tecnologia-ganadora.tex
│   └── 06-referencias.tex
├── logos/
│   └── logo_uniquindio.png
├── imagenes/                           # Figuras del documento
├── .github/workflows/
│   └── compilar-latex.yml              # Compila el PDF en cada push
└── .gitignore
```

**Para agregar una sección nueva:** crea el archivo en `secciones/` y añade su `\input`
al final de la lista en `main.tex`. No hay que tocar nada más.

---

## ⚙️ Compilación

**Local (VS Code + LaTeX Workshop)**

```bash
pdflatex main.tex
pdflatex main.tex   # segunda pasada: resuelve el índice y las referencias a tablas
```

La segunda pasada no es opcional: sin ella la tabla de contenido sale vacía y las
referencias a tablas aparecen como `??`.

**GitHub Actions:** cada `push` a `main` compila el documento y publica `main.pdf` como
artefacto descargable en la pestaña *Actions*.

---

## 🧾 Convenciones del documento

- Las leyendas de las tablas van **debajo**, configurado en `config/preambulo.tex`.
- Las tablas **no se parten entre páginas**: se colocan con `[H]` y pasan completas a la
  página siguiente si no caben.
- Las tablas se referencian con `\ref{tab:...}`, nunca escribiendo "Tabla 5" a mano. Así
  la numeración se ajusta sola si se reordenan.
- Las cabeceras de tabla multilínea usan `\thead{Texto\\Texto}`, no `\makecell` con
  `\textbf` (esa combinación no compila).
- La primera columna de las tablas es `p{}` con texto plano. No usar `\makecell` ahí:
  crea una tabla interna que ignora el ancho de la columna y desborda la página.
