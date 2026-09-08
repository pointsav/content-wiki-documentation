---
schema: foundry-doc-v1
type: topic
content_type: topic
index_group: brand-surface
category: design-system
slug: brand-family-swatch
short_description: "Un componente agnóstico respecto a la taxonomía que combina un punto codificado por color con una etiqueta semántica para identificar categorías de familias de anclas, con colores resueltos en tiempo de ejecución por cada implementación en lugar de venir fijados como una taxonomía única."
title: Muestrario de familias de marcas
paired_with: brand-family-swatch.md
state: authoritative
status: active
audience: vendor-public
bcsc_class: current-fact
language_protocol: DESIGN-COMPONENT
authored: 2026-04-30
last_edited: 2026-05-25
---

El muestrario de familias de marca es un componente de clasificación visual agnóstico respecto a la taxonomía: un punto codificado por color combinado con una etiqueta semántica, de modo que la membresía de categoría sea legible de un vistazo sin depender únicamente del color. Los identificadores de familia se resuelven a través de una configuración en tiempo de ejecución en lugar de un cambio de código, por lo que cada implementación define su propia lista de familias y colores — las tres familias mostradas a lo largo de este artículo (Departamental, Ferretería, Club de Compras) son los valores predeterminados de referencia del componente, no una taxonomía fija. La [[app-orchestration-gis|superficie GIS de la plataforma]], parte de la [[location-intelligence-platform|plataforma de inteligencia de ubicación]], es una implementación de referencia: define su propia taxonomía real de familias de anclas a través de este mismo mecanismo en tiempo de ejecución para impulsar la visualización de niveles de la [[retail-co-location-tier-methodology|metodología de niveles de co-ubicación minorista]], en lugar de usar los valores predeterminados mostrados aquí.

## Representación visual

El muestrario de familias de marca estandariza la apariencia de las categorías de anclas en marcadores de mapa, filtros tabulares y paneles de detalle. Un identificador codificado por color combinado con una etiqueta semántica garantiza una densidad de datos accesible. El componente desacopla la presentación de la taxonomía subyacente, resolviendo los identificadores de familia a través de una configuración JSON en tiempo de ejecución — la [[app-orchestration-gis|superficie GIS]], como implementación de referencia, define su propia taxonomía de esta misma manera, en lugar de que el componente venga con una única taxonomía fija para todas las implementaciones.

## Directrices de uso

### Escenarios de implementación
- **Marcadores de Mapa**: Funciona como la base visual para los marcadores de anclas, utilizando puntos codificados por colores para señalar la afiliación familiar.
- **Filtrado de Datos**: Sirve como la primitiva interactiva dentro de las filas de filtro (normalmente emparejada con una casilla de verificación).
- **Superposiciones de Detalles**: Proporciona categorización de alto nivel dentro de los paneles laterales y distintivos de encabezado.
- **Análisis de Conglomerados**: Emplea una variante de anillo concéntrico para representar la distribución familiar dentro de los conglomerados (clusters) agregados del mapa.

### Restricciones
El componente está reservado para la clasificación taxonómica. No debe utilizarse para indicadores de estado binarios, mensajes transitorios del sistema o etiquetas no taxonómicas, que son atendidos por los componentes Tag (Etiqueta) y Status Indicator (Indicador de Estado).

## Especificaciones técnicas

### Anatomía y composición
- **Indicador**: Un punto circular de 10px (predeterminado) o 24px (marcador) que utiliza tokens de color específicos de la familia.
- **Etiqueta**: Un nombre de visualización resuelto por la taxonomía (por ejemplo, "Warehouse Club").
- **Capa de Accesibilidad**: Un `aria-label` que combina la semántica del punto y la etiqueta, garantizando que el indicador visual esté oculto para los lectores de pantalla para evitar anuncios redundantes.

### Modelo de interacción
El muestrario es nativamente estático. La interactividad se hereda de su contenedor principal (por ejemplo, un botón de filtro o una función de mapa). En las superficies de mapas, el componente admite un comportamiento de revelación por zoom: se prevé que los anillos de centroide de conglomerado se representen en niveles de zoom bajos, transicionando a muestrarios individuales en aumentos mayores.

## Accesibilidad y cumplimiento
El componente está diseñado para cumplir con los estándares WCAG 2.2 AA:
- **Señalización Redundante**: El color nunca es el único canal de información; las etiquetas proporcionan el significado semántico principal.
- **Soporte de Alto Contraste**: En entornos de modo de alto contraste de Windows o `forced-colors`, el punto vuelve a los colores del sistema para enlaces mientras la etiqueta mantiene la integridad del texto.
- **Contraste de Luminancia**: Los tokens de color de la familia están validados para una relación de contraste mínima de 3:1 frente a mapas base tanto claros como oscuros.

## Tokens de diseño (DTCG)

El punto es CSS en línea, no un token dimensionado — `.ps-swatch__dot` está fijado en 10px por defecto y 24px en la variante de marcador de mapa. El componente referencia cuatro tokens compartidos (`{semantic.ink-primary}`, `{semantic.ink-secondary}`, `{primitive.space.05}`, `{primitive.radius.sm}`) más colores de familia de marca, específicos de cada implementación y definidos en tiempo de ejecución en lugar de venir incluidos en el paquete de tokens primitivos. Los tres valores predeterminados de referencia se incluyen como respaldo CSS para una implementación que aún no ha definido su propia taxonomía:

| Valor | Descripción |
| :--- | :--- |
| `#0B5FFF` | Department — azul azur (valor predeterminado de referencia) |
| `#FF6B00` | Hardware — naranja construcción (valor predeterminado de referencia) |
| `#00875A` | Warehouse Club — verde almacén (valor predeterminado de referencia) |

Estos son valores predeterminados, no un conjunto cerrado — una implementación amplía o reemplaza la lista de familias mediante su propio archivo de taxonomía en tiempo de ejecución, no editando el componente.

## Extensiones previstas
Se prevé que las futuras iteraciones incluyan:
- **Rellenos con Patrones**: Soporte planificado para patrones geométricos dentro del punto para mejorar la distinción para usuarios con deficiencias avanzadas de visión cromática.
- **Gráficos de Tarta Dinámicos**: Se está investigando la transición del anillo de centroide de conglomerado a un gráfico de dona dinámico una vez que la densidad del conglomerado supere un umbral configurado.

## Véase también

- [[brand-typography]] — los estándares de tipografía de impresión de la plataforma que complementan este sistema de identidad visual
- [[app-orchestration-gis]] — el motor analítico GIS, una implementación de referencia de este componente con su propia taxonomía real de familias de anclas
- [[location-intelligence-platform]] — la plataforma de inteligencia de ubicación que aloja esa implementación de referencia
- [[retail-co-location-tier-methodology]] — la metodología de niveles cuyos rankings reales, en esa implementación, impulsan sus propias asignaciones de color del muestrario
