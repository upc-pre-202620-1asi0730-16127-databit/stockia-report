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
Esta sección establece las decisiones que dirigen la organización del contenido en el Landing Page y en la futura Web Application de StockIA.

El objetivo es que los diferentes perfiles de usuario —dueños/CEOs, administradores, jefes de cocina, cocineros y meseros— encuentren la información que necesitan de manera rápida y sin perder el contexto.

---
### **4.2.1. Organization Systems**
Esta sección explica en qué partes del producto se aplica cada esquema de organización de contenido y los criterios de categorización utilizados para facilitar la comprensión y localización de la información.

### Organización jerárquica (Visual Hierarchy)

Se aplica principalmente en el Dashboard (US02), donde se priorizan visualmente los insumos críticos y próximos a vencer sobre métricas secundarias de rendimiento.

Esto se refleja en el mockup del hero, donde las alertas en rojo y amarillo aparecen antes que el gráfico de demanda.

### Organización secuencial (Step-by-Step)

Se aplica en la sección “Cómo funciona” del Landing Page y en diferentes flujos de la aplicación.

Los cuatro pasos principales son:

1. **Registra tu restaurante**
2. **Carga tu inventario y recetas**
3. **La IA empieza a aprender**
4. **Recibe alertas y decide**

También se utiliza en los flujos:

- **Solicitar demo (US20)**
- **Registrarme como nuevo usuario en StockIA (US29)**

### Organización matricial

Se aplica principalmente en:

- **Módulo de Inventario (US08):** cruza insumo × estado de stock.
- **Product Portfolio del Landing Page:** organizado mediante pestañas:
  - Todas las vistas
  - Inventario
  - IA & IoT

---

## Categorización

### Categorización por tópicos

La sección “Características” (US05 / `features.html`) se organiza en seis módulos principales:

1. **Inventario Inteligente**
2. **Predicción de Demanda con IA**
3. **Recomendaciones Automáticas**
4. **Monitoreo IoT de Cocina**
5. **Roles y Permisos**
6. **Sostenibilidad y Gamificación**

### Categorización según audiencia (Rol)

El Landing Page distingue dos segmentos principales:

- **Dueños / CEOs**
- **Administradores / Jefes de cocina**

En la Web Application, el contenido se organiza según el rol asignado en **US24**:

- **Administrador:** acceso completo.
- **Empleado:** acceso limitado.

### Categorización cronológica

Se utiliza en:

- Las predicciones de demanda organizadas por día de la semana (US25).
- Las alertas ordenadas según urgencia y proximidad del vencimiento (US22 y US23).

---
### **4.2.2. Labeling Systems**
Se definieron etiquetas para representar cada conjunto de información dentro del producto, priorizando términos simples y directos.

El objetivo es que el usuario pueda asociar rápidamente cada etiqueta con su contenido sin generar ambigüedad.

| Elemento | Etiqueta propuesta | Asociación esperada |
|---|---|---|
| Módulo de gestión de insumos | **Inventario** | Agregar, eliminar y modificar stock (US21) |
| Vínculo receta-insumos | **Recetas** | Composición de platos que descuenta stock automáticamente (US22) |
| Panel principal | **Dashboard** | Métricas de stock, alertas y ahorro semanal (US02) |
| Predicciones del sistema | **Predicción de Demanda con IA** | Proyección de ventas por plato (US25) |
| Sugerencias de compra/menú | **Recomendaciones Automáticas** | Alertas de compra y sugerencias de menú (US26) |
| Notificaciones críticas | **Alertas** | Alertas de insumos críticos y notificaciones multicanal (US27 / US28) |
| Sensores de cocina | **Monitoreo IoT de Cocina** | Puertas abiertas, fallas de equipo y flujo de clientes (US29) |
| Gestión de accesos | **Roles y Permisos** | Asignación de Administrador / Empleado (US24) |
| Planes de pago | **Planes / Precios** | Planes Esencial, Profesional e IoT Completo (US16) |
| Impacto ambiental | **Sostenibilidad y Gamificación** | Métricas de reducción de desperdicio y logros de equipo (US23) |

---
### **4.2.3. SEO Tags and Meta Tags**
A continuación, se presentan los meta tags implementados en cada página principal del Landing Page, incluyendo **Title, Description, Keywords y Author**, con el objetivo de mejorar el posicionamiento en buscadores y la presentación del sitio al compartirse en otros medios.

## Landing Page — Inicio (`index.html`)

```html
<title>StockIA — Inventario Inteligente para Restaurantes</title>
<meta name="description" content="StockIA predice la demanda de tu restaurante con Inteligencia Artificial, controla tu inventario en tiempo real y monitorea tu cocina con sensores IoT.">
<meta name="keywords" content="gestión de inventario, restaurantes, inteligencia artificial, machine learning, IoT, predicción de demanda, DataBite, StockIA, Perú">
<meta name="author" content="DataBite Corp">
<meta name="copyright" content="Copyright DataBite Corp 2026">
```

## Landing Page — Características (`features.html`)
```html
<title>Características — StockIA</title>
<meta name="description" content="Descubre todas las funcionalidades de StockIA: inventario inteligente, predicción de demanda con IA, IoT, roles y más para tu restaurante.">
```

## Landing Page — Precios (`pircing.html`)
```html
<title>Precios — StockIA</title>
<meta name="description" content="Planes de StockIA para un restaurante. Desde funciones básicas hasta predicción con IA y monitoreo IoT completo.">
```

## Landing Page — Nosotros (`about.html`)
```html
<title>Nosotros — StockIA</title>
<meta name="description" content="Somos DataBite Corp, el equipo detrás de StockIA, inventario inteligente para restaurantes.">
```

### **4.2.4. Searching Systems**
Esta sección describe los medios de ayuda que se brindarán al usuario para localizar información dentro del producto, evitando que se sienta perdido frente al volumen de datos manejados en el módulo de inventario.

## Buscador de texto libre

Se implementará un buscador de texto libre en el módulo de Inventario (US21), permitiendo buscar insumos por nombre.

## Filtros combinables

Se podrán aplicar diferentes filtros según el módulo:

- **Estado de stock:** disponible, bajo y próximo a vencer, según US27.
- **Rol:** aplicado en la vista de Roles y Permisos (US24).
- **Tipo de vista:** aplicado en el Portfolio del Landing Page mediante las pestañas:
  - Todas las vistas
  - Inventario
  - IA & IoT

## Ordenamiento de resultados

Los resultados podrán ordenarse según:

- Cantidad de stock.
- Fecha de vencimiento.
- Relevancia o urgencia de la alerta.

Las alertas críticas tendrán prioridad sobre las alertas de nivel medio.

## Presentación de resultados

La presentación se adaptará al dispositivo:

- **Desktop:** mediante tablas.
- **Mobile:** mediante tarjetas.

Los niveles de criticidad utilizarán colores semánticos consistentes con los badges del Landing Page:

- **Rojo (`--danger`):** alerta crítica.
- **Amarillo (`--warning`):** alerta de advertencia.
- **Verde (`--success`):** estado correcto.

---
### **4.2.5. Navigation Systems**
En esta sección se explican las acciones y técnicas que guían al usuario a través del Landing Page y que posteriormente guiarán su recorrido dentro de la Web Application, buscando que pueda cumplir sus objetivos sin perder el contexto de dónde se encuentra.

## Landing Page

El Landing Page cuenta con una navbar superior fija (sticky) con acceso a:

- Inicio
- Características
- Precios
- Nosotros

Además, incluye:

- **Selector de idioma:** ES / EN (US14).
- **Botón “Solicitar demo”:** siempre visible en la esquina superior derecha.

El CTA principal del hero:

> **“Optimiza tu inventario →”**

ancla hacia la sección de demo del dashboard (US01).

El CTA del banner final:

> **“Solicitar demo”**

redirige hacia la sección de contacto ubicada en Nosotros.

## Web Application

La Web Application contará con una navegación adaptada al rol del usuario autenticado.

### Administrador

El Administrador tendrá acceso completo a los siguientes módulos:

- Dashboard
- Inventario
- Recetas
- Predicción de Demanda
- Recomendaciones
- Alertas / IoT
- Roles y Permisos
- Planes

### Empleado

El Empleado contará con una vista reducida y acceso únicamente a las funcionalidades correspondientes a su rol.

Esta organización se encuentra alineada con las funcionalidades presentadas en el Landing Page y con la **US24**.

## Footer como navegación secundaria

El footer se encuentra estructurado en tres grupos principales:

### Producto

- Características
- Precios

### Empresa

- Nosotros

### Legal

- Términos
- Privacidad

El footer está presente en todas las páginas del Landing Page e incluye un enlace directo a **Términos y Condiciones**, según lo establecido en el enunciado del curso (US18).

## Navegación Mobile

En dispositivos móviles:

- Los enlaces del navbar (`.navbar-links`) se ocultan.
- Se habilita un menú hamburguesa.
- Se priorizan los accesos rápidos a **Dashboard** y **Alertas**.

Esta decisión responde a la importancia de las notificaciones críticas, las cuales también pueden enviarse mediante **WhatsApp (US27 / US28)**.

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