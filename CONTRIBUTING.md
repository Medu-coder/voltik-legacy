Guía para que cualquier herramienta IA navegue el repositorio voltik.es

Esta guía está diseñada para que un agente de IA pueda explorar, comprender y modificar el repositorio de manera eficiente y segura.

⸻

1. Contexto del proyecto
	•	Tipo: Sitio web estático (HTML + CSS) desplegado con GitHub Pages.
	•	Objetivo: Presentar los servicios de instalaciones eléctricas de Voltik en Córdoba (España).
	•	Tecnologías: HTML (~65%) y CSS (~35%).

Tip: Antes de cambiar nada, confirma que el comportamiento del sitio funciona localmente y en producción (GitHub Pages + dominio personalizado).

⸻

2. Estructura de archivos y carpetas (mapa rápido)

/
├── index.html           # Página de inicio (entry point principal)
├── styles.css           # Hoja de estilos global histórica
├── base.css             # Estilos base/reset/variables
├── components.css       # Estilos de componentes reutilizables
├── layout.css           # Estilos de estructura y layout general
├── assets/              # Imágenes, iconos, etc.
├── blog/                # Entradas del blog (formato a verificar: .html/.md)
├── _includes/           # Partials o fragmentos HTML (si se usan)
├── favicon.ico          # Icono del navegador
└── CNAME                # Configuración de dominio personalizado (voltik.es)

Nota: Confirma que el orden de carga de CSS (link tags en index.html) respete la cascada deseada: base.css → layout.css → components.css → styles.css (o el orden actual si se justifica).

⸻

3. Orden recomendado de exploración
	1.	README.md: Resumen del proyecto, instrucciones básicas.
	2.	index.html: Entrada principal; identifica cómo se importan CSS y assets.
	3.	Hojas de estilo (base.css, layout.css, components.css, styles.css):
  	  •	Variables globales, resets y tipografías.
  	  •	Clases reutilizables y específicas.
	4.	blog/: Verifica el patrón de los posts (nomenclatura, extensión, metadatos).
	5.	_includes/: Comprueba si se está usando Jekyll u otro sistema de plantillas.
	6.	CNAME: Revisa el dominio y asegúrate que el despliegue esté correcto.

⸻

4. Flujo de trabajo sugerido

Local

git clone https://github.com/Medu-coder/voltik.es.git
cd voltik.es
python -m http.server 8000   # o npx serve

Visita http://localhost:8000 para revisar los cambios.

Despliegue
	•	El sitio se publica con GitHub Pages.
	•	Verifica en Settings → Pages la rama usada (normalmente main).
	•	El archivo CNAME apunta el dominio voltik.es a GitHub Pages (revisar DNS si fuese necesario).

⸻

5. Heurísticas de navegación y edición
	•	Leer siempre el README primero para entender el propósito y pautas ya documentadas.
	•	Buscar patrones de clases (class="") para mapear componentes y estilos.
	•	Revisar si hay _config.yml o .nojekyll para saber si Jekyll está activo.
	•	Confirmar el formato del blog: si hay front matter YAML (---), GitHub Pages procesará Jekyll por defecto.
	•	Cuidar el orden CSS para no romper jerarquías de estilos.

⸻

6. Checklist previo a cada commit
	•	Previsualizar localmente.
	•	Verificar links relativos y absolutos.
	•	Mantener consistencia y convenciones de nombres.
	•	Confirmar que GitHub Pages no se rompe tras el cambio.
	•	Usar mensajes de commit claros (feat:, fix:, chore:, etc.).
