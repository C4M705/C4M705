
## Datos de la Empresa

![Planta Huaral drawio](https://github.com/C4M705/C4M705/assets/164358065/609a8931-0658-46aa-90a9-92845a07bdf6)

Nombre de la empresa: San Fernando

Descripción de la empresa: San Fernando S.A. es una empresa peruana dedicada a la producción y comercialización de alimentos de consumo masivo de las líneas pollo, pavo, cerdo, huevo y productos procesados.
### Modulo #2: Seguimiento

Responsabilidades:  

- Facilitar el desplazamiento entre información de los pedidos en proceso de traslado, los pedidos pendientes de traslado, los conductores y vehículos asignados a cada proceso de traslado
- Presentar información de ubicación satelital de un pedido en específico para proporcionar un seguimiento en tiempo real mientras el vehículo se encuentra realizando el proceso de traslado.
- Mostrar la ruta asignada a un determinado vehículo en su proceso de traslado, así como el conductor asignado, estatus de viaje, detalles del pedido, la hora de salida, hora estimada de llegada, punto de origen y destino.
- Almacenar, gestionar y mostrar datos importantes del transportista, como información de contacto, detalles del vehículo de transporte, licencias y certificaciones relevantes, para garantizar la seguridad y la trazabilidad del proceso de entrega.
- Enviar notificaciones y alertas automáticas a los usuarios pertinentes sobre eventos importantes relacionados con los pedidos, como cambios en el estado del pedido, retrasos en la entrega, o problemas con la disponibilidad de productos, para facilitar una respuesta rápida y eficiente.

Interacción con otros módulos: 

- Conexión con el módulo de pedidos para poder moverse de un módulo a otro dependiendo de si se quiere hacer seguimiento del pedido o se requiere detalles de este.
- Interacción con el módulo de reclamos en caso de alguna observación irregular en el seguimiento del pedido.
- Función de herramienta para el módulo de Control mostrando la información necesaria sobre el estado del pedido durante el proceso de traslado.

### 2. Requerimientos del módulo de Seguimiento
#### 2.1. Requerimientos funcionales

a. Usuarios
- Administrador: Puede visualizar todas las pantallas y editar los detalles de traslado.
- Usuario planta Huaral (Pedido cliente interno): Visualización de pedido en progreso y acceso a detalles de traslado y guía de remisión.
- Usuario Almacén General (Pedido cliente interno): Permisos de administrador, acceso a los documentos y vínculos adjuntos y registro de incidencias.
- Usuario de planta Huaral (Pedido de cliente externo): Puede visualizar las pantallas y acceder a los documentos y vínculos adjuntos, registrar incidencias.
- Usuario Transportista: Actualizar el estatus del transporte, registrar incidencias y entregas solo de traslados realizados por ellos mismos.
b. Casos de uso

Caso de Uso #1: Verificar Pedido en Progreso
| Código | R201 | 
|----------|----------|
|Objetivo | Permitir al encargado de almacén revisar los detalles del proceso de traslado de un pedido. |
|Descripción | El encargado ingresa al módulo en la pantalla de Pedidos en progreso y con el número de pedido que le corresponde busca y accede a los detalles del pedido en cuestión. |
|Actor Primario | Encargado de almacén. |
|Actor Secundario | N/A |
|Precondiciones | El encargado debe estar registrado en el sistema SAP | 
|Paso | Acción | 
|1 | El encargado selecciona la pantalla de Pedidos en Progreso en la pantalla Menú. |
|2 | El sistema muestra una serie de pedidos cuyo estatus se encuentra clasificado como “en progreso” | 
|3 | El encargado busca visualmente o a través del buscador el código del pedido del cual desea consultar los detalles y da click sobre el icono de dicho pedido. |
|4 | El sistema muestra toda la información detallada del pedido en cuestión y el proceso de traslado en el que se está realizando. |
|Pasos opcionales | Acciones opcionales |
|5 | El encargado puede dar click en el botón de “Ver guía de Remisión” para acceder a una versión digital del documento que consigna los detalles del traslado. |

Caso de Uso #2: Registrar Incidencia de viaje
| Código | R202 | 
|----------|----------|
|Objetivo | Permitir al transportista reportar alguna incidencia no prevista durante el proceso de traslado. |
|Descripción | El transportista ante una situación no planeada accede al sistema de seguimiento y registra una incidencia respecto al traslado que realiza, informando a los involucrados de la situación. |
|Actor Primario | Transportista. |
|Actor Secundario | Encargado de almacén planta Huaral, Almacenero Almacén General |
|Precondiciones | El transportista debe haber accedido al sistema | 
|Paso | Acción | 
|1 | El transportista entra a la pantalla de Pedidos en progreso. |
|2 | El transportista ingresa los datos del Traslado que está llevando a cabo o el pedido con respecto al cual tuvo una incidencia. | 
|3 | Realiza click sobre el botón “Reportar incidencia que lo redirige al módulo de Control donde realizará el llenado del formato de incidencias. |
|4 | El sistema registra la incidencia y genera una notificación en los usuarios relacionados con los pedidos del traslado. |

Caso de Uso #3: Revisar los pedidos pendientes de un Traslado
| Código | R203 | 
|----------|----------|
|Objetivo | Permitir a los supervisores informarse si un pedido se encuentra aún en proceso de traslado o de si ya fue registrado como entregado |
|Descripción | El supervisor entra al sistema en la pantalla de Pedidos Pendientes, ingresa la información del Traslado que desea consultar y revisa los pedidos de ese traslado que aún faltan entregar. |
|Actor Primario | Supervisor |
|Actor Secundario | Encargado de almacén planta Huaral, Almacenero Almacén General |
|Precondiciones | El supervisor debe estar logeado y tener el código de pedido y de traslado | 
|Paso | Acción | 
|1 | El supervisor entra a la pantalla de Pedidos Pendientes. |
|2 | El supervisor ingresa los datos del Traslado que está lleva el pedido en cuestión. | 
|3 | El sistema muestra los pedidos por entregar de ese Traslado. |
|4 | El supervisor busca visualmente en la tabla o ingresa el código del pedido en la barra de búsqueda para encontrar el pedido del cual quiere realizar el seguimiento. |

Caso de Uso #4: Registrar la entrega de un pedido
| Código | R204 | 
|----------|----------|
|Objetivo | Permitir cambiar el estatus de los pedidos que están siendo transportados en el Traslado |
|Descripción | El transportista ingresa al sistema, busca el traslado que está realizando y cambia el estado de un pedido a entregado. |
|Actor Primario | Transportista |
|Actor Secundario | Encargado de almacén planta Huaral, Almacenero Almacén General |
|Precondiciones | El transportista debe estar logeado y tener el código de pedido y de traslado | 
|Paso | Acción | 
|1 | El supervisor entra a la pantalla de Pedidos en Progreso y escribe el código del traslado actual en la barra respectiva. |
|2 | El supervisor da click en “Registrar entrega” y selecciona el pedido de dicho traslado que cambiará de estatus. | 
|3 | El sistema guarda los cambios y se ven reflejados en las otras pantallas. |

#### 2.2. Requerimientos de atributos de calidad
- Seguridad: Dado que el sistema manejará datos de ubicación e información sensible sobre las entregas, la seguridad es de suma importancia. Se debe procurar acceso solo a los trabajadores con las autorizaciones adecuadas para asignar lectura y escritura dependiendo del nivel de acceso.
- Confiabilidad: Es esencial asegurar que las ubicaciones y rutas de entrega registradas sean precisas y consistentes. Ya que los transportistas siguen estas rutas, se debe asegurar que son seguras y confiables para el transporte.
- Usabilidad: Dado que los trabajadores serán los principales usuarios del sistema, es importante que sea fácil de usar y comprender. La interfaz de usuario debe ser intuitiva y amigable, permitiendo a los usuarios acceder rápidamente a la información que necesitan y realizar las acciones requeridas sin dificultad. 
- Eficiencia: La eficiencia del sistema impactará directamente en la productividad y la efectividad de las operaciones de entrega. El sistema debe ser capaz de procesar y mostrar la información de ubicación de manera rápida y eficiente, minimizando los tiempos de espera y optimizando el uso de recursos.

#### 2.3. Requerimientos de restricciones
- El diseño del modelo relacional de datos debe ser compatible con las características y funcionalidades de PostgreSQL.
- El acceso a la base de datos desde el backend debe realizarse utilizando sentencias SQL nativas de PostgreSQL.
#### Pantalla Menú Principal:
Al ingresar al módulo el usuario podrá ver una serie de vínculos que lo lleva a las pantallas principales del módulo

<p align="center" width="90%"><img width="90%" src="https://github.com/fiis-bd241/grupo01/assets/164358065/0dc9d667-3f1c-4c7c-a8d0-3d78e583d0ef"></p>

#### Pantalla Pedidos en Progreso:
Al elegir el vínculo a “Pedidos en progreso” se dirigirá a la pantalla principal del módulo, donde no le aparecerán los datos hasta que escriba el código del traslado o el código del pedido en sus respectivos cuadros de búsqueda. 
Si por ejemplo el usuario solo cuenta con el código del pedido basta con buscarlo y automáticamente se completará el código del traslado debido a la relación entre ambas entidades.
En esta pantalla también están incluidas las funciones de inicio de Incidente y visualización de la guía de remisión, pero esto está sujeto al nivel de acceso del usuario.
<p align="center" width="90%"><img width="90%" src="https://github.com/fiis-bd241/grupo01/assets/164358065/f00dc926-ce6e-4098-8100-607abf265f7f"></p>
Para evitar manejar una cantidad grande de datos se plantea generar una actualización de la ubicación en el momento en el que se ingresa a esta pantalla y en periodos específicos de tiempo durante la permanencia del usuario en la pantalla (alrededor de 1 minuto de intervalo entre actualización y actualización).

Entidades involucradas:
- Traslados
- Pedidos
- Rutas
- Vehículos
- Ubicación

#### Pantalla Detalles de Traslado:
Se puede llegar a la pantalla de Detalles de Traslado desde el Menú principal o desde la pantalla Pedidos en Progreso; la diferencia radica que al usar la pantalla de Pedidos en Progreso el rellenado del campo “Código de traslado” sería automático y proveniente de lo último que se esté viendo en la otra pantalla. 
Una vez colocado el código respectivo el usuario tendrá acceso a la información del conductor y el automóvil con la finalidad de corroboración o en el intento de contactar con el conductor a través de su número celular.
<p align="center" width="90%"><img width="90%" src="https://github.com/fiis-bd241/grupo01/assets/164358065/95ef1cc0-4498-4372-aec9-654c03fb9d91"></p>
Este módulo interactúa con las entidades Transportista y Vehículo puesto que toma y muestra sus atributos.

Entidades involucradas:
- Transportista
- Vehículo

#### Pantalla Pedidos Pendientes:
Esta pantalla, al igual que la anterior, es accesible desde la pantalla principal y la de Pedidos en progreso, aunque está restringida a ciertos usuarios. Su función es mostrar los pedidos de un traslado en particular que aún no han sido entregados, esto le permite a un supervisor verificar los pedidos que faltan entregar y al transportista a registrar cuando realiza una entrega, para eso se genera un botón con el vínculo al modulo de control para verificar el proceso de entrega. Una vez culminado el proceso en ese otro modulo el sistema se actualizará y generará una notificación para los usuarios asignados.
<p align="center" width="90%"><img width="90%" src="https://github.com/fiis-bd241/grupo01/assets/164358065/d04fc44c-ef3b-4682-9c31-7912a648c48e"></p>

Entidades Involucradas:
- Pedidos
- Dirección
