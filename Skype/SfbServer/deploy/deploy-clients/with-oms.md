---
title: Implementar la administración de Sistemas de salas de Skype v2 con OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: En este artículo se describe cómo implementar la administración de dispositivos de sistemas de salas de Skype v2 de manera integrada, end-to-end usando Microsoft Operations Management Suite.
ms.openlocfilehash: 3d42f0777059870872e871c25591f16c103b5939
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>Implementar la administración de Sistemas de salas de Skype v2 con OMS
 
En este artículo se describe cómo configurar e implementar administración integrada end-to-end de los dispositivos de sistemas de salas de Skype v2 utilizando Microsoft Operations Management Suite.
  
Puede configurar Microsoft Operations Management Suite para proporcionar básico telemetry y alertas que le ayudarán a administración dispositivos para salas de reuniones de Skype. A medida que crezca su solución de gestión, decide implementar capacidades de administración para crear una vista más detallada de la performance y la disponibilidad de dispositivos y datos adicionales.

Siguiendo esta guía, puede utilizar un panel similar al ejemplo siguiente para obtener detallado informes de estado de disponibilidad del dispositivo, aplicación y mantenimiento de hardware y distribución de la versión de aplicación de sistemas de salas de Skype v2.

![Ver ejemplo OMS para SRS v2] (../../media/Deploy_OMS_1.png "Ver ejemplo OMS para SRS v2")
  
A un mayor nivel, debe realizar las siguientes tareas:


1.  [Validar configuración de Operations Management Suite](with-oms.md#validate_OMS)
2.  [Configurar dispositivos de prueba para el programa de instalación de administración de Operations Management Suite](with-oms.md#configure_test_devices)
3.  [Asignar campos personalizados](with-oms.md#Custom_fields)
4.  [Definir las vistas de los sistemas de salas de Skype v2 en Operations Management Suite](with-oms.md#Define_Views)
5.  [Definir alertas](with-oms.md#Alerts)
6.  [Configurar todos los dispositivos para Operations Management Suite](with-oms.md#configure_all_devices)
7.  [Configurar soluciones adicionales de Operations Management Suite](with-oms.md#Solutions)

> [!IMPORTANT]
> Aunque con la configuración mínima, la aplicación de gestión de operaciones puede supervisar un equipo que ejecuta un sistema operativo Windows, todavía hay algunos pasos de Skype sala sistemas específicos que debe seguir antes de iniciar el despliegue de agentes en todos los sistemas de salas de Skype dispositivos.
> Por lo tanto, recomendamos encarecidamente que realice todos los pasos de configuración en el orden correcto para una instalación controlada y configuración. La calidad del resultado final depende mucho de la calidad de la configuración inicial.

## <a name="validate-operations-management-suite-configuration"></a>Validar configuración de Operations Management Suite
<a name="validate_OMS"> </a>

Debe tener un área de trabajo de operaciones Management Suite para iniciar la recopilación de registros de dispositivos de sistemas de salas de Skype. Un área de trabajo es un entorno de análisis de registro único con su propio repositorio de datos, orígenes de datos y soluciones. Si ya tiene un área de trabajo de análisis de registro existente, se puede utilizar para supervisar la implementación de sistemas de salas de Skype o puede crear un área de análisis de registro dedicado específico para la supervisión de los sistemas de salas de Skype necesita.

Si necesita crear una nueva área de trabajo de análisis de registro, siga las instrucciones en el artículo [crear un área de trabajo de análisis de registro en el portal de Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-quick-create-workspace)

> [!NOTE]
> Para utilizar el registro de análisis con Operations Management Suite, debe tener una suscripción activa de Azure. Si no tienes una suscripción de Azure, puede crear [una suscripción de prueba gratuita](https://azure.microsoft.com/free) como punto de partida.


### <a name="configure-operations-management-suite-to-collect-skype-room-systems-event-logs"></a>Configurar operaciones Management Suite para recopilar los registros de sucesos de los sistemas de salas de Skype

Análisis del registro sólo recopila eventos de los registros de sucesos de Windows se especifican en la configuración. Para cada registro, se recopilan sólo los eventos con los niveles de gravedad seleccionados.

Debe configurar operaciones Management Suite para recopilar los registros necesarios para supervisar el estado de dispositivo y aplicación de sistemas de salas de Skype. Dispositivos de sistemas de salas de Skype v2 utilizan el registro de sucesos de los sistemas de salas de Skype.

Para configurar las operaciones Management Suite para recopilar los eventos de los sistemas de salas de Skype, vea [orígenes de datos de registro de sucesos de Windows en análisis de registro](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

![Configuración de registro de sucesos] (../../media/Deploy_OMS_2.png "Configuración de registro de sucesos")


> [!IMPORTANT]
> Seleccione el registro de sucesos del sistema del sitio de Skype y, a continuación, seleccione las casillas de verificación de **información** , **Advertencia**y **Error**.

## <a name="configure-test-devices-for-operations-management-suite-setup"></a>Configurar dispositivos de prueba para la instalación de Operations Management Suite
<a name="configure_test_devices"> </a>

Es necesario preparar Operations Management Suite para poder supervisar los eventos relacionados con sistemas de salas de Skype. Para empezar con, debe desplegar agentes de Operations Management Suite en uno o dos dispositivos de sistemas de salas de Skype que tener acceso físico a y los dispositivos de prueba generar algunos datos y enviarlo al área de trabajo de análisis de registro.

### <a name="install-operations-management-suite-agents-to-test-devices"></a>Instalar los agentes de Operations Management Suite para probar los dispositivos

Desplegar al agente de Operations Management Suite en los dispositivos de prueba utilizando las instrucciones proporcionadas en los [equipos de Windows conectarse al servicio de análisis de registro en Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows). Este artículo proporciona información detallada sobre los pasos para implementar Microsoft supervisión agente para Windows, instrucciones para obtener el identificador de área de trabajo de operaciones Management Suite y la clave principal para obtener dispositivos de sistemas de salas de Skype conectado a su Implementación de la Suite de gestión de operaciones y pasos para comprobar la conectividad del agente al análisis de registro.

### <a name="generate-sample-skype-room-systems-events"></a>Generar eventos de muestra sistemas de salas de Skype

Después de implementa el agente Operations Management Suite en los dispositivos de prueba, compruebe que se recopilan los datos de registro de sucesos necesarios mediante el análisis de registro.

1.  Iniciar sesión en el [portal de Microsoft Operations Management Suite](http://aka.ms/omsportal).

2.  Lista de los eventos generados por un dispositivo de sistemas de salas de Skype:
    1.  Ir a la **Búsqueda de registros** y usar una consulta para recuperar los registros que tendrán en el campo personalizado.
    2.  Consulta de ejemplo:`Event | where Source == "SRS-App"`

3.  Asegúrese de que la consulta devuelve registros que incluyen eventos exitosos de latido.

4.  Generar un problema de hardware y validar que se registran los sucesos necesarios en las operaciones de Management Suite.
    1.  Desconecte uno de los dispositivos periféricos en la prueba del sistema de sistemas de salas de Skype. Podría tratarse de la cámara, altavoz, micrófono o presentación del cuarto delantero
    2.  Espere 10 minutos para el registro de sucesos se llene en Operations Management Suite.
    3.  Utilizar una consulta para enumerar eventos de error de hardware:`Event | where EventID == 3001`

5.  Generar un problema de la aplicación y validar que se registran los sucesos necesarios.
    1.  Modificar la configuración de la aplicación de sistemas de salas de Skype, y escriba un par de dirección y contraseña incorrecta de protocolo de inicio de sesión (SIP).
    2.  Espere 10 minutos para el registro de sucesos se llene en Operations Management Suite.
    3.  Utilizar una consulta para enumerar eventos de error de aplicación:`Event | where EventID == 2001`

> [!IMPORTANT]
> Estos registros de eventos de ejemplo son necesarios antes de que se pueden configurar campos personalizados. No continúe con el paso siguiente hasta que haya reunido los registros de sucesos necesarios.

## <a name="map-custom-fields"></a>Asignar campos personalizados
<a name="Custom_fields"> </a>

Utilizar campos personalizados para extraer datos específicos de los registros de sucesos. Debe definir campos personalizados que se utilizará más adelante con los mosaicos, vistas de tablero y alertas. Ver [campos personalizados en el análisis de registro](https://docs.microsoft.com/azure/log-analytics/log-analytics-custom-fields) y familiarizarse con los conceptos antes de empezar a crear los campos personalizados.

Para extraer los campos personalizados de los registros de sucesos capturados, siga estos pasos:

1.  Iniciar sesión en el [portal de Microsoft Operations Management Suite](http://aka.ms/omsportal).

2.  Lista de los eventos generados por un dispositivo de sistemas de salas de Skype:
    1.  Ir a la **Búsqueda de registros** y usar una consulta para recuperar los registros que tendrán en el campo personalizado.
    2.  Consulta de ejemplo:`Event | where Source == "SRS-App"`

3.  Seleccione uno de los registros, seleccione el botón a la izquierda y, inicie al Asistente para extracción de campo.

![Asistente para extracción de campo] (../../media/Deploy_OMS_3.png "Asistente para extracción de campo")

4.  Resalte los datos que se desea extraer de la RenderedDescription y proporcionar un título de campo. Se proporcionan los nombres de campo que se deben utilizar en la tabla 1.

![Definición de campos personalizados] (../../media/Deploy_OMS_4.png "Definición de campos personalizados")

5.  Utilice las asignaciones que se muestra en la tabla 1. Operations Management Suite agregará automáticamente la ** \_CF** al definir el nuevo campo de cadena.

> [!IMPORTANT]
> Recuerde que todos los campos JSON y Operations Management Suite distinguen entre mayúsculas y minúsculas.

> Preste atención al estado de la casilla de verificación EventID en la tabla siguiente. Asegúrese de que confirmar el estado de esta casilla de verificación para Operations Management Suite extraer correctamente los valores de campo personalizado.
> ![Definición de campos personalizados] (../../media/Deploy_OMS_5.png "Definición de campos personalizados") 

**Tabla 1**

| **Campo JSON**               | **Campo personalizado de OMS**       | **Id. de suceso** |
|------------------------------|----------------------------|-----------------|
| Descripción                  | SRSEventDescription_CF     | No seleccionado    |
| ResourceState                | SRSResourceState_CF        | No seleccionado    |
| OperationName                | SRSOperationName_CF        | No seleccionado    |
| OperationResult              | SRSOperationResult_CF      | No seleccionado    |
| OS                           | SRSOSVersion_CF            | No seleccionado    |
| OSVersion                    | SRSOSLongVersion_CF        | No seleccionado    |
| Alias                        | SRSAlias_CF                | No seleccionado    |
| DisplayName                  | SRSDisplayName_CF          | No seleccionado    |
| AppVersion                   | SRSAppVersion_CF           | No seleccionado    |
| IPv4Address                  | SRSIPv4Address_CF          | No seleccionado    |
| IPv6Address                  | SRSIPv6Address_CF          | No seleccionado    |
| Parte delantera del estado de visualización de la habitación | SRSFORDStatus_CF           | 3001            |
| Estado de la cámara                | SRSCameraStatus_CF         | 3001            |
| Estado del micrófono de conferencia | SRSConfMicrophoneStatus_CF | 3001            |
| Estado de altavoz de conferencia    | SRSConfSpeakerStatus_CF    | 3001            |
| Estado de altavoz predeterminado       | SRSDefaultSpeakerStatus_CF | 3001            |
| Estado del Sensor de movimiento         | SRSMotionSensorStatus_CF   | 3001            |
| Estado de ingesta HDMI           | SRSHDMIIngestStatus_CF     | 3001            |


## <a name="define-the-skype-room-systems-v2-views-in-operations-management-suite"></a>Definir las vistas de los sistemas de salas de Skype v2 en Operations Management Suite
<a name="Define_Views"> </a>

Después de que los datos se recopilan y se asignan los campos personalizados, puede utilizar operaciones Management Suite Ver diseñador para desarrollar un panel que contenga varios azulejos para supervisar los eventos de los sistemas de salas de Skype v2. Use Diseñador de vistas para crear los siguientes iconos. Para obtener más información, vea [Utilizar el Diseñador de vistas para crear vistas personalizadas de análisis de registro](https://docs.microsoft.com/azure/log-analytics/log-analytics-view-designer)

> [!NOTE]
> Deben haber completado los pasos anteriores de esta guía para que las placas de escritorio funcione correctamente.


### <a name="create-a-skype-room-systems-v2-dashboard-by-using-the-import-method"></a>Crear un panel de sistemas de salas de Skype v2 mediante el método de importación

Puede importar un panel Operations Management Suite y empezar a supervisar los dispositivos inmediatamente. Realizar los pasos siguientes para importar el tablero de mandos:

1.  Descargue el [tablero de mandos](http://download.microsoft.com/download/9/0/D/90D4826A-9FD2-47D2-B911-97BF1737F4F7/SkypeRoomSystems_v2.omsview).
2.  Iniciar sesión en el [portal de Microsoft Operations Management Suite](http://aka.ms/omsportal).
3.  Abra el **Diseñador de vistas**.
4.  Seleccione **Importar**y, a continuación, seleccione el archivo **SkypeRoomSystems_v2.omsview** .
5.  Seleccione **Guardar**.

### <a name="create-a-skype-room-systems-v2-dashboard-manually"></a>Crear un panel de sistemas de salas de Skype v2 manualmente

Como alternativa, puede crear su propio panel y agregar sólo los azulejos que desee supervisar.

#### <a name="configure-the-overview-tile"></a>Configurar el mosaico de resumen
1.  Abra el **Diseñador de vistas**.
2.  Seleccione **Mosaico de introducción**y seleccione **dos números** de la galería.
3.  Nombre el mosaico **Sistemas de salas de Skype**.
4.  Definir el **primer mosaico**:<br>
    **La leyenda:** Dispositivos que ha enviado un latido al menos una vez en el último mes<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Defina el **segundo mosaico**:<br>
    **La leyenda:** Dispositivos activos que ha enviado un latido durante la última hora<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Seleccione **Aplicar**.

### <a name="create-a-tile-that-displays-active-devices"></a>Crear un mosaico muestra dispositivos activos
1.  Seleccione el **Panel de vista** para empezar a agregar los mosaicos.
2.  Seleccione **número y la lista** de la Galería
3.  Definir las propiedades **generales** :<br>
    **Título de grupo:** Estado del latido<br>
    **Nuevo grupo:** Seleccionado
4.  Definir las propiedades de **mosaico** :<br>
    **La leyenda:** Dispositivos activos (latido enviado en los últimos 20 minutos)<br>
    **Consulta en mosaico:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definir las propiedades de la **lista** :<br>
    **Lista de consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definir **títulos de columna**:<br>
    **Nombre:** Nombre para mostrar<br>
    **Valor:** Último latido
7.  Definir **consulta de exploración**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar**y, a continuación, en **Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Crear un mosaico muestra los dispositivos que tienen problemas de conectividad
1.  Seleccione **número y la lista** de la galería y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** :<br>
    **Título de grupo:** Deje en blanco<br>
    **Nuevo grupo:** No seleccionado
3.  Definir las propiedades de **mosaico** :<br>
    **La leyenda:** Dispositivos inactivos (sin mensajes de latido enviado en los últimos 20 minutos)<br>
    **Consulta en mosaico:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definir las propiedades de la **lista** :<br>
    **Lista de consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definir **títulos de columna**:<br>
    **Nombre:** Nombre para mostrar<br>
    **Valor:** Último latido
6.  Definir **consulta de exploración**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Seleccione **Aplicar**y, a continuación, en **Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Crear un mosaico muestra los dispositivos que tienen un error de hardware

1.  Seleccione **número y la lista** de la galería y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** :<br>
    **Título de grupo:** Hardware<br>
    **Nuevo grupo:** Seleccionado
3.  Definir las propiedades de **mosaico** :<br>
    **La leyenda:** Dispositivos que ha experimentado un error de hardware en la última hora <br>
    **Consulta en mosaico:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definir las propiedades de la **lista** :<br>
    **Lista de consulta:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer```
5.  Definir **títulos de columna**:<br>
    **Nombre:** Nombre para mostrar<br>
    **Valor:** Último Error
6.  Definir **consulta de exploración**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Seleccione **Aplicar**y, a continuación, en **Cerrar**.

### <a name="create-a-tile-that-displays-skype-room-systems-application-versions"></a>Crear un mosaico muestra las versiones de la aplicación de sistemas de salas de Skype

1.  Seleccione **anillos y la lista** de la galería y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** :<br>
    **Título de grupo:** Detalles de la aplicación de sistemas de salas de Skype v2 <br>
    **Nuevo grupo:** Seleccionado
3.  Definir las propiedades de **encabezado** :<br>
    **Título:** Versiones de la aplicación<br>
    **Subtítulo:** Dispositivos que ejecutan versiones de aplicación específica
4.  Definir las propiedades de **anillo** :<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Centra el texto:** Dispositivos<br>
    **Operación:** Suma
5.  Definir las propiedades de la **lista** .<br>
    **Lista de consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar gráfico:** Seleccionado<br>
    **Habilitar minigráficos:** No seleccionado
6.  Definir **títulos de columna**.<br>
    **Nombre:** Nombre para mostrar<br>
    **Valor:** Deje en blanco
7.  Definir **consulta de exploración**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar** y luego en **Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Crear un mosaico muestra los dispositivos que tienen un error de aplicación

1.  Seleccione **número y la lista** de la galería y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** .<br>
    **Título de grupo:** Deje en blanco<br>
    **Nuevo grupo:** No seleccionado
3.  Definir las propiedades de **mosaico** .<br>
    **La leyenda:** Dispositivos que ha experimentado un error de aplicación en la última hora<br>
    **Consulta en mosaico:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definir las propiedades de la **lista** .<br>
    **Lista de consulta:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **títulos de columna**.<br>
    **Nombre:** Nombre para mostrar<br>
    **Valor:** Último Error
6.  Definir **consulta de exploración**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Seleccione **Aplicar** y luego en **Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Crear un mosaico muestra los dispositivos que se haya reiniciado

1.  Seleccione **número y la lista** de la galería y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** .<br>
    **Título de grupo:** Deje en blanco<br>
    **Nuevo grupo:** No seleccionado
3.  Definir las propiedades de **mosaico** .<br>
    **La leyenda:** Donde se ha reiniciado la aplicación en los últimos 24 horas y el número de reinicios de los dispositivos<br>
    **Consulta en mosaico:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Definir las propiedades de la **lista** .<br>
    **Lista de consulta:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definir **títulos de columna**.<br>
    **Nombre:** Nombre para mostrar<br>
    **Valor:** Número de reinicios
6.  Definir **consulta de exploración**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Seleccione **Aplicar** y luego en **Cerrar**.
8.  Seleccione **Guardar** para guardar el panel.

Ahora ha terminado de crear las vistas.

Puede utilizar el portal de Microsoft Operations Management Suite o los clientes móviles Operations Management Suite para [Windows Phone](https://www.microsoft.com/en-us/store/p/microsoft-operations-management-suite/9wzdncrfjz2r), [iOS](https://itunes.apple.com/us/app/microsoft-operations-management-suite/id1042424859)y [Android](https://play.google.com/store/apps/details?id=com.microsoft.operations.AndroidPhone) tener acceso a las vistas.

## <a name="configure-alerts-in-operations-management-suite"></a>Configurar alertas en Operations Management Suite
<a name="Alerts"></a> Dispositivo de sistemas de salas de Skype a cuando detecta un problema, Microsoft Operations Management Suite puede generar alertas para notificar a los administradores con los detalles del problema.

Operations Management Suite incluye un mecanismo de alerta integrado que se ejecuta a través de búsquedas de registro programado a intervalos regulares. Si los resultados de la búsqueda de registros coinciden con algún criterio determinado, se crea un registro de alerta.

![Mecanismo de alerta de OMS] (../../media/Deploy_OMS_6.png "Mecanismo de alerta de OMS")

A continuación, la regla puede ejecutar automáticamente una o varias acciones para avisarle de la alerta de manera proactiva o invocar otro proceso. Las opciones posibles con las alertas de Operations Management Suite son:
-   Enviar un correo electrónico
-   Invocar a un proceso externo a través de una solicitud HTTP POST
-   A partir de un runbook servicio de automatización de Azure

Consulte [información sobre alertas en el registro de análisis](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts) para obtener más información acerca de las alertas de Operations Management Suite.

> [!NOTE]
> En los ejemplos siguientes envían alertas de correo electrónico cuando un dispositivo de sistemas de salas de Skype genera un error de aplicación o de hardware. 


### <a name="configure-an-email-alert-for-skype-room-systems-hardware-issues"></a>Configurar una alerta de correo electrónico para problemas de hardware de los sistemas de salas de Skype

Configurar una regla de alerta que busca dispositivos de sistemas de salas de Skype que han tenido problemas de hardware durante la última hora.
1.  Iniciar sesión en el [portal de Microsoft Operations Management Suite](http://aka.ms/omsportal).

2.  Seleccione **la búsqueda de registro**.

3.  Escriba la consulta siguiente y, a continuación, seleccione **Ejecutar**.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF 
    |sort by TimeGenerated desc
    ```

4.  Después de ejecuta la consulta, seleccione **alertas**. Se abrirá la página **Agregar regla de alerta** .

5.  Configurar las alertas utilizando la siguiente información:<br>
    **Nombre de regla:** Alerta de error de Hardware de sistemas de sala de Skype<br>
    **Descripción:** Lista de dispositivos que ha encontrado un problema de hardware durante la última hora<br>
    **Gravedad:** Crítica<br>
    **Consulta:** Utilice la consulta de búsqueda previamente rellenadas<br>
    **Ventana de tiempo:** 1 hora<br>
    **Frecuencia de alertas:** 1 hora<br>
    **Número de resultados:** Mayor que 0<br>
    **Asunto de correo electrónico:** Alerta de error de Hardware de sistemas de sala de Skype<br>
    **Destinatarios:** Incluir las direcciones de correo electrónico con puntos y comas como separadores<br>

6.  Seleccione **Guardar**.

### <a name="configure-an-email-alert-for-skype-room-systems-application-issues"></a>Configurar una alerta de correo electrónico para problemas de aplicación de sistemas de salas de Skype

Configurar una regla de alerta, que comprueba si hay dispositivos de sistemas de salas de Skype que han tenido problemas de aplicación durante la última hora.
1.  Seleccione **la búsqueda de registro**.

2.  Escriba la consulta siguiente y, a continuación, seleccione **Ejecutar**.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(10h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

3.  Después de ejecuta la consulta, seleccione **alertas**. Se abrirá la página **Agregar regla de alerta** .

4.  Configurar las alertas utilizando la siguiente información:<br>
    **Nombre de regla:** Alerta de error de aplicación de sistemas de sala de Skype<br>
    **Descripción:** Lista de dispositivos que ha encontrado un problema de aplicación durante la última hora<br>
    **Gravedad:** Crítica<br>
    **Consulta:** Utilice la consulta de búsqueda previamente rellenadas<br>
    **Ventana de tiempo:** 1 hora<br>
    **Frecuencia de alertas:** 1 hora<br>
    **Número de resultados:** Mayor que 0<br>
    **Asunto de correo electrónico:** Alerta de error de aplicación de sistemas de sala de Skype<br>
    **Destinatarios:** Incluir las direcciones de correo electrónico con puntos y comas como separadores

5.  Seleccione **Guardar**.

Ahora ha concluido definir alertas. Puede definir alertas adicionales mediante el uso de los ejemplos anteriores.

Cuando se genera una alerta, obtendrá un mensaje que enumera los dispositivos que ha encontrado un problema durante la última hora.

![Correo electrónico de alerta de OMS muestra] (../../media/Deploy_OMS_7.png "Correo electrónico de alerta de OMS muestra")

Utilice una página de configuración de alertas para modificar una configuración de alerta existente, o para deshabilitar o quitar una alerta.

![Configuración de alerta de OMS] (../../media/Deploy_OMS_8.png "Configuración de alerta de OMS")

> [!NOTE]
> Debe usar el portal de Azure para agregar o modificar alertas de Operations Management Suite si el área de trabajo de operaciones Management Suite está configurado para extender las alertas de Operations Management Suite en Azure. Para obtener más detalles, vea [Extender alertas desde portal OMS en Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-alerts-extend).

## <a name="configure-all-devices-for-operations-management-suite"></a>Configurar todos los dispositivos para Operations Management Suite
<a name="configure_all_devices"></a> Una vez configurados los paneles y los avisos, puede configurar y configurar los agentes de Operations Management Suite en todos los dispositivos de sistemas de salas de Skype para completar la implementación de la supervisión.

Aunque se puede instalar y configurar a los agentes de Operations Management Suite manualmente en cada dispositivo, se recomienda que aprovechar los métodos y herramientas de implementación de software existente.

Si va a crear los dispositivos de sistemas de salas de Skype por primera vez, desea incluir los pasos de instalación y configuración de agente Operations Management Suite como parte del proceso de compilación. Para obtener más información, vea [instalar al agente mediante la línea de comandos](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-operations-management-suite-agents-by-using-a-group-policy-object"></a>Despliegue de agentes de Operations Management Suite utilizando un objeto de directiva de grupo

Si ha implementado los dispositivos de sistemas de salas de Skype antes de implementar una aplicación de gestión de operaciones, puede utilizar la secuencia de comandos para instalar y configurar a los agentes mediante directivas de grupo de Active Directory.

1.  Crear una ruta de red compartida y conceder acceso de lectura al grupo **Equipos del dominio** .

2.  Descargue la versión de 64 bits de las operaciones de administración Suite agente para Windows de<http://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extraiga el contenido del paquete de instalación en el recurso compartido de red.
    1.  Abra una ventana del símbolo del sistema y, a continuación, ejecutar **/c MMASetup-AMD64.exe**
    2.  Especifique el recurso compartido que acaba de crear y extraiga el contenido.

4.  Crear un nuevo objeto de directiva de grupo y asigne a la unidad organizativa donde se encuentran las cuentas de equipo de sistemas del sitio de Skype.

5.  Configurar la directiva de ejecución de PowerShell:
    1.  Editar el objeto de directiva de grupo recién creado y vaya a configuración del equipo \\ directivas \\ plantillas administrativas \\ componentes de Windows \\ de Windows PowerShell
    2.  Habilitar el **activar la ejecución del Script** y establecer la **Directiva de ejecución** para **Permitir secuencias de comandos locales**.

6.  Configurar la secuencia de comandos de inicio:
    1.  Copie la secuencia de comandos siguiente y guárdelo como OMSAgent.ps1 de la instalación.
    2.  Modificar los parámetros WorkspaceId, WorkspaceKey y SetupPath para que coincida con la configuración.
    3.  Editar el mismo objeto de directiva de grupo y vaya a configuración del equipo \\ directivas \\ configuración de Windows \\ secuencias de comandos (inicio/apagado)
    4.  Haga doble clic para seleccionar **Inicio**y, a continuación, seleccione **Las secuencias de comandos de PowerShell**.
    5.  Seleccione **Mostrar archivos**y, a continuación, copie el archivo de **Instalación OMSAgent.ps1** a esa carpeta.
    6.  Seleccione **Agregar**y, a continuación, **Examinar**.
    7.  Seleccione la secuencia de comandos ps1 que acaba de copiar.

7.  Dispositivos de sistemas de salas de Skype deben instalar y configurar al agente de Microsoft Monitoring con el segundo reinicio.


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
> Puede consultar el artículo de [administración y mantenimiento del agente de análisis de registro](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-manage) cuando necesite volver a configurar a un agente, moverlo a otra área de trabajo o modificar la configuración de proxy tras la instalación inicial.

## <a name="additional-solutions"></a>Soluciones adicionales
<a name="Solutions"> </a>

Operations Management Suite ofrece soluciones integradas a través de su [Galería de soluciones](https://docs.microsoft.com/azure/log-analytics/log-analytics-add-solutions) más ayudar a monitorear su entorno. Recomendamos encarecidamente que agregar a su área de trabajo de operaciones Management Suite también soluciones de [Administración de alertas](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) y la [Salud del agente](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-agenthealth) .

![Vistas OMS] (../../media/Deploy_OMS_9.png "Vistas OMS")

> [!NOTE]
> La solución de salud del agente puede ayudarle a identificar a los agentes de Operations Management Suite anticuados o rotos dentro de su entorno y la solución de administración de alertas proporciona información detallada acerca de las alertas que se han desencadenado dentro de un período determinado.

## <a name="see-also"></a>Vea también

#### 
[Planear la administración de sistemas de salas de Skype v2 con OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[Administrar dispositivos de sistemas de salas de Skype v2 con OMS](../../manage/skype-room-systems-v2/oms.md)