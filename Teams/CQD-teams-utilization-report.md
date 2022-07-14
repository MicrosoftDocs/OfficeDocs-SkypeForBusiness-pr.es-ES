---
title: Ver el uso de Microsoft Teams en Power BI con datos del CQD
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Use los informes de Power BI de uso de Equipos para acceder a los datos del Panel de calidad de llamadas (CQD) de Microsoft Teams para realizar un seguimiento del uso de Microsoft Teams en su organización.
ms.openlocfilehash: 6e96f9dd06f872f2907d04aa335e2af2d7a75f2b
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790345"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>Ver el uso de Microsoft Teams en Power BI con datos del CQD

Como novedad en marzo de 2020, hemos agregado un informe sobre el uso de Equipos a nuestras plantillas de consulta descargables de [Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 

Estos nuevos informes de uso de Equipos le permiten ver cómo (y cuánto) usan los usuarios de Microsoft Teams accediendo a los datos del Panel de calidad de llamadas (CQD) de Teams. Estos informes están pensados para ser una ubicación centralizada a la que pueden dirigirse rápidamente tanto los administradores como los líderes empresariales para obtener estos datos.

El informe de Power BI sobre el uso de equipos consta de dos informes principales: **[Resumen del recuento de llamadas](#call-count-summary-report)** y **[Resumen de minutos de audio](#audio-minutes-summary-report)**. Los informes [Uso diario](#daily-usage), [Detalles regionales del audio](#regional-audio-details), [Detalles de conferencia](#conference-details) y [Lista](#user-list) de usuarios entran en juego cuando un usuario aprovecha los informes de detalles, que se indican en las descripciones siguientes.

> [!NOTE]
> Los datos de compilación y subred deben rellenarse para proporcionar capacidades regionales y de filtrado de red.

## <a name="call-count-summary-report"></a>Informe de resumen del recuento de llamadas

La página principal (Resumen del recuento de llamadas) proporciona inmediatamente el número de sesiones de audio, vídeo y uso compartido de pantalla en los últimos 30 y 90 días, como se indica en el título de la sección. Los datos mostrados inicialmente son para la organización en su conjunto y se pueden filtrar con las opciones desplegables de segmentación de datos del lado izquierdo de la página.

![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report1.png)

1. A la derecha de los menús desplegables de segmentación de datos, el número de llamadas por tipo de medio se desglosa en una vista interna o externa en los últimos treinta días. Podemos ver a través de la captura de pantalla anterior que hay más llamadas que ocurren desde ubicaciones externas a la organización, lo que tiene sentido teniendo en cuenta el entorno global actual.
  ![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report2.png)

1. A la derecha del cuadro Recuento de tipos de medios, tenemos el recuento mensual de llamadas por tipo de medio de los últimos 90 días. Puede mantener el puntero sobre cada tipo de columna y elemento multimedia para mostrar el recuento de un mes anterior o del mes actual hasta la fecha, proporcionando información de tendencias de uso.
  ![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report3.png)
 

1. El gráfico central funciona como lo hace el gráfico de 90 días, sin embargo, proporciona una vista de uso diario de los últimos 30 días y permite al usuario hacer clic con el botón derecho y explorar en profundidad los detalles de un día específico.
  ![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report4.png)

En la sección inferior izquierda de la página, encontrará una tabla que proporciona valores totales para cada tipo de elemento multimedia durante el último año. 
    ![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report5.png)
    ![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report6.png)   

A la derecha de la tabla, un gráfico de barras muestra los clientes con más uso (llamadas o transmisiones) de los últimos 30 días.
   ![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report7.png)

El último conjunto de gráficos de esta página muestra cada tipo de elemento multimedia individualmente, con un desglose que muestra la conferencia y el uso de P2P. Los siguientes gráficos muestran que hay un número significativamente mayor de uso de conferencias en comparación con P2P.
  ![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>Informe de resumen de minutos de audio

En el informe Uso de minutos de audio, el uso total de minutos se proporciona a través de algunas vistas diferentes. 

Tenemos el resumen de uso de treinta días que se muestra junto a las segmentaciones de datos como cuadros de texto fáciles de usar. El número superior muestra el total de treinta días, con desgloses internos y externos por debajo.

![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report9.png)

El gráfico de barras superior derecha proporciona una vista de un año del uso del audio de conferencia. Mantenga el mouse sobre el mes para mostrar los minutos de audio de la conferencia.

Para mostrar la diferencia entre P2P y el audio de conferencia, el gráfico inferior izquierdo toma todo el audio del año pasado y lo divide entre los dos tipos.

![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report10.png)

El último gráfico de la página Minutos de audio muestra el uso de minutos de audio en una superposición de mapa global. Este gráfico solo funcionará si los datos de compilación y subred se cargan en el inquilino. El gráfico circular en superposición en el mapa se puede explorar en profundidad, proporcionando posteriormente el uso de audio regional.

![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>Funciones de obtención de detalles

Como se indicó anteriormente, los usuarios pueden explorar en profundidad los informes de uso diario y regional.

### <a name="daily-usage"></a>Uso diario

El informe Uso diario permite a un administrador identificar los períodos máximos de consumo a lo largo de un día. Además del uso, también podemos capturar la opinión general del usuario y los comentarios de ese día.

![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report12.png)

El informe Uso diario muestra el número de recursos compartidos de audio, vídeo y pantalla para el día seleccionado con la capacidad adicional de diferenciar entre conectividad interna y externa. Un desglose de conferencias y pares es a la derecha inmediata del cuadro total de modalidades. En la parte superior derecha del informe se proporciona una lista de conferencias con su id. y participantes asociados para el día. La lista de conferencias también proporciona un resumen adicional del informe de detalles de la conferencia. REEMPLAZAR GRÁFICO

![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report13.png)

El gráfico de barras en el área central permite al usuario identificar periodos de consumo máximo a lo largo de un día. Los usuarios pueden explorar en profundidad la hora representada en el gráfico que presentará el informe de lista de usuarios durante la hora.

A la derecha del gráfico de barras, los comentarios del usuario se presentan en un formato visual. Aunque la opinión de los usuarios puede ser subjetiva, proporciona información que se puede usar para identificar posibles problemas.

La tabla inferior proporciona una gama de métricas para el día. Los porcentajes bajos junto con las tasas de errores pueden proporcionar a un administrador áreas potenciales de mejora. Cada hora también se puede seleccionar individualmente como se muestra a continuación.

Estos datos se pueden usar para identificar las regiones que tienen problemas durante las horas de consumo máximo.


Haga clic en la columna de ese día para mostrar las métricas de esa hora.
![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report14.png)
  
  1.  La tabla debajo del gráfico mostrará las métricas correspondientes a esa hora. Esto se puede ordenar por cualquier encabezado de columna; sin embargo, nos interesaría encontrar áreas problemáticas.  
    ![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report15.png)
    
  2.  Vemos que la región IND está experimentando un rendimiento de vídeo deficiente en las conferencias durante este período de tiempo. Posteriormente, los informes de Microsoft del QER del CQD se pueden utilizar para restringir la ubicación problemática a medida que se ha identificado la región y el período de tiempo.

### <a name="conference-details"></a>Detalles de conferencia

El informe Detalles de la conferencia proporciona información adicional para las reuniones, desde una lista de asistentes hasta los tipos de medios que se usan durante la sesión.

Haga clic con el botón derecho en una conferencia en la barra del participante en el gráfico de id. de conferencia de la página Uso diario para explorar en profundidad los detalles de la conferencia.

![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report24.png)

![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report25.png)
  

Podemos ver a los participantes en la conferencia, así como toda la información pertinente, hasta la pérdida de paquetes y la vibración para ayudar con los posibles esfuerzos de solución de problemas en la tabla inferior.

![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>Detalles de audio regional

La exploración en profundidad Detalles de audio regionales muestra específicamente el uso de minutos de audio para la región seleccionada. Los usuarios con acceso al CQD pueden ver las tendencias de uso del audio P2P y de conferencia dentro de la región seleccionada.

1.  En la página Resumen del recuento de llamadas, explore en profundidad hasta una región específica a través de la tabla.
  ![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report16.png)

2.  Seleccione la fila con la región para la que se necesita información adicional.
  ![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report17.png)

3.  Las tendencias de datos muestran un número significativo de minutos de uso en la red interna, con conferencias muy superiores al uso de P2P.
  ![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report18.png)

La tendencia regional de audio se puede utilizar para mostrar cómo los usuarios se ven afectados por influencias externas en el mundo. Concretamente, ahora mismo, esperamos que aumente el uso externo de las regiones EMEA y APAC, y que las personas que se les solicite trabajen de forma remota.


### <a name="user-list"></a>Lista de usuarios

El detalle Lista de usuarios proporciona, como es de esperar, información específica del usuario para una hora específica seleccionada por la persona que visualiza el informe. Se puede acceder al informe Lista de usuarios a través de un resumen del gráfico Tendencias horarias del informe Uso diario. Haga clic con el botón derecho en la hora en la que se necesita información adicional y seleccione Explorar en profundidad y Lista de usuarios, como se muestra a continuación.

![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report19.png)

El informe Lista de usuarios muestra la conectividad interna o externa a través del gráfico de anillos en la parte superior central de la página. Podemos ver que hay una gran participación de Fuera de la red corporativa en la imagen siguiente.

En la parte superior derecha del gráfico se muestra el número de llamadas realizadas por cada usuario en esa hora.

![Captura de pantalla: Informes de uso de Teams.](media/CQD-teams-utilization-report20.png)

La tabla inferior proporciona información detallada para las sesiones en las que participó cada usuario durante esa hora. La columna Tipo de error es útil para determinar qué causaba que se anulara una llamada. Las columnas Capture y Render Device son útiles para identificar por qué se ha notificado que una llamada tiene una mala calidad.


## <a name="related-topics"></a>Temas relacionados

[Dimensiones y medidas disponibles en el Panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de la secuencia en el Panel de calidad de llamadas](stream-classification-in-call-quality-dashboard.md)

[Configurar el análisis de llamadas de Skype Empresarial](set-up-call-analytics.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análisis de llamadas y Panel de calidad de llamadas](./monitor-call-quality-qos.md)

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)
