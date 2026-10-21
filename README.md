
# Sistema de Trazabilidad y Control de Inventario – Refres Now

## Descripción
Módulo de software que registra en tiempo real el recorrido de la materia
prima y del producto terminado, desde el ingreso a planta hasta la entrega
en los puntos de venta.

## Integrantes
- Luka Sfara – Tecnicatura Universitaria en Programación, UTN

## Documentación
- Diagrama BPMN del proceso de gestión de pedidos:

![Diagrama BPMN del proceso de gestión de pedidos](docs/bpmn_gestion_pedidos.png)

## Backlog Ágil
Tablero del proyecto: [Ver en GitHub Projects](https://github.com/users/Luka-Sfara/projects/4)

![Tablero ágil del proyecto en GitHub Projects](docs/tablero_agil.png)

### Historias de Usuario
- **HU-01** (#3): Como encargado de compras, quiero recibir una alerta cuando el stock de un insumo baje del umbral crítico, para generar la orden de compra antes de que falte.
- **HU-02** (#4): Como responsable de calidad, quiero rastrear un lote desde la materia prima hasta el cliente que lo recibió, para avisar rápido a quién se entregó si hay que retirarlo.
- **HU-03** (#5): Como encargado de distribución, quiero ver el stock real de producto terminado en tiempo real, para organizar los envíos y evitar sobrestock o faltantes en los puntos de venta.

## Declaración de Uso de IA

En este proyecto usé asistentes de IA como **guía de consulta**.

### 1. Estructura típica de la empresa para el diagrama BPMN

- **Herramienta:** Claude
- **Prompt (resumen):** ¿Cómo se organiza típicamente una empresa como Refres Now (producción y distribución a puntos de venta): áreas, roles y actores externos en la gestión de pedidos?
- **Por qué este prompt:** Quise usar la como punto de partida para definir los pools y lanes y tomar yo las decisiones del flujo.
- **Corrección y validación humana:** la respuesta de la IA fue una estructura general de empresa, no específica de Refres Now. La adapté yo: definí qué actores externos van como pools y qué roles internos y comportamientos automatizados del sistema van como lanes, y armé el flujo estándar y las compuertas de decisión para las excepciones del proceso. Validé el resultado contra lo que pedía la consigna (pools, lanes, flujo estándar y compuertas) y contra el material de las entregas anteriores del TP.

### 2. Resolución de un problema de Git (conflicto de merge)

- **Herramienta:** Claude

- **Problema:** en la carpeta `docs/` tenía tres archivos PNG iguales con nombres distintos (`tabler_ agil.png`, `tablero agil.png` y `tablero_agil.png`). Esto generó un conflicto en GitHub Desktop: los archivos aparecían con un triángulo naranja de advertencia y no se podían reemplazar. Al intentar descartar los cambios apareció el error "Failed to discard changes to Recycle Bin".
- **Prompts (resumen):** envié capturas de GitHub Desktop y consulté por qué aparecía la advertencia y cómo resolverla.
- **Corrección y validación humana:** la primera respuesta de la IA atribuyó la advertencia solo a los espacios en los nombres de archivo. Lo contrasté con lo que mostraba GitHub Desktop y era un **conflicto de merge** entre archivos binarios (PNG). Se lo señalé y la solución se corrigió: resolver el conflicto, descartar los cambios sobrantes y conservar una única versión, `tablero_agil.png`

### 3. Flujo de ramas y Pull Requests
Consulté cómo crear el Pull Request, qué escribir en los mensajes de commit y cómo ordenar las ramas ya mergeadas. Apliqué cada paso y lo verifiqué directamente en GitHub.

## Indicadores de Control y Estándares de Desempeño

| Indicador | Cómo se mide | Estándar | Origen |
|---|---|---|---|
| Tiempo de registro de un cambio de estado del inventario | Tiempo entre que se carga el movimiento y queda reflejado en el sistema | Menos de 5 segundos | Meta 1 · HU-03 |
| Capacidad de procesamiento | Registros diarios procesados sin que el tiempo de registro supere el estándar anterior | Al menos 10.000 registros diarios sin degradación de performance | Meta 2 |
| Faltantes y sobrantes de stock en puntos de venta | Casos de faltante o sobrante por mes, comparados con el promedio previo al uso del sistema | Reducción del 30 % en los primeros 6 meses | Meta 3 · HU-01, HU-03 |

**Nota de trabajo:** proyecto individual. Los Pull Requests fueron abiertos, revisados y mergeados por el autor, por lo que no hubo revisión de pares.