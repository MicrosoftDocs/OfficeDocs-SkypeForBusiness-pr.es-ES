---
title: Usar panel de calidad de llamadas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 'Resumen: obtenga información sobre cómo usar el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: d4787671955159d2bef0144872c50caccbbbb8eb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098966"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Usar panel de calidad de llamadas para Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo usar el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.

El Panel de calidad de llamadas (CQD) permite a los profesionales de TI usar datos agregados para identificar problemas de creación de problemas de calidad de medios comparando estadísticas de grupos de usuarios para identificar tendencias y patrones. CQD no se centra en resolver problemas de llamadas individuales, sino en identificar problemas y soluciones que se aplican a muchos usuarios.

## <a name="call-quality-dashboard-user-guide"></a>Guía del usuario del panel de calidad de llamadas

CQD es un portal web para crear y organizar rápidamente informes basados en datos de calidad de experiencia (QoE). CQD implementa un cubo SSAS para agregar los datos en la base de datos de métricas de QoE y permite a los administradores crear y modificar informes o realizar investigaciones en tiempo real. Aunque es posible usar Excel para conectarse directamente al cubo, el portal está optimizado para varios flujos de trabajo que implican datos de QoE. Los datos incluyen:

- Datos de informe almacenados en caché para un acceso rápido
- Vínculos profundos a páginas de informes para compartir y publicar información
- Edición y creación de informes optimizadas y metadatos editables para descripciones de informes.

Además, CQD expone las API web que dan a los usuarios acceso mediante programación a los datos del cubo para su uso en paneles personalizados.

### <a name="feature-overview"></a>Descripción de la característica

Cuando visite el Panel de calidad de llamadas, verá la siguiente pantalla:

![Usar CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. El "Panel de resumen" es donde se encuentra el contexto del "Conjunto de informes" (a la derecha).
2. Haga clic en "Editar" en el PaneReport de resumen para establecer las propiedades de nivel (incluido el alto del eje Y).
3. La ruta de navegación le ayuda a identificar la ubicación actual dentro de la jerarquía del conjunto de informes.
4. Los informes con subinforme se muestran con un vínculo azul. Haga clic en el vínculo para profundizar en los informes secundarios.

Mueva el mouse sobre los gráficos de barras y las líneas de tendencia para mostrar valores detallados. El informe que tiene el foco muestra el menú de acciones: "Editar", "Clonar", "Eliminar" y "Descargar".

### <a name="default-reports"></a>Informes predeterminados

Cuando accede por primera vez al portal del Panel de calidad de llamadas, se crea automáticamente un conjunto predeterminado de informes. Estos informes a veces se conocen como informes del sistema. Puede modificar o eliminar libremente estos informes o extenderlos mediante la creación de nuevos informes secundarios y del mismo nivel.

En el nivel superior, el informe "Tendencia mensual de secuencias de audio" muestra la tendencia mensual de todas las secuencias de audio. Mueva el mouse sobre las barras de un gráfico de barras para mostrar una vista más detallada de los datos representados por el gráfico de barras. Haga clic en el título del informe de tendencias mensuales de secuencias de audio para ir al informe "Secuencias de audio administradas frente a no administradas", donde los informes se dividen entre llamadas administradas y no administradas. Las llamadas administradas son llamadas realizadas desde dentro del firewall corporativo a través de conexiones cableadas. Las llamadas no administradas incluyen llamadas realizadas desde fuera del firewall corporativo y todas las llamadas realizadas a través de Wi-Fi.

El otro informe de nivel superior se denomina "Histograma de clasificación de calidad de llamada notificado por el usuario". Las clasificaciones de calidad de llamadas son los números que los usuarios de Skype Empresarial dan al final de una llamada para indicar la calidad de la llamada. Los números de clasificación oscilan entre 1 y 5, 1 es el peor y 5 es el mejor. El histograma muestra el número de llamadas de audio que tenían la clasificación indicada en un mes.

Haga clic en el título de cualquiera de los informes para navegar a los informes con más filtros en los datos. En los informes del sistema, cada informe secundario muestra un subconjunto de los datos disponibles en su informe primario. El modelo de solución de problemas es sencillo: investigar a qué subinforme se limitan los datos o tendencias que sugieren un problema y reducir gradualmente el espacio del problema. La capacidad de crear subinformes le permite investigar sus propias conjeturas sobre la causa de tendencias de datos específicas.

### <a name="create-and-edit-reports"></a>Crear y editar informes

Haga clic en "Editar" en el menú de acciones de un informe para ver el Editor de informes. Cada informe tiene una copia de seguridad de una consulta en el cubo. Un informe es una visualización de los datos devueltos por su consulta. El Editor de informes le ayuda a editar estas consultas y las opciones de presentación del informe. Al abrir el Editor de informes, verá:

![Usar CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Las dimensiones, las medidas y los filtros se eligen en el panel izquierdo. Mantenga el mouse sobre uno de los valores existentes para mostrar un botón "x" que permita quitar el valor. Haga clic en el botón "más" junto a un encabezado para abrir el cuadro de diálogo donde puede agregar una nueva dimensión, medida o filtro.
2. Las opciones de personalización del gráfico se muestran en la parte superior.
3. Una vista previa del informe está disponible en el Editor de informes.
4. Se puede crear una descripción detallada del informe con el cuadro de edición en la parte inferior.

### <a name="sparklines-in-tables"></a>Minigráficos en tablas

Cuando StartDate.Month se agrega como una dimensión y los datos se representan como una tendencia en forma de tabla, los gráficos de barras y los minigráficos se pueden mostrar dentro de las celdas de la tabla. Mueva el puntero del mouse sobre el gráfico de barras y los minigráficos para mostrar los valores de los meses individuales.

![Usar CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

Para que aparezcan los gráficos de barras y los minigráficos, se debe activar la casilla "Mostrar minigráficos" en la parte superior del Editor de informes. Esto selecciona la opción Tendencia y mueve Mes hacia abajo para ser la última dimensión, que también se puede lograr haciendo clic en Mes y usando las flechas arriba y abajo para desplazar StartDate.Month hacia arriba o hacia abajo.

### <a name="settings"></a>Configuración

El menú de configuración contiene vínculos a páginas útiles como las páginas Estado del sistema y Acerca de, y se encuentra en la esquina superior derecha del panel.

![Usar CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

Si se muestran descripciones y marcas de tiempo para usuarios individuales, esta configuración solo afecta a la versión individual del panel y no modifica el conjunto de informes ni lo que otros usuarios ven. Borrar la memoria caché hace que todas las consultas vuelvan a cargar sus datos del cubo, mientras que la restauración de valores predeterminados elimina todos los informes creados o modificados por el usuario y vuelve a crear el conjunto de informes del sistema, lo que un usuario vería al iniciar sesión por primera vez.

El vínculo Panel de usuarios muestra una página en la que los usuarios pueden ver otros usuarios de CQD y examinar sus informes. Para compartir un conjunto de informes, copie el vínculo en la barra de direcciones URL y compártolo con otro usuario de CQD. Este vínculo es el mismo vínculo que otros usuarios verían en la página Vínculo del panel de usuarios bajo el nombre de usuario del usuario.

### <a name="supplying-subnet-information"></a>Suministro de información de subred

Se puede revelar información adicional si se especifica información específica del sitio en la base de datos de archivo para proporcionar información de asignación de subred a edificio (por ejemplo, calidad de llamadas cableadas o inalámbricas por creación).

Como mínimo, complete las tablas siguientes para crear estos informes:

- CqdBuilding
- CqdNetwork

Se puede proporcionar información adicional en las tablas CqdBuildingType y CqdBuildingOwnershipType para permitir el filtrado y la obtención de detalles adicionales.

Los datos usados para estas tablas se definen de la siguiente manera:

**CqdBuilding**

|Column|Tipo de datos|¿Permitir valores Null?|Detalles|
|:-----|:-----|:-----|:-----|
|BuildingKey |Entero |No |Clave principal de la tabla CqdBuilding. |
|BuildingName |varchar(80) |No |Nombre del edificio. |
|BuildingShortName |varchar(10) |No |Versión más corta del nombre del edificio. |
|OwnershipTypeId |Entero |No |Clave externa, coincide con una de las entradas de la tabla CqdBuildingOwners. |
|BuildingTypeId |Entero |No |Clave externa, coincide con una de las entradas de la tabla CqdBuildingType. |
|Latitude |float |Sí |Latitud del edificio. |
|Longitude |float |Sí |Longitud del edificio. |
|CityName |varchar(30) |Sí |Nombre de la ciudad donde se encuentra el edificio. |
|ZipCode |varchar(25) |Sí |Código postal donde se encuentra el edificio. |
|CountryShortCode |varchar(2) |Sí |Códigos ISO 3166-1 alfa-2 para el país donde se encuentra el edificio. |
|StateProvinceCode |varchar(3) |Sí |Abreviatura de tres letras para el estado/provincia donde se encuentra el edificio. |
|InsideCorp |bit |Sí |Bit indica si el edificio forma parte de la red corporativa. |
|BuildingOfficeType |nvarchar(150) |Sí |Descripción del tipo de oficina de creación. |
|Región |varchar(25) |Sí |Región donde se encuentra el edificio. |
|||||

**CqdNetwork**

|Column|Tipo de datos|¿Permitir valores Null?|Detalles|
|:-----|:-----|:-----|:-----|
|Red |varchar(25) |No |Dirección de subred. |
|NetworkRange |tinyint |Sí |Máscara de la subred. |
|NetworkNameID |Entero |Sí |Opcionalmente se asigna a una fila de la tabla CqdNetworkName. |
|BuildingKey |Entero |Sí |Clave externa, coincide con una de las entradas de la tabla CqdBuilding. |
|UpdatedDate |datetime |No |Fecha y hora de la última actualización de la entrada. |
||||||

De forma predeterminada, esta tabla siguiente tiene una entrada (0, "Desconocido").

**CqdBuildingType**

|Column|Tipo de datos|¿Permitir valores Null?|Detalles|
|:-----|:-----|:-----|:-----|
|BuildingTypeId |Entero |No |Clave principal de la tabla CqdBuildingType. |
|BuildingTypeDesc |char(18) |No |Descripción del tipo de creación. |
|||||

De forma predeterminada, esta tabla siguiente tiene una entrada (0, 'Unknown', 0, null).

**CqdBuildingOwnershipType**

|Column|Tipo de datos|¿Permitir valores Null?|Detalles|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId |Entero |No |Clave principal de la tabla CqdBuildingOwnershipType. |
|OwnershipTypeDesc |varchar(25) |No |Descripción del tipo de propiedad. |
|LeaseInd |tinyint |Sí |Índice que hace referencia a otra fila de la tabla CqdBuildingOwnershipType, que se usa para identificar los edificios arrendados. |
|Owner |varchar(50) |Sí |Propietario del edificio. |
|||||

De forma predeterminada, esta tabla siguiente tiene una entrada (0, 'Unknown', 0, null).

**CqdBssid**

|Column|Tipo de datos|¿Permitir valores Null?|Detalles|
|:-----|:-----|:-----|:-----|
|bss |nvarchar(50) |No |Clave principal para la tabla CqdBssid. Es el BSSID del punto de acceso WiFi. |
|ess |nvarchar(50) |Sí |Información del controlador de punto de acceso Wifi. |
|phy |nvarchar(50) |Sí |Información de Phy. |
|ap |nvarchar(50) |Sí |Nombre del punto de acceso Wifi. |
|Creación |nvarchar(500) |Sí |Nombre de edificio en el que se encuentra el punto de acceso WiFi. |
||||

## <a name="cqd-streams"></a>Secuencias CQD

Una secuencia CQD se considera buena, mala o sin clasificar. CQM 1.5 ahora usa la siguiente definición de CQD:

- Una secuencia deficiente es cualquier combinación de las métricas de llamadas deficientes más allá del umbral.
- Cuando una secuencia de una llamada es deficiente, ambas secuencias de la llamada se marcan como deficientes. En las conferencias, cada participante se cuenta como una llamada única y se notifica de forma independiente de todas las demás.
- Las secuencias sin clasificar son secuencias sin métricas de calidad (es decir, transacciones sintéticas o llamadas cortas).
- Secuencias válidas = clientes que no son móviles
- Clasificador no se puede modificar

**Definición o clasificador de llamadas deficientes**

|Métrica|Umbral|
|:-----|:-----|
|DegradationAvg |Mayor que 1.0 (-1 MOS de red) |
|RoundTrip |Más de 500 |
|PacketLossRate |Mayor que 0,1 (10 %) |
|JitterInterArrival |Mayor de 30 |
|RatioConcealedSamplesAvg |Mayor que 0,07 |
|||

Definición de JPDR = Definición de llamada deficiente menos RatioConcealedSamplesAvg

## <a name="where-is-callercallee"></a>¿Dónde está el autor de la llamada/el destinatario de la llamada?

CQD no usa campos de llamador o destinatario de llamada, sino que usa "First" y "Second" porque hay pasos que intervienen entre el autor de la llamada y el destinatario de la llamada.

 **Primero** Siempre será el extremo del servidor (por ejemplo, MCU av o servidor de mediación) si un servidor está implicado en la secuencia.

 **Segundo** Siempre será el extremo cliente, a menos que sea una Server-Server secuencia.

**Ejemplo de clasificación first y second**

|Endpoint 1 UAType|Endpoint 2 UUAType|Primero|Segundo|
|:-----|:-----|:-----|:-----|
|2 (AVMCU) |4 (Skype Empresarial) |Extremo 1 |Extremo 2 |
|2 (AVMCU) |1 (mMediationServer) |Extremo 2 |Extremo 1 |
|4 (Skype Empresarial) |4 (Skype Empresarial) |El autor de la llamada en MediaLine |El destinatario de la llamada en MMediaLine |
|||||

Si ambos extremos son del mismo tipo, CQD hace que la entrada autor de la llamada sea First y la Llamada Second. Para obtener más información acerca de los nombres de los puntos de conexión, [vea este blog](/archive/blogs/jenstr/call-quality-dashboard-tips-and-tricks).

## <a name="accounting-for-vpn"></a>Contabilidad de VPN

Si se sabe que la solución VPN establece con precisión la marca VPN, está todo establecido. De lo contrario, use uno de los métodos siguientes:

- Cree un tipo de red denominado VPN (preferido) y, a continuación, asocie subredes VPN con este nuevo tipo de red VPN.
- Cree un edificio denominado VPN y, a continuación, asocie subredes VPN con este edificio.

## <a name="query-fundamentals"></a>Conceptos básicos de consulta

Una consulta bien formada contiene los tres parámetros siguientes:

- Medida
- Dimension
- Filter

Un ejemplo de una consulta bien formada sería "Show me Poor Streams [Measurement] by Subnet [Dimension] for Building 6 [Filter]".

## <a name="what-does-union-do"></a>¿Qué hace UNION?

Union permite filtrar las condiciones con el operador AND. Hay escenarios en los que puede combinar varias condiciones de filtro para lograr un resultado similar a una operación OR.

Ejemplo: para obtener todas las secuencias de un edificio, UNION proporciona una vista distinta del conjunto de datos combinado. Para usar UNION, inserte texto común en el campo UNION en las dos condiciones de filtro que desea union.

## <a name="default-report-breakdown"></a>Desglose de informes predeterminado

Si la tecnología inalámbrica se administra internamente, puede volver a crear los informes inalámbricos en el cubo administrado.

![Desglose de informes CQD](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a>Procesos operativos

Revise y corrija primero las secuencias administradas. La calidad en esta área debe estar al 100 % dentro del control y, por lo tanto, es más fácil de corregir.

### <a name="managed-streams"></a>Secuencias administradas

Revise y corrija secuencias administradas en el siguiente orden:

1. Server-Server
2. Server-Wired-Inside
3. Wired-Wired-Inside

### <a name="unmanaged-streams"></a>Secuencias no administradas

Revise y corrija secuencias no administradas en el siguiente orden:

1. Server-Wifi-Inside
2. Server-Wired-Outside
3. Server-Wifi-Outside
4. Wired-Outside-Direct
5. Wired-Outside-Relay
6. Otros no administrados