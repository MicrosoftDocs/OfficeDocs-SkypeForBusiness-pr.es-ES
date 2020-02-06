---
title: Usar el panel de calidad de llamadas para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 'Resumen: Obtenga información sobre cómo usar el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 61b20062925f59474d387a022a92663e0ffcd6ba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816669"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Usar el panel de calidad de llamadas para Skype empresarial Server

**Resumen:** Más información sobre cómo usar el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.

El panel de calidad de llamadas (CQD) permite a los profesionales de TI usar datos de agregado para identificar problemas al crear problemas de calidad de medios comparando las estadísticas de los grupos de usuarios para identificar tendencias y patrones. El CQD no se concentra en resolver problemas de llamadas individuales, sino en identificar problemas y soluciones que se aplican a muchos usuarios.

## <a name="call-quality-dashboard-user-guide"></a>Manual de usuario del panel de calidad de llamadas

El CQD es un portal web para crear y organizar rápidamente informes basados en los datos de la calidad de la experiencia (QoE). El CQD implementa un cubo SSAS para agregar los datos de la base de datos QoE Metrics, y permite a los administradores crear y modificar informes o realizar investigaciones en tiempo real. Aunque es posible usar Excel para conectarse directamente al cubo, el portal está optimizado para varios flujos de trabajo que incluyen datos de calidad. Los datos incluyen:

- Datos del informe almacenados en caché para agilizar el acceso
- Vínculos profundos a páginas de informes para la publicación y el uso compartido de información
- Edición y creación de informes simplificada, y metadatos editables para descripciones de informes.

Además, el CQD expone las API Web que proporcionan a los usuarios acceso mediante programación a los datos del cubo para usarlos en paneles personalizados.

### <a name="feature-overview"></a>Información general sobre las características

Cuando visite el panel de calidad de llamadas, verá la siguiente pantalla:

![Usar el CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. El "panel Resumen" es donde puede encontrarse el contexto para el "conjunto de informes" (a la derecha).
2. Haga clic en "Editar" en el PaneReport de resumen para establecer las propiedades del nivel (incluyendo el alto del eje Y).
3. La ruta de navegación le ayuda a identificar su ubicación actual dentro de la jerarquía del conjunto de informes.
4. Los informes con subinformes se muestran con un vínculo azul. Haga clic en el vínculo para explorar en profundidad los informes secundarios.

Mueva el mouse por los gráficos de barras y las líneas de tendencia para mostrar valores detallados. El informe que tiene el foco muestra el menú de acciones: "Editar", "clonar", "eliminar" y "Descargar".

### <a name="default-reports"></a>Informes predeterminados

La primera vez que acceda al portal del panel de calidad de llamadas, se creará automáticamente un conjunto de informes predeterminado. Estos informes a veces se conocen como informes del sistema. Puede modificar o eliminar estos informes de forma gratuita o extenderlos creando nuevos informes relacionados y secundarios.

En el nivel superior, el informe "la tendencia mensual de las secuencias de audio" muestra la tendencia mensual para todas las transmisiones de audio. Mueva el mouse sobre las barras de un gráfico de barras para mostrar una vista más detallada de los datos representados por el gráfico de barras. Haga clic en el título del informe de tendencia mensual de secuencias de audio para navegar al informe "administrado vs, secuencias de audio no administrados", donde los informes se dividen entre llamadas administradas y no administradas. Las llamadas administradas son llamadas realizadas desde dentro del Firewall corporativo a través de conexiones cableadas. Las llamadas no administradas incluyen llamadas realizadas desde fuera del Firewall corporativo y todas las llamadas hechas a través de Wi-Fi.

El otro informe de nivel superior se denomina "histograma de la calidad de las llamadas notificadas por el usuario". Las clasificaciones de calidad de las llamadas son los números proporcionados por los usuarios de Skype empresarial al final de una llamada para indicar la calidad de la llamada. Los números de clasificación van de 1 a 5, 1 es el peor y el 5 es el mejor. El histograma muestra la cantidad de llamadas de audio que tuvieron la valoración indicada en el plazo de un mes.

Haga clic en el título de cualquiera de los informes para navegar por los informes con más filtros en los datos. En los informes del sistema, cada informe secundario muestra un subconjunto de los datos disponibles en su informe primario. El modelo de solución de problemas es simple: investigue qué subinforme los datos o la tendencia que sugiere un problema se limitan a y reducen gradualmente el espacio de problemas. La capacidad de crear subinformes permite investigar sus propias averiguaciones sobre la causa de las tendencias de datos específicas.

### <a name="create-and-edit-reports"></a>Crear y editar informes

Haga clic en "Editar" en el menú de acciones de un informe para ver el editor de informes. Cada informe está respaldado por una consulta dentro del cubo. Un informe es una visualización de los datos devueltos por su consulta. El editor de informes le ayuda a editar estas consultas y las opciones de presentación del informe. Al abrir el editor de informes, verá:

![Usar el CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Las dimensiones, las medidas y los filtros se eligen en el panel de la izquierda. Pase el puntero sobre uno de los valores existentes para mostrar un botón "x" que permite quitar el valor. Haga clic en el botón "más" situado junto a un título para abrir el cuadro de diálogo en el que puede Agregar una nueva dimensión, medida o filtro.
2. Las opciones para personalizar los gráficos se visualizan en la parte superior.
3. En el editor de informes hay una vista previa del informe. 
4. Se puede crear una descripción de informe detallada con el cuadro de edición de la parte inferior.

### <a name="sparklines-in-tables"></a>Minigráficos en las tablas

Si se agrega el mes de inicio como dimensión y los datos se representan como tendencia en formato de tabla, se pueden mostrar los gráficos de barras y los minigráficos dentro de las celdas de la tabla. Mueva el puntero del mouse sobre el gráfico de barras y los minigráficos para mostrar los valores de cada mes.

![Usar el CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

Para que aparezcan los gráficos de barras y los minigráficos, se debe activar la casilla "Mostrar minigráficos" en la parte superior del editor de informes. De esta forma, se selecciona la opción tendencia y se mueve el mes hacia abajo para que sea la última dimensión, que también se puede lograr haciendo clic en el mes y usando las flechas arriba y abajo para desplazar la tecla de función.

### <a name="settings"></a>Configuración

El menú configuración contiene vínculos a páginas útiles, como el estado del sistema y las páginas, y se encuentra en la esquina superior derecha del panel.

![Usar el CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

Si desea mostrar descripciones y marcas de tiempo para los usuarios individuales, esta configuración solo afecta a la versión del panel de la persona y no modifica el conjunto de informes ni lo que ven otros usuarios. Borrar la caché hace que todas las consultas vuelvan a cargar los datos del cubo, mientras que al restaurar valores predeterminados, se eliminan todos los informes creados o modificados por el usuario y se vuelve a crear el conjunto de informes del sistema: lo que vería un usuario al iniciar sesión por primera vez.

El Vínculo del panel de usuarios muestra una página en la que los usuarios pueden ver otros usuarios del CQD y examinar sus informes. Para compartir un conjunto de informes, copie el vínculo en la barra de direcciones URL y compártalo con otro usuario de CQD. Este vínculo es el mismo vínculo que otros usuarios verían en la página del vínculo del panel de usuarios debajo del nombre de usuario.

### <a name="supplying-subnet-information"></a>Suministrar información de subred

Se puede revelar información adicional si se introduce información específica del sitio en la base de datos de archivado para proporcionar información de asignación de subred a la creación (por ejemplo, calidad de llamadas inalámbricas/cableadas por construcción).

Para crear estos informes, completa como mínimo las siguientes tablas:

- CqdBuilding
- CqdNetwork

En las tablas CqdBuildingType y CqdBuildingOwnershipType se puede proporcionar información adicional para permitir más opciones de filtro y exploración. 

Los datos que se usan para estas tablas se definen de la siguiente manera:

**CqdBuilding**

|Columna|Tipo de datos|¿Permite valores nulos?|Detalles|
|:-----|:-----|:-----|:-----|
|BuildingKey |int |No |Clave principal para la tabla CqdBuilding. |
|BuildingName |varchar(80) |No |Nombre del edificio. |
|BuildingShortName |varchar(10) |No |Versión abreviada del nombre del edificio. |
|OwnershipTypeId |int |No |Clave externa, coincide con una de las entradas de la tabla CqdBuildingOwners. |
|BuildingTypeId |int |No |Clave externa, coincide con una de las entradas de la tabla CqdBuildingType. |
|Latitud |float |Sí |Latitud del edificio. |
|Longitude |float |Sí |Longitud del edificio. |
|CityName |varchar(30) |Sí |Nombre de la ciudad en la que se encuentra el edificio. |
|ZipCode |varchar(25) |Sí |Código postal en el que se encuentra el edificio. |
|CountryShortCode |varchar(2) |Sí |Códigos ISO 3166-1 alfa-2 para el país en el que se encuentra el edificio. |
|StateProvinceCode |varchar(3) |Sí |Abreviatura de tres letras del estado o provincia donde se encuentra el edificio. |
|InsideCorp |bit |Sí |Bit indica si la compilación forma parte de la red corporativa. |
|BuildingOfficeType |nvarchar(150) |Sí |Descripción del tipo de oficina del edificio. |
|Region |varchar(25) |Sí |Región en la que se encuentra el edificio. |
|||||

**CqdNetwork**

|Columna|Tipo de datos|¿Permite valores nulos?|Detalles|
|:-----|:-----|:-----|:-----|
|Network |varchar(25) |No |Dirección de subred. |
|NetworkRange |tinyint |Sí |Máscara de la subred. |
|NetworkNameID |int |Sí |Se asigna de forma opcional a una fila de la tabla CqdNetworkName. |
|BuildingKey |int |Sí |Clave externa, coincide con una de las entradas de la tabla CqdBuilding. |
|UpdatedDate |datetime |No |Fecha y hora de la última actualización de la entrada. |
||||||

De forma predeterminada, la siguiente tabla tiene una entrada (0, ' unknown ').

**CqdBuildingType**

|Columna|Tipo de datos|¿Permite valores nulos?|Detalles|
|:-----|:-----|:-----|:-----|
|BuildingTypeId |int |No |Clave principal para la tabla CqdBuildingType. |
|BuildingTypeDesc |char(18) |No |Descripción del tipo de edificio. |
|||||

De forma predeterminada, la siguiente tabla tiene una entrada (0, ' unknown ', 0, null).

**CqdBuildingOwnershipType**

|Columna|Tipo de datos|¿Permite valores nulos?|Detalles|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId |int |No |Clave principal para la tabla CqdBuildingOwnershipType. |
|OwnershipTypeDesc |varchar(25) |No |Descripción del tipo de propiedad. |
|LeaseInd |tinyint |Sí |Índice que hace referencia a otra fila de la tabla CqdBuildingOwnershipType, que se usa para identificar edificios alquilados. |
|Owner |varchar(50) |Sí |Propietario del edificio. |
|||||

De forma predeterminada, la siguiente tabla tiene una entrada (0, ' unknown ', 0, null).

**CqdBssid**

|Columna|Tipo de datos|¿Permite valores nulos?|Detalles|
|:-----|:-----|:-----|:-----|
|bss |nvarchar(50) |No |Clave principal para la tabla CqdBssid. Es el BSSID del punto de acceso WiFi. |
|ess |nvarchar(50) |Sí |Información del controlador del punto de acceso Wi-Fi. |
|phy |nvarchar(50) |Sí |Información de phy. |
|ap |nvarchar(50) |Sí |Nombre del punto de acceso Wi-Fi. |
|Building |nvarchar(500) |Sí |El nombre del edificio en el que se encuentra el punto de acceso WiFi. |
||||

## <a name="cqd-streams"></a>Secuencias del CQD

Una secuencia de CQD se considera buena, mala o no clasificada. CQM 1.5 ahora usa la siguiente definición de CQD:

- Un flujo deficiente es cualquier combinación de las métricas de llamadas deficientes más allá del umbral.
- Cuando una secuencia de una llamada es mala, ambas secuencias de la llamada se marcan como deficientes. En las conferencias, cada participante se cuenta como una llamada única y se registra de forma independiente de todos los demás.
- Las transmisiones sin clasificar son secuencias sin métricas de calidad (es decir, transacciones sintéticas o llamadas cortas).
- Secuencias válidas = clientes no móviles
- No se puede modificar el clasificador

**Definición de llamada deficiente/clasificador**

|Métrica|Umbral|
|:-----|:-----|
|DegradationAvg |Mayor que 1,0 (-1 red MOS) |
|RoundTrip |Mayor que 500  |
|PacketLossRate |Mayor que 0,1 (10%) |
|JitterInterArrival |Mayor que 30  |
|RatioConcealedSamplesAvg |Mayor que 0,07 |
|||

Definición de JPDR = definición de llamada deficiente menos RatioConcealedSamplesAvg 

## <a name="where-is-callercallee"></a>¿Dónde está el autor/destinatario de la llamada?

El CQD no usa los campos llamador y destinatario, en su lugar, usa "primero" y "segundo" porque hay pasos que intervienen entre quien llama y quien llama.

 **Primer** Siempre será el extremo del servidor (por ejemplo, el MCU AV o el servidor de mediación) si un servidor está involucrado en la transmisión.

 **Segundo**: siempre será el extremo del cliente, a no ser que se trate de una secuencia servidor-servidor. 

**Ejemplo de clasificación de Primero y Segundo**

|Extremo 1 UAType |Extremo 2 UUAType |Primero|Segundo|
|:-----|:-----|:-----|:-----|
|2 (AVMCU)  |4 (Skype Empresarial)  |Extremo 1 |Extremo 2 |
|2 (AVMCU)  |1 (mMediationServer)  |Extremo 2 |Extremo 1 |
|4 (Skype Empresarial) |4 (Skype Empresarial)  |El autor de la llamada en MediaLine  |El destinatario de la llamada en MMediaLine  |
|||||

Si ambos puntos de conexión son del mismo tipo, el CQD realiza la entrada de la llamada en primer lugar y el destinatario de la llamada en segundo lugar. Para obtener más información sobre los nombres de extremos, consulte [este blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx).

## <a name="accounting-for-vpn"></a>Preparación para VPN

Si se sabe que la solución VPN está configurada correctamente, está todo listo. En caso contrario, use uno de los métodos siguientes:

- Cree un tipo de red llamado VPN (recomendado) y asocie las subredes VPN con el nuevo tipo de red "VPN".
- Cree un edificio llamado VPN y asocie las subredes VPN con este edificio. 

## <a name="query-fundamentals"></a>Aspectos básicos de las consultas

Una consulta con el formato correcto contiene estos tres parámetros: 

- Medida
- Dimensión
- Filtro

Un ejemplo de una consulta con el formato correcto sería "Mostrarme secuencias deficientes [Medida] por subred [dimensión] para el edificio 6 [filtro]."

## <a name="what-does-union-do"></a>¿Qué hace UNION?

Union le permite filtrar condiciones con el operador AND. Hay escenarios en los que puede combinar varias condiciones de filtro para lograr un resultado similar a una operación OR.

Ejemplo: para obtener todas las transmisiones de un edificio, UNION proporciona una vista distintiva del conjunto de los datasets combinados. Para usar UNION, inserte texto común en el campo UNION en las dos condiciones de filtro que quiera unir.

## <a name="default-report-breakdown"></a>Desglose de informe predeterminado

Si la red inalámbrica se administra internamente, puede volver a crear los informes de red inalámbrica en el cubo Administradas. 

![Desglose del informe de CQD](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a>Procesos operativos

Revise y solucione las secuencias administradas en primer lugar. La calidad en esta sección debe estar totalmente bajo su control, por lo que es más sencillo solucionar problemas en este punto.

### <a name="managed-streams"></a>Secuencias administradas 

Revise y solucione las secuencias administradas en el siguiente orden: 

1. Servidor-servidor 
2.  Servidor-cable-interior
3. Cable-cable-interior 

### <a name="unmanaged-streams"></a>Secuencias no administradas

Revise y solucione las secuencias no administradas en el siguiente orden: 

1. Servidor-Wi-Fi-interior
2. Servidor-cable-exterior
3. Servidor-Wi-Fi-exterior
4. Cable-externa-directa
5. Cable-externa-relé
6. Otras no gestionadas
