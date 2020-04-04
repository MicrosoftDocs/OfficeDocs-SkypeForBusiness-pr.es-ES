---
title: Implementar la administración de salas de Microsoft Teams con Azure monitor
author: lanachin
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
description: En este artículo se explica cómo implementar la administración de los dispositivos de salas de Microsoft Teams de forma integrada, de extremo a extremo, con Azure monitor.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3e01ae7a0fddcb63595b7dcc15b719ad1d41db32
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137650"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>Implementar :::no-loc text="Microsoft Teams Rooms"::: la administración con:::no-loc text="Azure Monitor":::

En este artículo se explica cómo configurar e implementar la administración integrada y completa de :::no-loc text="Microsoft Teams Rooms"::: los dispositivos con. :::no-loc text="Azure Monitor":::

Puede :::no-loc text="Log Analytics"::: configurarlo :::no-loc text="Azure Monitor"::: en para proporcionar alertas y telemetría básicas que le ayudarán :::no-loc text="Microsoft Teams Rooms"::: a administrar los dispositivos de la sala de reuniones. A medida que crece la solución de administración, es posible que decida implementar capacidades adicionales de administración y datos para crear una vista más detallada de la disponibilidad y el rendimiento de los dispositivos.

Siguiendo esta guía, puede usar un panel como el siguiente ejemplo para obtener informes detallados sobre el estado de la disponibilidad del dispositivo, el estado :::no-loc text="Microsoft Teams Rooms"::: de las aplicaciones y el hardware, así como la distribución de versiones de aplicaciones y sistemas operativos.

![Captura de pantalla de la vista análisis de registros de ejemplo para salas de Microsoft Teams](../media/Deploy-Azure-Monitor-1.png "Vista de análisis de registros de ejemplo para salas de Microsoft Teams")

A un mayor nivel, debe realizar las siguientes tareas:


1. [Validar :::no-loc text="Log Analytics"::: configuración](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurar dispositivos de prueba :::no-loc text="Log Analytics"::: para la configuración de administración](azure-monitor-deploy.md#configure_test_devices)
3. [Asignar campos personalizados](azure-monitor-deploy.md#Custom_fields)
4. [Definir las :::no-loc text="Microsoft Teams Rooms"::: vistas de:::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Definir alertas](azure-monitor-deploy.md#Alerts)
6. [Configurar todos los dispositivos para la supervisión](azure-monitor-deploy.md#configure_all_devices)
7. [Configurar soluciones :::no-loc text="Azure Monitor"::: adicionales](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Aunque con la configuración mínima :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: , puede supervisar un equipo con :::no-loc text="Windows"::: un sistema operativo, aún hay algunos :::no-loc text="Microsoft Teams Rooms":::pasos específicos que debe seguir antes de empezar a implementar agentes en todos los :::no-loc text="Microsoft Teams Rooms"::: dispositivos.
> Por lo tanto, le recomendamos encarecidamente que realice todos los pasos de configuración en el orden correcto para una instalación y configuración controlada. La calidad del resultado final depende de la calidad de la configuración inicial.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Validar :::no-loc text="Log Analytics"::: configuración
<a name="validate_LogAnalytics"> </a>

Debe tener un área de :::no-loc text="Log Analytics"::: trabajo para iniciar la recopilación de :::no-loc text="Microsoft Teams Rooms"::: registros de los dispositivos. Un área de trabajo es :::no-loc text="Log Analytics"::: un entorno único con su propio repositorio de datos, orígenes de datos y soluciones. Si ya tiene un área de :::no-loc text="Log Analytics"::: trabajo existente, puede usarla para supervisar la :::no-loc text="Microsoft Teams Rooms"::: implementación o, de forma alternativa, puede crear un área :::no-loc text="Log Analytics"::: de trabajo dedicada específica :::no-loc text="Microsoft Teams Rooms"::: para sus necesidades de supervisión.

Si necesita crear un área de trabajo :::no-loc text="Log Analytics"::: nueva, siga las instrucciones del artículo [crear un :::no-loc text="Log Analytics"::: área de trabajo en :::no-loc text="Azure"::: el portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Para usar :::no-loc text="Log Analytics"::: con :::no-loc text="Azure Monitor":::, necesita tener una suscripción activa :::no-loc text="Azure"::: . Si no tiene una :::no-loc text="Azure"::: suscripción, puede crear [una suscripción de prueba gratuita](https://azure.microsoft.com/free) como punto de partida.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Configurar :::no-loc text="Log Analytics"::: para recopilar :::no-loc text="Microsoft Teams Rooms"::: registros de eventos

:::no-loc text="Log Analytics":::solo recopila eventos de los :::no-loc text="Windows"::: registros de eventos que se especifican en la configuración. Para cada registro, solo se recopilan los eventos con las gravedades seleccionadas.

Debe configurar :::no-loc text="Log Analytics"::: para recopilar los registros necesarios para supervisar :::no-loc text="Microsoft Teams Rooms"::: el estado del dispositivo y de la aplicación. :::no-loc text="Microsoft Teams Rooms":::los dispositivos usan **:::no-loc text="Skype Room System":::** el registro de eventos.

Para configurar :::no-loc text="Log Analytics"::: para recopilar :::no-loc text="Microsoft Teams Rooms"::: los eventos, consulte [ :::no-loc text="Windows"::: orígenes de datos del :::no-loc text="Azure Monitor"::: registro de eventos en](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Captura de pantalla de configuración de registro de eventos](../media/Deploy-Azure-Monitor-2.png "Configuración del registro de eventos")

> [!IMPORTANT]
> Configure :::no-loc text="Windows"::: los parámetros del registro **:::no-loc text="Skype Room System":::** de eventos y especifique el nombre del registro de eventos y, a continuación, active las casillas de **error**, **ADVERTENCIA**e **información** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurar dispositivos de prueba para la supervisión de Azure
<a name="configure_test_devices"> </a>

Debe prepararse :::no-loc text="Log Analytics"::: para poder supervisar :::no-loc text="Microsoft Teams Rooms":::los eventos relacionados. Para empezar, debe implementar :::no-loc text="Microsoft Monitoring"::: agentes en uno o dos :::no-loc text="Microsoft Teams Rooms"::: dispositivos a los que tiene acceso físico y obtener esos dispositivos generan datos y los inserta en el :::no-loc text="Log Analytics"::: área de trabajo.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Instalar :::no-loc text="Microsoft Monitoring"::: agentes para probar dispositivos

Implemente :::no-loc text="Microsoft Monitoring"::: el agente en los dispositivos de prueba con las instrucciones proporcionadas en [conectar :::no-loc text="Windows"::: equipos :::no-loc text="Log Analytics"::: al servicio :::no-loc text="Azure":::en ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). En este artículo se proporciona información detallada sobre los pasos para :::no-loc text="Microsoft Monitoring"::: implementar el :::no-loc text="Windows":::agente, instrucciones para obtener el :::no-loc text="Log Analytics"::: ***identificador de área de trabajo*** y la :::no-loc text="Microsoft Teams Rooms"::: ***clave principal*** para obtener :::no-loc text="Azure Monitor"::: los dispositivos conectados a la implementación, y pasos :::no-loc text="Log Analytics"::: para comprobar la conectividad de los agentes con la instancia.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Generar eventos :::no-loc text="Microsoft Teams Rooms"::: de ejemplo

Después de :::no-loc text="Microsoft Monitoring"::: que el agente se haya implementado en los dispositivos de prueba, compruebe que los datos del :::no-loc text="Azure Monitor":::registro de eventos necesarios sean recopilados por.

> [!NOTE]
> Reinicie el dispositivo después de la instalación del :::no-loc text="Microsoft Monitoring"::: agente y asegúrese de que :::no-loc text="Microsoft Teams Rooms"::: se haya iniciado la aplicación de la reunión para que pueda generar nuevos eventos en el registro de eventos.

1.  Inicie sesión en el [ :::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) y vaya a :::no-loc text="Log Analytics"::: su área de trabajo y selecciónela.

2.  Mostrar los eventos de latido generados :::no-loc text="Microsoft Teams Rooms"::: por un dispositivo:
    1.  Seleccione el área de trabajo y vaya a **registros** y use una consulta para recuperar los registros de latido para :::no-loc text="Microsoft Teams Rooms":::los que tendrán los campos personalizados.
    2.  Consulta de ejemplo:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Asegúrese de que la consulta devuelve los registros que incluyen los eventos generados :::no-loc text="Microsoft Teams Rooms"::: por la aplicación reuniones.

4.  Genere un problema de hardware y compruebe que los eventos necesarios estén registrados :::no-loc text="Azure Log Analytics":::.
    1.  Desconecte uno de los dispositivos periféricos en el :::no-loc text="Microsoft Teams Rooms"::: sistema de prueba. Puede ser la cámara, el teléfono con manos libres, el micrófono o la habitación frontal
    2.  Espere 10 minutos para que se rellene el registro de :::no-loc text="Azure Log Analytics":::eventos.
    3.  Usar una consulta para enumerar eventos de error de hardware:`Event | where Source == "SRS-App" and EventID == 3001`

5.  Genere un problema de aplicación y compruebe que los eventos necesarios estén registrados.
    1.  Modifique :::no-loc text="Microsoft Teams Rooms"::: la configuración de la aplicación y escriba una pareja incorrecta de dirección y contraseña del Protocolo de inicio de sesión (SIP).
    2.  Espere 10 minutos para que se rellene el registro de :::no-loc text="Azure Log Analytics":::eventos.
    3.  Usar una consulta para enumerar eventos de error de la aplicación:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Estos registros de eventos de ejemplo son obligatorios para poder configurar campos personalizados. No continúe con el paso siguiente hasta que haya recopilado los registros de eventos necesarios.

## <a name="map-custom-fields"></a>Asignar campos personalizados
<a name="Custom_fields"> </a>

Los campos personalizados se usan para extraer datos específicos de los registros de eventos. Debe definir campos personalizados que se usarán más adelante con los mosaicos, las vistas de panel y las alertas. Vea los [campos personalizados :::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) y familiarícese con los conceptos antes de empezar a crear los campos personalizados.

Para extraer los campos personalizados fuera de los registros de eventos capturados, siga estos pasos:

1.  Inicie sesión en el [ :::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) y vaya a :::no-loc text="Log Analytics"::: su área de trabajo y selecciónela.

2. Enumerar los eventos generados :::no-loc text="Microsoft Teams Rooms"::: por un dispositivo:
   1.  Vaya a **registros** y use una consulta para recuperar los registros que tendrán el campo personalizado.
   2.  Consulta de ejemplo:`Event | where Source == "SRS-App" and EventID == 2000`

3. Seleccione uno de los registros, seleccione el botón de la izquierda e inicie el Asistente para extracción de campos.
4. Resalte los datos que desea extraer de la RenderedDescription y proporcione un título para el campo. Los nombres de campo que debe usar se proporcionan en la tabla 1.

   ![Definición de campo personalizado](../media/Deploy-Azure-Monitor-4.png "Definición de campo personalizado")

5. Use las asignaciones que se muestran en la *tabla 1*. :::no-loc text="Log Analytics":::anexará automáticamente la ** \_** cadena de tipo CF al definir el nuevo campo.

> [!IMPORTANT]
> Recuerde que todos los campos :::no-loc text="Log Analytics"::: y JSON distinguen entre mayúsculas y minúsculas.
> 
> Preste atención a las consultas necesarias para cada campo personalizado de la tabla siguiente. Debe usar las consultas correctas para poder extraer :::no-loc text="Log Analytics"::: correctamente los valores de los campos personalizados.
> 
 ![Definición de campo personalizado](../media/Deploy-Azure-Monitor-5.png "Definición de campo personalizado")

**Tabla 1**

| **Campo JSON**                   | **:::no-loc text="Log Analytics":::campo personalizado** | **Nivel del** | **Consulta para usar con la extracción**                   |
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


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Definir las :::no-loc text="Microsoft Teams Rooms"::: vistas de:::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Una vez que se recopilan los datos y se asignan los campos personalizados, puede usar el diseñador de vistas para desarrollar :::no-loc text="Microsoft Teams Rooms"::: un panel con varios mosaicos para supervisar los eventos. Use Diseñador de vistas para crear los siguientes iconos. Para obtener más información, vea [crear vistas personalizadas con el diseñador de :::no-loc text="Log Analytics"::: vistas en](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Los pasos anteriores de esta guía deberían haberse completado para que los mosaicos del panel funcionen correctamente.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Crear un panel de salas de Microsoft Teams con el método de importación

Puede importar un :::no-loc text="Microsoft Teams Rooms"::: panel y empezar a supervisar los dispositivos rápidamente. Siga estos pasos para importar el panel:

1.  Obtenga el archivo de panel [SkypeRoomSystems_v2. omsview](https://go.microsoft.com/fwlink/?linkid=835675) .
2.  Inicie sesión en el [ :::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) y vaya a :::no-loc text="Log Analytics"::: su área de trabajo y selecciónela.
3.  Abra el **Diseñador de vistas**.
4.  Seleccione **importar**y, a continuación, seleccione el archivo **SkypeRoomSystems_v2. omsview** .
5.  Seleccione **Guardar**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Crear un panel de salas de Microsoft Teams manualmente

También puede crear su propio panel y agregar solo los mosaicos que desea supervisar.

#### <a name="configure-the-overview-tile"></a>Configurar el mosaico Descripción general

1.  Abra el **Diseñador de vistas**.
2.  Seleccione **mosaico de información general**y, a continuación, seleccione **dos números** de la galería.
3.  Asigne un nombre **:::no-loc text="Microsoft Teams Rooms":::** al mosaico.
4.  Definir el **primer mosaico**:<br>
    **Leyenda:** Dispositivos que han enviado un latido al menos una vez durante el mes pasado<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Defina el **segundo mosaico**:<br>
    **Leyenda:** Dispositivos activos que han enviado un latido durante la última hora<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Seleccione **aplicar**.

### <a name="create-a-tile-that-displays-active-devices"></a>Crear un mosaico que muestre los dispositivos activos

1.  Seleccione **Ver panel** para empezar a agregar los mosaicos.
2.  Seleccionar el **número & lista** de la galería
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

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Crear un mosaico que muestre :::no-loc text="Microsoft Teams Rooms"::: las versiones del sistema operativo

1.  Seleccione **Donut & lista** en la galería y, a continuación, agregue un nuevo mosaico.
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

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Crear un mosaico que muestre :::no-loc text="Microsoft Teams Rooms"::: las versiones de la aplicación

1.  Seleccione **Donut & lista** en la galería y, a continuación, agregue un nuevo mosaico.
2.  Defina las propiedades **generales** :<br>
    **Título del Grupo:** :::no-loc text="Microsoft Teams Rooms"::: detalles de la aplicación<br>
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

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Configurar alertas en:::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor":::puede generar alertas para notificar a los administradores cuando una :::no-loc text="Microsoft Teams Rooms"::: consola encuentra un problema.

:::no-loc text="Azure Monitor":::incluye un mecanismo de alertas integrado que se ejecuta a través de búsquedas de registro programadas a intervalos regulares. Si los resultados de la búsqueda de registro coinciden con algunos criterios determinados, se crea un registro de alerta.

Después, la regla puede ejecutar automáticamente una o más acciones para notificarlo de manera proactiva o invocar otro proceso. Las posibles opciones con alertas son las siguientes:
-   Enviar un correo electrónico
-   Invocar un proceso externo a través de una solicitud HTTP POST
-   Iniciando un runbook :::no-loc text="Azure Automation"::: en el servicio

Consulte [registrar alertas en :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) para obtener más información sobre las alertas :::no-loc text="Azure Monitor":::de.

> [!NOTE]
> En los siguientes ejemplos se envían alertas por :::no-loc text="Microsoft Teams Rooms"::: correo electrónico cuando un dispositivo genera un error de hardware o de aplicación.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Configurar una alerta por correo :::no-loc text="Microsoft Teams Rooms"::: electrónico para problemas de hardware

Configure una regla de :::no-loc text="Microsoft Teams Rooms"::: alerta que busque dispositivos que hayan encontrado problemas de hardware dentro de la última hora.
1.  Inicie sesión en el [ :::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) y vaya a :::no-loc text="Log Analytics"::: su área de trabajo y selecciónela.

2. Navegue hasta el :::no-loc text="Log Analytics"::: área de trabajo y seleccione **alertas** y, a continuación, seleccione **nueva regla de alertas** .

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
    **Umbral:** 0<br>

6. Configure las opciones de evaluación y seleccione **listo**: <br>
    **Período (en minutos):** 60<br>
    **Frecuencia (en minutos):** 60<br>

7. Configurar grupos de acciones:
    1.  Seleccione **crear nuevo**
    2.  Proporcione nombres adecuados para los campos *nombre de grupo de acciones* y *nombre corto* .
    3.  Especifique un *nombre de acción* único y seleccione **correo electrónico/SMS/inserción/voz**y, después, seleccione **editar detalles**.
    4.  Seleccione la casilla **email (correo electrónico** ) y proporcione la dirección de correo electrónico de la persona o grupo que recibirá las alertas.
    5.  También puedes proporcionar tu número de teléfono para recibir notificaciones con SMS, llamadas de voz o ambas cosas.
    6. Seleccione **Aceptar**.

8. **Personalizar acciones** si desea anular la línea de asunto de los mensajes de correo electrónico de alerta.

9. Especifique un nombre y una descripción para la regla.<br>
    **Nombre de la regla:** :::no-loc text="Microsoft Teams Rooms"::: alerta de error de hardware<br>
    **Descripción:** Lista de dispositivos que tuvieron un problema de hardware dentro de la última hora<br>

10. Seleccione la gravedad prevista y asegúrese de que la regla esté habilitada.

11. Seleccione **crear regla de alertas**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Configurar una alerta por correo :::no-loc text="Microsoft Teams Rooms"::: electrónico para los problemas de las aplicaciones

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

! [Correo :::no-loc text="Azure Monitor"::: electrónico de alerta de ejemplo] (.. /media/Deploy-Azure-Monitor-6.png "mensaje :::no-loc text="Azure Monitor"::: de alerta de ejemplo")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Configurar todos los dispositivos para:::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a> Una vez configurados los paneles y las alertas, puede configurar y configurar :::no-loc text="Microsoft Monitoring"::: el agente en :::no-loc text="Microsoft Teams Rooms"::: todos los dispositivos para completar la implementación de la supervisión.

Aunque puede instalar y configurar el :::no-loc text="Microsoft Monitoring"::: agente de forma manual en cada dispositivo, le recomendamos encarecidamente que aproveche las herramientas y métodos de implementación de software existentes.

Si está creando sus :::no-loc text="Microsoft Teams Rooms"::: dispositivos por primera vez, es posible que desee incluir los :::no-loc text="Microsoft Monitoring"::: pasos de configuración y configuración del agente como parte de su proceso de compilación. Para obtener más información, consulte [instalar el agente mediante la línea de comandos](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Implementación del :::no-loc text="Microsoft Monitoring"::: agente mediante un objeto de directiva de grupo (GPO)

Si ya ha implementado :::no-loc text="Microsoft Teams Rooms"::: los dispositivos antes de :::no-loc text="Azure Monitoring":::implementarlos, puede usar el script proporcionado para configurar y configurar los agentes mediante :::no-loc text="Active Directory"::: objetos de directiva de grupo.

1.  Crear una ruta de red compartida y conceder acceso de lectura al grupo **equipos del dominio** .

2.  Descargar la versión de 64 bits del :::no-loc text="Microsoft Monitoring"::: agente para de :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extraiga el contenido del paquete de instalación en el recurso compartido de red.
    1.  Abra una ventana del símbolo del sistema y ejecute **MMASetup-AMD64. exe/c**
    2.  Especifique el recurso compartido que acaba de crear y extraiga el contenido.

4.  Cree un nuevo objeto de directiva de grupo y asígnelo a la unidad organizativa :::no-loc text="Microsoft Teams Rooms"::: donde se encuentren las cuentas de equipo.

5.  Configurar la Directiva de ejecución de PowerShell:
    1.  Modificar el objeto de directiva de grupo recién creado y navegar a \\ directivas \\ de configuración \\ :::no-loc text="Windows"::: del \\ equipo componentes de plantillas administrativas:::no-loc text="Windows PowerShell":::
    2.  Habilitar la **activación de la ejecución de script** y establecer la **Directiva de ejecución** para **permitir scripts locales**.

6.  Configure el script de Inicio:
    1.  Copie el script siguiente y guárdelo como Install-MMAgent. ps1.
    2.  Modifique los parámetros WorkspaceId, WorkspaceKey y SetupPath para que coincidan con la configuración.
    3.  Modificar el mismo objeto de directiva de grupo y navegar a \\ configuración \\ :::no-loc text="Windows"::: \\ de directivas de configuración del equipo secuencias de comandos (inicio/apagado)
    4.  Haga doble clic para seleccionar **Startup (Inicio**) y, a continuación, seleccione **scripts de PowerShell**.
    5.  Seleccione **Mostrar archivos**y, a continuación, copie el archivo **install-MMAgent. PS1** a esa carpeta.
    6.  Seleccione **Agregar**y, a continuación, **examinar**.
    7.  Seleccione el script PS1 que acaba de copiar.

7.  :::no-loc text="Microsoft Teams Rooms":::los dispositivos deben instalar y configurar :::no-loc text="Microsoft Monitoring"::: el agente con el segundo reinicio.

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
> Puede consultar el artículo [administrar y mantener :::no-loc text="Log Analytics"::: el agente](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) cuando necesite volver a configurar un agente, moverlo a un área de trabajo diferente o modificar la configuración de proxy después de la instalación inicial.

## <a name="additional-solutions"></a>Soluciones adicionales
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor":::proporciona soluciones de administración integradas a través de la [Galería de soluciones](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) para ayudarle a supervisar su entorno. Le recomendamos encarecidamente que agregue también la [ :::no-loc text="Azure Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) administración de [alertas](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) y las soluciones de estado del agente a su área de trabajo.

> [!NOTE]
> La solución de estado del agente puede ayudarle a identificar :::no-loc text="Microsoft Monitoring"::: agentes anticuados o dañados en su entorno, y la solución de administración de alertas proporciona detalles sobre las alertas que se han producido en un período determinado.

## <a name="see-also"></a>Consulte también

[Administración :::no-loc text="Microsoft Teams Rooms"::: de planes con:::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Administrar :::no-loc text="Microsoft Teams Rooms"::: dispositivos con:::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
