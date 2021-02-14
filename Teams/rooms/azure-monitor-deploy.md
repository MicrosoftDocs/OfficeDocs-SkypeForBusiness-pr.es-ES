---
title: Implementar la administración de salas de Microsoft Teams con Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: En este artículo se describe cómo implementar la administración de dispositivos de Salas de Microsoft Teams de un modo integrado y integral con Monitor de Azure.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b05c490c157c9f6530ca79ecdd8df19f15d94c68
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662105"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>Implementar :::no-loc text="Microsoft Teams Rooms"::: administración con :::no-loc text="Azure Monitor":::

En este artículo se describe cómo configurar e implementar la administración integrada y integral de :::no-loc text="Microsoft Teams Rooms"::: dispositivos mediante el :::no-loc text="Azure Monitor"::: uso.

Puede configurar esta opción para proporcionar telemetría básica y alertas que le ayudarán a administrar los dispositivos de :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: las salas de :::no-loc text="Microsoft Teams Rooms"::: reuniones. A medida que madure su solución de administración, puede decidir implementar más capacidades de administración y datos para crear una vista más detallada de la disponibilidad y el rendimiento del dispositivo.

Si sigue esta guía, puede usar un panel como el ejemplo siguiente para obtener informes de estado detallados sobre la disponibilidad del dispositivo, el estado de las aplicaciones y hardware, y la distribución de versiones de aplicaciones y sistemas :::no-loc text="Microsoft Teams Rooms"::: operativos.

![Captura de pantalla de la vista Log Analytics de ejemplo para salas de Microsoft Teams](../media/Deploy-Azure-Monitor-1.png "Vista de análisis de registro de ejemplo para salas de Microsoft Teams")

A un mayor nivel, debe realizar las siguientes tareas:


1. [Validar :::no-loc text="Log Analytics"::: la configuración](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurar dispositivos de prueba para la :::no-loc text="Log Analytics"::: configuración de administración](azure-monitor-deploy.md#configure_test_devices)
3. [Asignar campos personalizados](azure-monitor-deploy.md#Custom_fields)
4. [Definir las :::no-loc text="Microsoft Teams Rooms"::: vistas en :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Definir alertas](azure-monitor-deploy.md#Alerts)
6. [Configurar todos los dispositivos para la supervisión](azure-monitor-deploy.md#configure_all_devices)
7. [Configurar soluciones :::no-loc text="Azure Monitor"::: adicionales](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Aunque con una configuración mínima puede supervisar un equipo que ejecuta un sistema operativo, hay algunos pasos específicos que debe seguir antes de iniciar la implementación de agentes en :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: todos los :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Teams Rooms"::: dispositivos.
> Por lo tanto, le recomendamos que realice todos los pasos de configuración en el orden correcto para una configuración y configuración controladas. La calidad del resultado final depende en gran medida de la calidad de la configuración inicial.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Validar :::no-loc text="Log Analytics"::: la configuración
<a name="validate_LogAnalytics"> </a>

Debe tener un área de trabajo para empezar a :::no-loc text="Log Analytics"::: recopilar registros de :::no-loc text="Microsoft Teams Rooms"::: dispositivos. Un área de trabajo es un entorno único con su propio repositorio de :::no-loc text="Log Analytics"::: datos, orígenes de datos y soluciones. Si ya tiene un área de trabajo existente, puede usarla para supervisar la implementación o, como alternativa, puede crear un área de trabajo dedicada específica :::no-loc text="Log Analytics"::: para sus necesidades de :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: supervisión.

Si necesitas crear un área de trabajo nueva, sigue las instrucciones del artículo Crear un área :::no-loc text="Log Analytics"::: de trabajo en el [ :::no-loc text="Log Analytics"::: :::no-loc text="Azure"::: portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Para usarlo :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: con, debe tener una suscripción :::no-loc text="Azure"::: activa. Si no tiene una suscripción, puede crear una suscripción de prueba :::no-loc text="Azure"::: [gratuita](https://azure.microsoft.com/free) como punto de partida.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Configurar para :::no-loc text="Log Analytics"::: recopilar registros :::no-loc text="Microsoft Teams Rooms"::: de eventos

:::no-loc text="Log Analytics"::: solo recopila eventos de los registros :::no-loc text="Windows"::: de eventos especificados en la configuración. Para cada registro, solo se recopilan los eventos con las gravedades seleccionadas.

Debe configurarlo para recopilar los registros necesarios para supervisar el :::no-loc text="Log Analytics"::: estado de la aplicación y el :::no-loc text="Microsoft Teams Rooms"::: dispositivo. :::no-loc text="Microsoft Teams Rooms"::: dispositivos usan el **:::no-loc text="Skype Room System":::** registro de eventos.

Para configurar para :::no-loc text="Log Analytics"::: recopilar los eventos, vea los orígenes de datos :::no-loc text="Microsoft Teams Rooms"::: del registro de eventos [ :::no-loc text="Windows"::: en :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Captura de pantalla de la configuración del registro de eventos](../media/Deploy-Azure-Monitor-2.png "Configuración del registro de eventos")

> [!IMPORTANT]
> Configure las opciones del registro de eventos, escriba como nombre del registro de eventos y, a continuación, active las casillas :::no-loc text="Windows"::: **:::no-loc text="Skype Room System":::** **Error,** Advertencia  **e** Información.

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurar dispositivos de prueba para Azure Monitoring
<a name="configure_test_devices"> </a>

Debe prepararse :::no-loc text="Log Analytics"::: para poder supervisar los eventos :::no-loc text="Microsoft Teams Rooms"::: relacionados. Para empezar, necesita implementar agentes en uno o dos dispositivos a los que solo tenga acceso físico y conseguir que esos dispositivos de prueba generen algunos datos y los empujen al área de :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: trabajo.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Instalar :::no-loc text="Microsoft Monitoring"::: agentes para probar dispositivos

Implementa el agente en los dispositivos de prueba con las instrucciones proporcionadas en Equipos conectados :::no-loc text="Microsoft Monitoring"::: [al servicio :::no-loc text="Windows"::: :::no-loc text="Log Analytics"::: de :::no-loc text="Azure"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). En este artículo se proporciona información detallada sobre los pasos para implementar el agente para, instrucciones para obtener el Id. del área de trabajo _ y la clave principal para conectar los dispositivos a la implementación, y los pasos para comprobar la conectividad de agente en la :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  * ** _**_ :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: instancia.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Generar eventos de :::no-loc text="Microsoft Teams Rooms"::: ejemplo

Después de implementar el agente en los dispositivos de prueba, compruebe que los datos de registro de :::no-loc text="Microsoft Monitoring"::: eventos requeridos los recopila :::no-loc text="Azure Monitor"::: .

> [!NOTE]
> Reinicie el dispositivo después de la instalación del agente y asegúrese de que la aplicación Reunión está iniciada, para que pueda generar nuevos eventos :::no-loc text="Microsoft Monitoring"::: en el registro de :::no-loc text="Microsoft Teams Rooms"::: eventos.

1.  Inicie sesión en el [ :::no-loc text="Microsoft Azure"::: portal y](https://portal.azure.com) vaya al :::no-loc text="Log Analytics"::: área de trabajo y selecciónelo.

2.  Enumerar los eventos de heartbeat generados por un :::no-loc text="Microsoft Teams Rooms"::: dispositivo:
    1.  Seleccione el área de trabajo, vaya a _ *Logs** y use una consulta para recuperar los registros de heartbeat que tendrán los campos :::no-loc text="Microsoft Teams Rooms"::: personalizados.
    2.  Consulta de ejemplo: `Event | where Source == "SRS-App" and EventID == 2000`

3.  Asegúrese de que la consulta devuelve registros de registro que incluyen eventos generados por la :::no-loc text="Microsoft Teams Rooms"::: aplicación de reuniones.

4.  Genere un problema de hardware y valide que los eventos necesarios estén :::no-loc text="Azure Log Analytics"::: registrados.
    1.  Desconecta uno de los dispositivos periféricos del sistema de :::no-loc text="Microsoft Teams Rooms"::: prueba. Esto podría ser la cámara, el altavoz, el micrófono o la pantalla de la sala frontal.
    2.  Espere 10 minutos hasta que se rellene el registro de :::no-loc text="Azure Log Analytics"::: eventos.
    3.  Use una consulta para enumerar los eventos de error de hardware: `Event | where Source == "SRS-App" and EventID == 3001`

5.  Genere un problema de la aplicación y valide que se registran los eventos necesarios.
    1.  Modifique la configuración de la aplicación y escriba un par incorrecto de dirección y contraseña del Protocolo de inicio de sesión :::no-loc text="Microsoft Teams Rooms"::: (SIP).
    2.  Espere 10 minutos hasta que se rellene el registro de :::no-loc text="Azure Log Analytics"::: eventos.
    3.  Use una consulta para enumerar los eventos de error de la aplicación: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Estos registros de eventos de ejemplo son necesarios antes de que se puedan configurar campos personalizados. No continúe con el paso siguiente hasta que haya recopilado los registros de eventos necesarios.

## <a name="map-custom-fields"></a>Asignar campos personalizados
<a name="Custom_fields"> </a>

Los campos personalizados se usan para extraer datos específicos de los registros de eventos. Necesita definir campos personalizados que se usarán más adelante con los mosaicos, las vistas de panel y las alertas. Vea [los :::no-loc text="Log Analytics"::: campos personalizados y](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) familiarícese con los conceptos antes de empezar a crear los campos personalizados.

Para extraer los campos personalizados de los registros de eventos capturados, siga estos pasos:

1.  Inicie sesión en el [ :::no-loc text="Microsoft Azure"::: portal y](https://portal.azure.com) vaya al :::no-loc text="Log Analytics"::: área de trabajo y selecciónelo.

2. Enumerar los eventos generados por un :::no-loc text="Microsoft Teams Rooms"::: dispositivo:
   1.  Vaya a **Registros** y use una consulta para recuperar los registros que tendrán el campo personalizado.
   2.  Consulta de ejemplo: `Event | where Source == "SRS-App" and EventID == 2000`

3. Seleccione uno de los registros, seleccione el botón de la izquierda e inicie el asistente para extracción de campos.
4. Resalte los datos que desea extraer del formato RenderedDescription y proporcione un título de campo. Los nombres de campo que debe usar se proporcionan en la tabla 1.
5. Use las asignaciones que se muestran en *la tabla 1.* :::no-loc text="Log Analytics":::anexará automáticamente la cadena **\_ CF** cuando defina el nuevo campo.

> [!IMPORTANT]
> Recuerde que todos los campos y JSON :::no-loc text="Log Analytics"::: distinguen entre mayúsculas y minúsculas.
> 
> Preste atención a las consultas necesarias para cada campo personalizado de la tabla siguiente. Debe usar las consultas correctas para extraer correctamente los valores de :::no-loc text="Log Analytics"::: campo personalizados.
> 
**Tabla 1**

| **Campo JSON**                   | **:::no-loc text="Log Analytics"::: campo personalizado** | **Nivel del** | **Consulta que se usará para la extracción**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Descripción                      | SRSEventDescription         | **2000**     | Evento \| donde Source == "SRS-App" y EventID == 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Evento \| donde Source == "SRS-App" y EventID == 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Evento \| donde Source == "SRS-App" y EventID == 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Evento \| donde Source == "SRS-App" y EventID == 2000 |
| Sistema operativo                               | SRSOSVersion                | **2000**     | Evento \| donde Source == "SRS-App" y EventID == 2000 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | Evento \| donde Source == "SRS-App" y EventID == 2000 |
| Alias                            | SRSAlias                    | **2000**     | Evento \| donde Source == "SRS-App" y EventID == 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Evento \| donde Source == "SRS-App" y EventID == 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Evento \| donde Source == "SRS-App" y EventID == 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Evento \| donde Source == "SRS-App" y EventID == 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Evento \| donde Source == "SRS-App" y EventID == 2000 |
| Estado del micrófono de conferencia     | SRSConfMicrophoneStatus     | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |
| Estado del orador de la conferencia        | SRSConfSpeakerStatus        | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |
| Estado predeterminado del altavoz           | SRSDefaultSpeakerStatus     | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |
| Estado de la cámara                    | SRSCameraStatus             | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |
| Estado de visualización del anverso de la sala     | SRSFORDStatus               | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |
| Estado del Sensor de movimiento             | SRSMotion SensorStatus       | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |
| Estado de ingerir HDMI               | SRSHDMIIngestStatus         | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Definir las :::no-loc text="Microsoft Teams Rooms"::: vistas en :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Una vez que se recopilan los datos y se asignan los campos personalizados, puede usar el Diseñador de vistas para desarrollar un panel que contenga varios mosaicos para supervisar :::no-loc text="Microsoft Teams Rooms"::: eventos. Use Diseñador de vistas para crear los siguientes iconos. Para obtener más información, vea [Crear :::no-loc text="Log Analytics"::: vistas personalizadas con el Diseñador de vistas en](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Los pasos anteriores de esta guía deberían haber finalizado para que los mosaicos del panel funcionen correctamente.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Crear un panel de salas de Microsoft Teams con el método de importación

Puede importar un panel :::no-loc text="Microsoft Teams Rooms"::: y empezar a supervisar sus dispositivos rápidamente. Siga estos pasos para importar el panel:

1.  Obtén el [archivo SkypeRoomSystems_v2 panel de omsview.](https://go.microsoft.com/fwlink/?linkid=835675)
2.  Inicie sesión en el [ :::no-loc text="Microsoft Azure"::: portal y](https://portal.azure.com) vaya al :::no-loc text="Log Analytics"::: área de trabajo y selecciónelo.
3.  Abra **el Diseñador de vistas.**
4.  Seleccione **Importar** y, a continuación, seleccione **el SkypeRoomSystems_v2.omsview.**
5.  Seleccione **Guardar**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Crear manualmente un panel de salas de Microsoft Teams

Como alternativa, puede crear su propio panel y agregar solo los mosaicos que desee supervisar.

#### <a name="configure-the-overview-tile"></a>Configurar el mosaico Información general

1.  Abra **el Diseñador de vistas.**
2.  Seleccione **Mosaico De información** general y, a continuación, seleccione Dos **números** de la galería.
3.  Asigne un nombre al **:::no-loc text="Microsoft Teams Rooms":::** icono.
4.  Definir el **primer icono:**<br>
    **Leyenda:** Dispositivos que enviaron un pulsación al menos una vez en el último mes<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Definir el **segundo icono:**<br>
    **Leyenda:** Dispositivos activos que enviaron un corazón en la última hora<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Seleccione **Aplicar.**

### <a name="create-a-tile-that-displays-active-devices"></a>Crear un icono que muestre dispositivos activos

1.  Seleccione **Ver panel** para empezar a agregar los mosaicos.
2.  Seleccione **Número & de** la galería
3.  Definir las **propiedades** generales:<br>
    **Título del grupo:** Heartbeat Status<br>
    **Nuevo grupo:** Seleccionado
4.  Definir las **propiedades de** mosaico:<br>
    **Leyenda:** Dispositivos activos (el corazón se envió en los últimos 20 minutos)<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definir las **propiedades de** lista:<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definir **títulos de columna:**<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Last Heartbeat
7.  Definir **consulta de navegación.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar** y, a continuación, **Cerrar.**

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Crear un icono que muestre los dispositivos que tienen problemas de conectividad

1.  Seleccione **Número & de** la galería y, a continuación, agregue un nuevo icono.
2.  Definir las **propiedades** generales:<br>
    **Título del grupo:** Dejar vacío<br>
    **Nuevo grupo:** No seleccionado
3.  Definir las **propiedades de** mosaico:<br>
    **Leyenda:** Dispositivos inactivos (ningún mensaje de heartbeat enviado en los últimos 20 minutos)<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definir las **propiedades de** lista:<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definir **títulos de columna:**<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Last Heartbeat
6.  Definir **consulta de navegación:**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Seleccione **Aplicar** y, a continuación, **Cerrar.**

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Crear un icono que muestre los dispositivos que tienen un error de hardware

1.  Seleccione **Número & de** la galería y, a continuación, agregue un nuevo icono.
2.  Definir las **propiedades** generales:<br>
    **Título del grupo:** Estado del hardware<br>
    **Nuevo grupo:** Seleccionado
3.  Definir las **propiedades de** mosaico:<br>
    **Leyenda:** Dispositivos que experimentaron un error de hardware en la última hora<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definir las **propiedades de** lista:<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **títulos de columna:**<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último error
6.  Definir **consulta de navegación:**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Seleccione **Aplicar** y, a continuación, **Cerrar.**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Crear un mosaico que muestre las :::no-loc text="Microsoft Teams Rooms"::: versiones del sistema operativo

1.  Seleccione **Anillos & de** la galería y, a continuación, agregue un nuevo icono.
2.  Definir las **propiedades** generales:<br>
    **Título del grupo:** Detalles del sistema operativo<br>
    **Nuevo grupo:** Seleccionado
3.  Definir las **propiedades del** encabezado:<br>
    **Título:** Versiones del sistema operativo<br>
    **Subtítulo:** Dispositivos que ejecutan versiones específicas del sistema operativo
4.  Definir las **propiedades de anillos:**<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Centrar texto:** Dispositivos<br>
    **Operación:** Suma
5.  Defina las **propiedades de** lista.<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar Gráfico:** Seleccionado<br>
    **Habilitar minigráficos:** No seleccionado
6.  Definir **títulos de columna.**<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Dejar vacío
7.  Definir **consulta de navegación.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar** y, a continuación, **Cerrar.**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Crear un mosaico que muestre las versiones :::no-loc text="Microsoft Teams Rooms"::: de la aplicación

1.  Seleccione **Anillos & de** la galería y, a continuación, agregue un nuevo icono.
2.  Definir las **propiedades** generales:<br>
    **Título del grupo:** :::no-loc text="Microsoft Teams Rooms"::: detalles de la aplicación<br>
    **Nuevo grupo:** Seleccionado
3.  Definir las **propiedades del** encabezado:<br>
    **Título:** Versiones de la aplicación<br>
    **Subtítulo:** Dispositivos que ejecutan versiones de aplicación específicas
4.  Definir las **propiedades de anillos:**<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Centrar texto:** Dispositivos<br>
    **Operación:** Suma
5.  Defina las **propiedades de** lista.<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar Gráfico:** Seleccionado<br>
    **Habilitar minigráficos:** No seleccionado
6.  Definir **títulos de columna.**<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Dejar vacío
7.  Definir **consulta de navegación.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar** y, a continuación, **Cerrar.**

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Crear un icono que muestre los dispositivos que tienen un error de aplicación

1.  Seleccione **Número & de** la galería y, a continuación, agregue un nuevo icono.
2.  Defina las **propiedades** Generales.<br>
    **Título del grupo:** Dejar vacío<br>
    **Nuevo grupo:** No seleccionado
3.  Definir las **propiedades de** mosaico.<br>
    **Leyenda:** Dispositivos que experimentaron un error de aplicación en la última hora<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina las **propiedades de** lista.<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **títulos de columna.**<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último error
6.  Definir **consulta de navegación.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Seleccione **Aplicar** y, a continuación, **Cerrar.**

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Crear un icono que muestre los dispositivos que se han reiniciado

1.  Seleccione **Número & de** la galería y, a continuación, agregue un nuevo icono.
2.  Defina las **propiedades** Generales.<br>
    **Título del grupo:** Dejar vacío<br>
    **Nuevo grupo:** No seleccionado
3.  Definir las **propiedades de** mosaico.<br>
    **Leyenda:** Dispositivos en los que la aplicación se ha reiniciado en las últimas 24 horas y el número de reinicios<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina las **propiedades de** lista.<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definir **títulos de columna.**<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Número de reinicios
6.  Definir **consulta de navegación.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Seleccione **Aplicar** y, a continuación, **Cerrar.**
8.  Seleccione **Guardar** para guardar el panel.

Ya ha terminado de crear las vistas.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Configurar alertas en :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: puede alertas para notificar a los administradores cuando una :::no-loc text="Microsoft Teams Rooms"::: consola se encuentra con un problema.

:::no-loc text="Azure Monitor"::: incluye un mecanismo integrado de alertas que se ejecuta a través de búsquedas de registro programadas a intervalos regulares. Si los resultados de la búsqueda de registro coinciden con algunos criterios concretos, se crea un registro de alertas.

A continuación, la regla puede ejecutar automáticamente una o más acciones para notificar de forma proactiva la alerta o invocar otro proceso. Las posibles opciones con alertas son:
-   Enviar un correo electrónico
-   Invocar un proceso externo a través de una solicitud HTTP POST
-   Iniciar una sesión en :::no-loc text="Azure Automation"::: el servicio

Vea [Registrar :::no-loc text="Azure Monitor"::: alertas para](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) obtener más información sobre las alertas. :::no-loc text="Azure Monitor":::

> [!NOTE]
> Los ejemplos siguientes envían alertas de correo electrónico cuando :::no-loc text="Microsoft Teams Rooms"::: un dispositivo genera un error de hardware o de aplicación.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Configurar una alerta de correo electrónico para problemas :::no-loc text="Microsoft Teams Rooms"::: de hardware

Configure una regla de alerta que comprueba los dispositivos que han detectado problemas :::no-loc text="Microsoft Teams Rooms"::: de hardware en la última hora.
1.  Inicie sesión en el [ :::no-loc text="Microsoft Azure"::: portal y](https://portal.azure.com) vaya al :::no-loc text="Log Analytics"::: área de trabajo y selecciónelo.

2. Vaya al área :::no-loc text="Log Analytics"::: de trabajo, seleccione **Alertas** y, a continuación, **seleccione Nueva regla de alertas**

3. Seleccione **Agregar condición y,** a continuación, **Búsqueda de registros personalizada**

4.  Escriba la consulta siguiente en el cuadro de texto De la consulta de búsqueda.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configure las opciones de lógica de alerta:<br>
    **Basado en:** Número de resultados<br>
    **Condición:** Mayor que<br>
    **Umbral:** 0<br>

6. Configure las opciones de evaluación y seleccione **Listo:** <br>
    **Período (en minutos):** 60<br>
    **Frecuencia (en minutos):** 60<br>

7. Configurar grupos de acciones:
    1.  Seleccione **Crear nuevo**
    2.  Proporcione nombres adecuados para los *campos Nombre del grupo de* acciones y *Nombre* corto.
    3.  Especifica un nombre *de acción único,* selecciona **Correo electrónico/SMS/Push/Voice** y, a continuación, selecciona **Editar detalles.**
    4.  Seleccione la **casilla Correo** electrónico y proporcione la dirección de correo electrónico de la persona o grupo que recibirá las alertas.
    5.  También puedes proporcionar tu número de teléfono para recibir notificaciones por SMS, una llamada de voz o ambos.
    6. Seleccione **Aceptar.**

8. **Personalice Acciones** si desea reemplazar la línea de asunto de los correos electrónicos de alerta.

9. Especifique un nombre de regla y una descripción.<br>
    **Nombre de regla:** :::no-loc text="Microsoft Teams Rooms"::: Alerta de error de hardware<br>
    **Descripción:** Lista de dispositivos que se han encontrado con un problema de hardware en la última hora<br>

10. Seleccione la gravedad deseada y asegúrese de que la regla está habilitada.

11. Seleccione **Crear regla de alerta.**

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Configurar una alerta de correo electrónico para problemas :::no-loc text="Microsoft Teams Rooms"::: con la aplicación

Repita el mismo procedimiento, pero use la consulta siguiente para enumerar los dispositivos que han detectado problemas con la aplicación en la última hora.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

Ahora ya ha completado la definición de alertas. Puede definir alertas adicionales con los ejemplos anteriores.

Cuando se genera una alerta, recibe un correo electrónico que enumera los dispositivos que se han encontrado con un problema en la última hora.

! [Correo :::no-loc text="Azure Monitor"::: electrónico de alerta de ejemplo](.. /media/Deploy-Azure-Monitor-6.png "Correo :::no-loc text="Azure Monitor"::: electrónico de alerta de ejemplo")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Configurar todos los dispositivos para :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a> Después de configurar los paneles y las alertas, puede configurar el agente en todos los dispositivos :::no-loc text="Microsoft Monitoring"::: para completar la implementación de :::no-loc text="Microsoft Teams Rooms"::: supervisión.

Aunque puede instalar y configurar el agente manualmente en cada dispositivo, le recomendamos encarecidamente que use los métodos y las herramientas de implementación de :::no-loc text="Microsoft Monitoring"::: software existentes.

Si va a crear sus dispositivos por primera vez, es posible que desee incluir los pasos de configuración y configuración del agente como parte del proceso :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: de compilación. Para obtener más información, [vea Instalar el agente con la línea de comandos.](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Implementar un :::no-loc text="Microsoft Monitoring"::: agente mediante un objeto de directiva de grupo (GPO)

Si ya implementó los dispositivos antes de implementar, puede usar el script proporcionado para configurar los agentes mediante objetos de directiva :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: de :::no-loc text="Active Directory"::: grupo.

1.  Cree una ruta de acceso de red compartida y conceda acceso de lectura al **grupo Equipos de** dominio.

2.  Descarga la versión de 64 bits del :::no-loc text="Microsoft Monitoring"::: agente para :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrae el contenido del paquete de configuración en el recurso compartido de red.
    1.  Abrir una ventana del símbolo del sistema y, a **continuación,MMASetup-AMD64.exe /c**
    2.  Especifique el recurso compartido que acaba de crear y extraiga el contenido.

4.  Cree un nuevo objeto de directiva de grupo y asígnelo a la unidad de organización donde :::no-loc text="Microsoft Teams Rooms"::: se encuentran las cuentas de equipo.

5.  Configurar la directiva de ejecución de PowerShell:
    1.  Edite el objeto de directiva de grupo recién creado y vaya a Componentes de plantillas \\ administrativas de directivas de configuración del \\ \\ :::no-loc text="Windows"::: equipo \\:::no-loc text="Windows PowerShell":::
    2.  Habilite la **activación de la ejecución del script** y establezca la directiva de **ejecución** para permitir **scripts locales.**

6.  Configurar el script de inicio:
    1.  Copie el script siguiente y guárdelo como Install-MMAgent.ps1.
    2.  Modifique los parámetros WorkspaceId, WorkspaceKey y SetupPath para que coincidan con la configuración.
    3.  Edite el mismo objeto de directiva de grupo y vaya a Scripts de configuración de directivas de configuración \\ \\ :::no-loc text="Windows"::: del equipo \\ (inicio/apagado)
    4.  Haga doble clic para seleccionar **Inicio y,** a continuación, seleccione **Scripts de PowerShell.**
    5.  Seleccione **Mostrar archivos** y, a continuación, copie el **Install-MMAgent.ps1** archivo en esa carpeta.
    6.  Seleccione **Agregar** y, a continuación, **Examinar.**
    7.  Seleccione el script ps1 que acaba de copiar.

7.  :::no-loc text="Microsoft Teams Rooms"::: los dispositivos deben instalar y configurar el :::no-loc text="Microsoft Monitoring"::: agente con el segundo reinicio.

```PowerShell
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
> Puede consultar el [ :::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) artículo Administrar y mantener el agente cuando tenga que volver a configurar un agente, moverlo a un área de trabajo diferente o modificar la configuración de proxy después de la instalación inicial.

## <a name="additional-solutions"></a>Soluciones adicionales
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: proporciona soluciones de administración integradas a través de su galería de [soluciones](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) para ayudarle a supervisar su entorno. Recomendamos encarecidamente que agregue también soluciones [de administración de](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) [ :::no-loc text="Azure Log Analytics"::: alertas y estado](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) del agente al área de trabajo.

> [!NOTE]
> La solución De estado del agente puede ayudarle a identificar agentes obsoletos o rotos en su entorno, y la solución de administración de alertas proporciona detalles sobre las alertas que se han elevado en :::no-loc text="Microsoft Monitoring"::: un período determinado.

## <a name="see-also"></a>Consulte también

[Planear :::no-loc text="Microsoft Teams Rooms"::: la administración con :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Administrar :::no-loc text="Microsoft Teams Rooms"::: dispositivos con :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
