---
schema: foundry-doc-v1
type: topic
content_type: topic
index_group: brand-surface
category: design-system
slug: brand-family-swatch
short_description: "A taxonomy-agnostic component pairing a color-coded dot with a semantic label to identify anchor-family categories, with per-deployment colors resolved at runtime rather than shipped as a fixed taxonomy."
title: "Brand-family swatch"
paired_with: brand-family-swatch.es.md
state: authoritative
status: active
audience: vendor-public
bcsc_class: current-fact
language_protocol: DESIGN-COMPONENT
authored: 2026-04-30
last_edited: 2026-05-25
---

The brand-family swatch is a taxonomy-agnostic visual classification component: a color-coded dot paired with a semantic label, so that category membership is legible at a glance without relying on color alone. Family identifiers resolve through a runtime configuration rather than a code change, so each deployment supplies its own family list and colors — the three families shown throughout this article (Department, Hardware, Warehouse Club) are the component's baseline defaults, not a fixed taxonomy. The [[app-orchestration-gis|platform's GIS surface]], part of the [[location-intelligence-platform|location intelligence platform]], is one reference deployment: it supplies its own real anchor-family taxonomy through this same runtime mechanism to drive the [[retail-co-location-tier-methodology|retail co-location tier methodology]]'s tier visualization, rather than using the baseline defaults shown here.

## Visual representation

The brand-family swatch standardizes how anchor categories appear across map markers, tabular filters, and detail drawers. A color-coded identifier paired with a semantic label ensures accessible data density. The component decouples presentation from the underlying taxonomy, resolving family identifiers through a runtime JSON configuration — the [[app-orchestration-gis|GIS surface]] reference deployment supplies its own taxonomy this way, rather than the component shipping one taxonomy for every deployment.

## Usage guidelines

### Deployment scenarios
- **Map Markers**: Functions as the visual foundation for anchor markers, using color-coded dots to signal family affiliation.
- **Data Filtering**: Serves as the interactive primitive within filter rows (typically paired with a checkbox).
- **Detail Overlays**: Provides high-level categorization within side drawers and header chips.
- **Cluster Analysis**: Employs a concentric ring variant to represent family distribution within aggregate map clusters.

### Constraints

The component is reserved for taxonomic classification. It must not be used for binary state indicators, transient system feedback, or non-taxonomic tagging, which are serviced by the Tag and Status Indicator components.

## Technical specifications

### Anatomy and composition
- **Indicator**: A 12px (default) or 24px (marker) circular dot using family-specific color tokens.
- **Label**: A taxonomy-resolved display name (e.g., "Warehouse Club").
- **Accessibility Layer**: An `aria-label` that combines the dot and label semantics, ensuring the visual indicator is hidden from screen readers to prevent redundant announcements.

### Interaction model
The swatch is natively static. Interactivity is inherited from its parent container (e.g., a filter button or map feature). On map surfaces, the component supports a reveal-by-zoom behavior: cluster-centroid rings are intended to render at low zoom levels, transitioning to individual swatches at higher magnifications.

## Accessibility and compliance
The component is engineered to meet WCAG 2.2 AA standards:
- **Redundant Signaling**: Color is never the sole channel for information; labels provide primary semantic meaning.
- **High-Contrast Support**: In Windows High Contrast Mode or `forced-colors` environments, the dot reverts to system link colors while the label maintains text integrity.
- **Luminance Contrast**: Family color tokens are validated for a minimum 3:1 contrast ratio against both light and dark map basemaps.

## Design tokens (DTCG)

The dot is inline CSS, not a sized token — `.ps-swatch__dot` is hardcoded to 10px by default and 24px for the map-marker variant. The component references four shared tokens (`{semantic.ink-primary}`, `{semantic.ink-secondary}`, `{primitive.space.05}`, `{primitive.radius.sm}`) plus brand-family colors, which are deployment-specific and set at runtime rather than shipped in the primitive token bundle. The three baseline defaults ship as CSS fallbacks for a deployment that hasn't supplied its own taxonomy:

| Value | Description |
| :--- | :--- |
| `#0B5FFF` | Department — azure blue (baseline default) |
| `#FF6B00` | Hardware — construction orange (baseline default) |
| `#00875A` | Warehouse Club — warehouse green (baseline default) |

These are defaults, not a closed set — a deployment extends or replaces the family list through its own runtime taxonomy file rather than by editing the component.

## Planned extensions
Future iterations are intended to include:
- **Pattern Infills**: Planned support for geometric patterns within the dot to enhance distinguishability for users with advanced color vision deficiencies.
- **Dynamic Pie Charts**: Research is underway to transition the cluster-centroid ring into a dynamic donut chart once cluster density crosses a configured threshold.

## See also

- [[brand-typography]] — the platform's print typography standards that pair with this visual identity system
- [[app-orchestration-gis]] — the GIS analytics engine, one reference deployment of this component with its own real anchor-family taxonomy
- [[location-intelligence-platform]] — the location intelligence platform that hosts that reference deployment
- [[retail-co-location-tier-methodology]] — the tier methodology whose real tier rankings, on that deployment, drive its own swatch color assignments
