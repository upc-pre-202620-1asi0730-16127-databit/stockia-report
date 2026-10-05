# **Chapter III: Requirements Specification**
## **3.1. User Stories**
### Objetivos estratégicos de StockIA
 
| ID | Objetivo estratégico | Métrica (KPI) |
| :---: | :--- | :--- |
| **OE1** | Reducir las mermas de insumos | Valor de insumos desechados ÷ valor de insumos comprados (%) |
| **OE2** | Reducir los quiebres de stock | Insumos agotados durante el servicio por semana |
| **OE3** | Reducir el tiempo de control de inventario | Horas semanales de conteo y cuadre; % de discrepancia entre stock registrado y conteo físico |
| **OE4** | Captar restaurantes interesados desde la Landing Page | Solicitudes de demo ÷ visitas al sitio (%) |
| **OE5** | Lograr la activación de las cuentas nuevas | % de cuentas que registran su primer insumo y su primera receta dentro de las primeras 24 h |
| **OE6** | Asegurar ingresos recurrentes | % de restaurantes con plan activo; % de renovaciones exitosas |
| **OE7** | Proteger la información y el control interno del restaurante | Accesos sin sesión o sin rol permitido = 0; % de acciones administrativas restringidas por rol |

### Epics
 
| Epic ID | Título | Descripción | Objetivo estratégico | Métrica de la épica (KPI) | Ítems relacionados |
| :---: | :--- | :--- | :---: | :--- | :--- |
| **EP01** | Propuesta de valor en la Landing Page | Como dueño o administrador de un restaurante que visita StockIA, quiero entender qué problema resuelve el producto, para quién es y cómo funciona, para decidir en una sola visita si solicito una demo. | OE4 | Clics en un CTA de conversión ÷ visitas al Home (%) | US01, US02, US03 |
| **EP02** | Conversión a demo: planes, confianza y contacto | Como dueño o administrador interesado, quiero comparar planes, conocer al equipo y dejar mis datos de contacto, para pasar de la evaluación a una demo sin llamar a ventas. | OE4, OE6 | Solicitudes de demo ÷ visitas a pricing.html y about.html (%) | US04, US05, US06 |
| **EP03** | Experiencia web bilingüe, accesible y performante | Como visitante o usuario, quiero un sitio y una aplicación que carguen rápido, se adapten a mi dispositivo, estén en mi idioma y puedan usarse con teclado y lector de pantalla, para recorrerlos completos sin abandonarlos. | OE4 | Tasa de rebote del sitio; puntajes Lighthouse de Performance, Accessibility y SEO ≥ 90 | US07, US08, RNF01, RNF02, RNF03, RNF04, RNF05, RNF06, RNF07, RNF10, RNF11 |
| **EP04** | Acceso seguro y cuenta del restaurante | Como dueño o administrador, quiero crear mi cuenta, iniciar sesión y mantener mis datos actualizados, para empezar a usar StockIA el mismo día con la información protegida. | OE5, OE7 | % de registros que llegan al dashboard en el primer intento; accesos sin sesión = 0 | US09, US10, RNF08 |
| **EP05** | Gestión del equipo y permisos | Como administrador, quiero incorporar a mi personal y asignarle un rol, para delegar el registro diario sin perder el control de la gestión del restaurante. | OE7 | % de rutas administrativas restringidas por rol (meta: 100 %); equipos con al menos un administrador (meta: 100 %) | US11 |
| **EP06** | Control de inventario de insumos | Como administrador, quiero registrar mis insumos y ver su estado de stock y vencimiento, para que el inventario del sistema coincida con el físico sin conteos diarios. | OE3, OE1 | % de discrepancia entre stock registrado y conteo físico; insumos vencidos detectados antes de usarse | US12 |
| **EP07** | Recetas y ventas con descuento automático | Como administrador, quiero que cada plato vendido descuente sus insumos según su receta, para eliminar el registro manual del consumo. | OE3, OE2 | % de ventas que actualizan el stock sin registro manual (meta: 100 %) | US13, US14, US15, US20 |
| **EP08** | Dashboard operativo | Como administrador, quiero un resumen diario de mi inventario y mis alertas, para decidir qué reponer o usar antes del servicio. | OE2, OE1 | Tiempo para identificar los insumos críticos del día (meta: ≤ 10 s); quiebres por semana | US16 |
| **EP09** | Alertas y notificaciones | Como administrador, quiero recibir y atender alertas de stock bajo, vencimiento y fallas por los canales que uso, para actuar antes de un quiebre o una merma. | OE2, OE1 | % de alertas críticas entregadas por todos sus canales requeridos; tiempo entre alerta y atención | US17, US21 |
| **EP10** | Predicción de demanda y recomendaciones | Como administrador, quiero anticipar la demanda de los próximos días y aplicar recomendaciones de compra y de menú, para comprar lo necesario antes de los días de mayor venta. | OE2, OE1 | % de recomendaciones aplicadas; quiebres de stock en días pico | US18 |
| **EP11** | Suscripción y planes | Como administrador, quiero elegir, cambiar y pagar mi plan, para mantener el servicio activo según el tamaño de mi restaurante. | OE6 | % de restaurantes con plan activo; % de renovaciones exitosas | US19, US22 |
| **EP12** | Base técnica y despliegue continuo | Como Developer, quiero una base de código organizada, versionada y desplegada automáticamente, para entregar cada incremento verificable en una URL pública. | Habilitador de OE4 a OE7 | % de despliegues exitosos desde la rama de producción; tiempo desde el merge hasta la publicación | TS01, TS02, TS03, TS04, TS05, TS06, TS07, TS08, TS09, TS10, TS11, TS12, TS13, TS14, TS15, TS16, RNF09 |



## **3.2. Impact Mapping**
En la siguiente sección se presenta el Impact Mapping elaborado a partir del user persona principal: el administrador o dueño del restaurante. Este mapa asegura que se construya funcionalidades que realmente aporten valor al negocio y resuelvan los problemas más críticos de nuestro segmento objetivo.

**Business Goal de StockIA:** Gestión de stock y reducción de pérdidas
<p align="center"><img alt="Impact-Map" src="../assets/chapter-3/Impact-map.png" /></p>
<p align="center"><i>Artefacto: Mapa de impacto orientado a la optimización del stock y reducción del desperdicio en restaurantes.</i></p>

## **3.3. Product Backlog**
| # Orden | User Story ID | Título | Descripción | Story Points(1/2/3/5/8) |
| :---: | :--- | :--- | :--- | :---: |
| 1 | **US01** | Conocer la propuesta de valor de StockIA | Como visitante del sitio, quiero ver de inmediato de qué trata StockIA y qué problema resuelve, para decidir en pocos segundos si es relevante para mi restaurante. | 8 |
| 2 | **US20** | Solicitar una demo mediante un formulario de contacto | Como visitante interesado en StockIA, quiero enviar mis datos y una breve descripción de mi restaurante, para que DataBite Corp se contacte conmigo. | 8 |
| 3 | **US21** | Gestionar el inventario de insumos (alta, baja y modificación) | Como administrador, quiero agregar, eliminar y modificar insumos en el inventario, para mantener actualizado el stock de mi restaurante. | 8 |
| 4 | **US25** | Recibir predicción de demanda según históricos y clima | Como administrador, quiero que el sistema prediga la demanda según históricos de ventas y clima, para poder preparar insumos con anticipación. | 8 |
| 5 | **US37** | Recopilar automáticamente los datos de ventas diarias | Como administrador, quiero que el sistema recopile automáticamente los datos de ventas diarias, para que el modelo de Machine Learning pueda analizarlos y detectar patrones de consumo. | 8 |
| 6 | **US38** | Entrenar periódicamente el modelo de predicción de demanda | Como administrador, quiero que el sistema entrene periódicamente el modelo de Machine Learning con datos históricos, para que las predicciones de demanda sean cada vez más precisas. | 8 |
| 7 | **US31** | Pagar o renovar mi suscripción con Stripe o PayPal | Como administrador, quiero pagar mi suscripción con Stripe o PayPal, para poder seguir usando StockIA sin interrupciones. | 8 |
| 8 | **US03** | Conocer estadísticas e indicadores de impacto de StockIA | Como visitante, quiero ver cifras sobre el desperdicio y el impacto económico de usar StockIA, para dimensionar el beneficio potencial en mi negocio. | 5 |
| 9 | **US04** | Identificar si StockIA es para mi rol dentro del restaurante | Como dueño/CEO o administrador/jefe de cocina, quiero identificar contenido dirigido a mi rol, para reconocer que StockIA entiende mis necesidades particulares. | 5 |
| 10 | **US15** | Consultar los planes disponibles y sus características | Como visitante interesado en el precio, quiero ver los planes de StockIA y qué incluye cada uno, para elegir la opción que mejor se ajuste a mi restaurante. | 5 |
| 11 | **US22** | Vincular recetas al inventario con descuento automático de insumos | Como administrador, quiero guardar recetas con ingredientes vinculados al inventario, para que al venderse un plato se descuenten automáticamente los insumos. | 5 |
| 12 | **US23** | Visualizar un dashboard operativo con alertas y métricas clave | Como administrador, quiero ver un dashboard con métricas de stock y alertas, para tomar decisiones rápidas sobre insumos críticos. | 5 |
| 13 | **US26** | Recibir recomendaciones automáticas de ajuste de menú | Como administrador, quiero recibir sugerencias de menú según popularidad y estacionalidad, para ajustar la oferta de mi restaurante. | 5 |
| 14 | **US27** | Recibir alertas de insumos por stock bajo o vencimiento próximo | Como administrador, quiero recibir alertas antes de que falten insumos, para poder comprar con tiempo y evitar quiebres de stock. | 5 |
| 15 | **US28** | Recibir alertas y recomendaciones por WhatsApp | Como empleado, quiero recibir sugerencias y alertas en mi WhatsApp, para poder actuar rápido sin necesidad de entrar al sistema. | 5 |
| 16 | **US29** | Registrarme como nuevo usuario en StockIA | Como nuevo usuario, quiero registrarme en StockIA con mis datos, para poder acceder al sistema y configurar mi restaurante. | 5 |
| 17 | **US30** | Iniciar sesión con mis credenciales | Como usuario registrado, quiero iniciar sesión con mis credenciales, para poder acceder a mi dashboard personalizado. | 5 |
| 18 | **US34** | Consultar la vida útil predeterminada de un insumo mediante una API externa | Como administrador, quiero que el sistema consulte una API externa de vida útil de alimentos, para asignar automáticamente un tiempo de conservación estándar a cada insumo. | 5 |
| 19 | **US36** | Calcular automáticamente la fecha límite de consumo de un insumo | Como administrador, quiero que el sistema calcule automáticamente la fecha límite de consumo según la vida útil registrada, para recibir alertas precisas de vencimiento. | 5 |
| 20 | **RNF11** | Protección de credenciales y datos de pago | Como usuario registrado, quiero que mis credenciales y mis datos de pago se manejen de forma segura, para confiar en la plataforma al usar mi tarjeta o mi cuenta de PayPal. | 5 |
| 21 | **RNF12** | Confiabilidad y trazabilidad de las notificaciones multicanal | Como administrador que depende de alertas por WhatsApp, correo y SMS, quiero que las notificaciones se envíen de forma confiable y quede registro de ellas, para no perder información crítica de mi restaurante. | 5 |
| 22 | **US02** | Ver una vista previa del dashboard de StockIA | Como visitante, quiero ver una representación visual del futuro dashboard, para entender cómo luciría el producto antes de solicitar una demo. | 3 |
| 23 | **US05** | Conocer las funcionalidades principales desde el Home | Como visitante, quiero ver un resumen de las funcionalidades clave de StockIA sin salir del Home, para evaluar rápidamente el alcance del producto. | 3 |
| 24 | **US06** | Conocer los diferenciadores de StockIA | Como visitante, quiero entender qué hace distinto a StockIA de un simple control de inventario, para justificar por qué elegirlo. | 3 |
| 25 | **US07** | Conocer las integraciones externas en evaluación | Como visitante, quiero saber con qué otras herramientas podría integrarse StockIA, para entender qué tan conectado estará con servicios que ya uso. | 3 |
| 26 | **US09** | Ver el video de presentación del producto | Como visitante, quiero ver un video que explique StockIA en acción, para comprender el producto más rápido que solo leyendo texto. | 3 |
| 27 | **US13** | Cambiar el idioma del sitio entre español e inglés | Como visitante que prefiere leer en inglés, quiero cambiar el idioma del sitio, para entender el contenido sin depender de traducción externa. | 3 |
| 28 | **US16** | Comparar precios mensuales y anuales | Como visitante evaluando el costo, quiero alternar entre facturación mensual y anual, para comparar cuánto ahorraría pagando anualmente. | 3 |
| 29 | **US17** | Resolver dudas frecuentes sobre los planes | Como visitante con dudas puntuales, quiero consultar preguntas frecuentes sobre los planes, para resolver objeciones antes de solicitar una demo. | 3 |
| 30 | **US24** | Configurar roles y permisos de los empleados | Como administrador, quiero asignar roles a empleados, para que cada uno tenga permisos adecuados dentro del sistema. | 3 |
| 31 | **US32** | Recibir historial de alertas críticas por correo electrónico | Como administrador, quiero recibir alertas críticas por correo vía SendGrid, para tener un historial documentado de eventos importantes. | 3 |
| 32 | **US33** | Recibir SMS urgentes ante emergencias operativas | Como administrador, quiero recibir SMS críticos vía Twilio, para poder reaccionar rápido ante emergencias en tiempo real. | 3 |
| 33 | **US35** | Editar la vida útil sugerida de un insumo | Como administrador, quiero poder modificar la vida útil sugerida por la API, para ajustarla a las condiciones reales de mi restaurante. | 3 |
| 34 | **RNF01** | Experiencia responsiva en dispositivos móviles y tablets | Como visitante que navega desde el celular o una tablet, quiero que el sitio se adapte a mi pantalla, para poder leer y usar el sitio sin hacer zoom ni desplazamiento horizontal. | 3 |
| 35 | **RNF04** | Carga rápida al ser un sitio estático sin dependencias pesadas | Como visitante con una conexión limitada, quiero que el sitio cargue rápido, para no abandonar la página mientras espera que termine de cargar. | 3 |
| 36 | **RNF05** | Buen posicionamiento en buscadores | Como equipo de DataBite Corp, quiero que cada página tenga metadatos descriptivos, para mejorar la indexación de StockIA en motores de búsqueda. | 3 |
| 37 | **US08** | Explorar vistas ilustrativas de la plataforma | Como visitante, quiero ver ejemplos visuales de las pantallas de StockIA, para imaginar cómo sería usar el producto día a día. | 2 |
| 38 | **US10** | Navegar entre las páginas del sitio | Como visitante, quiero moverme fácilmente entre Inicio, Características, Precios y Nosotros, para explorar el sitio según lo que me interese. | 2 |
| 39 | **US11** | Ver el detalle completo de las funcionalidades de StockIA | Como visitante interesado en profundizar, quiero ver una descripción extendida de cada funcionalidad, para evaluar si el producto cubre mis necesidades. | 2 |
| 40 | **US12** | Entender cómo empezar a usar StockIA | Como visitante interesado en adoptar StockIA, quiero conocer los pasos para comenzar a usarlo, para saber qué esperar antes de solicitar una demo. | 2 |
| 41 | **US14** | Mantener mi idioma preferido al navegar entre páginas | Como visitante que ya eligió un idioma, quiero que esa preferencia se mantenga al ir a otra página, para no reseleccionar el idioma en cada una. | 2 |
| 42 | **US18** | Conocer la misión, visión y valores de DataBite Corp | Como visitante, quiero conocer el propósito y valores del equipo detrás de StockIA, para generar confianza antes de contactarlos. | 2 |
| 43 | **US19** | Conocer al equipo detrás de StockIA | Como visitante, quiero ver quiénes conforman el equipo de DataBite Corp, para saber que hay personas reales respaldando el producto. | 2 |
| 44 | **RNF02** | Contraste y legibilidad accesible | Como visitante, incluyendo personas con baja visión, quiero que los textos tengan suficiente contraste con el fondo, para poder leer el contenido sin esfuerzo adicional. | 2 |
| 45 | **RNF03** | Navegación consistente y predecible entre páginas | Como visitante que recorre varias páginas, quiero encontrar siempre el mismo menú, pie de página y estilo visual, para no perder la orientación. | 2 |
| 46 | **RNF06** | Compatibilidad con navegadores modernos de escritorio y móvil | Como visitante, quiero que el sitio se vea y funcione igual sin importar el navegador que use, para tener una experiencia confiable. | 2 |
| 47 | **RNF07** | Animaciones de entrada que no bloquean la interacción | Como visitante, quiero que las animaciones de aparición sean sutiles y fluidas, para una experiencia moderna sin sentir la página lenta. | 1 |
| 48 | **RNF08** | Identificación clara de contenido pendiente de completar | Como equipo de DataBite Corp, quiero que el contenido de ejemplo esté claramente señalizado, para no publicar por error información ficticia como definitiva. | 1 |
| 49 | **RNF09** | Sistema de diseño reutilizable y centralizado | Como equipo de desarrollo, quiero que colores, tipografías y espaciados estén centralizados en variables CSS, para actualizar la identidad visual desde un solo lugar. | 1 |
| 50 | **RNF10** | Textos traducibles centralizados en un solo archivo | Como equipo de desarrollo, quiero que todos los textos traducibles vivan en un único archivo, para actualizar el contenido sin editar cada página. | 1 |

</br>
<p align="center">
  <img src="../assets/chapter-3/Jira-Epics.png" width="500" alt="Epicas"/>
  <br/><i>Artefacto: Jira para Epics</i>
</p>

<p align="center">
  <img src="../assets/chapter-3/Jira-HU.png" width="500" alt="Historias de Usuario"/>
  <br/><i>Artefacto: Jira para User Storys</i>
</p>

<p align="center">
  <img src="../assets/chapter-3/Jira-Backlog.png" width="500" alt="Product Backlog"/>
  <br/><i>Artefacto: Jira para Backlog Priorizado</i>
</p>

>Acceso a artefacto Jira para el desarrollo de Backlog
<https://laplaceho-22.atlassian.net/jira/software/projects/SCRUM/boards/1?filter=&groupBy=none&atlOrigin=eyJpIjoiOGVhOTM0YjRkNzZkNGEzZWExMmY0ZmQ4MTU1NTcyYmQiLCJwIjoiaiJ9>