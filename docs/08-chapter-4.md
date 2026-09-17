# **Chapter IV: Product Design**
## **4.1. Style Guidelines**
En esta sección se documentan las decisiones de diseño visual e interacción adoptadas por el equipo StockIA, con el objetivo de mantener una experiencia consistente entre el Landing Page y la futura Web Application. Estas decisiones se traducen en un conjunto de variables y componentes reutilizables implementados directamente en el proyecto.

### **4.1.1. General Style Guidelines**
El equipo estableció un repositorio central de assets (logos, tipografías, paleta de colores e iconografía) mediante variables CSS (custom properties) definidas en `styles.css`, con el fin de mantener consistencia visual entre el Landing Page y la futura Web Application de StockIA.

La arquitectura de estilos reutiliza la estructura de un sistema de diseño previo del equipo (mismo patrón de variables y componentes), retomada con una paleta propia para StockIA.

---

## Branding

El branding de StockIA, producto de la startup DataBite Corp, se centra en transmitir tecnología aplicada a la sostenibilidad y precisión operativa.

El naming combina “Stock” (inventario) e “IA” (inteligencia artificial), reforzado por los valores de marca declarados en el sitio:

- **Innovación**
- **Precisión**
- **Sostenibilidad**
- **Confiabilidad**
- **Cercanía**

---

## Typography

Se definieron dos familias tipográficas provenientes de Google Fonts:

- **Inter:** tipografía base para todo el cuerpo de texto (`body`), seleccionada por su alta legibilidad en interfaces orientadas a datos.
- **Orbitron:** tipografía de acento (`.brand-font`), utilizada exclusivamente para el logotipo/nombre de marca y elementos que refuerzan la identidad tecnológica del producto, como la numeración de pasos en la sección “Cómo funciona”.

### Jerarquías tipográficas

| Elemento | Tipografía | Peso | Tamaño | Color |
|---|---|---:|---:|---|
| Heading 1/2/3/4 | Inter | 700 | Según jerarquía | `var(--primary)` |
| Body | Inter | 400 | 15px | `var(--text-muted)` |
| Caption / Labels | Inter | 400/700 | 11–13px | Según componente |

Las etiquetas y badges utilizan mayúsculas y `letter-spacing` para facilitar su identificación visual.

---

## Colors

### Colores principales

| Categoría | Variable | Valor | Uso |
|---|---|---|---|
| Primario | `--primary` | `#16332B` | Identidad tecnológica y sostenibilidad |
| Primario oscuro | `--primary-dark` | `#0E211B` | Estados oscuros y contraste |
| Primario hover | `--primary-hover` | `#1F4438` | Estado hover |
| Acento | `--accent` | `#E2673B` | CTAs y elementos destacados |
| Acento oscuro | `--accent-dark` | `#C6522A` | Estado active/hover |
| Gris | `--gray` | `#5B6B66` | Textos y elementos secundarios |
| Gris claro | `--gray-50` | `#F6F8F6` | Fondos suaves |
| Gris 100 | `--gray-100` | `#F1F4F2` | Fondos secundarios |
| Borde | `--gray-border` | `#E4E8E6` | Bordes y divisores |
| Blanco | `--white` | `#FFFFFF` | Fondos principales |
| Texto | `--text` | `#16211D` | Texto principal |

### Colores semánticos

Los colores semánticos se utilizan principalmente en alertas de inventario y funcionalidades relacionadas con IoT:

| Estado | Color | Uso |
|---|---|---|
| Éxito | `#22C55E` | Stock disponible / estado correcto |
| Advertencia | `#FACC15` | Stock bajo / situación preventiva |
| Peligro | `#EF4444` | Stock crítico / alerta importante |

Cada color semántico cuenta además con una variante `light` para utilizarse como fondo de badges y alertas.

---

## Spacing

El sistema de espaciado y radios está definido mediante variables CSS reutilizable.

- Radios de borde escalonados desde 4px hasta 38px (`--r-xs` a `--r-xl`).
- Espaciado vertical estándar entre secciones: 5rem (`--section-y`).
- En dispositivos móviles, el espaciado vertical se reduce a 3.5rem para aprovechar mejor el espacio disponible.

---

## Tono de comunicación

| Característica | Definición |
|---|---|
| Formal / Casual | Tendencia a Formal |
| Serio / Divertido | Serio |
| Respetuoso / Irreverente | Respetuoso |
| Entusiasta / Sereno | Entusiasta, manteniendo un tono profesional |

El tono está orientado principalmente a dueños y administradores de restaurantes que toman decisiones operativas. Se priorizan datos concretos y beneficios medibles, por ejemplo:

- **“-35% desperdicio”**
- **“+18% margen operativo”**

---
### **4.1.2. Web Style Guidelines**
A partir de los principios generales definidos en la sección anterior, se establecieron los estándares visuales y de interacción específicos para las interfaces web responsivas de StockIA, aplicables tanto al Landing Page como a la futura Web Application.
## Componentes UI

Se desarrolló un sistema de componentes propio directamente en CSS. Entre los principales componentes se encuentran:

- **Botones:** `.btn-primary`, `.btn-accent`, `.btn-outline`, `.btn-ghost`
- **Cards:** `.feat-card`, `.price-card`, `.seg-card`
- **Badges / Tags:** `.section-tag`
- **Formularios:** `.form-input`, `.form-textarea`
- **Toggles:** `.toggle-switch`

Estos componentes permiten mantener una apariencia consistente y facilitan su reutilización en las diferentes vistas del producto.

---

## Breakpoints Responsive

El diseño utiliza tres rangos principales:

| Dispositivo | Breakpoint | Características |
|---|---|---|
| Desktop | `>1024px` | Layout completo mediante grids |
| Tablet | `768px–1024px` | Grids reducidos a 2 columnas |
| Mobile | `<768px` | Navegación colapsada y grids de 1 columna |

En Mobile, la navegación se transforma en un menú hamburguesa y el mockup del dashboard ubicado en el hero se oculta para priorizar el contenido principal.

---

## Estados de interacción

Los componentes contemplan diferentes estados para proporcionar retroalimentación visual:

- **Hover:** elevación sutil mediante `transform: translateY(-1px)` o `translateY(-2px)` acompañada de una sombra.
- **Focus:** anillo de color utilizando `--primary-alpha`.
- **Active:** cambio de fondo mediante `--primary-hover` o `--accent-dark`.

---

## Consistencia visual Landing–Dashboard

De acuerdo con la User Story 1 (Conocer la propuesta de valor de StockIA), al hacer clic en “Optimiza tu inventario”, el usuario debe reconocer la misma paleta y estilo visual entre el Landing Page y la demo del dashboard.

Esta coherencia se mantiene porque el mockup del dashboard integrado en el hero reutiliza las mismas variables de color empleadas en el resto del sitio:

- `var(--primary)`
- `var(--danger)`
- `var(--success)`

De esta manera, el flujo entre el Landing Page y la futura Web Application mantiene una identidad visual unificada.

---

## Accesibilidad visual

Para mejorar la accesibilidad visual se utiliza:

- Fondo `--white (#FFFFFF)` con texto principal `--text (#16211D)`.
- Texto secundario `--text-muted (#5B6B66)` para mantener una lectura clara.
- Los estados críticos utilizan color + texto + ícono simultáneamente, evitando depender únicamente del color para transmitir información.

---

## **4.2. Information Architecture**
### **4.2.1. Organization Systems**
### **4.2.2. Labeling Systems**
### **4.2.3. SEO Tags and Meta Tags**
### **4.2.4. Searching Systems**
### **4.2.5. Navigation Systems**
## **4.3. Landing Page UI Design**
### **4.3.1. Landing Page Wireframe**
### **4.3.2. Landing Page Mockup**
## **4.4. Web Applications UX/UI Design**
### **4.4.1. Web Applications Wireframes**
### **4.4.2. Web Applications Wireflow Diagrams**
### **4.4.2. Web Applications Mock-ups**
### **4.4.3. Web Applications User Flow Diagrams**
## **4.5. Web Applications Prototyping**
## **4.6. Domain-Driven Software Architecture**
### **4.6.1. Design-Level EventStorming**
### **4.6.2. Software Architecture Context Diagram**
### **4.6.3. Software Architecture Container Diagrams**

<img src="/assets/chapter-4/C4/container-diagram.png" alt="C4 Diagram" width="1000"/> <br>

### **4.6.4. Software Architecture Components Diagrams**
## **4.7. Object-Oriented Design Software**
### **4.7.1. Class Diagrams**
## **4.8. Database Design**
### **4.8.1. Database Diagrams**