# Research Diagram Visual Specification

This guide defines a reusable visual system for dense scientific technical-route and system-architecture diagrams. It intentionally contains no source or reference image.

## 1. Visual tokens

| Role | Suggested color |
|---|---|
| Canvas | `#000000` or transparent |
| Card surface | `#FFFFFF` |
| Primary text | `#172338` |
| Secondary text | `#5D6A7D` |
| Hard shadow | `#08276A` at 100% opacity |
| Primary blue | `#087FBD` |
| Mint green | `#08A77A` |
| Amber | `#E7A000` |
| Orange feedback | `#ED720D` |
| Lavender | `#8264B6` |
| Rose | `#D378A8` |
| Pale blue fill | `#DDEFFD` |
| Pale mint fill | `#DFF4EC` |
| Pale lavender fill | `#EEE8F8` |
| Pale orange fill | `#FFF0D8` |
| Dark emphasis bar | `#18212C` |

Use color semantically and consistently. A module keeps the same accent color across its top rule, outline, nested groups, and related connectors.

## 2. Geometry

- Outer card radius: 14–22 px per 1200 px canvas width.
- Inner group radius: 8–14 px.
- Outer stroke: 2–3 px. Inner stroke: 1.5–2 px.
- Hard shadow: duplicate the card silhouette, fill dark navy, offset 4–8 px downward and 2–4 px right. No blur and no glow.
- Outer margin: 3–5% of canvas width.
- Major card gap: 3–5% of canvas height. Internal gap: 1.5–2.5% of canvas width.
- Header height: 18–28% of its card height.
- Primary connector: 4–6 px solid blue with compact triangular arrowhead.
- Feedback connector: 3–5 px orange, dash 10–14 px, gap 7–11 px, compact triangular arrowhead.

## 3. Typography

Use a modern Chinese sans-serif family such as PingFang SC, Noto Sans CJK SC, Source Han Sans SC, or Microsoft YaHei.

- Page or system title: bold, approximately 2.8–3.8% of canvas width.
- Module title: bold, approximately 2.0–2.8% of canvas width.
- Inner label: semibold, approximately 1.4–2.0% of canvas width.
- Supporting line: regular or medium, approximately 1.2–1.7% of canvas width.
- Primary text is dark navy, never pure black on white. Supporting text uses muted blue-gray.
- Center text inside compact modules. Left-align longer explanatory content with consistent insets.
- Do not stretch, outline, bevel, glow, or shadow text.

## 4. Layout families

Choose the family that best matches the user's topology.

### A. Vertical pipeline

Use for a technical route with four to seven sequential stages.

- Stack full-width white cards from top to bottom.
- Put the stage title in a pastel header band.
- Arrange two or three inner groups horizontally inside each stage.
- Place solid blue down arrows in the center gap.
- Route a long orange dashed recovery loop along the outer edge from the final or failure state back to the relevant earlier stage.
- Place a separate pale-orange safety-boundary card below the main flow when system-wide constraints apply to every stage.

### B. Split-label process

Use for a compact end-to-end architecture.

- Each major card has a colored label column occupying roughly 25–30% width and a white content field occupying 70–75%.
- Use one pastel family per stage.
- Put the stage name in the label column and exact technical content in the right field.
- Place success and recovery pills in the final card.

### C. Dual-column architecture

Use for parallel perception/decision paths or model/system layers.

- Use two aligned columns of equal or intentionally weighted width.
- Align card tops and major baselines across columns.
- Use blue arrows for data/state movement and orange arrows for policy gates, rejection, uncertainty, and recovery.
- Prefer direct orthogonal connectors. A diagonal connector is allowed only when it expresses an intentional cross-column dependency and does not cross text.
- Use one dark emphasis bar for a backbone, shared state, or final platform.

## 5. Semantic components

- **Major stage:** white rounded card with colored top rule or pale header band.
- **Algorithm block:** white or very pale tinted inner rectangle with a thin colored outline.
- **State pill:** compact rounded capsule for state, signal, or modality names.
- **Foundation/platform bar:** dark navy or bright blue solid rounded bar with white bold text.
- **Safety/rule block:** orange-outlined white module.
- **Success state:** bright blue solid pill with white text.
- **Failure/recovery state:** white or pale-orange pill with orange outline and dark text.
- **Global boundary:** pale-orange full-width card separated slightly from the main flow.

## 6. Composition rules

- The diagram should be readable as a hierarchy at thumbnail size and readable as technical detail at full size.
- Use one dominant flow direction. Secondary loops must be visually subordinate.
- Keep 70–85% of the usable area occupied; preserve clear outer margins.
- Prefer nested grouping over long unstructured text lists.
- Do not use icons, photographs, people, character illustrations, decorative grids, gradients, glass effects, soft shadows, glows, textures, or ornamental backgrounds.
- Do not crop cards, connector labels, arrowheads, or outer feedback loops.

## 7. Prompt scaffold for image generation

Replace every bracketed field. Keep the style and negative constraints intact.

```text
Create a professional scientific technical-route and system-architecture diagram for [use case].

Canvas: [vertical 4:5 / landscape 16:9 / exact dimensions], pure black or genuinely transparent background.
Title: “[exact title]”.
Topology: [vertical pipeline / split-label process / dual-column architecture].
Modules and exact text:
[ordered modules, nested blocks, states, and outputs]
Directed edges:
[source -> target, with connector label if any]
Feedback or recovery loops:
[source -> target, with exact label]

Visual system: strict flat vector infographic; white rounded rectangular cards; thin semantic color outlines; crisp dark-navy hard shadows offset downward and slightly right with no blur; pale blue, mint, lavender, and pale-orange title bands; modern Chinese sans-serif typography; bold dark-navy headings; muted blue-gray body text. Use small outlined rounded rectangles for algorithms, states, constraints, and signals. Use a dark-navy or bright-blue solid bar only for the shared backbone, validated platform, or final success state.

Connections: solid blue orthogonal arrows for primary data and control flow; orange dashed orthogonal arrows for retry, rejection, abnormal recovery, and feedback. Route connectors around modules and never through text. Keep every arrowhead visible.

Layout: rigorous grid alignment, uniform gaps, generous outer margins, high information density with sufficient whitespace, exact Chinese wording, all elements fully inside the canvas.

Avoid: photos, people, robots as illustrations, icons, decorative illustrations, gradients, glow, soft shadows, glassmorphism, 3D, textures, decorative background, watermark, logos, curved arrows, overlapping labels, unreadably small text, garbled Chinese, or cropped feedback loops.
```

## 8. SVG implementation notes

For precise editable output, use one SVG `viewBox` and group each major card. Draw the hard shadow as an offset duplicate path instead of an SVG blur filter. Draw arrowheads as explicit polygons if the renderer does not preserve marker definitions. Embed a fallback font stack and keep all text as text unless the user requests outlined paths.

Export at 1200×1500 for 4:5 or 1920×1080 for 16:9. Inspect the raster export because some converters omit SVG markers or crop content outside the viewBox.

