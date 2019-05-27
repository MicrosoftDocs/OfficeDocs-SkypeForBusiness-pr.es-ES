---
title: Implementar la administración de salas de Microsoft Teams con Azure monitor
ms.author: v-lanac
author: lanachin
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: En este artículo se explica cómo implementar la administración de los dispositivos de salas de Microsoft Teams de forma integrada, de extremo a extremo, con Azure monitor.
ms.openlocfilehash: fd1f1b32bd999c18144831e2458b426bf55ca1a9
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433378"
---
# <a name="deploy-microsoft-teams-rooms-management-with-azure-monitor"></a>Implementar la administración de salas de Microsoft Teams con Azure monitor

En este artículo se describe cómo configurar e implementar la administración integrada y completa de los dispositivos de salas de Microsoft Teams con Azure monitor.

Puede configurar el análisis de registros en Azure monitor para proporcionar alertas y telemetría básicas que le ayudarán a administrar salas de reuniones de Microsoft Teams. A medida que crece la solución de administración, es posible que decida implementar capacidades adicionales de administración y datos para crear una vista más detallada de la disponibilidad y el rendimiento de los dispositivos.

Siguiendo esta guía, puede usar un panel como el siguiente ejemplo para obtener informes detallados sobre el estado de la disponibilidad de dispositivos, el estado de las aplicaciones y el hardware, y la distribución de versiones del sistema operativo y las salas de Microsoft Teams.

![Captura de pantalla de la vista análisis de registros de ejemplo para salas de Microsoft Teams] (../media/Deploy-Azure-Monitor-1.png "Vista de análisis de registros de ejemplo para salas de Microsoft Teams")

A un mayor nivel, debe realizar las siguientes tareas:


1.  [Validar la configuración de análisis de registros](azure-monitor-deploy.md#validate_LogAnalytics)
2.  [Configurar dispositivos de prueba para la configuración de administración del análisis de registros](azure-monitor-deploy.md#configure_test_devices)
3.  [Asignar campos personalizados](azure-monitor-deploy.md#Custom_fields)
4.  [Definir las vistas de salas de Microsoft Teams en análisis de registros](azure-monitor-deploy.md#Define_Views)
5.  [Definir alertas](azure-monitor-deploy.md#Alerts)
6.  [Configurar todos los dispositivos para la supervisión](azure-monitor-deploy.md#configure_all_devices)
7.  [Configurar otras soluciones de Azure monitor](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Aunque con la configuración mínima, el análisis de registros de Azure monitor puede supervisar un equipo con un sistema operativo Windows, pero sigue habiendo algunos pasos específicos de las salas de Microsoft teams que debe llevar a cabo antes de empezar a implementar agentes en todos los equipos de Microsoft. Dispositivos de salas.
> Por lo tanto, le recomendamos encarecidamente que realice todos los pasos de configuración en el orden correcto para una instalación y configuración controlada. La calidad del resultado final depende de la calidad de la configuración inicial.

## <a name="validate-log-analytics-configuration"></a>Validar la configuración de análisis de registros
<a name="validate_LogAnalytics"> </a>

Debe tener un área de trabajo de análisis de registros para empezar a recopilar registros de los dispositivos de salas de Microsoft Teams. Un área de trabajo es un entorno de análisis de registros único con su propio repositorio de datos, orígenes de datos y soluciones. Si ya tiene un área de trabajo de análisis de registros, puede usarla para supervisar la implementación de las salas de Microsoft Teams o también puede crear un área de trabajo de análisis de registros dedicada específica para sus necesidades de supervisión de salas de Microsoft Teams.

Si necesita crear un nuevo área de trabajo de análisis de registros, siga las instrucciones del artículo [crear un área de trabajo de análisis de registros en el portal de Azure](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Para usar el análisis de registros con el monitor de Azure, debe tener una suscripción de Azure activa. Si no tiene una suscripción de Azure, puede crear [una suscripción de prueba gratuita](https://azure.microsoft.com/free) como punto de partida.

### <a name="configure-log-analytics-to-collect-microsoft-teams-rooms-event-logs"></a>Configurar el análisis de registros para recopilar los registros de eventos de Microsoft Teams Rooms

El análisis de registros solo recopila eventos de los registros de eventos de Windows que se especifican en la configuración. Para cada registro, solo se recopilan los eventos con las gravedades seleccionadas.

Debe configurar el análisis de registros para recopilar los registros necesarios para supervisar el estado de la aplicación y el dispositivo de las salas de Microsoft Teams. Los dispositivos de salas de Microsoft Teams usan el registro de eventos **del sistema** de salas de Skype.

Para configurar el análisis de registros para recopilar eventos de Microsoft Teams Rooms, consulte [orígenes de datos del registro de eventos de Windows en Azure monitor](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Captura de pantalla de configuración de registro de eventos] (../media/Deploy-Azure-Monitor-2.png "Configuración del registro de eventos")

> [!IMPORTANT]
> Configure el registro de eventos de Windows y especifique **sistema de salas de Skype** como nombre de registro de eventos y, a continuación, seleccione las casillas **error**, **ADVERTENCIA**e **información** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurar dispositivos de prueba para la supervisión de Azure
<a name="configure_test_devices"> </a>

Debe preparar el análisis de registros para poder supervisar los eventos relacionados con las salas de Microsoft Teams. Para empezar, debe implementar agentes de supervisión de Microsoft en solo uno o dos dispositivos de Microsoft Team Rooms a los que tiene acceso físico y obtener esos dispositivos de prueba generados en el área de trabajo del análisis de registros.

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a>Instalar agentes de supervisión de Microsoft para probar dispositivos

Implemente el agente de supervisión de Microsoft en los dispositivos de prueba con las instrucciones proporcionadas en [conectar equipos de Windows con el servicio de análisis de registros en Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). Este artículo proporciona información detallada sobre los pasos para implementar Microsoft Monitoring Agent para Windows, instrucciones para obtener el identificador del área de ***trabajo*** del análisis de registros y la ***clave principal*** para conectar los dispositivos de Microsoft Teams Rooms la implementación de Azure monitor y los pasos para comprobar la Conectividad del agente para la instancia de análisis de registros.

### <a name="generate-sample-microsoft-teams-rooms-events"></a>Generar eventos de salas de Microsoft Teams de ejemplo

Una vez implementado el agente de supervisión de Microsoft en los dispositivos de prueba, compruebe que Azure monitor recopile los datos necesarios del registro de eventos.

> [!NOTE]
> Reinicie el dispositivo después de la instalación de Microsoft Monitoring Agent y asegúrese de que se haya iniciado la aplicación de reuniones Microsoft Teams Rooms para que pueda generar nuevos eventos en el registro de eventos.

1.  Inicie sesión en el [portal de Microsoft Azure](https://portal.azure.com) y vaya a análisis de registros y seleccione su área de trabajo.

2.  Enumere los eventos de latido generados por un dispositivo de salas de Microsoft Teams:
    1.  Seleccione el área de trabajo y vaya a **registros** y use una consulta para recuperar los registros de latido que tendrán los campos personalizados para salas de Microsoft Teams.
    2.  Consulta de ejemplo:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Asegúrese de que la consulta devuelve los registros que incluyen los eventos generados por la aplicación reuniones de salas de Microsoft Teams.

4.  Genere un problema de hardware y valide que los eventos necesarios estén registrados en análisis de registros de Azure.
    1.  Desconecte uno de los dispositivos periféricos en el sistema de prueba de salas de Microsoft Teams. Puede ser la cámara, el teléfono con manos libres, el micrófono o la habitación frontal
    2.  Espere 10 minutos para que el registro de eventos se rellene en análisis de registros de Azure.
    3.  Usar una consulta para enumerar eventos de error de hardware:`Event | where Source == "SRS-App" and EventID == 3001`

5.  Genere un problema de aplicación y compruebe que los eventos necesarios estén registrados.
    1.  Modifique la configuración de la aplicación salas de Microsoft Teams y escriba una pareja de dirección y contraseña incorrecta en el protocolo de inicio de sesión (SIP).
    2.  Espere 10 minutos para que el registro de eventos se rellene en análisis de registros de Azure.
    3.  Usar una consulta para enumerar eventos de error de la aplicación:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Estos registros de eventos de ejemplo son obligatorios para poder configurar campos personalizados. No continúe con el paso siguiente hasta que haya recopilado los registros de eventos necesarios.

## <a name="map-custom-fields"></a>Asignar campos personalizados
<a name="Custom_fields"> </a>

Los campos personalizados se usan para extraer datos específicos de los registros de eventos. Debe definir campos personalizados que se usarán más adelante con los mosaicos, las vistas de panel y las alertas. Consulte [campos personalizados en análisis de registros](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) y familiarícese con los conceptos antes de empezar a crear los campos personalizados.

Para extraer los campos personalizados fuera de los registros de eventos capturados, siga estos pasos:

1.  Inicie sesión en el [portal de Microsoft Azure](https://portal.azure.com) y vaya a análisis de registros y seleccione su área de trabajo.

2. Enumere los eventos generados por un dispositivo de salas de Microsoft Teams:
   1.  Vaya a **registros** y use una consulta para recuperar los registros que tendrán el campo personalizado.
   2.  Consulta de ejemplo:`Event | where Source == "SRS-App" and EventID == 2000`

3. Seleccione uno de los registros, seleccione el botón de la izquierda e inicie el Asistente para extracción de campos.
4. Resalte los datos que desea extraer de la RenderedDescription y proporcione un título para el campo. Los nombres de campo que debe usar se proporcionan en la tabla 1.

   ![Definición de campo personalizado] (../media/Deploy-Azure-Monitor-4.png "Definición de campo personalizado")

5. Use las asignaciones que se muestran en la *tabla 1*. El análisis de registros anexará automáticamente la cadena de ** \_CF** al definir el nuevo campo.

> [!IMPORTANT]
> Recuerde que todos los campos de análisis de registro y JSON distinguen entre mayúsculas y minúsculas.
> 
> Preste atención a las consultas necesarias para cada campo personalizado de la tabla siguiente. Debe usar las consultas correctas para el análisis de registros para extraer correctamente los valores de campo personalizados.
> 
 ![Definición de campo personalizado] (../media/Deploy-Azure-Monitor-5.png "Definición de campo personalizado")

**Tabla 1**

| **Campo JSON**                   | **Campo personalizado de análisis de registros** | **Nivel del** | **Consulta para usar con la extracción**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Descripción                      | SRSEventDescription         | **2000**     | Evento \| donde Source = = "SRS-app" y EventID = = 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Evento \| donde Source = = "SRS-app" y EventID = = 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Evento \| donde Source = = "SRS-app" y EventID = = 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Evento \| donde Source = = "SRS-app" y EventID = = 2000 |
| Sistema operativo                               | SRSOSVersion                | **2000**     | Evento \| donde Source = = "SRS-app" y EventID = = 2000 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | Evento \| donde Source = = "SRS-app" y EventID = = 2000 |
| Alias                            | SRSAlias                    | **2000**     | Evento \| donde Source = = "SRS-app" y EventID = = 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Evento \| donde Source = = "SRS-app" y EventID = = 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Evento \| donde Source = = "SRS-app" y EventID = = 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Evento \| donde Source = = "SRS-app" y EventID = = 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Evento \| donde Source = = "SRS-app" y EventID = = 2000 |
| Estado del micrófono de la Conferencia     | SRSConfMicrophoneStatus     | **3001**     | Evento \| donde Source = = "SRS-app" y EventID = = 3001 |
| Estado del altavoz de la Conferencia        | SRSConfSpeakerStatus        | **3001**     | Evento \| donde Source = = "SRS-app" y EventID = = 3001 |
| Estado de altavoz predeterminado           | SRSDefaultSpeakerStatus     | **3001**     | Evento \| donde Source = = "SRS-app" y EventID = = 3001 |
| Estado de la cámara                    | SRSCameraStatus             | **3001**     | Evento \| donde Source = = "SRS-app" y EventID = = 3001 |
| Estado de visualización del salón     | SRSFORDStatus               | **3001**     | Evento \| donde Source = = "SRS-app" y EventID = = 3001 |
| Estado del sensor de movimiento             | SRSMotionSensorStatus       | **3001**     | Evento \| donde Source = = "SRS-app" y EventID = = 3001 |
| Estado de ingesta HDMI               | SRSHDMIIngestStatus         | **3001**     | Evento \| donde Source = = "SRS-app" y EventID = = 3001 |


## <a name="define-the-microsoft-teams-rooms-views-in-log-analytics"></a>Definir las vistas de salas de Microsoft Teams en análisis de registros
<a name="Define_Views"> </a>

Una vez que se recopilan los datos y se asignan los campos personalizados, puede usar el diseñador de vistas para desarrollar un panel con varios mosaicos para supervisar los eventos de salas de Microsoft Teams. Use Diseñador de vistas para crear los siguientes iconos. Para obtener más información, vea [crear vistas personalizadas con el diseñador de vistas en análisis de registros](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Los pasos anteriores de esta guía deberían haberse completado para que los mosaicos del panel funcionen correctamente.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Crear un panel de salas de Microsoft Teams con el método de importación

Puede importar un panel de salas de Microsoft Teams y empezar a supervisar los dispositivos rápidamente. Siga estos pasos para importar el panel:

1.  Obtén el archivo del panel [SkypeRoomSystems_v2. omsview](https://go.microsoft.com/fwlink/?linkid=835675) .
2.  Inicie sesión en el [portal de Microsoft Azure](https://portal.azure.com) y vaya a análisis de registros y seleccione su área de trabajo.
3.  Abra el **Diseñador de vistas**.
4.  Seleccione **importar**y, a continuación, seleccione el archivo **SkypeRoomSystems_v2. omsview** .
5.  Seleccione **Guardar**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Crear un panel de salas de Microsoft Teams manualmente

También puede crear su propio panel y agregar solo los mosaicos que desea supervisar.

#### <a name="configure-the-overview-tile"></a>Configurar el mosaico Descripción general

1.  Abra el **Diseñador de vistas**.
2.  Seleccione **mosaico de información general**y, a continuación, seleccione **dos números** de la galería.
3.  Asigne un nombre al mosaico **salas de Microsoft Teams**.
4.  Definir el **primer mosaico**:<br>
    **Leyenda:** Dispositivos que han enviado un latido al menos una vez durante el mes pasado<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Defina el **segundo mosaico**:<br>
    **Leyenda:** Dispositivos activos que han enviado un latido durante la última hora<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Seleccione **aplicar**.

### <a name="create-a-tile-that-displays-active-devices"></a>Crear un mosaico que muestre los dispositivos activos

1.  Seleccione **Ver panel** para empezar a agregar los mosaicos.
2.  Seleccionar **número & lista** de la galería
3.  Defina las propiedades **generales** :<br>
    **Título del Grupo:** Estado de latido<br>
    **Grupo nuevo:** Determinado
4.  Defina las propiedades del **mosaico** :<br>
    **Leyenda:** Dispositivos activos (latido enviado en los últimos 20 minutos)<br>
    **Consulta de icono: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Defina las propiedades de la **lista** :<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definir los **títulos de columna**:<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último latido
7.  Definir la **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **aplicar**y, después, **cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Crear un mosaico que muestre los dispositivos que tienen problemas de conectividad

1.  Seleccione **número & lista** en la galería y, a continuación, agregue un nuevo mosaico.
2.  Defina las propiedades **generales** :<br>
    **Título del Grupo:** Dejar vacío<br>
    **Grupo nuevo:** No seleccionado
3.  Defina las propiedades del **mosaico** :<br>
    **Leyenda:** Dispositivos inactivos (sin mensaje de latido enviado en los últimos 20 minutos)<br>
    **Consulta de icono: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Defina las propiedades de la **lista** :<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definir los **títulos de columna**:<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último latido
6.  Definir **consulta de navegación**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Seleccione **aplicar**y, después, **cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Crear un mosaico que muestre los dispositivos que tienen un error de hardware

1.  Seleccione **número & lista** en la galería y, a continuación, agregue un nuevo mosaico.
2.  Defina las propiedades **generales** :<br>
    **Título del Grupo:** Estado del hardware<br>
    **Grupo nuevo:** Determinado
3.  Defina las propiedades del **mosaico** :<br>
    **Leyenda:** Dispositivos en los que se ha producido un error de hardware en la última hora<br>
    **Consulta de icono: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina las propiedades de la **lista** :<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir los **títulos de columna**:<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último error
6.  Definir **consulta de navegación**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Seleccione **aplicar**y, después, **cerrar**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-operating-system-versions"></a>Crear un mosaico que muestre las salas de Microsoft Teams versiones del sistema operativo

1.  Seleccione la lista de &s de **Donut** de la galería y, a continuación, agregue un nuevo mosaico.
2.  Defina las propiedades **generales** :<br>
    **Título del Grupo:** Detalles del sistema operativo<br>
    **Grupo nuevo:** Determinado
3.  Defina las propiedades del **encabezado** :<br>
    **Título:** Versiones de sistema operativo<br>
    **Subtítulo:** Dispositivos que ejecutan versiones específicas del sistema operativo
4.  Defina las propiedades de **Donut** :<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Centrar el texto:** Dispositivo<br>
    **Operación:** Resumen
5.  Defina las propiedades de la **lista** .<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar gráfico:** Determinado<br>
    **Habilitar minigráficos:** No seleccionado
6.  Definir los **títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Dejar vacío
7.  Definir la **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **aplicar** y, después, **cerrar**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-application-versions"></a>Crear un mosaico que muestre las versiones de la aplicación salas de Microsoft Teams

1.  Seleccione la lista de &s de **Donut** de la galería y, a continuación, agregue un nuevo mosaico.
2.  Defina las propiedades **generales** :<br>
    **Título del Grupo:** Detalles de la aplicación salas de Microsoft Teams<br>
    **Grupo nuevo:** Determinado
3.  Defina las propiedades del **encabezado** :<br>
    **Título:** Versiones de la aplicación<br>
    **Subtítulo:** Dispositivos que ejecutan versiones de aplicaciones específicas
4.  Defina las propiedades de **Donut** :<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Centrar el texto:** Dispositivo<br>
    **Operación:** Resumen
5.  Defina las propiedades de la **lista** .<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar gráfico:** Determinado<br>
    **Habilitar minigráficos:** No seleccionado
6.  Definir los **títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Dejar vacío
7.  Definir la **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **aplicar** y, después, **cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Crear un mosaico que muestre los dispositivos que tienen un error de aplicación

1.  Seleccione **número & lista** en la galería y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** .<br>
    **Título del Grupo:** Dejar vacío<br>
    **Grupo nuevo:** No seleccionado
3.  Defina las propiedades del **mosaico** .<br>
    **Leyenda:** Dispositivos en los que se produjo un error de aplicación en la última hora<br>
    **Consulta de icono: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina las propiedades de la **lista** .<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir los **títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último error
6.  Definir la **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Seleccione **aplicar** y, después, **cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Crear un icono que muestre los dispositivos que se han reiniciado

1.  Seleccione **número & lista** en la galería y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** .<br>
    **Título del Grupo:** Dejar vacío<br>
    **Grupo nuevo:** No seleccionado
3.  Defina las propiedades del **mosaico** .<br>
    **Leyenda:** Los dispositivos en los que la aplicación se reinició en las últimas 24 horas y la cantidad de reinicios<br>
    **Consulta de icono: ** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina las propiedades de la **lista** .<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definir los **títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Número de reinicios
6.  Definir la **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Seleccione **aplicar** y, después, **cerrar**.
8.  Seleccione **Guardar** para guardar el panel.

Ya ha completado la creación de las vistas.

## <a name="configure-alerts-in-azure-monitor"></a>Configurar alertas en Azure monitor
<a name="Alerts"> </a>

Azure monitor puede generar alertas para notificar a los administradores Cuándo una consola de Microsoft Team Rooms encuentra un problema.

El monitor de Azure incluye un mecanismo de alertas integrado que se ejecuta a través de búsquedas de registro programadas a intervalos regulares. Si los resultados de la búsqueda de registro coinciden con algunos criterios determinados, se crea un registro de alerta.

Después, la regla puede ejecutar automáticamente una o más acciones para notificarlo de manera proactiva o invocar otro proceso. Las posibles opciones con alertas son las siguientes:
-   Enviar un correo electrónico
-   Invocar un proceso externo a través de una solicitud HTTP POST
-   Iniciar un runbook en el servicio Azure Automation

Consulte [registrar alertas en Azure monitor](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) para obtener más información sobre las alertas de Azure monitor.

> [!NOTE]
> En los siguientes ejemplos se envían alertas por correo electrónico cuando un dispositivo de salas de Microsoft Teams genera un error de hardware o de aplicación.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-hardware-issues"></a>Configurar una alerta por correo electrónico para problemas de hardware de las salas de Microsoft Teams

Configure una regla de alerta que compruebe los dispositivos de las salas de Microsoft teams que hayan encontrado problemas de hardware dentro de la última hora.
1.  Inicie sesión en el [portal de Microsoft Azure](https://portal.azure.com) y vaya a análisis de registros y seleccione su área de trabajo.

2. Navegue hasta el área de trabajo del análisis de registros, seleccione **alertas** y, a continuación, seleccione **nueva regla de alertas**

3. Seleccione **Agregar condición** y, después, **búsqueda de registros personalizada**

4.  Escriba la siguiente consulta en el cuadro de texto consulta de búsqueda.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configure la configuración de la lógica de alertas:<br>
    **Basado en:** Número de resultados<br>
    **Condición:** Más, después<br>
    **Treshold:** 0<br>

6. Configure las opciones de evaluación y seleccione **listo**: <br>
    **Período (en minutos):** 60<br>
    **Frecuencia (en minutos):** 60<br>

7. Configurar grupos de acciones:
    1.  Seleccione **crear nuevo**
    2.  Proporcione nombres adecuados para los campos *nombre de grupo de acciones* y *nombre corto* .
    3.  Especifique un *nombre de acción* único y seleccione **correo electrónico/SMS/inserción/voz**y, después, seleccione **editar detalles**.
    4.  Seleccione la casilla email (correo electrónico) y proporcione la dirección de correo electrónico de la persona o grupo que recibirá las alertas.
    5.  También puedes proporcionar tu número de teléfono para recibir notificaciones con SMS, llamadas de voz o ambas cosas.
    6. Seleccione **Aceptar**.

8. **Personalizar acciones** si desea anular la línea de asunto de los mensajes de correo electrónico de alerta.

9. Especifique un nombre y una descripción para la regla.<br>
    **Nombre de la regla:** Alerta de error de hardware de salas de Microsoft Teams<br>
    **Descripción:** Lista de dispositivos que tuvieron un problema de hardware dentro de la última hora<br>

10. Seleccione la gravedad prevista y asegúrese de que la regla esté habilitada.

11. Seleccione **crear regla de alertas**.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-application-issues"></a>Configurar una alerta por correo electrónico para problemas de la aplicación salas de Microsoft Teams

Repita el mismo procedimiento pero use la siguiente consulta para enumerar los dispositivos que hayan encontrado problemas de la aplicación dentro de la última hora.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

Ahora has terminado de definir las alertas. Puede definir alertas adicionales con los ejemplos anteriores.

Cuando se genera una alerta, recibirá un mensaje de correo electrónico con una lista de los dispositivos que tuvieron un problema dentro de la última hora.

![Ejemplo de correo electrónico de alerta de Azure monitor] (../media/Deploy-Azure-Monitor-6.png "Ejemplo de correo electrónico de alerta de Azure monitor")

## <a name="configure-all-devices-for-azure-monitoring"></a>Configurar todos los dispositivos para la supervisión de Azure
<a name="configure_all_devices"></a> Una vez configurados los paneles y las alertas, puede configurar Microsoft Monitoring Agent en todos los dispositivos de salas de Microsoft Teams para completar la implementación de la supervisión.

Aunque puede instalar y configurar Microsoft Monitoring Agent manualmente en cada dispositivo, le recomendamos encarecidamente que aproveche las herramientas y métodos de implementación de software existentes.

Si está creando los dispositivos de salas de Microsoft Teams por primera vez, es posible que desee incluir los pasos de configuración y configuración de Microsoft Monitoring Agent como parte del proceso de compilación. Para obtener más información, consulte [instalar el agente mediante la línea de comandos](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Implementar el agente de supervisión de Microsoft con un objeto de directiva de grupo (GPO)

Si ya ha implementado los dispositivos de salas de Microsoft Teams antes de implementar la supervisión de Azure, puede usar el script proporcionado para configurar y configurar los agentes con objetos de directiva de grupo de Active Directory.

1.  Crear una ruta de red compartida y conceder acceso de lectura al grupo **equipos del dominio** .

2.  Descargue la versión de 64 bits de Microsoft Monitoring Agent para Windows de<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extraiga el contenido del paquete de instalación en el recurso compartido de red.
    1.  Abra una ventana del símbolo del sistema y ejecute **MMASetup-AMD64. exe/c**
    2.  Especifique el recurso compartido que acaba de crear y extraiga el contenido.

4.  Cree un nuevo objeto de directiva de grupo y asígnelo a la unidad organizativa en la que se encuentren las cuentas de Microsoft Teams Rooms Machine.

5.  Configurar la Directiva de ejecución de PowerShell:
    1.  Modificar el objeto de directiva de grupo recién creado y navegar a \\ directivas \\ de configuración \\ del equipo \\ plantillas administrativas Windows PowerShell
    2.  Habilitar la **activación de la ejecución de script** y establecer la **Directiva de ejecución** para **permitir scripts locales**.

6.  Configure el script de Inicio:
    1.  Copie el script siguiente y guárdelo como Install-MMAgent. ps1.
    2.  Modifique los parámetros WorkspaceId, WorkspaceKey y SetupPath para que coincidan con la configuración.
    3.  Modificar el mismo objeto de directiva de grupo y navegar a \\ directivas \\ de configuración \\ del equipo secuencias de comandos de configuración de Windows (inicio/apagado)
    4.  Haga doble clic para seleccionar **Startup (Inicio**) y, a continuación, seleccione scripts de **PowerShell**.
    5.  Seleccione **Mostrar archivos**y, a continuación, copie el archivo **install-MMAgent. PS1** a esa carpeta.
    6.  Seleccione **Agregar**y, a continuación, **examinar**.
    7.  Seleccione el script PS1 que acaba de copiar.

7.  Los dispositivos de salas de Microsoft Teams deberían instalar y configurar Microsoft Monitoring Agent con el segundo reinicio.

```
# Install-MMAgent.ps1
<#
Date:        04/20/2018
Script:      Install-MMAgent.ps1
Version:     1.0
#>

# Set the parameters
$WorkspaceId = "<your workspace id>"
$WorkspaceKey = "<your workspace key>"
$SetupPath = "\\Server\Share"

$SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

# $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

# Start PowerShell logging
Start-Transcript -Path C:\Temp\MMA-Install.Log

# Check if the Microsoft Monitoring Agent is installed
$mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

# Check if the Microsoft Monitoring agent is installed
if (!$mma)
{
    #Install agent
    Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
}

# Check if the agent has a valid configuration
$CheckMMA = $mma.GetCloudWorkspace($WorkspaceId).AgentId
if (!$CheckMMA)
{
    # Apply new configuration
    $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
    $mma.ReloadConfiguration()
}

Stop-Transcript
```

> [!NOTE]
> Puede consultar el artículo [administrar y mantener el agente de análisis de registros](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) cuando necesita volver a configurar un agente, moverlo a un área de trabajo diferente o modificar la configuración de proxy después de la instalación inicial.

## <a name="additional-solutions"></a>Soluciones adicionales
<a name="Solutions"> </a>

Azure Monitor proporciona soluciones de administración integradas a través de su [Galería de soluciones](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) para ayudarle a supervisar su entorno. Le recomendamos encarecidamente que agregue también la [Administración de alertas](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) y las soluciones de estado del agente de [análisis de Azure log](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) a su área de trabajo.

> [!NOTE]
> La solución de estado del agente puede ayudarle a identificar agentes de supervisión de Microsoft anticuados o desactualizados en su entorno, y la solución de administración de alertas proporciona detalles sobre las alertas que se han producido dentro de un período determinado.

## <a name="see-also"></a>Vea también

[Planear la administración de salas de Microsoft Teams con Azure monitor](azure-monitor-plan.md)

[Administrar dispositivos de salas de Microsoft Teams con Azure monitor](azure-monitor-manage.md)
