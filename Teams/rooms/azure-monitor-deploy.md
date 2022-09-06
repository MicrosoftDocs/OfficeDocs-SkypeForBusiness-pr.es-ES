---
title: Implementar Salas de Microsoft Teams supervisión con Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: En este artículo se describe cómo implementar la supervisión de Salas de Microsoft Teams de forma integrada y de un extremo a otro con Azure Monitor.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5dbea45008024762f30d9555f4762c4377d2ed1f
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606419"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-monitoring-with-no-loc-textazure-monitor"></a>Implementar :::no-loc text="Microsoft Teams Rooms"::: supervisión con :::no-loc text="Azure Monitor":::

En este artículo se describe cómo configurar e implementar la supervisión integrada de un extremo a otro de :::no-loc text="Microsoft Teams Rooms"::: los dispositivos mediante :::no-loc text="Azure Monitor":::.

[!INCLUDE [teams-pro-license-requirement](../includes/teams-pro-license-requirement.md)]

Puedes configurar :::no-loc text="Log Analytics"::: dentro :::no-loc text="Azure Monitor"::: para proporcionar telemetría básica y alertas que te ayudarán a administrar :::no-loc text="Microsoft Teams Rooms":::. A medida que su solución de administración madura, puede decidir implementar capacidades de administración y datos adicionales para crear una vista más detallada de la disponibilidad y el rendimiento del dispositivo.

Siguiendo esta guía, puede usar un panel como el siguiente ejemplo para obtener informes detallados del estado de disponibilidad del dispositivo, el estado de la aplicación y el hardware, y :::no-loc text="Microsoft Teams Rooms"::: la distribución de la versión del sistema operativo y de las aplicaciones.

![Captura de pantalla de la vista análisis de registro de ejemplo para Salas de Microsoft Teams.](../media/Deploy-Azure-Monitor-1.png "Vista de análisis de registro de ejemplo para Salas de Microsoft Teams")

A un mayor nivel, debe realizar las siguientes tareas:


1. [Validar configuración :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurar dispositivos de prueba para la :::no-loc text="Log Analytics"::: configuración de administración](azure-monitor-deploy.md#configure_test_devices)
3. [Asignar campos personalizados](azure-monitor-deploy.md#Custom_fields)
4. [Definir las :::no-loc text="Microsoft Teams Rooms"::: vistas en :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Definir alertas](azure-monitor-deploy.md#Alerts)
6. [Configurar todos los dispositivos para la supervisión](azure-monitor-deploy.md#configure_all_devices)
7. [Configurar soluciones adicionales :::no-loc text="Azure Monitor":::](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Aunque con una configuración mínima, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: puede supervisar un equipo que ejecuta un :::no-loc text="Windows"::: sistema operativo, todavía hay algunos :::no-loc text="Microsoft Teams Rooms":::pasos específicos que debe seguir antes de empezar a implementar agentes en todos los :::no-loc text="Microsoft Teams Rooms"::: dispositivos.
> Por lo tanto, le recomendamos que realice todos los pasos de configuración en el orden correcto para una configuración y configuración controlada. La calidad del resultado final depende en gran parte de la calidad de la configuración inicial.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Validar configuración :::no-loc text="Log Analytics":::
<a name="validate_LogAnalytics"> </a>

Debe tener un :::no-loc text="Log Analytics"::: área de trabajo para empezar a recopilar registros de :::no-loc text="Microsoft Teams Rooms":::. Un área de trabajo es un entorno único :::no-loc text="Log Analytics"::: con su propio repositorio de datos, orígenes de datos y soluciones. Si ya tiene un área de trabajo existente :::no-loc text="Log Analytics"::: , puede usarla para supervisar la :::no-loc text="Microsoft Teams Rooms"::: implementación o, como alternativa, puede crear un área de trabajo dedicada :::no-loc text="Log Analytics"::: específica para sus :::no-loc text="Microsoft Teams Rooms"::: necesidades de supervisión.

Si necesitas crear un área de trabajo, :::no-loc text="Log Analytics"::: sigue las instrucciones del artículo [Crear un :::no-loc text="Log Analytics"::: área de trabajo en el :::no-loc text="Azure"::: portal](/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Para usar :::no-loc text="Log Analytics"::: con :::no-loc text="Azure Monitor":::, debes tener una suscripción activa :::no-loc text="Azure"::: . Si no tiene una :::no-loc text="Azure"::: suscripción, puede crear [una suscripción de prueba gratuita](https://azure.microsoft.com/free) como punto de partida.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Configurar :::no-loc text="Log Analytics"::: para recopilar :::no-loc text="Microsoft Teams Rooms"::: registros de eventos

:::no-loc text="Log Analytics"::: solo recopila eventos de los :::no-loc text="Windows"::: registros de eventos especificados en la configuración. Para cada registro, solo se recopilan los eventos con la gravedad seleccionada.

Debe configurar :::no-loc text="Log Analytics"::: para recopilar los registros necesarios para supervisar :::no-loc text="Microsoft Teams Rooms"::: el estado del dispositivo y la aplicación. :::no-loc text="Microsoft Teams Rooms"::: use el registro de **:::no-loc text="Skype Room System":::** eventos.

Para configurar :::no-loc text="Log Analytics"::: para recopilar los eventos, consulte [:::no-loc text="Windows"::: orígenes de datos del registro de eventos en :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/data-sources-windows-events) :::no-loc text="Microsoft Teams Rooms":::

![Captura de pantalla de la configuración del registro de eventos.](../media/Deploy-Azure-Monitor-2.png "Configuración del registro de eventos")

> [!IMPORTANT]
> Configure las :::no-loc text="Windows"::: opciones de registro de eventos, escriba **:::no-loc text="Skype Room System":::** como nombre del registro de eventos y, después, active las casillas **Error**, **Advertencia** e **Información** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurar dispositivos de prueba para Azure Monitoring
<a name="configure_test_devices"> </a>

Debe prepararse :::no-loc text="Log Analytics"::: para poder supervisar :::no-loc text="Microsoft Teams Rooms":::los eventos relacionados. Para empezar, debes implementar :::no-loc text="Microsoft Monitoring"::: agentes en uno o dos :::no-loc text="Microsoft Teams Rooms"::: dispositivos a los que tengas acceso físico y obtener esos dispositivos de prueba para generar algunos datos y enviarlos al :::no-loc text="Log Analytics"::: área de trabajo.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Instalar :::no-loc text="Microsoft Monitoring"::: agentes para probar dispositivos

Implementa el :::no-loc text="Microsoft Monitoring"::: agente en los dispositivos de prueba siguiendo las instrucciones proporcionadas en [Conectar :::no-loc text="Windows"::: equipos al :::no-loc text="Log Analytics"::: servicio en :::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows). Este artículo proporciona información detallada sobre los pasos para implementar :::no-loc text="Microsoft Monitoring"::: el agente para :::no-loc text="Windows":::, instrucciones para obtener el *:::no-loc text="Log Analytics"::: **Id**. de área de trabajo_ y la _ *_clave principal_** para conectar :::no-loc text="Microsoft Teams Rooms"::: los dispositivos a la :::no-loc text="Azure Monitor"::: implementación y pasos para comprobar la conectividad del agente a :::no-loc text="Log Analytics"::: la instancia.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Generar eventos de ejemplo :::no-loc text="Microsoft Teams Rooms":::

Después de implementar el :::no-loc text="Microsoft Monitoring"::: agente en los dispositivos de prueba, compruebe que los datos de registro de eventos requeridos los recopila :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Reinicie el dispositivo después de la instalación del :::no-loc text="Microsoft Monitoring"::: agente y asegúrese de que :::no-loc text="Microsoft Teams Rooms"::: se inicia la aplicación Meeting, para que pueda generar nuevos eventos en el registro de eventos.

1.  Inicia sesión en el [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) y ve a :::no-loc text="Log Analytics"::: y selecciona tu área de trabajo.

2.  Enumera los eventos de latido del corazón generados por un :::no-loc text="Microsoft Teams Rooms"::: dispositivo:
    1.  Seleccione el área de trabajo y vaya a **Registros** y use una consulta para recuperar los registros de latido del corazón que tendrán los campos personalizados para :::no-loc text="Microsoft Teams Rooms":::.
    2.  Consulta de ejemplo: `Event | where Source == "SRS-App" and EventID == 2000`

3.  Asegúrese de que la consulta devuelve registros de registro que incluyen eventos generados por la :::no-loc text="Microsoft Teams Rooms"::: aplicación reuniones.

4.  Genera un problema de hardware y valida que se hayan iniciado sesión los :::no-loc text="Azure Log Analytics":::eventos necesarios.
    1.  Desconecta uno de los dispositivos periféricos del sistema de prueba :::no-loc text="Microsoft Teams Rooms"::: . Puede ser la cámara, el altavoz, el micrófono o la pantalla de la sala frontal.
    2.  Espere 10 minutos hasta que el registro de eventos se rellene en :::no-loc text="Azure Log Analytics":::.
    3.  Use una consulta para enumerar eventos de error de hardware: `Event | where Source == "SRS-App" and EventID == 3001`

5.  Genere un problema de la aplicación y valide que se registren los eventos necesarios.
    1.  Modifica la :::no-loc text="Microsoft Teams Rooms"::: configuración de la cuenta y escribe un par incorrecto de Email/contraseña.
    2.  Espere 10 minutos hasta que el registro de eventos se rellene en :::no-loc text="Azure Log Analytics":::.
    3.  Use una consulta para enumerar los eventos de error de la aplicación: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Estos registros de eventos de ejemplo son necesarios antes de que se puedan configurar campos personalizados. No continúe con el paso siguiente hasta que haya recopilado los registros de eventos necesarios.

## <a name="map-custom-fields"></a>Asignar campos personalizados
<a name="Custom_fields"> </a>

Los campos personalizados se usan para extraer datos específicos de los registros de eventos. Debe definir campos personalizados que se usarán más adelante con los mosaicos, las vistas de panel y las alertas. Vea [Campos :::no-loc text="Log Analytics":::personalizados](/azure/azure-monitor/platform/custom-fields) y familiarícese con los conceptos antes de empezar a crear los campos personalizados.

Para extraer los campos personalizados de los registros de eventos capturados, siga estos pasos:

1.  Inicia sesión en el [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) y ve a :::no-loc text="Log Analytics"::: y selecciona tu área de trabajo.

2. Enumera los eventos generados por un :::no-loc text="Microsoft Teams Rooms"::: dispositivo:
   1.  Vaya a **Registros** y use una consulta para recuperar los registros que tendrán el campo personalizado.
   2.  Consulta de ejemplo: `Event | where Source == "SRS-App" and EventID == 2000`

3. Seleccione uno de los registros, seleccione el botón de la izquierda e inicie el asistente para extracción de campos.
4. Resalte los datos que desea extraer de renderedDescription y proporcione un Título de campo. Los nombres de campo que debe usar se proporcionan en la Tabla 1.
5. Use las asignaciones que se muestran en *la Tabla 1*. :::no-loc text="Log Analytics"::: añadirá automáticamente la **\_cadena CF** cuando defina el nuevo campo.

> [!IMPORTANT]
> Recuerde que todos los JSON y :::no-loc text="Log Analytics"::: los campos distinguen mayúsculas de minúsculas.
> 
> Preste atención a las consultas necesarias para cada campo personalizado de la tabla siguiente. Debe usar las consultas correctas para :::no-loc text="Log Analytics"::: extraer correctamente los valores de campo personalizados.
> 
**Tabla 1**

| **Campo JSON**                   | **:::no-loc text="Log Analytics"::: campo personalizado** | **Nivel del** | **Consulta para usar con la extracción**                   |
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
| Estado del orador de conferencia        | SRSConfSpeakerStatus        | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |
| Estado predeterminado del altavoz           | SRSDefaultSpeakerStatus     | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |
| Estado de la cámara                    | SRSCameraStatus             | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |
| Estado de la pantalla frontal de la sala     | SRSFORDStatus               | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |
| Estado del sensor de movimiento             | SRSMotionSensorStatus       | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |
| Estado de entrada de HDMI               | SRSHDMIIngestStatus         | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Definir las :::no-loc text="Microsoft Teams Rooms"::: vistas en :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Después de recopilar datos y asignar campos personalizados, puede usar el Diseñador de vistas para desarrollar un panel que contenga varios mosaicos para supervisar :::no-loc text="Microsoft Teams Rooms"::: eventos. Use Diseñador de vistas para crear los siguientes iconos. Para obtener más información, vea [Crear vistas personalizadas con el Diseñador de vistas en :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Los pasos anteriores de esta guía deberían haberse completado para que los mosaicos de panel funcionaran correctamente.
>
> [!IMPORTANT]
> [View Designer en Azure Monitor se retirará el 31 de agosto de 2023](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) y las funcionalidades de creación y clonación se deshabilitarán el 30 de noviembre de 2020. Los libros se pueden usar en su lugar. Para obtener más información sobre la guía de transición del diseñador de vistas a los libros, vea [Inicio rápido con plantillas de diseñador de vistas predefinidas](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates).

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Crear manualmente un panel de Salas de Microsoft Teams

Como alternativa, puede crear su propio panel y agregar solo los iconos que desea supervisar.

#### <a name="configure-the-overview-tile"></a>Configurar el icono De información general

1.  Abra **el Diseñador de vistas**.
2.  Seleccione **Mosaico de información general** y, después, seleccione **Dos números** en la galería.
3.  Asigne un nombre al icono **:::no-loc text="Microsoft Teams Rooms":::**.
4.  Definir el **primer mosaico**:<br>
    **Leyenda:** Dispositivos que enviaron un latido del corazón al menos una vez en el último mes<br>
    **Consulta:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Definir el **segundo mosaico**:<br>
    **Leyenda:** Dispositivos activos que enviaron un latido del corazón en la última hora<br>
    **Consulta:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Seleccione **Aplicar**.

### <a name="create-a-tile-that-displays-active-devices"></a>Crear un icono que muestre los dispositivos activos

1.  Seleccione **Ver panel** para empezar a agregar los iconos.
2.  Seleccione **Número & lista** de la galería
3.  Defina las propiedades **General** :<br>
    **Título del grupo:** Estado del latido del corazón<br>
    **Nuevo grupo:** Seleccionado
4.  Defina las propiedades **de Mosaico** :<br>
    **Leyenda:** Dispositivos activos (latido del corazón enviado en los últimos 20 minutos)<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definir las propiedades **de lista** :<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definir **títulos de columna**:<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último latido
7.  Definir **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar** y, después, **Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Crear un icono que muestre los dispositivos que tienen problemas de conectividad

1.  Seleccione **Número & lista** de la galería y, a continuación, agregue un nuevo icono.
2.  Defina las propiedades **General** :<br>
    **Título del grupo:** Dejar vacío<br>
    **Nuevo grupo:** No seleccionado
3.  Defina las propiedades **de Mosaico** :<br>
    **Leyenda:** Dispositivos inactivos (ningún mensaje de latido del corazón enviado en los últimos 20 minutos)<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definir las propiedades **de lista** :<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definir **títulos de columna**:<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último latido
6.  Definir **consulta de navegación**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Seleccione **Aplicar** y, después, **Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Crear un icono que muestre los dispositivos que tienen un error de hardware

1.  Seleccione **Número & lista** de la galería y, a continuación, agregue un nuevo icono.
2.  Defina las propiedades **General** :<br>
    **Título del grupo:** Estado del hardware<br>
    **Nuevo grupo:** Seleccionado
3.  Defina las propiedades **de Mosaico** :<br>
    **Leyenda:** Dispositivos que experimentaron un error de hardware en la última hora<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definir las propiedades **de lista** :<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **títulos de columna**:<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último error
6.  Definir **consulta de navegación**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Seleccione **Aplicar** y, después, **Cerrar**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Crear un icono que muestre :::no-loc text="Microsoft Teams Rooms"::: las versiones del sistema operativo

1.  Selecciona **Anillo & lista** en la galería y, a continuación, agrega un nuevo icono.
2.  Defina las propiedades **General** :<br>
    **Título del grupo:** Detalles del sistema operativo<br>
    **Nuevo grupo:** Seleccionado
3.  Definir las propiedades **de encabezado** :<br>
    **Título:** Versiones del sistema operativo<br>
    **Subtítulo:** Dispositivos que ejecutan versiones específicas del sistema operativo
4.  Definir las propiedades **de la anillo** :<br>
    **Consulta:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Centrar texto:** Dispositivos<br>
    **Operación:** Suma
5.  Defina las propiedades **List** .<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar gráfico:** Seleccionado<br>
    **Habilitar minigráficos:** No seleccionado
6.  Definir **títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Dejar vacío
7.  Definir **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar** y, después **, Cerrar**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Crear un icono que muestre :::no-loc text="Microsoft Teams Rooms"::: las versiones de la aplicación

1.  Selecciona **Anillo & lista** en la galería y, a continuación, agrega un nuevo icono.
2.  Defina las propiedades **General** :<br>
    **Título del grupo:** :::no-loc text="Microsoft Teams Rooms"::: detalles de la aplicación<br>
    **Nuevo grupo:** Seleccionado
3.  Definir las propiedades **de encabezado** :<br>
    **Título:** Versiones de la aplicación<br>
    **Subtítulo:** Dispositivos que ejecutan versiones de aplicaciones específicas
4.  Definir las propiedades **de la anillo** :<br>
    **Consulta:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Centrar texto:** Dispositivos<br>
    **Operación:** Suma
5.  Defina las propiedades **List** .<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar gráfico:** Seleccionado<br>
    **Habilitar minigráficos:** No seleccionado
6.  Definir **títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Dejar vacío
7.  Definir **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar** y, después **, Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Crear un icono que muestre los dispositivos que tienen un error de aplicación

1.  Seleccione **Número & lista** de la galería y, a continuación, agregue un nuevo icono.
2.  Defina las propiedades **General** .<br>
    **Título del grupo:** Dejar vacío<br>
    **Nuevo grupo:** No seleccionado
3.  Defina las propiedades **Mosaico** .<br>
    **Leyenda:** Dispositivos que experimentaron un error de aplicación en la última hora<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina las propiedades **List** .<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último error
6.  Definir **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Seleccione **Aplicar** y, después **, Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Crear un icono que muestre los dispositivos que se han reiniciado

1.  Seleccione **Número & lista** de la galería y, a continuación, agregue un nuevo icono.
2.  Defina las propiedades **General** .<br>
    **Título del grupo:** Dejar vacío<br>
    **Nuevo grupo:** No seleccionado
3.  Defina las propiedades **Mosaico** .<br>
    **Leyenda:** Dispositivos en los que se ha reiniciado la aplicación en las últimas 24 horas y número de reinicios<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina las propiedades **List** .<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definir **títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Número de reinicios
6.  Definir **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Seleccione **Aplicar** y, después **, Cerrar**.
8.  Seleccione **Guardar** para guardar el panel.

Ahora ya ha terminado de crear las vistas.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Configurar alertas en :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: puede generar alertas para notificar a los administradores, cuando una :::no-loc text="Microsoft Teams Rooms"::: consola se encuentra con un problema.

:::no-loc text="Azure Monitor"::: incluye un mecanismo de alerta integrado que se ejecuta a través de búsquedas de registro programadas a intervalos regulares. Si los resultados de la búsqueda del registro coinciden con algunos criterios concretos, se crea un registro de alerta.

A continuación, la regla puede ejecutar automáticamente una o más acciones para notificarle de forma proactiva la alerta o invocar otro proceso. Las posibles opciones con alertas son:
-   Enviar un correo electrónico
-   Invocar un proceso externo a través de una solicitud HTTP POST
-   Iniciar un runbook en :::no-loc text="Azure Automation"::: el servicio

Consulte [Iniciar sesión de alertas :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log) para obtener más información sobre las alertas en :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Los ejemplos siguientes envían alertas por correo electrónico cuando un :::no-loc text="Microsoft Teams Rooms"::: dispositivo genera un error de hardware o de aplicación.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Configurar una alerta de correo electrónico para :::no-loc text="Microsoft Teams Rooms"::: problemas de hardware

Configura una regla de alerta que compruebe si :::no-loc text="Microsoft Teams Rooms"::: hay dispositivos que han detectado problemas de hardware en la última hora.
1.  Inicia sesión en el [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) y ve a :::no-loc text="Log Analytics"::: y selecciona tu área de trabajo.

2. Vaya al :::no-loc text="Log Analytics"::: área de trabajo y seleccione **Alertas** y, a continuación **, seleccione Nueva regla de alerta**

3. Seleccione **Agregar condición** y, después, **Búsqueda de registros personalizada**

4.  Escriba la siguiente consulta en el cuadro de texto Buscar consulta.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configurar la configuración lógica de alertas:<br>
    **Basado en:** Número de resultados<br>
    **Condición:** Mayor que<br>
    **Umbral:** 0<br>

6. Configure las opciones de Evaluación y seleccione **Listo**: <br>
    **Período (en minutos):** 60<br>
    **Frecuencia (en minutos):** 60<br>

7. Configurar grupos de acciones:
    1.  Seleccione **Crear nuevo**
    2.  Proporcione nombres adecuados para los campos *Nombre del grupo* de acciones y *Nombre corto* .
    3.  Especifique un *nombre de acción* único y seleccione **Email/SMS/Push/Voice** y, a continuación, seleccione **Editar detalles**.
    4.  Seleccione la casilla **Email** y proporcione la dirección de correo electrónico de la persona o el grupo que recibirá las alertas.
    5.  También puede proporcionar su número de teléfono para recibir una notificación con SMS, una llamada de voz o ambos.
    6. Seleccione **Aceptar**.

8. **Personalice Acciones** si desea reemplazar la línea de asunto de los correos electrónicos de alerta.

9. Especifique un nombre de regla y una descripción.<br>
    **Nombre de regla:** :::no-loc text="Microsoft Teams Rooms"::: Alerta de error de hardware<br>
    **Descripción:** Lista de dispositivos que han detectado un problema de hardware en la última hora<br>

10. Seleccione la gravedad deseada y asegúrese de que la regla está habilitada.

11. Seleccione **Crear regla de alerta**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Configurar una alerta de correo electrónico para :::no-loc text="Microsoft Teams Rooms"::: los problemas de la aplicación

Repita el mismo procedimiento, pero use la consulta siguiente para enumerar los dispositivos que han detectado problemas de aplicación en la última hora.

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

Ahora ha completado la definición de alertas. Puede definir alertas adicionales usando los ejemplos anteriores.

Cuando se genera una alerta, recibirás un correo electrónico que enumera los dispositivos que se encontraron con un problema en la última hora.

! [Ejemplo de correo electrónico de :::no-loc text="Azure Monitor"::: alerta](.. /media/Deploy-Azure-Monitor-6.png "Correo electrónico de alerta de ejemplo :::no-loc text="Azure Monitor"::: ")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Configurar todos los dispositivos para :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a> Una vez configurados los paneles y las alertas, puede configurar el :::no-loc text="Microsoft Monitoring"::: agente en todos los :::no-loc text="Microsoft Teams Rooms"::: dispositivos para completar la implementación de supervisión.

Aunque puede instalar y configurar el :::no-loc text="Microsoft Monitoring"::: agente manualmente en cada dispositivo, le recomendamos encarecidamente que aproveche los métodos y las herramientas de implementación de software existentes.

Si estás creando tus :::no-loc text="Microsoft Teams Rooms"::: dispositivos por primera vez, es posible que quieras incluir los pasos de configuración y configuración del :::no-loc text="Microsoft Monitoring"::: agente como parte del proceso de compilación. Para obtener más información, consulte [Instalar el agente con la línea de comandos](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>:::no-loc text="Microsoft Monitoring"::: Implementar agente mediante un objeto de directiva de grupo (GPO)

Si ya ha implementado los :::no-loc text="Microsoft Teams Rooms"::: dispositivos antes de implementar :::no-loc text="Azure Monitoring":::, puede usar el script proporcionado para configurar y configurar los agentes mediante :::no-loc text="Active Directory"::: objetos de directiva de grupo.

1.  Cree una ruta de acceso de red compartida y conceda acceso de lectura al grupo **Equipos de dominio** .

2.  Descarga la versión de 64 bits del :::no-loc text="Microsoft Monitoring"::: agente para :::no-loc text="Windows"::: desde <https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrae el contenido del paquete de instalación en el recurso compartido de red.
    1.  Abre una ventana del símbolo del sistema y ejecuta **MMASetup-AMD64.exe /c**
    2.  Especifique el recurso compartido que acaba de crear y extraiga el contenido.

4.  Cree un nuevo directiva de grupo Objeto y asígnelo a la unidad organizativa donde :::no-loc text="Microsoft Teams Rooms"::: se encuentran las cuentas de máquina.

5.  Configurar la directiva de ejecución de PowerShell:
    1.  Edite el objeto directiva de grupo recién creado y vaya a Componentes de plantillas :::no-loc text="Windows"::: \\ administrativas de directivas \\ \\ de configuración \\ del equipo :::no-loc text="Windows PowerShell":::
    2.  Habilite **activar ejecución de script** y establezca la **directiva de ejecución** para **Permitir scripts locales**.

6.  Configure el script de inicio:
    1.  Copie el script siguiente y guárdelo como Install-MMAgent.ps1.
    2.  Modifique los parámetros WorkspaceId, WorkspaceKey y SetupPath para que coincidan con la configuración.
    3.  Edita el mismo objeto directiva de grupo y ve a Scripts de configuración \\ de directivas :::no-loc text="Windows"::: \\ de configuración \\ del equipo (inicio o apagado)
    4.  Haga doble clic para seleccionar **Inicio** y, a continuación, seleccione **Scripts de PowerShell**.
    5.  Selecciona **Mostrar archivos** y, a continuación, copia el archivo **Install-MMAgent.ps1** a esa carpeta.
    6.  Selecciona **Agregar** y, a continuación **, Examinar**.
    7.  Seleccione el script ps1 que acaba de copiar.

7.  :::no-loc text="Microsoft Teams Rooms"::: debería instalar y configurar el :::no-loc text="Microsoft Monitoring"::: agente con el segundo reinicio.

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
> Puede consultar el artículo [Administrar y mantener el :::no-loc text="Log Analytics"::: agente](/azure/azure-monitor/platform/agent-manage) cuando necesite volver a configurar un agente, moverlo a un área de trabajo diferente o modificar la configuración de proxy después de la instalación inicial.

## <a name="additional-solutions"></a>Soluciones adicionales
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: proporciona soluciones de administración integradas a través de su [galería de soluciones](/azure/azure-monitor/insights/solutions) para ayudarle a supervisar aún más su entorno. Le recomendamos encarecidamente que agregue soluciones de [Administración de alertas](/azure/azure-monitor/platform/alert-management-solution) y [:::no-loc text="Azure Log Analytics"::: Estado del agente](/azure/azure-monitor/insights/solution-agenthealth) a su área de trabajo.

> [!NOTE]
> La solución Agent Health puede ayudarle a identificar agentes obsoletos o rotos :::no-loc text="Microsoft Monitoring"::: en su entorno y la solución Administración de alertas proporciona detalles sobre las alertas que se han generado en un período determinado.

## <a name="see-also"></a>Vea también

[Administración de :::no-loc text="Microsoft Teams Rooms"::: planes con :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Administrar :::no-loc text="Microsoft Teams Rooms"::: dispositivos con :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
