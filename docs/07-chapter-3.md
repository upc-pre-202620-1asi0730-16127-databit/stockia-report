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

### User Stories
 
<table>
<tr><th>Story ID</th><th>Título</th><th>Descripción</th><th>Criterios de Aceptación</th><th>Relacionado con Epic ID</th></tr>
<tr>
<td><strong>US01</strong></td>
<td>Comprender la propuesta de valor y el impacto de StockIA desde el Home</td>
<td>Como visitante del segmento dueños y administradores de restaurantes, quiero entender en el primer pantallazo qué problema de inventario resuelve, cuánto le cuesta hoy el desperdicio a un restaurante y cuál es el siguiente paso, para decidir en menos de 30 segundos si continúo hacia la solicitud de demo.</td>
<td>
<strong>Scenario 1: Mensaje principal visible al cargar</strong><br>
<strong>Given</strong> que el visitante abre index.html en una pantalla de escritorio<br>
<strong>When</strong> la página termina de cargar<br>
<strong>Then</strong> el hero muestra el título con la propuesta de valor, la descripción del producto y el nombre StockIA sin necesidad de hacer scroll<br><br>
<strong>Scenario 2: CTA principal hacia la conversión</strong><br>
<strong>Given</strong> que el visitante está en el hero<br>
<strong>When</strong> hace clic en "Optimiza tu inventario →"<br>
<strong>Then</strong> el sitio lo lleva al banner final "Empieza a optimizar tu inventario hoy"<br>
<strong>And</strong> ese banner ofrece el botón que abre el formulario de contacto en about.html#contacto<br><br>
<strong>Scenario 3: CTA secundario hacia el detalle del producto</strong><br>
<strong>Given</strong> que el visitante quiere saber cómo funciona StockIA antes de contactar<br>
<strong>When</strong> hace clic en "Ver cómo funciona"<br>
<strong>Then</strong> el sitio abre features.html<br><br>
<strong>Scenario 4: Indicadores clave del hero identificados como referenciales</strong><br>
<strong>Given</strong> que el visitante revisa el hero<br>
<strong>When</strong> observa los indicadores debajo de los botones<br>
<strong>Then</strong> el hero muestra tres indicadores: "−25 % desperdicio de alimentos*", "+18 % margen operativo estimado*" y "&lt;5 s descuento de insumos por venta"<br>
<strong>And</strong> los indicadores con asterisco se identifican como cifras referenciales<br><br>
<strong>Scenario 5: Vista previa del dashboard según el ancho de pantalla</strong><br>
<strong>Given</strong> que el visitante abre el Home<br>
<strong>When</strong> el ancho de la pantalla es mayor a 768 px<br>
<strong>Then</strong> el hero muestra el mockup ilustrativo del dashboard junto al texto<br>
<strong>And</strong> con un ancho de 768 px o menos el mockup se oculta y el texto ocupa todo el ancho<br><br>
<strong>Scenario 6: Barra de cuatro indicadores</strong><br>
<strong>Given</strong> que el visitante se desplaza por el Home<br>
<strong>When</strong> llega a la barra de estadísticas<br>
<strong>Then</strong> el sitio muestra cuatro indicadores: "30 %*" de insumos desperdiciados, "1 de 3*" restaurantes sin sistema predictivo, "−20 %*" de pérdidas evitables y "24/7" de monitoreo<br><br>
<strong>Scenario 7: Nota de transparencia visible</strong><br>
<strong>Given</strong> que los indicadores con asterisco son referenciales<br>
<strong>When</strong> el visitante lee la barra<br>
<strong>Then</strong> debajo de los indicadores aparece una nota que los identifica como cifras referenciales en el idioma seleccionado
</td>
<td>EP01 — Propuesta de valor en la Landing Page</td>
</tr>
<tr>
<td><strong>US02</strong></td>
<td>Identificar si StockIA es para mi rol y explorar sus funcionalidades</td>
<td>Como visitante del segmento dueños o jefes de cocina de restaurantes, quiero ver un mensaje dirigido a mi rol, el detalle de cada módulo y los pasos para empezar, para confirmar en una sola visita que StockIA cubre inventario, recetas y alertas antes de contactar al equipo.</td>
<td>
<strong>Scenario 1: Tarjeta para dueños y CEOs</strong><br>
<strong>Given</strong> que el visitante es dueño del restaurante<br>
<strong>When</strong> revisa la sección "¿Para quién es StockIA?"<br>
<strong>Then</strong> encuentra una tarjeta que describe el control de inventario, mermas y rentabilidad<br><br>
<strong>Scenario 2: Tarjeta para administradores y jefes de cocina</strong><br>
<strong>Given</strong> que el visitante dirige la operación diaria<br>
<strong>When</strong> revisa la misma sección<br>
<strong>Then</strong> encuentra una tarjeta que describe recetas, stock de insumos y alertas de vencimiento<br><br>
<strong>Scenario 3: Resumen de funcionalidades en el Home</strong><br>
<strong>Given</strong> que el visitante llega a la sección "Todo lo que necesita tu restaurante"<br>
<strong>When</strong> la sección se muestra<br>
<strong>Then</strong> el sitio presenta seis tarjetas de funcionalidades<br>
<strong>And</strong> ofrece el botón "Ver todas las características →" que abre features.html<br><br>
<strong>Scenario 4: Detalle completo en features.html</strong><br>
<strong>Given</strong> que el visitante abre features.html<br>
<strong>When</strong> la página termina de cargar<br>
<strong>Then</strong> el sitio presenta los seis módulos con su descripción extendida<br><br>
<strong>Scenario 5: Pasos de adopción</strong><br>
<strong>Given</strong> que el visitante quiere saber qué esfuerzo implica empezar<br>
<strong>When</strong> llega a la sección "Empieza en minutos"<br>
<strong>Then</strong> el sitio muestra cuatro pasos numerados desde el registro del restaurante hasta la recepción de alertas<br><br>
<strong>Scenario 6: Cierre hacia la conversión</strong><br>
<strong>Given</strong> que el visitante terminó de revisar features.html<br>
<strong>When</strong> hace clic en el botón del banner final<br>
<strong>Then</strong> el sitio abre el formulario de contacto en about.html#contacto
</td>
<td>EP01 — Propuesta de valor en la Landing Page</td>
</tr>
<tr>
<td><strong>US03</strong></td>
<td>Evaluar diferenciadores, integraciones y vistas del producto</td>
<td>Como visitante del segmento dueños y administradores que compara alternativas, quiero ver qué diferencia a StockIA, con qué servicios se integrará y cómo lucen sus pantallas, para justificar el cambio desde mi cuaderno o Excel sin reunirme todavía con el equipo.</td>
<td>
<strong>Scenario 1: Diferenciadores</strong><br>
<strong>Given</strong> que el visitante llega a la sección "Más que un inventario"<br>
<strong>When</strong> la sección se muestra<br>
<strong>Then</strong> el sitio presenta tres tarjetas con los diferenciadores de StockIA<br><br>
<strong>Scenario 2: Integraciones identificadas como en evaluación</strong><br>
<strong>Given</strong> que el visitante llega a "Se conecta con el ecosistema que ya usas"<br>
<strong>When</strong> revisa las integraciones<br>
<strong>Then</strong> el sitio muestra cuatro tarjetas con la etiqueta "En evaluación"<br>
<strong>And</strong> una nota aclara que la integración definitiva aún no ha sido elegida<br><br>
<strong>Scenario 3: Pestañas del portafolio</strong><br>
<strong>Given</strong> que el visitante está en "La plataforma en acción"<br>
<strong>When</strong> hace clic en una pestaña<br>
<strong>Then</strong> esa pestaña queda resaltada como activa y las demás dejan de estarlo<br><br>
<strong>Scenario 4: Espacio del video del producto</strong><br>
<strong>Given</strong> que el video del producto aún no ha sido publicado<br>
<strong>When</strong> el visitante llega a la sección de video<br>
<strong>Then</strong> el sitio muestra el bloque "Video demostrativo próximamente" sin enlaces rotos
</td>
<td>EP01 — Propuesta de valor en la Landing Page</td>
</tr>
<tr>
<td><strong>US04</strong></td>
<td>Comparar planes y resolver dudas antes de contratar</td>
<td>Como visitante del segmento dueños y administradores, quiero comparar los planes, alternar entre pago mensual y anual y resolver mis dudas frecuentes, para estimar el costo frente a lo que pierdo en mermas y decidir sin contactar a soporte.</td>
<td>
<strong>Scenario 1: Planes con precios en soles</strong><br>
<strong>Given</strong> que el visitante abre pricing.html<br>
<strong>When</strong> la página termina de cargar<br>
<strong>Then</strong> el sitio muestra los planes Esencial (S/ 0), Profesional (S/ 39) e IoT Completo (S/ 79) con sus características<br>
<strong>And</strong> el plan Profesional aparece con la etiqueta "Más popular"<br>
<strong>And</strong> una nota indica que son precios de ejemplo<br><br>
<strong>Scenario 2: Cambio a facturación anual</strong><br>
<strong>Given</strong> que los planes muestran el precio mensual<br>
<strong>When</strong> el visitante activa el interruptor "Anual"<br>
<strong>Then</strong> los precios cambian a S/ 0, S/ 27 y S/ 55 sin recargar la página<br><br>
<strong>Scenario 3: Regreso a facturación mensual</strong><br>
<strong>Given</strong> que el interruptor está en "Anual"<br>
<strong>When</strong> el visitante lo desactiva<br>
<strong>Then</strong> los precios vuelven a S/ 0, S/ 39 y S/ 79<br><br>
<strong>Scenario 4: Apertura de una pregunta frecuente</strong><br>
<strong>Given</strong> que el visitante llega a "Preguntas frecuentes"<br>
<strong>When</strong> hace clic en una pregunta cerrada<br>
<strong>Then</strong> el sitio despliega su respuesta<br><br>
<strong>Scenario 5: Una sola pregunta abierta a la vez</strong><br>
<strong>Given</strong> que una pregunta ya está desplegada<br>
<strong>When</strong> el visitante abre otra pregunta<br>
<strong>Then</strong> el sitio cierra la anterior y muestra solo la nueva respuesta
</td>
<td>EP02 — Conversión a demo: planes, confianza y contacto</td>
</tr>
<tr>
<td><strong>US05</strong></td>
<td>Conocer a DataBite Corp y a su equipo</td>
<td>Como visitante del segmento dueños y administradores, quiero conocer la misión, la visión, los valores y las personas detrás de StockIA, para confiar en el producto antes de compartir los datos de mi restaurante.</td>
<td>
<strong>Scenario 1: Propósito de la startup</strong><br>
<strong>Given</strong> que el visitante abre about.html<br>
<strong>When</strong> la página termina de cargar<br>
<strong>Then</strong> el sitio muestra el mensaje principal y las tarjetas de misión y visión<br><br>
<strong>Scenario 2: Valores de DataBite Corp</strong><br>
<strong>Given</strong> que el visitante llega a "Sobre DataBite Corp"<br>
<strong>When</strong> la sección se muestra<br>
<strong>Then</strong> el sitio presenta la descripción de la startup y sus valores<br><br>
<strong>Scenario 3: Fichas del equipo</strong><br>
<strong>Given</strong> que el visitante llega a "El equipo detrás de StockIA"<br>
<strong>When</strong> la sección se muestra<br>
<strong>Then</strong> el sitio presenta una ficha por integrante<br>
<strong>And</strong> si una ficha contiene datos de ejemplo, el sitio lo indica en una nota visible<br><br>
<strong>Scenario 4: Espacio del video del equipo</strong><br>
<strong>Given</strong> que el video del equipo aún no ha sido publicado<br>
<strong>When</strong> el visitante llega a la sección de video<br>
<strong>Then</strong> el sitio muestra un bloque que indica que el video estará disponible próximamente
</td>
<td>EP02 — Conversión a demo: planes, confianza y contacto</td>
</tr>
<tr>
<td><strong>US06</strong></td>
<td>Solicitar una demo desde el formulario de contacto</td>
<td>Como visitante del segmento dueños y administradores interesado en StockIA, quiero dejar mis datos y los de mi restaurante en un formulario, para que DataBite Corp me contacte y coordinar una demo en una sola interacción.</td>
<td>
<strong>Scenario 1: Acceso al formulario desde cualquier página</strong><br>
<strong>Given</strong> que el visitante está en index.html, features.html o pricing.html<br>
<strong>When</strong> hace clic en el botón del banner "Empieza a optimizar tu inventario hoy"<br>
<strong>Then</strong> el sitio abre about.html en la sección de contacto<br><br>
<strong>Scenario 2: Campos obligatorios incompletos</strong><br>
<strong>Given</strong> que el visitante deja vacío el nombre o el correo<br>
<strong>When</strong> presiona "Enviar solicitud"<br>
<strong>Then</strong> el navegador bloquea el envío e indica el campo obligatorio<br><br>
<strong>Scenario 3: Correo con formato inválido</strong><br>
<strong>Given</strong> que el visitante escribe un correo sin "@"<br>
<strong>When</strong> presiona "Enviar solicitud"<br>
<strong>Then</strong> el navegador bloquea el envío y señala el formato del correo<br><br>
<strong>Scenario 4: Confirmación del envío simulado</strong><br>
<strong>Given</strong> que el visitante completó nombre y correo válidos<br>
<strong>When</strong> presiona "Enviar solicitud"<br>
<strong>Then</strong> el botón cambia a "✓ Enviado" y se deshabilita durante 3 segundos<br>
<strong>And</strong> luego el formulario se limpia<br>
<strong>And</strong> en esta versión el envío es simulado en el navegador y no transmite datos a un servidor
</td>
<td>EP02 — Conversión a demo: planes, confianza y contacto</td>
</tr>
<tr>
<td><strong>US07</strong></td>
<td>Navegar entre las páginas del sitio</td>
<td>Como visitante, quiero un menú y un pie de página consistentes en las cuatro páginas, para llegar a precios o al formulario de demo en máximo dos clics desde cualquier página.</td>
<td>
<strong>Scenario 1: Menú común en las cuatro páginas</strong><br>
<strong>Given</strong> que el visitante está en cualquier página del sitio<br>
<strong>When</strong> observa la barra de navegación<br>
<strong>Then</strong> encuentra los enlaces Inicio, Características, Precios y Nosotros, el selector ES/EN y el botón "Solicitar demo"<br><br>
<strong>Scenario 2: Página actual resaltada</strong><br>
<strong>Given</strong> que el visitante abre pricing.html<br>
<strong>When</strong> la barra de navegación se muestra<br>
<strong>Then</strong> el enlace "Precios" aparece resaltado como página activa<br><br>
<strong>Scenario 3: Regreso al inicio desde el logo</strong><br>
<strong>Given</strong> que el visitante está en una página interna<br>
<strong>When</strong> hace clic en el logo de StockIA<br>
<strong>Then</strong> el sitio abre index.html<br><br>
<strong>Scenario 4: Pie de página común</strong><br>
<strong>Given</strong> que el visitante llega al final de cualquier página<br>
<strong>When</strong> el pie de página se muestra<br>
<strong>Then</strong> presenta las columnas Producto, Empresa y Legal con los mismos enlaces en las cuatro páginas
</td>
<td>EP03 — Experiencia web bilingüe, accesible y performante</td>
</tr>
<tr>
<td><strong>US08</strong></td>
<td>Leer el sitio en inglés o en español</td>
<td>Como visitante, quiero leer el sitio en inglés, su idioma por defecto, o cambiarlo a español y que mi elección se mantenga entre páginas, para evaluar StockIA sin barreras de idioma y sin repetir la selección en cada página.</td>
<td>
<strong>Scenario 1: Inglés como idioma por defecto</strong><br>
<strong>Given</strong> que el visitante abre el sitio por primera vez y no tiene un idioma guardado<br>
<strong>When</strong> la página termina de cargar<br>
<strong>Then</strong> todos los textos marcados para traducción se muestran en inglés (en_US)<br>
<strong>And</strong> el botón "EN" queda resaltado<br><br>
<strong>Scenario 2: Cambio a español</strong><br>
<strong>Given</strong> que el sitio está en inglés<br>
<strong>When</strong> el visitante hace clic en "ES"<br>
<strong>Then</strong> todos los textos marcados para traducción cambian a español latinoamericano (es_419) sin recargar la página<br><br>
<strong>Scenario 3: Regreso a inglés</strong><br>
<strong>Given</strong> que el sitio está en español<br>
<strong>When</strong> el visitante hace clic en "EN"<br>
<strong>Then</strong> todos los textos vuelven a inglés<br><br>
<strong>Scenario 4: Idioma conservado entre páginas</strong><br>
<strong>Given</strong> que el visitante eligió español en index.html<br>
<strong>When</strong> navega a pricing.html<br>
<strong>Then</strong> la página se carga directamente en español<br><br>
<strong>Scenario 5: Idioma conservado en una nueva visita</strong><br>
<strong>Given</strong> que el visitante eligió español y cerró la pestaña<br>
<strong>When</strong> vuelve a abrir el sitio en el mismo navegador<br>
<strong>Then</strong> el sitio se muestra en español
</td>
<td>EP03 — Experiencia web bilingüe, accesible y performante</td>
</tr>
<tr>
<td><strong>US09</strong></td>
<td>Registrar mi restaurante y crear mi cuenta de administrador</td>
<td>Como dueño o administrador de un restaurante, quiero crear mi cuenta con los datos de mi restaurante, para empezar a registrar mi inventario en menos de 5 minutos sin depender de soporte.</td>
<td>
<strong>Scenario 1: Registro exitoso</strong><br>
<strong>Given</strong> que el usuario está en /auth/sign-up<br>
<strong>When</strong> completa nombre, restaurante, correo y contraseña válidos y presiona "Crear cuenta"<br>
<strong>Then</strong> el sistema crea la cuenta con el rol Administrador<br>
<strong>And</strong> inicia su sesión y lo lleva a /app/dashboard<br><br>
<strong>Scenario 2: Datos inválidos</strong><br>
<strong>Given</strong> que el usuario escribe un nombre de menos de 3 caracteres, un correo inválido o una contraseña de menos de 4 caracteres<br>
<strong>When</strong> presiona "Crear cuenta"<br>
<strong>Then</strong> el sistema marca los campos inválidos y no envía el formulario<br><br>
<strong>Scenario 3: Correo ya registrado</strong><br>
<strong>Given</strong> que existe una cuenta con el correo ingresado<br>
<strong>When</strong> el usuario presiona "Crear cuenta"<br>
<strong>Then</strong> el sistema muestra "Ya existe una cuenta con este correo" y no crea una cuenta duplicada<br><br>
<strong>Scenario 4: Falla del servicio</strong><br>
<strong>Given</strong> que la API no responde<br>
<strong>When</strong> el usuario presiona "Crear cuenta"<br>
<strong>Then</strong> el sistema muestra "No se pudo crear la cuenta. Intenta nuevamente." y conserva los datos escritos
</td>
<td>EP04 — Acceso seguro y cuenta del restaurante</td>
</tr>
<tr>
<td><strong>US10</strong></td>
<td>Iniciar sesión y mantener actualizada mi cuenta</td>
<td>Como administrador o empleado registrado, quiero iniciar y cerrar sesión de forma segura y mantener actualizados mis datos y los de mi restaurante, para que nadie acceda sin sesión a la información de mi restaurante y el 100 % de las notificaciones llegue a un contacto vigente.</td>
<td>
<strong>Scenario 1: Inicio de sesión exitoso</strong><br>
<strong>Given</strong> que el usuario tiene una cuenta<br>
<strong>When</strong> ingresa su correo y contraseña correctos y presiona "Iniciar sesión"<br>
<strong>Then</strong> el sistema abre /app/dashboard con su nombre y su rol en la barra superior<br><br>
<strong>Scenario 2: Credenciales incorrectas</strong><br>
<strong>Given</strong> que el usuario escribe un correo o una contraseña incorrectos<br>
<strong>When</strong> presiona "Iniciar sesión"<br>
<strong>Then</strong> el sistema muestra "Correo o contraseña incorrectos." y permanece en la pantalla de inicio de sesión<br><br>
<strong>Scenario 3: Acceso sin sesión</strong><br>
<strong>Given</strong> que no hay una sesión iniciada<br>
<strong>When</strong> alguien intenta abrir una ruta bajo /app<br>
<strong>Then</strong> el sistema lo redirige a /auth/sign-in<br><br>
<strong>Scenario 4: Sesión conservada al recargar</strong><br>
<strong>Given</strong> que el usuario inició sesión<br>
<strong>When</strong> recarga el navegador<br>
<strong>Then</strong> el sistema mantiene su sesión y su rol<br><br>
<strong>Scenario 5: Cierre de sesión</strong><br>
<strong>Given</strong> que el usuario está dentro de la aplicación<br>
<strong>When</strong> presiona "Salir"<br>
<strong>Then</strong> el sistema elimina la sesión guardada y muestra /auth/sign-in<br><br>
<strong>Scenario 6: Cambios guardados</strong><br>
<strong>Given</strong> que el usuario abre /app/profile con su nombre, restaurante y correo precargados<br>
<strong>When</strong> modifica datos válidos y presiona "Guardar cambios"<br>
<strong>Then</strong> el sistema muestra "✓ Perfil actualizado"<br>
<strong>And</strong> la barra superior muestra el nombre actualizado<br><br>
<strong>Scenario 7: Contraseña opcional</strong><br>
<strong>Given</strong> que el usuario deja vacío el campo de nueva contraseña<br>
<strong>When</strong> guarda los cambios<br>
<strong>Then</strong> el sistema conserva su contraseña actual<br><br>
<strong>Scenario 8: Datos inválidos</strong><br>
<strong>Given</strong> que el usuario escribe un correo inválido o un nombre de menos de 3 caracteres<br>
<strong>When</strong> intenta guardar<br>
<strong>Then</strong> el sistema muestra el mensaje del campo y no guarda
</td>
<td>EP04 — Acceso seguro y cuenta del restaurante</td>
</tr>
<tr>
<td><strong>US11</strong></td>
<td>Gestionar el equipo y sus roles</td>
<td>Como administrador, quiero invitar a mi personal, asignarle el rol Administrador o Empleado y dar de baja a quien ya no trabaja conmigo, para delegar el registro de inventario sin exponer la gestión del equipo y mantener el 100 % de las rutas administrativas restringidas por rol.</td>
<td>
<strong>Scenario 1: Invitación exitosa</strong><br>
<strong>Given</strong> que el administrador está en /app/roles<br>
<strong>When</strong> completa nombre, correo y rol del integrante y presiona "Enviar invitación"<br>
<strong>Then</strong> el integrante aparece en la lista del equipo con el rol elegido<br>
<strong>And</strong> la pantalla informa que la cuenta se crea con una contraseña temporal<br><br>
<strong>Scenario 2: Invitación con datos inválidos</strong><br>
<strong>Given</strong> que el administrador deja el nombre vacío o escribe un correo inválido<br>
<strong>When</strong> presiona "Enviar invitación"<br>
<strong>Then</strong> el sistema no crea la cuenta y marca los campos<br><br>
<strong>Scenario 3: Baja de un integrante</strong><br>
<strong>Given</strong> que el administrador presiona "Eliminar" en un integrante<br>
<strong>When</strong> confirma la acción<br>
<strong>Then</strong> el integrante desaparece de la lista y pierde el acceso<br><br>
<strong>Scenario 4: Intento de eliminar la propia cuenta</strong><br>
<strong>Given</strong> que el administrador presiona "Eliminar" en su propia fila<br>
<strong>When</strong> el sistema evalúa la acción<br>
<strong>Then</strong> muestra "No puedes eliminar tu propia cuenta desde aquí." y no elimina nada<br><br>
<strong>Scenario 5: Cambio de rol</strong><br>
<strong>Given</strong> que el administrador está en la lista del equipo<br>
<strong>When</strong> elige otro rol para un integrante<br>
<strong>Then</strong> el sistema guarda el nuevo rol y lo muestra en la lista<br><br>
<strong>Scenario 6: Último administrador protegido</strong><br>
<strong>Given</strong> que el equipo tiene un solo administrador<br>
<strong>When</strong> se intenta eliminarlo o cambiarlo a Empleado<br>
<strong>Then</strong> el sistema muestra "Debe quedar al menos un Administrador en el equipo." y conserva su cuenta y su rol<br><br>
<strong>Scenario 7: Menú del empleado</strong><br>
<strong>Given</strong> que un usuario con rol Empleado inicia sesión<br>
<strong>When</strong> revisa el menú lateral<br>
<strong>Then</strong> no aparece la opción "Roles y permisos"<br><br>
<strong>Scenario 8: Ruta administrativa protegida</strong><br>
<strong>Given</strong> que un Empleado escribe /app/roles en el navegador<br>
<strong>When</strong> intenta abrir la ruta<br>
<strong>Then</strong> el sistema lo redirige a /app/dashboard
</td>
<td>EP05 — Gestión del equipo y permisos</td>
</tr>
<tr>
<td><strong>US12</strong></td>
<td>Registrar y monitorear los insumos del inventario</td>
<td>Como administrador, quiero registrar, editar y eliminar insumos y ver el estado de stock y vencimiento de cada uno, para que el stock del sistema coincida con el físico y detectar en menos de 10 segundos los insumos vencidos, agotados o bajo el mínimo.</td>
<td>
<strong>Scenario 1: Alta de un insumo</strong><br>
<strong>Given</strong> que el administrador está en /app/inventory<br>
<strong>When</strong> completa los datos de un insumo nuevo y presiona "Guardar"<br>
<strong>Then</strong> el insumo aparece en la tabla<br>
<strong>And</strong> su fecha de vencimiento se calcula como la fecha actual más su vida útil en días<br><br>
<strong>Scenario 2: Datos inválidos</strong><br>
<strong>Given</strong> que el administrador deja el nombre vacío, escribe una cantidad, un stock mínimo o un costo negativos, o una vida útil menor a 1 día<br>
<strong>When</strong> presiona "Guardar"<br>
<strong>Then</strong> el sistema marca los campos inválidos y no guarda<br><br>
<strong>Scenario 3: Edición de un insumo</strong><br>
<strong>Given</strong> que el administrador presiona "Editar" en un insumo<br>
<strong>When</strong> cambia sus datos y guarda<br>
<strong>Then</strong> la tabla muestra los valores actualizados<br><br>
<strong>Scenario 4: Eliminación confirmada</strong><br>
<strong>Given</strong> que el administrador presiona "Eliminar" en un insumo<br>
<strong>When</strong> confirma la acción<br>
<strong>Then</strong> el insumo desaparece de la tabla<br>
<strong>And</strong> si cancela, el insumo se conserva<br><br>
<strong>Scenario 5: Insumo vencido</strong><br>
<strong>Given</strong> que la fecha de vencimiento de un insumo es anterior a la fecha actual<br>
<strong>When</strong> se muestra el inventario<br>
<strong>Then</strong> el insumo aparece con el estado "Vencido" en rojo, aunque tenga cantidad disponible<br><br>
<strong>Scenario 6: Insumo agotado</strong><br>
<strong>Given</strong> que un insumo vigente tiene cantidad 0<br>
<strong>When</strong> se muestra el inventario<br>
<strong>Then</strong> el insumo aparece con el estado "Crítico" en rojo<br><br>
<strong>Scenario 7: Insumo bajo el mínimo</strong><br>
<strong>Given</strong> que la cantidad de un insumo vigente es mayor a 0 y menor o igual a su stock mínimo<br>
<strong>When</strong> se muestra el inventario<br>
<strong>Then</strong> el insumo aparece con el estado "Stock bajo" en amarillo<br><br>
<strong>Scenario 8: Estado actualizado tras una venta</strong><br>
<strong>Given</strong> que una venta descuenta un insumo por debajo de su stock mínimo<br>
<strong>When</strong> el administrador vuelve al inventario<br>
<strong>Then</strong> el estado del insumo cambia a "Stock bajo" sin intervención manual
</td>
<td>EP06 — Control de inventario de insumos</td>
</tr>
<tr>
<td><strong>US13</strong></td>
<td>Vincular recetas a los insumos del inventario</td>
<td>Como administrador, quiero registrar la receta de cada plato con las cantidades de insumo que consume, para que el 100 % de las ventas de ese plato descuente el stock sin registro manual.</td>
<td>
<strong>Scenario 1: Receta registrada</strong><br>
<strong>Given</strong> que el administrador está en /app/recipes<br>
<strong>When</strong> escribe el nombre del plato, agrega al menos un insumo con su cantidad y presiona "Guardar receta"<br>
<strong>Then</strong> la receta aparece en la lista con sus ingredientes<br><br>
<strong>Scenario 2: Línea de ingrediente inválida</strong><br>
<strong>Given</strong> que el administrador no seleccionó un insumo o escribió una cantidad de 0 o menos<br>
<strong>When</strong> presiona "Agregar"<br>
<strong>Then</strong> el sistema no agrega la línea a la receta<br><br>
<strong>Scenario 3: Quitar un ingrediente</strong><br>
<strong>Given</strong> que la receta en edición tiene varias líneas<br>
<strong>When</strong> el administrador presiona "Quitar" en una línea<br>
<strong>Then</strong> la línea desaparece del borrador de la receta<br><br>
<strong>Scenario 4: Receta incompleta</strong><br>
<strong>Given</strong> que el plato no tiene nombre o la receta no tiene ingredientes<br>
<strong>When</strong> el administrador intenta guardar<br>
<strong>Then</strong> el sistema no guarda la receta<br><br>
<strong>Scenario 5: Edición y eliminación</strong><br>
<strong>Given</strong> que el administrador edita o elimina una receta y confirma la acción<br>
<strong>When</strong> el sistema procesa el cambio<br>
<strong>Then</strong> la lista de recetas refleja la receta actualizada o eliminada
</td>
<td>EP07 — Recetas y ventas con descuento automático</td>
</tr>
<tr>
<td><strong>US14</strong></td>
<td>Registrar una venta con descuento automático de insumos</td>
<td>Como administrador o empleado, quiero registrar la venta de un plato y que el sistema valide y descuente sus insumos, para que el 100 % de las ventas actualice el stock sin digitación adicional.</td>
<td>
<strong>Scenario 1: Venta con stock suficiente</strong><br>
<strong>Given</strong> que todos los insumos de la receta tienen stock suficiente<br>
<strong>When</strong> el usuario presiona "Simular venta" en el plato<br>
<strong>Then</strong> el sistema registra una venta confirmada en el historial<br>
<strong>And</strong> descuenta de cada insumo la cantidad indicada en la receta<br><br>
<strong>Scenario 2: Venta rechazada por stock insuficiente</strong><br>
<strong>Given</strong> que al menos un insumo de la receta no alcanza<br>
<strong>When</strong> el usuario presiona "Simular venta"<br>
<strong>Then</strong> el sistema muestra "Stock insuficiente para vender" con la lista de insumos faltantes<br>
<strong>And</strong> no registra la venta ni modifica el inventario<br><br>
<strong>Scenario 3: Stock nunca negativo</strong><br>
<strong>Given</strong> que una venta consume exactamente el stock disponible de un insumo<br>
<strong>When</strong> se registra la venta<br>
<strong>Then</strong> el insumo queda en 0 y pasa al estado "Crítico"<br><br>
<strong>Scenario 4: Confirmación visual</strong><br>
<strong>Given</strong> que una venta se registró<br>
<strong>When</strong> el sistema termina de procesarla<br>
<strong>Then</strong> el plato vendido se resalta durante 2 segundos
</td>
<td>EP07 — Recetas y ventas con descuento automático</td>
</tr>
<tr>
<td><strong>US15</strong></td>
<td>Consultar el historial de ventas y anular ventas erróneas</td>
<td>Como administrador, quiero consultar las ventas registradas con su total y anular las ventas registradas por error, para que el historial que alimenta la proyección de demanda refleje solo ventas reales.</td>
<td>
<strong>Scenario 1: Historial de ventas</strong><br>
<strong>Given</strong> que existen ventas registradas<br>
<strong>When</strong> el administrador abre /app/sales<br>
<strong>Then</strong> el sistema muestra cada venta con fecha, canal, platos, total en S/ y estado<br><br>
<strong>Scenario 2: Ingresos del período</strong><br>
<strong>Given</strong> que hay ventas confirmadas y anuladas<br>
<strong>When</strong> el administrador revisa el resumen<br>
<strong>Then</strong> "Ingresos totales del período" suma solo las ventas confirmadas<br><br>
<strong>Scenario 3: Anulación confirmada</strong><br>
<strong>Given</strong> que el administrador presiona "Anular" en una venta confirmada<br>
<strong>When</strong> confirma la acción<br>
<strong>Then</strong> la venta pasa al estado "Anulada" y deja de mostrar el botón "Anular"<br><br>
<strong>Scenario 4: Historial vacío</strong><br>
<strong>Given</strong> que aún no hay ventas<br>
<strong>When</strong> el administrador abre el historial<br>
<strong>Then</strong> el sistema indica que use "Simular venta" en Recetas para generar la primera
</td>
<td>EP07 — Recetas y ventas con descuento automático</td>
</tr>
<tr>
<td><strong>US16</strong></td>
<td>Visualizar el resumen operativo en el dashboard</td>
<td>Como administrador, quiero ver en una sola pantalla los indicadores del inventario, los insumos críticos, las alertas recientes y la última proyección, para identificar en menos de 10 segundos qué debo reponer o usar hoy.</td>
<td>
<strong>Scenario 1: Indicadores del inventario</strong><br>
<strong>Given</strong> que el administrador abre /app/dashboard<br>
<strong>When</strong> la pantalla carga<br>
<strong>Then</strong> el sistema muestra insumos registrados, insumos con stock bajo o crítico, insumos por vencer en 3 días o menos y el valor del inventario en S/<br><br>
<strong>Scenario 2: Insumos críticos</strong><br>
<strong>Given</strong> que hay insumos con stock bajo, crítico o vencidos<br>
<strong>When</strong> el administrador revisa el dashboard<br>
<strong>Then</strong> la tabla "Insumos críticos" los lista con su cantidad y estado<br>
<strong>And</strong> si no hay ninguno, muestra "Sin insumos en estado crítico."<br><br>
<strong>Scenario 3: Alertas recientes</strong><br>
<strong>Given</strong> que existen alertas registradas<br>
<strong>When</strong> el administrador revisa el dashboard<br>
<strong>Then</strong> el sistema muestra las cinco alertas más recientes con su severidad<br><br>
<strong>Scenario 4: Resumen de la última proyección</strong><br>
<strong>Given</strong> que existe al menos una proyección de demanda<br>
<strong>When</strong> el administrador revisa el dashboard<br>
<strong>Then</strong> el sistema muestra el resumen de la proyección más reciente<br><br>
<strong>Scenario 5: Saludo personalizado</strong><br>
<strong>Given</strong> que el usuario inició sesión<br>
<strong>When</strong> abre el dashboard<br>
<strong>Then</strong> el encabezado lo saluda por su nombre y muestra el nombre de su restaurante
</td>
<td>EP08 — Dashboard operativo</td>
</tr>
<tr>
<td><strong>US17</strong></td>
<td>Gestionar y entregar las alertas operativas</td>
<td>Como administrador, quiero registrar, atender y eliminar alertas de stock bajo, vencimiento o fallas, y asegurar que cada alerta crítica se entregue por WhatsApp y por correo, para que ninguna alerta quede sin responsable y el 100 % de las alertas críticas llegue por todos sus canales requeridos.</td>
<td>
<strong>Scenario 1: Alerta registrada o editada</strong><br>
<strong>Given</strong> que el administrador está en /app/alerts<br>
<strong>When</strong> elige tipo, severidad y canal, escribe un mensaje de al menos 5 caracteres y presiona "Crear alerta"<br>
<strong>Then</strong> la alerta aparece en la lista<br>
<strong>And</strong> el contador de pendientes aumenta en uno cuando la alerta es nueva<br>
<strong>And</strong> al editar una alerta, la lista muestra los datos actualizados<br><br>
<strong>Scenario 2: Mensaje inválido</strong><br>
<strong>Given</strong> que el mensaje tiene menos de 5 caracteres<br>
<strong>When</strong> el administrador intenta crear la alerta<br>
<strong>Then</strong> el sistema muestra "Mínimo 5 caracteres." y no la registra<br><br>
<strong>Scenario 3: Alerta atendida</strong><br>
<strong>Given</strong> que una alerta ya fue entregada por todos sus canales<br>
<strong>When</strong> el administrador presiona "Marcar atendida"<br>
<strong>Then</strong> la alerta se atenúa en la lista<br>
<strong>And</strong> el contador de pendientes disminuye en uno<br><br>
<strong>Scenario 4: Eliminación confirmada</strong><br>
<strong>Given</strong> que el administrador presiona "Eliminar" en una alerta<br>
<strong>When</strong> confirma la acción<br>
<strong>Then</strong> la alerta desaparece de la lista<br><br>
<strong>Scenario 5: Canales requeridos por severidad</strong><br>
<strong>Given</strong> que una alerta tiene severidad CRITICAL<br>
<strong>When</strong> el sistema evalúa su entrega<br>
<strong>Then</strong> exige WhatsApp y correo como canales requeridos<br>
<strong>And</strong> una alerta de otra severidad solo exige su canal principal<br><br>
<strong>Scenario 6: Reintento del canal pendiente</strong><br>
<strong>Given</strong> que a una alerta crítica le falta el canal de correo<br>
<strong>When</strong> el administrador presiona "Reintentar entrega"<br>
<strong>Then</strong> el sistema registra la entrega por ese canal y la alerta pasa a "Entregada"<br><br>
<strong>Scenario 7: Atención bloqueada hasta la entrega</strong><br>
<strong>Given</strong> que una alerta tiene un canal pendiente<br>
<strong>When</strong> el administrador revisa la alerta<br>
<strong>Then</strong> "Marcar atendida" aparece deshabilitado con el motivo<br><br>
<strong>Scenario 8: Entrega simulada</strong><br>
<strong>Given</strong> que el frontend usa la API simulada<br>
<strong>When</strong> se registra una entrega<br>
<strong>Then</strong> el sistema actualiza solo el estado de entrega y no envía mensajes reales
</td>
<td>EP09 — Alertas y notificaciones</td>
</tr>
<tr>
<td><strong>US18</strong></td>
<td>Anticipar la demanda y aplicar recomendaciones</td>
<td>Como administrador, quiero generar la proyección de unidades por plato de los próximos siete días y aplicar las recomendaciones de compra y de menú, para planificar mis compras antes de los días de mayor demanda y medir qué porcentaje de recomendaciones se convierte en acciones.</td>
<td>
<strong>Scenario 1: Sin proyecciones previas</strong><br>
<strong>Given</strong> que el restaurante no tiene proyecciones<br>
<strong>When</strong> el administrador abre /app/forecast<br>
<strong>Then</strong> el sistema indica que use el botón de generación<br><br>
<strong>Scenario 2: Generación de la proyección</strong><br>
<strong>Given</strong> que el administrador presiona "Generar nueva predicción"<br>
<strong>When</strong> el sistema procesa la solicitud<br>
<strong>Then</strong> el botón muestra "Generando…" y queda deshabilitado hasta terminar<br><br>
<strong>Scenario 3: Resultado de la proyección</strong><br>
<strong>Given</strong> que la proyección se generó<br>
<strong>When</strong> el administrador revisa la pantalla<br>
<strong>Then</strong> el sistema muestra siete días con unidades proyectadas y plato, el nivel de confianza en %, la condición climática y la fecha de generación<br><br>
<strong>Scenario 4: Proyección identificada como simulada</strong><br>
<strong>Given</strong> que el modelo de predicción aún no está conectado al backend<br>
<strong>When</strong> el administrador revisa la proyección<br>
<strong>Then</strong> la pantalla indica que los valores son simulados<br><br>
<strong>Scenario 5: Lista de recomendaciones</strong><br>
<strong>Given</strong> que existen recomendaciones<br>
<strong>When</strong> el administrador abre /app/recommendations<br>
<strong>Then</strong> el sistema muestra cada una con su tipo, su mensaje y su impacto esperado<br><br>
<strong>Scenario 6: Recomendación aplicada</strong><br>
<strong>Given</strong> que una recomendación está pendiente<br>
<strong>When</strong> el administrador presiona "Aplicar"<br>
<strong>Then</strong> la recomendación pasa a "Aplicada" y deja de mostrar el botón<br><br>
<strong>Scenario 7: Sin recomendaciones</strong><br>
<strong>Given</strong> que no hay recomendaciones<br>
<strong>When</strong> el administrador abre la pantalla<br>
<strong>Then</strong> el sistema muestra "No hay recomendaciones por ahora."
</td>
<td>EP10 — Predicción de demanda y recomendaciones</td>
</tr>
<tr>
<td><strong>US19</strong></td>
<td>Elegir o cambiar el plan de suscripción</td>
<td>Como administrador, quiero elegir o cambiar mi plan desde la aplicación, para mantener el servicio activo sin interrupciones y subir de plan cuando mi restaurante lo necesite.</td>
<td>
<strong>Scenario 1: Planes disponibles</strong><br>
<strong>Given</strong> que el administrador abre /app/plans<br>
<strong>When</strong> la pantalla carga<br>
<strong>Then</strong> el sistema muestra cada plan con su precio mensual en S/, sus características y la etiqueta "Más popular" cuando corresponde<br>
<strong>And</strong> un aviso indica que el pago es simulado<br><br>
<strong>Scenario 2: Activación con Stripe simulado</strong><br>
<strong>Given</strong> que el administrador no tiene plan activo<br>
<strong>When</strong> presiona "Pagar con Stripe" en un plan<br>
<strong>Then</strong> el botón muestra "Procesando…"<br>
<strong>And</strong> luego el plan muestra "✓ Suscripción activada" y aparece como plan activo<br><br>
<strong>Scenario 3: Activación con PayPal simulado</strong><br>
<strong>Given</strong> que el administrador elige un plan<br>
<strong>When</strong> presiona "Pagar con PayPal"<br>
<strong>Then</strong> el sistema activa la suscripción con el método PayPal<br><br>
<strong>Scenario 4: Cambio de plan</strong><br>
<strong>Given</strong> que el administrador ya tiene un plan activo<br>
<strong>When</strong> paga otro plan<br>
<strong>Then</strong> el sistema actualiza la suscripción existente sin crear una segunda
</td>
<td>EP11 — Suscripción y planes</td>
</tr>
<tr>
<td><strong>US20</strong></td>
<td>Importar las ventas diarias desde el sistema de ventas</td>
<td>Como administrador, quiero importar el archivo CSV de ventas del día exportado de mi punto de venta, para que el stock se descuente sin volver a digitar ninguna venta.</td>
<td>
<strong>Scenario 1: Importación válida</strong><br>
<strong>Given</strong> que el administrador sube un CSV con fecha, plato y cantidad<br>
<strong>When</strong> el sistema procesa el archivo<br>
<strong>Then</strong> registra las ventas y descuenta los insumos de cada plato con receta<br><br>
<strong>Scenario 2: Plato sin receta</strong><br>
<strong>Given</strong> que una fila corresponde a un plato sin receta<br>
<strong>When</strong> el sistema procesa el archivo<br>
<strong>Then</strong> omite esa fila y la reporta al final de la importación<br><br>
<strong>Scenario 3: Archivo inválido</strong><br>
<strong>Given</strong> que el archivo no tiene las columnas esperadas<br>
<strong>When</strong> el administrador lo sube<br>
<strong>Then</strong> el sistema rechaza el archivo e indica las columnas requeridas<br><br>
<strong>Scenario 4: Importación duplicada</strong><br>
<strong>Given</strong> que las ventas de esa fecha ya fueron importadas<br>
<strong>When</strong> el administrador sube el mismo archivo<br>
<strong>Then</strong> el sistema advierte la duplicidad y no registra ventas repetidas
</td>
<td>EP07 — Recetas y ventas con descuento automático</td>
</tr>
<tr>
<td><strong>US21</strong></td>
<td>Recibir las alertas críticas en mi correo electrónico</td>
<td>Como administrador, quiero recibir por correo las alertas críticas, para enterarme aunque no tenga la aplicación abierta y atenderlas dentro del mismo turno.</td>
<td>
<strong>Scenario 1: Correo enviado</strong><br>
<strong>Given</strong> que se genera una alerta crítica<br>
<strong>When</strong> el sistema la procesa<br>
<strong>Then</strong> envía un correo mediante SendGrid a cada administrador con el insumo afectado y la acción sugerida<br><br>
<strong>Scenario 2: Reintentos ante falla</strong><br>
<strong>Given</strong> que el envío del correo falla<br>
<strong>When</strong> el sistema lo reintenta<br>
<strong>Then</strong> realiza hasta 3 intentos y, si todos fallan, registra la notificación como fallida<br><br>
<strong>Scenario 3: Registro de notificaciones</strong><br>
<strong>Given</strong> que se envía cualquier notificación<br>
<strong>When</strong> el envío termina<br>
<strong>Then</strong> el sistema guarda fecha, canal, destinatario y estado de entrega
</td>
<td>EP09 — Alertas y notificaciones</td>
</tr>
<tr>
<td><strong>US22</strong></td>
<td>Pagar la suscripción con tarjeta mediante Stripe</td>
<td>Como administrador, quiero pagar mi plan con tarjeta en un checkout seguro, para activar o renovar mi suscripción en un solo paso sin entregar los datos de mi tarjeta a StockIA.</td>
<td>
<strong>Scenario 1: Pago aprobado</strong><br>
<strong>Given</strong> que el administrador elige un plan y paga con una tarjeta válida en Stripe (modo de prueba)<br>
<strong>When</strong> Stripe confirma el cobro<br>
<strong>Then</strong> el sistema activa o renueva la suscripción y muestra la nueva fecha de renovación<br><br>
<strong>Scenario 2: Pago rechazado</strong><br>
<strong>Given</strong> que la tarjeta es rechazada<br>
<strong>When</strong> Stripe responde con error<br>
<strong>Then</strong> el sistema muestra el motivo y conserva la suscripción sin cambios<br><br>
<strong>Scenario 3: Datos de tarjeta protegidos</strong><br>
<strong>Given</strong> que el administrador ingresa su tarjeta<br>
<strong>When</strong> Stripe la procesa<br>
<strong>Then</strong> el API de StockIA solo recibe un token y nunca el número de la tarjeta
</td>
<td>EP11 — Suscripción y planes</td>
</tr>
</table>

### Technical Stories
 
Las Technical Stories describen el trabajo técnico que habilita las User Stories y se redactan con el rol Developer. Su «para» expresa el resultado verificable que obtiene el equipo. Las Technical Stories del RESTful API (TS09 y TS11 a TS16) usan como criterios de aceptación los escenarios de request y response.
 
<table>
<tr><th>Story ID</th><th>Título</th><th>Descripción</th><th>Criterios de Aceptación</th><th>Relacionado con Epic ID</th></tr>
<tr>
<td><strong>TS01</strong></td>
<td>Configurar el repositorio de la Landing Page con GitFlow</td>
<td>Como Developer, quiero un repositorio con estructura base y ramas main y develop protegidas por Pull Request, para que el 100 % de los cambios de la Landing Page se integre con revisión y con autor identificable.</td>
<td>
<strong>Scenario 1: Estructura base del proyecto</strong><br>
<strong>Given</strong> que el repositorio de la Landing Page fue creado en la organización<br>
<strong>When</strong> un integrante lo clona<br>
<strong>Then</strong> encuentra index.html, features.html, pricing.html, about.html y las carpetas css, js y assets<br><br>
<strong>Scenario 2: Integración por Pull Request</strong><br>
<strong>Given</strong> que un integrante terminó una tarea en una rama feature/*<br>
<strong>When</strong> abre un Pull Request hacia develop<br>
<strong>Then</strong> el cambio solo se integra después de la revisión de otro integrante<br><br>
<strong>Scenario 3: Publicación desde develop</strong><br>
<strong>Given</strong> que develop contiene un incremento revisado<br>
<strong>When</strong> el equipo prepara la publicación<br>
<strong>Then</strong> el cambio llega a main mediante un Pull Request desde develop
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS02</strong></td>
<td>Implementar el sistema de diseño centralizado en CSS</td>
<td>Como Developer, quiero colores, tipografías, espaciados y componentes definidos como variables y clases reutilizables, para cambiar la identidad visual editando un solo archivo y sin colores repetidos fuera de :root.</td>
<td>
<strong>Scenario 1: Tokens de diseño en :root</strong><br>
<strong>Given</strong> que styles.css define las variables de color, tipografía, espaciado y radios en :root<br>
<strong>When</strong> un integrante revisa el archivo<br>
<strong>Then</strong> ningún color hexadecimal aparece fuera de :root<br><br>
<strong>Scenario 2: Componentes reutilizables</strong><br>
<strong>Given</strong> que una página necesita un botón, una tarjeta o un campo de formulario<br>
<strong>When</strong> el integrante lo maqueta<br>
<strong>Then</strong> usa las clases .btn, .feat-card, .price-card o .form-input sin estilos en línea<br><br>
<strong>Scenario 3: Cambio de identidad en un solo lugar</strong><br>
<strong>Given</strong> que el equipo decide cambiar el color primario<br>
<strong>When</strong> modifica --primary en :root<br>
<strong>Then</strong> el nuevo color se aplica en las cuatro páginas
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS03</strong></td>
<td>Implementar el motor de internacionalización de la Landing Page</td>
<td>Como Developer, quiero que todos los textos traducibles vivan en un único diccionario aplicado mediante atributos data-i18n, para traducir el 100 % del contenido visible sin editar cada página.</td>
<td>
<strong>Scenario 1: Traducción por atributo</strong><br>
<strong>Given</strong> que un elemento tiene el atributo data-i18n con una clave del diccionario<br>
<strong>When</strong> se aplica el idioma seleccionado<br>
<strong>Then</strong> el elemento muestra el texto de esa clave en el idioma elegido<br><br>
<strong>Scenario 2: Clave sin traducción en inglés</strong><br>
<strong>Given</strong> que una clave existe en español pero no en inglés<br>
<strong>When</strong> el visitante cambia a inglés<br>
<strong>Then</strong> el elemento conserva el texto en español en lugar de quedar vacío<br><br>
<strong>Scenario 3: Placeholders traducidos</strong><br>
<strong>Given</strong> que un campo del formulario tiene data-i18n<br>
<strong>When</strong> se aplica el idioma<br>
<strong>Then</strong> su placeholder se muestra en el idioma elegido
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS04</strong></td>
<td>Desplegar la Landing Page en Vercel con despliegue continuo</td>
<td>Como Developer, quiero publicar la Landing Page en Vercel conectada al repositorio, para que cada cambio aprobado esté en línea en menos de 5 minutos sin pasos manuales.</td>
<td>
<strong>Scenario 1: Despliegue automático</strong><br>
<strong>Given</strong> que el proyecto de Vercel está vinculado al repositorio<br>
<strong>When</strong> se integra un cambio en la rama de producción<br>
<strong>Then</strong> Vercel publica la nueva versión sin intervención manual<br><br>
<strong>Scenario 2: Cuatro páginas disponibles</strong><br>
<strong>Given</strong> que el despliegue terminó<br>
<strong>When</strong> un integrante abre index.html, features.html, pricing.html y about.html en el dominio público<br>
<strong>Then</strong> las cuatro páginas cargan con sus estilos, scripts y traducciones<br><br>
<strong>Scenario 3: Vista previa de cambios</strong><br>
<strong>Given</strong> que un integrante abre un Pull Request<br>
<strong>When</strong> Vercel procesa la rama<br>
<strong>Then</strong> genera una URL de vista previa para revisar el cambio antes de integrarlo
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS05</strong></td>
<td>Estructurar la Web Application en Angular por Bounded Context</td>
<td>Como Developer, quiero organizar la Web Application en contextos con capas domain, application, infrastructure y presentation, para que cada integrante trabaje un contexto sin conflictos y ningún componente dependa de HttpClient.</td>
<td>
<strong>Scenario 1: Capas por contexto</strong><br>
<strong>Given</strong> que se revisa src/app<br>
<strong>When</strong> se abre cualquier contexto (iam, product-inventory, sales-order, alerts, demand-forecasting, subscription)<br>
<strong>Then</strong> el contexto contiene las capas domain, application, infrastructure y presentation<br><br>
<strong>Scenario 2: Acceso HTTP aislado</strong><br>
<strong>Given</strong> que un componente de presentation necesita datos<br>
<strong>When</strong> los solicita<br>
<strong>Then</strong> lo hace a través de un servicio de application y solo infrastructure usa HttpClient<br><br>
<strong>Scenario 3: Shell y rutas diferidas</strong><br>
<strong>Given</strong> que el usuario inicia sesión<br>
<strong>When</strong> navega entre módulos<br>
<strong>Then</strong> el shell con menú lateral y barra superior se mantiene y cada pantalla se carga con loadComponent
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS06</strong></td>
<td>Implementar y desplegar la API simulada de la Web Application</td>
<td>Como Developer, quiero una API REST simulada y desplegada con las colecciones del dominio, para desarrollar y demostrar el frontend con datos persistentes mientras se construye el backend real.</td>
<td>
<strong>Scenario 1: Servicio disponible</strong><br>
<strong>Given</strong> que la API simulada está desplegada en Render<br>
<strong>When</strong> se consulta /api/v1/health<br>
<strong>Then</strong> responde con estado "ok"<br><br>
<strong>Scenario 2: Colecciones del dominio</strong><br>
<strong>Given</strong> que el frontend consulta /api/v1/inventoryItems, /recipes, /sales, /alerts u otra colección<br>
<strong>When</strong> envía GET, POST, PUT, PATCH o DELETE<br>
<strong>Then</strong> la API responde con el comportamiento REST correspondiente<br><br>
<strong>Scenario 3: Cambio de API sin tocar componentes</strong><br>
<strong>Given</strong> que el equipo necesita apuntar a otra API<br>
<strong>When</strong> cambia apiBaseUrl en environment.ts<br>
<strong>Then</strong> ningún componente ni servicio de application requiere cambios<br><br>
<strong>Scenario 4: Modo sin conexión</strong><br>
<strong>Given</strong> que no hay acceso a la red<br>
<strong>When</strong> se activa useFakeApi en environment.ts<br>
<strong>Then</strong> la aplicación funciona con la API en memoria del navegador
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS07</strong></td>
<td>Desplegar la Web Application en Vercel</td>
<td>Como Developer, quiero publicar la Web Application en Vercel conectada a la API simulada, para que el docente y los restaurantes del piloto accedan a la versión vigente desde una URL pública.</td>
<td>
<strong>Scenario 1: Build de producción</strong><br>
<strong>Given</strong> que se integra un cambio en la rama de producción<br>
<strong>When</strong> Vercel ejecuta npm run build<br>
<strong>Then</strong> publica el contenido de dist/stockia-webapp/browser<br><br>
<strong>Scenario 2: Rutas internas sin error 404</strong><br>
<strong>Given</strong> que el usuario recarga /app/inventory en el sitio publicado<br>
<strong>When</strong> Vercel atiende la solicitud<br>
<strong>Then</strong> la regla de reescritura entrega index.html y Angular muestra la pantalla<br><br>
<strong>Scenario 3: Conexión con la API simulada</strong><br>
<strong>Given</strong> que la aplicación publicada inicia sesión<br>
<strong>When</strong> consulta datos<br>
<strong>Then</strong> obtiene la información de la API simulada desplegada en Render
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS08</strong></td>
<td>Corregir los hallazgos de la revisión del AV1 en la Landing Page</td>
<td>Como Developer, quiero corregir los defectos y las notas internas señalados en la revisión del AV1, para que la Landing Page publicada no contenga placeholders, instrucciones de edición ni enlaces rotos, y lleve a cada segmento a su vista de la Web Application.</td>
<td>
<strong>Scenario 1: Botón "Solicitar demo" del menú</strong><br>
<strong>Given</strong> que el visitante está en cualquiera de las cuatro páginas<br>
<strong>When</strong> presiona "Solicitar demo" en la barra de navegación<br>
<strong>Then</strong> el sitio abre about.html#contacto<br><br>
<strong>Scenario 2: Menú en móvil</strong><br>
<strong>Given</strong> que el visitante usa una pantalla de 768 px o menos<br>
<strong>When</strong> presiona el botón de menú<br>
<strong>Then</strong> el sitio despliega los enlaces Inicio, Características, Precios y Nosotros<br><br>
<strong>Scenario 3: Equipo real sin notas internas</strong><br>
<strong>Given</strong> que el visitante abre about.html<br>
<strong>When</strong> revisa "El equipo detrás de StockIA"<br>
<strong>Then</strong> encuentra las fichas reales de los cinco integrantes con nombre, rol y código<br>
<strong>And</strong> ninguna nota pide completar o reemplazar datos<br><br>
<strong>Scenario 4: Portafolio filtrable</strong><br>
<strong>Given</strong> que el visitante presiona la pestaña "Inventario" o "IA &amp; IoT"<br>
<strong>When</strong> el portafolio se actualiza<br>
<strong>Then</strong> solo se muestran las vistas de esa categoría<br><br>
<strong>Scenario 5: Enlaces legales operativos</strong><br>
<strong>Given</strong> que el visitante presiona "Términos" en el pie de página<br>
<strong>When</strong> el sitio procesa el clic<br>
<strong>Then</strong> abre la página de términos y condiciones en lugar de un enlace vacío<br><br>
<strong>Scenario 6: CTA del segmento dueños hacia el registro</strong><br>
<strong>Given</strong> que un visitante del segmento dueños de restaurantes está en la sección "¿Para quién es StockIA?"<br>
<strong>When</strong> presiona el call-to-action de su segmento<br>
<strong>Then</strong> el sitio abre /auth/sign-up de la Web Application en un solo clic<br><br>
<strong>Scenario 7: CTA del segmento jefes de cocina hacia el inicio de sesión</strong><br>
<strong>Given</strong> que un visitante del segmento administradores o jefes de cocina ya fue invitado por su restaurante<br>
<strong>When</strong> presiona el call-to-action de su segmento o "Iniciar sesión" en la barra de navegación<br>
<strong>Then</strong> el sitio abre /auth/sign-in de la Web Application<br><br>
<strong>Scenario 8: Regreso a la Landing Page</strong><br>
<strong>Given</strong> que el usuario está en la pantalla de inicio de sesión o de registro de la Web Application<br>
<strong>When</strong> presiona el logo de StockIA<br>
<strong>Then</strong> la Web Application abre index.html de la Landing Page
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS09</strong></td>
<td>Estructurar el RESTful API de StockIA en ASP.NET Core por Bounded Context</td>
<td>Como Developer, quiero un RESTful API en ASP.NET Core con Entity Framework Core, MySQL, un módulo por Bounded Context y documentación OpenAPI, para reemplazar la API simulada sin cambiar los componentes del frontend.</td>
<td>
<strong>Scenario 1: Endpoints documentados</strong><br>
<strong>Given</strong> que el API está desplegado<br>
<strong>When</strong> se abre Swagger UI<br>
<strong>Then</strong> se listan los endpoints de IAM, Inventory, Recipes, Sales, Alerts, Demand Forecasting y Subscriptions con sus esquemas de request y response en inglés<br><br>
<strong>Scenario 2: Solicitud sin token</strong><br>
<strong>Given</strong> que un cliente envía una solicitud a un endpoint protegido sin un token JWT válido<br>
<strong>When</strong> el API procesa la solicitud<br>
<strong>Then</strong> responde 401 Unauthorized sin ejecutar la operación<br><br>
<strong>Scenario 3: Validación de datos</strong><br>
<strong>Given</strong> que un cliente envía un body que no cumple las reglas del recurso<br>
<strong>When</strong> el API procesa la solicitud<br>
<strong>Then</strong> responde 400 Bad Request con el detalle de cada campo inválido<br><br>
<strong>Scenario 4: Ownership de datos por contexto</strong><br>
<strong>Given</strong> que un contexto necesita datos de otro<br>
<strong>When</strong> los solicita<br>
<strong>Then</strong> los obtiene por la fachada del contexto dueño y nunca leyendo sus tablas
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS10</strong></td>
<td>Conectar la Web Application al RESTful API real</td>
<td>Como Developer, quiero apuntar la Web Application al RESTful API real y enviar el token en cada solicitud, para pasar del entorno simulado a datos persistentes sin modificar la capa de presentación.</td>
<td>
<strong>Scenario 1: Cambio de entorno</strong><br>
<strong>Given</strong> que el RESTful API está desplegado<br>
<strong>When</strong> se actualiza apiBaseUrl en environment.prod.ts<br>
<strong>Then</strong> todas las pantallas funcionan contra el API real<br><br>
<strong>Scenario 2: Token en cada solicitud</strong><br>
<strong>Given</strong> que el usuario inició sesión<br>
<strong>When</strong> la aplicación consulta el API<br>
<strong>Then</strong> un interceptor agrega el token JWT a la cabecera Authorization<br><br>
<strong>Scenario 3: Sesión expirada</strong><br>
<strong>Given</strong> que el token expiró<br>
<strong>When</strong> el API responde 401<br>
<strong>Then</strong> la aplicación cierra la sesión y muestra /auth/sign-in
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS11</strong></td>
<td>Exponer los endpoints de registro e inicio de sesión</td>
<td>Como Developer, quiero endpoints de registro e inicio de sesión que emitan un token JWT, para que la Web Application autentique a administradores y empleados contra el RESTful API.</td>
<td>
<strong>Scenario 1: Registro exitoso</strong><br>
<strong>Given</strong> que no existe un usuario con el correo enviado<br>
<strong>When</strong> se envía POST /api/v1/authentication/sign-up con fullName, restaurantName, email y password<br>
<strong>Then</strong> el API responde 201 Created con el id del usuario y el rol ADMIN, sin incluir la contraseña<br><br>
<strong>Scenario 2: Correo duplicado</strong><br>
<strong>Given</strong> que ya existe un usuario con el correo enviado<br>
<strong>When</strong> se envía POST /api/v1/authentication/sign-up<br>
<strong>Then</strong> el API responde 409 Conflict con el mensaje "Email already registered"<br><br>
<strong>Scenario 3: Inicio de sesión</strong><br>
<strong>Given</strong> un usuario registrado<br>
<strong>When</strong> se envía POST /api/v1/authentication/sign-in con credenciales válidas<br>
<strong>Then</strong> el API responde 200 OK con el token JWT y el rol del usuario<br>
<strong>And</strong> con credenciales inválidas responde 401 Unauthorized
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS12</strong></td>
<td>Exponer los endpoints de insumos</td>
<td>Como Developer, quiero endpoints para listar, crear, actualizar y eliminar insumos con su estado de stock calculado, para que la Web Application administre el inventario del restaurante.</td>
<td>
<strong>Scenario 1: Creación de insumo</strong><br>
<strong>Given</strong> un token válido<br>
<strong>When</strong> se envía POST /api/v1/inventory-items con name, unit, quantity, minThreshold, storageType, shelfLifeDays y unitCost<br>
<strong>Then</strong> el API responde 201 Created con el insumo, su expirationDate calculada como la fecha actual más shelfLifeDays y la cabecera Location<br><br>
<strong>Scenario 2: Datos inválidos</strong><br>
<strong>Given</strong> un token válido<br>
<strong>When</strong> quantity, minThreshold o unitCost son negativos o shelfLifeDays es menor a 1<br>
<strong>Then</strong> el API responde 400 Bad Request indicando cada campo inválido<br><br>
<strong>Scenario 3: Estado de stock</strong><br>
<strong>Given</strong> un insumo con quantity menor o igual a minThreshold<br>
<strong>When</strong> se envía GET /api/v1/inventory-items/{id}<br>
<strong>Then</strong> el API responde 200 OK con status LOW<br><br>
<strong>Scenario 4: Insumo inexistente</strong><br>
<strong>Given</strong> un id que no existe<br>
<strong>When</strong> se envía GET, PUT o DELETE a /api/v1/inventory-items/{id}<br>
<strong>Then</strong> el API responde 404 Not Found
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS13</strong></td>
<td>Exponer los endpoints de recetas</td>
<td>Como Developer, quiero endpoints de recetas que validen que cada ingrediente exista en el inventario, para mantener la integridad entre recetas e insumos.</td>
<td>
<strong>Scenario 1: Receta válida</strong><br>
<strong>Given</strong> que todos los ingredientes referencian insumos existentes con quantityRequired mayor a 0<br>
<strong>When</strong> se envía POST /api/v1/recipes<br>
<strong>Then</strong> el API responde 201 Created con la receta y sus ingredientes<br><br>
<strong>Scenario 2: Ingrediente inexistente</strong><br>
<strong>Given</strong> que un ingrediente referencia un insumo que no existe<br>
<strong>When</strong> se envía POST o PUT a /api/v1/recipes<br>
<strong>Then</strong> el API responde 400 Bad Request indicando el id del insumo inexistente<br><br>
<strong>Scenario 3: Receta sin ingredientes</strong><br>
<strong>Given</strong> que la receta no tiene ingredientes<br>
<strong>When</strong> se envía POST /api/v1/recipes<br>
<strong>Then</strong> el API responde 400 Bad Request
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS14</strong></td>
<td>Exponer los endpoints de registro y anulación de ventas</td>
<td>Como Developer, quiero un endpoint que registre ventas descontando los insumos en una sola transacción y otro que las anule, para que el stock nunca quede inconsistente.</td>
<td>
<strong>Scenario 1: Venta registrada</strong><br>
<strong>Given</strong> que hay stock suficiente para todos los ingredientes de la receta<br>
<strong>When</strong> se envía POST /api/v1/sales con recipeId y quantity<br>
<strong>Then</strong> el API responde 201 Created con la venta en estado CONFIRMED<br>
<strong>And</strong> descuenta los insumos en la misma transacción<br><br>
<strong>Scenario 2: Stock insuficiente</strong><br>
<strong>Given</strong> que al menos un ingrediente no tiene stock suficiente<br>
<strong>When</strong> se envía POST /api/v1/sales<br>
<strong>Then</strong> el API responde 409 Conflict con la lista de insumos faltantes y no modifica ningún insumo<br><br>
<strong>Scenario 3: Anulación</strong><br>
<strong>Given</strong> una venta en estado CONFIRMED<br>
<strong>When</strong> se envía PATCH /api/v1/sales/{id}/void<br>
<strong>Then</strong> el API responde 200 OK con la venta en estado VOIDED<br>
<strong>And</strong> si la venta ya estaba anulada responde 409 Conflict
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS15</strong></td>
<td>Exponer los endpoints de alertas</td>
<td>Como Developer, quiero endpoints para filtrar alertas por severidad y estado, registrar su entrega por canal y marcarlas como atendidas, para alimentar el dashboard y la pantalla de alertas.</td>
<td>
<strong>Scenario 1: Filtro de alertas</strong><br>
<strong>Given</strong> un token válido<br>
<strong>When</strong> se envía GET /api/v1/alerts?severity=CRITICAL&acknowledged=false<br>
<strong>Then</strong> el API responde 200 OK solo con las alertas críticas no atendidas, de la más reciente a la más antigua<br><br>
<strong>Scenario 2: Entrega por canal</strong><br>
<strong>Given</strong> una alerta crítica con el canal EMAIL pendiente<br>
<strong>When</strong> se envía POST /api/v1/alerts/{id}/deliveries con channel EMAIL<br>
<strong>Then</strong> el API responde 200 OK y agrega EMAIL a deliveredChannels sin duplicarlo<br><br>
<strong>Scenario 3: Atención bloqueada</strong><br>
<strong>Given</strong> una alerta con al menos un canal requerido pendiente<br>
<strong>When</strong> se envía PATCH /api/v1/alerts/{id}/acknowledge<br>
<strong>Then</strong> el API responde 409 Conflict indicando el canal pendiente
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
<tr>
<td><strong>TS16</strong></td>
<td>Exponer el endpoint de proyección de demanda</td>
<td>Como Developer, quiero un endpoint que genere la proyección de siete días a partir del histórico de ventas y del clima de un servicio externo, para entregar a la Web Application predicciones basadas en datos reales.</td>
<td>
<strong>Scenario 1: Proyección generada</strong><br>
<strong>Given</strong> que el restaurante tiene al menos 14 días de ventas confirmadas<br>
<strong>When</strong> se envía POST /api/v1/demand-forecasts<br>
<strong>Then</strong> el API responde 201 Created con 7 puntos de proyección (uno por día), un confidenceScore entre 0 y 1 y la condición climática consultada<br><br>
<strong>Scenario 2: Histórico insuficiente</strong><br>
<strong>Given</strong> que el restaurante tiene menos de 14 días de ventas confirmadas<br>
<strong>When</strong> se envía POST /api/v1/demand-forecasts<br>
<strong>Then</strong> el API responde 422 Unprocessable Entity indicando cuántos días de ventas faltan<br><br>
<strong>Scenario 3: Servicio de clima no disponible</strong><br>
<strong>Given</strong> que el servicio externo de clima no responde en 5 segundos<br>
<strong>When</strong> se envía POST /api/v1/demand-forecasts<br>
<strong>Then</strong> el API calcula la proyección solo con el histórico de ventas y lo indica en la respuesta
</td>
<td>EP12 — Base técnica y despliegue continuo</td>
</tr>
</table>

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