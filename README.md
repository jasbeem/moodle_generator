# Moodle Generator v2

La aplicación es un generador visual de bloques para Moodle que combina utilidades de personalización, generación de contenidos y extracción semiautomática a partir del código fuente del curso. Está construida con Vite + React + TypeScript, y se orienta a docentes que necesitan crear cabeceras, bloques de gamificación y situaciones de aprendizaje sin escribir de cero el HTML adaptado a Moodle.

## Funcionalidades clave

- **Paleta de asignaturas:** define nombre corto, nombre completo y color para cada asignatura y genera un bloque de estilos que puede pegarse directamente en Moodle.
- **Bloque general:** crea avisos, enlaces importantes y mensajes de bienvenida; permite pegar HTML existente para que extraiga automáticamente enlaces y genere tarjetas coherentes con el color elegido.
- **Bloque de juegos:** arma tarjetas Bootstrap con títulos, descripciones, botones y etiquetas de color; puedes editar la lista de juegos o pegar tu propio HTML.
- **Bloque de situación de aprendizaje:** gestiona teorías, prácticas y lecturas; el editor acorta títulos y genera subtítulos simulando IA, extrae items desde HTML importado y produce acordeones con CTA adaptados al color de la materia.
- **Previsualización + exportación:** cada bloque muestra una vista previa en tiempo real, copia al portapapeles y descarga directa como archivo HTML.
- **Automatismos ligeros:** detecta HTML de Moodle para rellenar enlaces y recursos, genera textos de bienvenida y subtítulos mediante heurísticas locales, y mantiene notificaciones y feedback de usuario.

## Cómo usar

1. Instala dependencias: `npm install`.
2. Lanza el entorno de desarrollo: `npm run dev`.
3. Para producción, ejecuta `npm run build`; el HTML compilado queda en `dist/` y, tras la compilación, `README.md` también se copia dentro de `dist/`.

## Estructura principal

- `App.tsx`: controlador de pestañas, estado de asignaturas y lógica de extracción/edición.
- `utils/templates.ts`: funciones que generan los bloques HTML reutilizables y aplican estilos personalizados.
- `components/`: módulos auxiliares de teoría, ejercicios, lectura y navegación (algunos no están montados en la UI principal).
- `utils/odtGenerator.ts` y `utils/curriculumHelper.ts`: utilidades adicionales para generar documentos ODT y consultar criterios curriculares desde constantes.
