---
title: Implementar la administración de Sistemas de salas de Skype v2 con OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: En este artículo se explica cómo implementar la administración de dispositivos de sistemas de salón de Skype v2 de manera integrada, end-to-end con el conjunto de aplicaciones de administración de operaciones de Microsoft.
ms.openlocfilehash: b0e43360b92b2ac8fdc32794a03942ec5c7755dc
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501035"
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>Implementar la administración de Sistemas de salas de Skype v2 con OMS
 
En este artículo se describe cómo configurar e implementar administración integrada, end-to-end de dispositivos de sistemas de salón de Skype v2 mediante el uso conjunto de aplicaciones de administración de operaciones de Microsoft.
  
Puede configurar Microsoft Operations Management Suite para proporcionar básico telemetry y alertas que le ayudarán a administración Skype dispositivos de sala de la reunión. A medida que crezca la solución de administración, decide implementar datos adicionales y capacidades de administración para crear una vista más detallada de la disponibilidad de dispositivos y el rendimiento.

Siguiendo esta guía, puede usar un panel similar al ejemplo siguiente para obtener el estado detallado de informes de disponibilidad de dispositivo, aplicación y mantenimiento de hardware y distribución de la versión de aplicación de sistemas de salón de Skype v2.

![Vista de OMS de ejemplo para SRS v2] (../../media/Deploy_OMS_1.png "Vista de OMS de ejemplo para SRS v2")
  
A un mayor nivel, debe realizar las siguientes tareas:


1.  [Validar la configuración del conjunto de aplicaciones de administración de operaciones](with-oms.md#validate_OMS)
2.  [Configurar dispositivos de prueba para la instalación de administración del conjunto de aplicaciones de administración de operaciones](with-oms.md#configure_test_devices)
3.  [Asignar campos personalizados](with-oms.md#Custom_fields)
4.  [Definir las vistas de v2 de sistemas de salón de Skype en conjunto de aplicaciones de administración de operaciones](with-oms.md#Define_Views)
5.  [Definir alertas](with-oms.md#Alerts)
6.  [Configurar todos los dispositivos para el conjunto de aplicaciones de administración de operaciones](with-oms.md#configure_all_devices)
7.  [Configurar más soluciones del conjunto de aplicaciones de administración de operaciones](with-oms.md#Solutions)

> [!IMPORTANT]
> Aunque con la configuración mínima, el conjunto de aplicaciones de administración de operaciones puede supervisar un equipo que ejecute un sistema operativo Windows, aún hay algunos pasos de sistemas específicas de la sala de Skype que debe tomar antes de iniciar la implementación de agentes a todos los sistemas de salón de Skype dispositivos.
> Por lo tanto, se recomienda encarecidamente que realizar todos los pasos de configuración en el orden correcto para un controlado el programa de instalación y configuración. La calidad del resultado final depende mucho de la calidad de la configuración inicial.

## <a name="validate-operations-management-suite-configuration"></a>Validar la configuración del conjunto de aplicaciones de administración de operaciones
<a name="validate_OMS"> </a>

Debe tener un área de trabajo del conjunto de aplicaciones de administración de operaciones para iniciar la recopilación de registros de dispositivos de sistemas de salón de Skype. Un área de trabajo es un entorno de análisis de registro único con su propio repositorio de datos, orígenes de datos y soluciones. Si ya dispone de un área de trabajo de análisis de registro existente, puede utilizarlo para supervisar la implementación de sistemas de salón de Skype o puede crear un área de trabajo de análisis de registro dedicado específico de la supervisión de los sistemas de la sala de Skype necesita.

Si necesita crear una nueva área de trabajo de análisis de registro, siga las instrucciones que aparecen en el artículo [crear un área de trabajo de análisis de registro en el portal de Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-quick-create-workspace)

> [!NOTE]
> Para usar el análisis de registro con el conjunto de aplicaciones de administración de operaciones, debe tener una suscripción de Azure activa. Si no dispone de una suscripción de Azure, puede crear [una suscripción de prueba gratuita](https://azure.microsoft.com/free) como punto de partida.


### <a name="configure-operations-management-suite-to-collect-skype-room-systems-event-logs"></a>Configurar el conjunto de aplicaciones de administración de operaciones para recopilar los registros de eventos de sistemas de salón de Skype

Análisis de registro sólo recopila eventos de los registros de eventos de Windows que se especifican en la configuración. Para cada registro, se recopilan sólo los eventos con los niveles de gravedad seleccionados.

Debe configurar el conjunto de aplicaciones de administración de operaciones para recopilar los registros necesarios para supervisar el estado de dispositivo y aplicación de sistemas de salón de Skype. Los dispositivos de v2 de Skype salón sistemas usan el registro de eventos de sistemas de salón de Skype.

Para configurar el conjunto de aplicaciones de administración de operaciones para recopilar los eventos de sistemas de salón de Skype, vea [orígenes de datos de registro de eventos de Windows en el registro de análisis](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

![Configuración del registro de eventos] (../../media/Deploy_OMS_2.png "Configuración del registro de eventos")


> [!IMPORTANT]
> Seleccione el registro de eventos del sistema de salas de Skype y, a continuación, seleccione las casillas de verificación **Error**, **Advertencia**e **información** .

## <a name="configure-test-devices-for-operations-management-suite-setup"></a>Configurar dispositivos de prueba para el programa de instalación del conjunto de aplicaciones de administración de operaciones
<a name="configure_test_devices"> </a>

Debe preparar el conjunto de aplicaciones de las operaciones de administración para poder supervisar los eventos relacionados con sistemas de salón de Skype. Para empezar con, necesita implementar los agentes del conjunto de aplicaciones de administración de operaciones en sólo uno o dos sistemas de salón de Skype los dispositivos que tienen acceso físico a y los dispositivos de prueba generar algunos datos e inserción al área de trabajo de análisis de registro.

### <a name="install-operations-management-suite-agents-to-test-devices"></a>Instalar los agentes de conjunto de aplicaciones de administración de operaciones para los dispositivos de prueba

Implementar al agente de conjunto de aplicaciones de administración de operaciones en los dispositivos de prueba mediante el uso de las instrucciones proporcionadas en [equipos Windows conectarse al servicio de registro de análisis de Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows). En este artículo se proporciona información detallada sobre los pasos para la implementación de Microsoft de supervisión agente para Windows, instrucciones para obtener el identificador de área de trabajo de las operaciones de administración de conjunto de aplicaciones de y la clave principal para obtener los dispositivos de sistemas de salón de Skype conectado a su Implementación de conjunto de aplicaciones de administración de operaciones y los pasos para comprobar la conectividad del agente para el análisis de registro.

### <a name="generate-sample-skype-room-systems-events"></a>Generar eventos de sistemas de salón de Skype de ejemplo

Después de que el agente de conjunto de aplicaciones de administración de operaciones se implementa en los dispositivos de prueba, compruebe que se recopilan los datos de registro de eventos necesarios por el análisis de registro.

1.  Inicie sesión el [portal del conjunto de aplicaciones de administración de operaciones de Microsoft](http://aka.ms/omsportal).

2.  Se enumeran los eventos generados por un dispositivo de sistemas de salón de Skype:
    1.  Vaya a la **Búsqueda de registro** y usar una consulta para recuperar los registros que va a tener el campo personalizado.
    2.  Consulta de ejemplo:`Event | where Source == "SRS-App"`

3.  Asegúrese de que la consulta devuelve los registros de registro que incluyen eventos de latido correcta.

4.  Generar un problema de hardware y validar que se registran los eventos necesarios en el conjunto de aplicaciones de administración de operaciones.
    1.  Desconecte uno de los dispositivos periféricos en la prueba del sistema de sistemas de salón de Skype. Podría tratarse de la cámara, altavoz, micrófono o para mostrar de la sala de frente
    2.  Espere 10 minutos para el registro de eventos se rellene el conjunto de aplicaciones de administración de operaciones.
    3.  Utilizar una consulta para los eventos de error de hardware de lista:`Event | where EventID == 3001`

5.  Generar un problema de la aplicación y validar que se registran los eventos necesarios.
    1.  Modificar la configuración de la aplicación de sistemas de salón de Skype y escriba un par de dirección y contraseña de protocolo de inicio de sesión (SIP) incorrecta.
    2.  Espere 10 minutos para el registro de eventos se rellene el conjunto de aplicaciones de administración de operaciones.
    3.  Utilizar una consulta para los eventos de error de aplicación de lista:`Event | where EventID == 2001`

> [!IMPORTANT]
> Estos registros de eventos de ejemplo se requieren antes de que se pueden configurar los campos personalizados. No continúe con el siguiente paso hasta que haya recopilado los registros de eventos necesarios.

## <a name="map-custom-fields"></a>Asignar campos personalizados
<a name="Custom_fields"> </a>

Usar campos personalizados para extraer datos específicos de los registros de eventos. Debe definir los campos personalizados que se usará más adelante con los mosaicos, vistas de panel y alertas. Vea [campos personalizados de análisis de registro de](https://docs.microsoft.com/azure/log-analytics/log-analytics-custom-fields) y a familiarizarse con los conceptos antes de empezar a crear los campos personalizados.

Para extraer los campos personalizados fuera de los registros de eventos capturados, siga estos pasos:

1.  Inicie sesión el [portal del conjunto de aplicaciones de administración de operaciones de Microsoft](http://aka.ms/omsportal).

2.  Se enumeran los eventos generados por un dispositivo de sistemas de salón de Skype:
    1.  Vaya a la **Búsqueda de registro** y usar una consulta para recuperar los registros que va a tener el campo personalizado.
    2.  Consulta de ejemplo:`Event | where Source == "SRS-App"`

3.  Seleccione uno de los registros, seleccione el botón situado a la izquierda e iniciar al Asistente para la extracción de campo.

![Asistente para la extracción de campo] (../../media/Deploy_OMS_3.png "Asistente para la extracción de campo")

4.  Resalte los datos que le gustaría extraer el RenderedDescription y proporcione un título de campo. Se proporcionan los nombres de campo que se deben usar en la tabla 1.

![Definición de campos personalizados] (../../media/Deploy_OMS_4.png "Definición de campos personalizados")

5.  Use las asignaciones que se muestra en la tabla 1. Conjunto de aplicaciones de administración de operaciones agregará automáticamente la ** \_CF** al definir el nuevo campo de cadena.

> [!IMPORTANT]
> Recuerde que todos los campos JSON y conjunto de aplicaciones de administración de operaciones distinguen mayúsculas de minúsculas.

> Preste atención al estado de la casilla de verificación de suceso en la tabla siguiente. Asegúrese de que confirmar el estado de esta casilla de verificación para el conjunto de aplicaciones de administración de operaciones extraer correctamente los valores de campo personalizado.
> ![Definición de campos personalizados] (../../media/Deploy_OMS_5.png "Definición de campos personalizados") 

**Tabla 1**

| **Campo JSON**               | **Campo personalizado de OMS**       | **Identificador de evento** |
|------------------------------|----------------------------|-----------------|
| Descripción                  | SRSEventDescription_CF     | No seleccionado    |
| ResourceState                | SRSResourceState_CF        | No seleccionado    |
| NombreDeOperación                | SRSOperationName_CF        | No seleccionado    |
| OperationResult              | SRSOperationResult_CF      | No seleccionado    |
| OS                           | SRSOSVersion_CF            | No seleccionado    |
| OSVersion                    | SRSOSLongVersion_CF        | No seleccionado    |
| Alias                        | SRSAlias_CF                | No seleccionado    |
| DisplayName                  | SRSDisplayName_CF          | No seleccionado    |
| AppVersion                   | SRSAppVersion_CF           | No seleccionado    |
| IPv4Address                  | SRSIPv4Address_CF          | No seleccionado    |
| IPv6Address                  | SRSIPv6Address_CF          | No seleccionado    |
| Parte delantera del estado de visualización de salón | SRSFORDStatus_CF           | 3001            |
| Estado de la cámara                | SRSCameraStatus_CF         | 3001            |
| Estado de micrófono de conferencia | SRSConfMicrophoneStatus_CF | 3001            |
| Estado de altavoz de conferencia    | SRSConfSpeakerStatus_CF    | 3001            |
| Estado del altavoz predeterminado       | SRSDefaultSpeakerStatus_CF | 3001            |
| Estado del Sensor de movimiento         | SRSMotionSensorStatus_CF   | 3001            |
| Estado de ingesta HDMI           | SRSHDMIIngestStatus_CF     | 3001            |


## <a name="define-the-skype-room-systems-v2-views-in-operations-management-suite"></a>Definir las vistas de v2 de sistemas de salón de Skype en conjunto de aplicaciones de administración de operaciones
<a name="Define_Views"> </a>

Una vez que se recopilan los datos y se asignan los campos personalizados, puede usar el Diseñador de vistas de conjunto de aplicaciones de administración de operaciones para desarrollar un panel que contiene varios mosaicos para supervisar los eventos de sistemas de salón de Skype v2. Use Diseñador de vistas para crear los siguientes iconos. Para obtener más información, vea [Usar el Diseñador de vistas para crear vistas personalizadas en el registro de análisis](https://docs.microsoft.com/azure/log-analytics/log-analytics-view-designer)

> [!NOTE]
> Deben haber completado los pasos anteriores en esta guía para que los mosaicos del panel funcionen correctamente.


### <a name="create-a-skype-room-systems-v2-dashboard-by-using-the-import-method"></a>Crear un panel de v2 de Skype salón sistemas mediante el método de importación

Puede importar un panel de conjunto de aplicaciones de administración de operaciones e iniciar la supervisión de los dispositivos inmediatamente. Lleve a cabo los siguientes pasos para importar el panel:

1.  Obtenga el archivo del panel de [SkypeRoomSystems_v2.omsview](http://download.microsoft.com/download/9/0/D/90D4826A-9FD2-47D2-B911-97BF1737F4F7/SkypeRoomSystems_v2.omsview) .
2.  Inicie sesión el [portal del conjunto de aplicaciones de administración de operaciones de Microsoft](http://aka.ms/omsportal).
3.  Abra el **Diseñador de vistas**.
4.  Seleccione **Importar**y, a continuación, seleccione el archivo **SkypeRoomSystems_v2.omsview** .
5.  Seleccione **Guardar**.

### <a name="create-a-skype-room-systems-v2-dashboard-manually"></a>Crear un panel de sistemas de salón de Skype v2 de forma manual

Como alternativa, puede crear su propio escritorio y agregar sólo los mosaicos que desea supervisar.

#### <a name="configure-the-overview-tile"></a>Configurar el icono de información general
1.  Abra el **Diseñador de vistas**.
2.  Seleccione el **Icono de información general sobre**y, a continuación, seleccione **dos números** de la galería.
3.  Nombre el mosaico **Skype salón de sistemas**.
4.  Definir el **primer mosaico**:<br>
    **Leyenda:** Dispositivos que se ha enviado un latido al menos una vez dentro del último mes<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Defina el **segundo icono**:<br>
    **Leyenda:** Dispositivos activos que envían un latido dentro de la última hora<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Seleccione **Aplicar**.

### <a name="create-a-tile-that-displays-active-devices"></a>Crear un icono que muestra los dispositivos de activos
1.  Seleccione el **Panel de vista** para empezar a agregar los mosaicos.
2.  Seleccione el **número y la lista** de la Galería de
3.  Definir las propiedades **generales** :<br>
    **Título de grupo:** Estado del latido<br>
    **Nuevo grupo:** Seleccionado
4.  Definir las propiedades de **icono** :<br>
    **Leyenda:** Dispositivos activos (latido enviado en los últimos 20 minutos)<br>
    **Consulta en mosaico:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definir las propiedades de **lista** :<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definir **los títulos de columna**:<br>
    **Nombre:** Nombre para mostrar<br>
    **Valor:** Último latido
7.  Definir **consultas de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar**y, a continuación, en **Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Crear un icono que muestra los dispositivos que tienen problemas de conectividad
1.  Seleccione el **número y la lista** de la Galería de y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** :<br>
    **Título de grupo:** Deje en blanco<br>
    **Nuevo grupo:** No seleccionado
3.  Definir las propiedades de **icono** :<br>
    **Leyenda:** Dispositivos inactivos (ningún mensaje de latido enviado en los últimos 20 minutos)<br>
    **Consulta en mosaico:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definir las propiedades de **lista** :<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definir **los títulos de columna**:<br>
    **Nombre:** Nombre para mostrar<br>
    **Valor:** Último latido
6.  Definir **consultas de navegación**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Seleccione **Aplicar**y, a continuación, en **Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Crear un icono que muestra los dispositivos que tienen un error de hardware

1.  Seleccione el **número y la lista** de la Galería de y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** :<br>
    **Título de grupo:** Hardware<br>
    **Nuevo grupo:** Seleccionado
3.  Definir las propiedades de **icono** :<br>
    **Leyenda:** Dispositivos que ha experimentado un error de hardware en la última hora <br>
    **Consulta en mosaico:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definir las propiedades de **lista** :<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer```
5.  Definir **los títulos de columna**:<br>
    **Nombre:** Nombre para mostrar<br>
    **Valor:** Último Error
6.  Definir **consultas de navegación**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Seleccione **Aplicar**y, a continuación, en **Cerrar**.

### <a name="create-a-tile-that-displays-skype-room-systems-application-versions"></a>Crear un icono que muestra las versiones de la aplicación de sistemas de salón de Skype

1.  Seleccione **rosquilla & lista** de la galería y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** :<br>
    **Título de grupo:** Detalles de la aplicación de sistemas de salón de Skype v2 <br>
    **Nuevo grupo:** Seleccionado
3.  Definir las propiedades de **encabezado** :<br>
    **Título:** Versiones de la aplicación<br>
    **Subtítulo:** Dispositivos que ejecutan versiones de la aplicación específica
4.  Definir las propiedades de **anillo** :<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Del centro de texto:** Dispositivos<br>
    **Operación:** Suma
5.  Definir las propiedades de la **lista** .<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar gráfico:** Seleccionado<br>
    **Habilitar minigráficos:** No seleccionado
6.  Definir **los títulos de columna**.<br>
    **Nombre:** Nombre para mostrar<br>
    **Valor:** Deje en blanco
7.  Definir **consultas de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar** y, a continuación, en **Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Crear un icono que muestra los dispositivos que tienen un error de aplicación

1.  Seleccione el **número y la lista** de la Galería de y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** .<br>
    **Título de grupo:** Deje en blanco<br>
    **Nuevo grupo:** No seleccionado
3.  Definir las propiedades de **mosaico** .<br>
    **Leyenda:** Dispositivos que se produjo un error de aplicación en la última hora<br>
    **Consulta en mosaico:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definir las propiedades de la **lista** .<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **los títulos de columna**.<br>
    **Nombre:** Nombre para mostrar<br>
    **Valor:** Último Error
6.  Definir **consultas de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Seleccione **Aplicar** y, a continuación, en **Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Crear un icono que muestra los dispositivos que se haya reiniciado

1.  Seleccione el **número y la lista** de la Galería de y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** .<br>
    **Título de grupo:** Deje en blanco<br>
    **Nuevo grupo:** No seleccionado
3.  Definir las propiedades de **mosaico** .<br>
    **Leyenda:** Dispositivos donde se ha reiniciado la aplicación en el último 24 horas y el número de reinicios<br>
    **Consulta en mosaico:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Definir las propiedades de la **lista** .<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definir **los títulos de columna**.<br>
    **Nombre:** Nombre para mostrar<br>
    **Valor:** Número de reinicios
6.  Definir **consultas de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Seleccione **Aplicar** y, a continuación, en **Cerrar**.
8.  Seleccione **Guardar** para guardar el panel.

Ahora ha completado la creación de las vistas.

Puede usar el portal del conjunto de aplicaciones de administración de operaciones de Microsoft o los clientes móviles de conjunto de aplicaciones de administración de operaciones para [Windows Phone](https://www.microsoft.com/en-us/store/p/microsoft-operations-management-suite/9wzdncrfjz2r), [iOS](https://itunes.apple.com/us/app/microsoft-operations-management-suite/id1042424859)o [Android](https://play.google.com/store/apps/details?id=com.microsoft.operations.AndroidPhone) para tener acceso a las vistas.

## <a name="configure-alerts-in-operations-management-suite"></a>Configurar las alertas en el conjunto de aplicaciones de administración de operaciones
<a name="Alerts"></a> Dispositivo de sistemas de salón de Skype un cuando detecta un problema, conjunto de aplicaciones de administración de operaciones de Microsoft pueden generar alertas para notificar a los administradores con los detalles del problema.

Conjunto de aplicaciones de administración de operaciones incluye un mecanismo de alerta integrado que se ejecuta a través de las búsquedas de registro programadas a intervalos regulares. Si los resultados de la búsqueda de registro coinciden con algunos criterios determinados, se crea un registro de alerta.

![Mecanismo de alerta de OMS] (../../media/Deploy_OMS_6.png "Mecanismo de alerta de OMS")

La regla, a continuación, puede ejecutar automáticamente una o más acciones para informarle de la alerta de manera proactiva o invocar otro proceso. Las opciones posibles con las alertas del conjunto de aplicaciones de administración de operaciones son:
-   Enviar un correo electrónico
-   Invocación de un proceso externo a través de una solicitud HTTP POST
-   Iniciar un runbook en servicios de automatización de Azure

Vea [las alertas de descripción en el análisis de registro](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts) para obtener más información acerca de las alertas en el conjunto de aplicaciones de administración de operaciones.

> [!NOTE]
> Los siguientes ejemplos envían alertas de correo electrónico cuando un dispositivo de Skype salón sistemas genera un hardware o un error de aplicación. 


### <a name="configure-an-email-alert-for-skype-room-systems-hardware-issues"></a>Configurar una alerta de correo electrónico para problemas de hardware de sistemas de salón de Skype

Configurar una regla de alerta que comprueba para dispositivos de sistemas de salón de Skype que han tenido problemas de hardware dentro de la última hora.
1.  Inicie sesión el [portal del conjunto de aplicaciones de administración de operaciones de Microsoft](http://aka.ms/omsportal).

2.  Seleccione la **búsqueda de registro**.

3.  Escriba la siguiente consulta y, a continuación, seleccione **Ejecutar**.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF 
    |sort by TimeGenerated desc
    ```

4.  Después de ejecuta la consulta, seleccione **alerta**. Se abrirá la página **Agregar regla de alerta** .

5.  Configuración de las alertas mediante el uso de la información siguiente:<br>
    **Nombre de la regla:** Alerta de error de Hardware de sistemas de salón de Skype<br>
    **Descripción:** Lista de los dispositivos que se encuentra un problema de hardware dentro de la última hora<br>
    **Gravedad:** Crítica<br>
    **Consulta:** Utilice la consulta de búsqueda rellenados previamente<br>
    **Ventana de tiempo:** 1 hora<br>
    **Frecuencia de alerta:** 1 hora<br>
    **Número de resultados:** Mayor que 0<br>
    **Asunto de correo electrónico:** Alerta de error de Hardware de sistemas de salón de Skype<br>
    **Destinatarios:** Incluir las direcciones de correo electrónico, con punto y coma como separadores<br>

6.  Seleccione **Guardar**.

### <a name="configure-an-email-alert-for-skype-room-systems-application-issues"></a>Configurar una alerta de correo electrónico para problemas de aplicaciones de sistemas de salón de Skype

Configurar una regla de alerta, que comprueba para dispositivos de sistemas de salón de Skype que han tenido problemas de aplicaciones dentro de la última hora.
1.  Seleccione la **búsqueda de registro**.

2.  Escriba la siguiente consulta y, a continuación, seleccione **Ejecutar**.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(10h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

3.  Después de ejecuta la consulta, seleccione **alerta**. Se abrirá la página **Agregar regla de alerta** .

4.  Configuración de las alertas mediante el uso de la información siguiente:<br>
    **Nombre de la regla:** Alerta de error de aplicación de sistemas de salón de Skype<br>
    **Descripción:** Lista de los dispositivos que se encuentra un problema de la aplicación dentro de la última hora<br>
    **Gravedad:** Crítica<br>
    **Consulta:** Utilice la consulta de búsqueda rellenados previamente<br>
    **Ventana de tiempo:** 1 hora<br>
    **Frecuencia de alerta:** 1 hora<br>
    **Número de resultados:** Mayor que 0<br>
    **Asunto de correo electrónico:** Alerta de error de aplicación de sistemas de salón de Skype<br>
    **Destinatarios:** Incluir las direcciones de correo electrónico, con punto y coma como separadores

5.  Seleccione **Guardar**.

Ahora ha completado las alertas de definición. Puede definir alertas adicionales mediante el uso de los ejemplos anteriores.

Cuando se genera una alerta, obtendrá un correo electrónico que se enumera los dispositivos que encontraron un problema durante la última hora.

![Correo electrónico de alerta de OMS de ejemplo] (../../media/Deploy_OMS_7.png "Correo electrónico de alerta de OMS de ejemplo")

Usar una página de configuración de alertas para modificar una configuración de alerta existente, o para deshabilitar o quitar una alerta.

![Configuración de alertas de OMS] (../../media/Deploy_OMS_8.png "Configuración de alertas de OMS")

> [!NOTE]
> Es posible que necesite utilizar el portal de Azure para agregar o modificar las alertas del conjunto de aplicaciones de administración de operaciones si el área de trabajo del conjunto de aplicaciones de administración de operaciones está configurado para extender las alertas del conjunto de aplicaciones de administración de operaciones en Azure. Para obtener más detalles, vea [Extend alertas desde portal de OMS en Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-alerts-extend).

## <a name="configure-all-devices-for-operations-management-suite"></a>Configurar todos los dispositivos para el conjunto de aplicaciones de administración de operaciones
<a name="configure_all_devices"></a> Una vez configuradas los paneles y las alertas, puede instalar y configurar los agentes del conjunto de aplicaciones de administración de las operaciones en todos los dispositivos de sistemas de salón de Skype para completar la implementación de supervisión.

Aunque se puede instalar y configurar a los agentes de conjunto de aplicaciones de administración de operaciones de forma manual en cada dispositivo, se recomienda encarecidamente que aprovechar los métodos y herramientas de implementación de software existente.

Si va a crear los dispositivos de sistemas de salón de Skype por primera vez, es posible que desee incluir los pasos del programa de instalación y configuración del agente de conjunto de aplicaciones de administración de operaciones como parte del proceso de compilación. Para obtener más información, vea [instalar al agente mediante la línea de comandos](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-operations-management-suite-agents-by-using-a-group-policy-object"></a>Implementación de agentes del conjunto de aplicaciones de administración de operaciones mediante el uso de un objeto de directiva de grupo

Si ya ha implementado los dispositivos de sistemas de salón de Skype antes de implementar el conjunto de aplicaciones de administración de operaciones, puede utilizar la secuencia de comandos para instalar y configurar a los agentes mediante el uso de directivas de grupo de Active Directory.

1.  Crear una ruta de acceso de red compartida y conceder acceso de lectura al grupo de **Equipos del dominio** .

2.  Descargue la versión de 64 bits de la operaciones de administración de conjunto de aplicaciones de agente para Windows desde<http://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extraiga el contenido del paquete del programa de instalación en el recurso compartido de red.
    1.  Abra una ventana del símbolo del sistema y, a continuación, ejecutar **MMASetup-AMD64.exe /c**
    2.  Especifique el recurso compartido que acaba de crear y extraiga el contenido.

4.  Crear un nuevo objeto de directiva de grupo y asignar a la unidad organizativa donde se encuentran las cuentas de máquina de sistemas de salón de Skype.

5.  Configurar la directiva de ejecución de PowerShell:
    1.  Editar el objeto de directiva de grupo recién creada y vaya a configuración del equipo \\ directivas \\ plantillas administrativas \\ componentes de Windows \\ Windows PowerShell
    2.  Habilite la **activar la ejecución del Script** y establecer la **Directiva de ejecución** para **Permitir que los Scripts de Local**.

6.  Configurar el script de inicio:
    1.  Copie la siguiente secuencia de comandos y guárdelo como Install-OMSAgent.ps1.
    2.  Modificar parámetros WorkspaceId, WorkspaceKey y SetupPath para que coincida con la configuración.
    3.  Editar el mismo objeto de directiva de grupo y vaya a configuración del equipo \\ directivas \\ configuración de Windows \\ secuencias de comandos (inicio/apagado)
    4.  Haga doble clic para seleccionar el **Inicio**y, a continuación, seleccione **Las secuencias de comandos de PowerShell**.
    5.  Seleccione **Mostrar archivos**y, a continuación, copie el archivo de **Instalación OMSAgent.ps1** a esa carpeta.
    6.  Seleccione **Agregar**y, a continuación, **busque**.
    7.  Seleccione la secuencia de comandos ps1 que acaba de copiar.

7.  Dispositivos de sistemas de salón de Skype deben instalar y configurar al agente de Microsoft Monitoring con el segundo reinicio.


    ```
    # Install-OMSAgent.ps1
    <# 
    Date:        04/20/2018 
    Script:      Install-OMSAgent.ps1 
    Version:     1.0
    #> 
    
    # Set the parameters
    $WorkspaceId = "<your workspace id>"
    $WorkspaceKey = "<your workspace key>"
    $SetupPath = "\\Server\Share"
    
    $SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"
    
    # $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"
    
    # Start PowerShell logging
    Start-Transcript -Path C:\OMSAgentInstall.Log  
    
    # Check if the Microsoft Monitoring Agent is installed
    $mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'
    
    # Check if the Microsoft Monitoring agent is installed 
    if (!$mma)
    {
        #Install agent
        Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
    }
    
    # Check if the agent has a valid configuration
    $CheckOMS = $mma.GetCloudWorkspace($WorkspaceId).AgentId
    if (!$CheckOMS)
    {
        # Apply new configuration
        $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
        $mma.ReloadConfiguration()
    } 
    
    Stop-Transcript 
    
    ```
    
> [!NOTE]
> Puede consultar el artículo de [administrar y mantener al agente de análisis de registro](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-manage) cuando es necesario volver a configurar a un agente, moverlo a un área de trabajo diferente, o modificar la configuración de proxy después de la instalación inicial.

## <a name="additional-solutions"></a>Soluciones adicionales
<a name="Solutions"> </a>

Conjunto de aplicaciones de administración de operaciones proporciona soluciones integradas a través de su [Galería de soluciones](https://docs.microsoft.com/azure/log-analytics/log-analytics-add-solutions) que aún más, le ayudarán a supervisar el entorno. Se recomienda que agregue las soluciones de [Administración de alertas](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) y [Mantenimiento de agente](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-agenthealth) a así como su área de trabajo de conjunto de aplicaciones de administración de operaciones.

![Vistas OMS] (../../media/Deploy_OMS_9.png "Vistas OMS")

> [!NOTE]
> La solución de mantenimiento de agente puede ayudar a identificar a obsoletos o rotos agentes de conjunto de aplicaciones de administración de las operaciones dentro de su entorno y la solución de administración de alertas proporciona información detallada acerca de las alertas que se han desencadenado dentro de un período determinado.

## <a name="see-also"></a>Vea también

[Planeación de la administración de sistemas de salón de Skype v2 con OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[Administrar dispositivos de sistemas de salón de Skype v2 con OMS](../../manage/skype-room-systems-v2/oms.md)