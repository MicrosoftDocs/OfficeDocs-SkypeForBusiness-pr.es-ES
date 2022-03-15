---
title: Implementar Salas de Microsoft Teams supervisión con Azure Monitor
ms.author: czawideh
author: cazawideh
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
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: En este artículo se describe cómo implementar la supervisión de Salas de Microsoft Teams de forma integrada y de un extremo a otro con Azure Monitor.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b991465bfff8f67fdbd3bdc9c03eba485690d5fb
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503877"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-monitoring-with-no-loc-textazure-monitor"></a>Implementar :::no-loc text="Microsoft Teams Rooms"::: supervisión con :::no-loc text="Azure Monitor":::

En este artículo se explica cómo configurar e implementar la supervisión integrada de :::no-loc text="Microsoft Teams Rooms"::: un extremo a otro de los dispositivos mediante :::no-loc text="Azure Monitor":::.

Puede configurar dentro para :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: proporcionar telemetría básica y alertas que le ayudarán a administrar :::no-loc text="Microsoft Teams Rooms":::. A medida que la solución de administración va madurando, es posible que decida implementar capacidades de administración y datos adicionales para crear una vista más detallada de la disponibilidad y el rendimiento de los dispositivos.

Siguiendo esta guía, puede usar un panel como el siguiente ejemplo para obtener informes de estado detallados sobre la disponibilidad del dispositivo, el estado de las aplicaciones y el hardware, :::no-loc text="Microsoft Teams Rooms"::: y la distribución de versiones de aplicaciones y sistemas operativos.

![Captura de pantalla de la vista de log analytics de ejemplo para Salas de Microsoft Teams.](../media/Deploy-Azure-Monitor-1.png "Vista Análisis de registro de ejemplo para Salas de Microsoft Teams")

A un mayor nivel, debe realizar las siguientes tareas:


1. [Validar la :::no-loc text="Log Analytics"::: configuración](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurar dispositivos de prueba para la :::no-loc text="Log Analytics"::: configuración de administración](azure-monitor-deploy.md#configure_test_devices)
3. [Asignar campos personalizados](azure-monitor-deploy.md#Custom_fields)
4. [Definir las vistas :::no-loc text="Microsoft Teams Rooms"::: en :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Definir alertas](azure-monitor-deploy.md#Alerts)
6. [Configurar todos los dispositivos para la supervisión](azure-monitor-deploy.md#configure_all_devices)
7. [Configurar soluciones :::no-loc text="Azure Monitor"::: adicionales](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Aunque con una configuración mínima, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: puede supervisar un equipo que ejecuta un sistema operativo, :::no-loc text="Microsoft Teams Rooms":::todavía hay algunos pasos específicos que debe seguir antes de empezar a :::no-loc text="Windows"::: implementar agentes en todos los :::no-loc text="Microsoft Teams Rooms"::: dispositivos.
> Por lo tanto, le recomendamos que realice todos los pasos de configuración en el orden correcto para una configuración y configuración controladas. La calidad del resultado final depende en gran medida de la calidad de la configuración inicial.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Validar la :::no-loc text="Log Analytics"::: configuración
<a name="validate_LogAnalytics"> </a>

Necesita tener un área de trabajo para empezar a :::no-loc text="Log Analytics"::: recopilar registros desde :::no-loc text="Microsoft Teams Rooms":::. Un área de trabajo es un entorno :::no-loc text="Log Analytics"::: único con su propio repositorio de datos, orígenes de datos y soluciones. Si ya tiene un área de :::no-loc text="Log Analytics"::: trabajo existente, :::no-loc text="Microsoft Teams Rooms"::: puede usarla para supervisar la implementación o, como alternativa, puede crear un área de trabajo dedicada específica para :::no-loc text="Log Analytics"::: sus necesidades :::no-loc text="Microsoft Teams Rooms"::: de supervisión.

Si necesita crear un área de :::no-loc text="Log Analytics"::: trabajo, siga las instrucciones del artículo [Crear un :::no-loc text="Log Analytics"::: área de trabajo en el :::no-loc text="Azure"::: portal](/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Para usar :::no-loc text="Log Analytics"::: con :::no-loc text="Azure Monitor":::, necesita tener una suscripción :::no-loc text="Azure"::: activa. Si no tiene una suscripción :::no-loc text="Azure"::: , puede crear una [suscripción de prueba gratuita](https://azure.microsoft.com/free) como punto de partida.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Configurar :::no-loc text="Log Analytics"::: para recopilar registros :::no-loc text="Microsoft Teams Rooms"::: de eventos

:::no-loc text="Log Analytics"::: solo recopila eventos de los registros :::no-loc text="Windows"::: de eventos especificados en la configuración. Para cada registro, solo se recopilan los eventos con las gravedades seleccionadas.

Debe configurar para recopilar :::no-loc text="Log Analytics"::: los registros necesarios para supervisar el estado :::no-loc text="Microsoft Teams Rooms"::: del dispositivo y la aplicación. :::no-loc text="Microsoft Teams Rooms"::: usar el registro **:::no-loc text="Skype Room System":::** de eventos.

Para configurar para :::no-loc text="Log Analytics"::: recopilar los eventos:::no-loc text="Microsoft Teams Rooms":::, vea [orígenes:::no-loc text="Windows"::: de datos de registro de eventos en :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/data-sources-windows-events)

![Captura de pantalla de la configuración del registro de eventos.](../media/Deploy-Azure-Monitor-2.png "Configuración del registro de eventos")

> [!IMPORTANT]
> Configure :::no-loc text="Windows"::: la configuración del registro de eventos, escriba **:::no-loc text="Skype Room System":::** como nombre del registro de eventos y, a continuación, active las casillas **Error**, **Advertencia** **e Información** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurar dispositivos de prueba para Azure Monitoring
<a name="configure_test_devices"> </a>

Debe prepararse para :::no-loc text="Log Analytics"::: poder supervisar :::no-loc text="Microsoft Teams Rooms":::eventos relacionados. Para empezar, :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: necesita implementar agentes en uno o dos dispositivos a los que tenga acceso físico y :::no-loc text="Log Analytics"::: conseguir que esos dispositivos de prueba generen algunos datos y los empujen al área de trabajo.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Instalar agentes :::no-loc text="Microsoft Monitoring"::: para probar dispositivos

Implemente el :::no-loc text="Microsoft Monitoring"::: agente en los dispositivos de prueba mediante las instrucciones proporcionadas [en Conectar :::no-loc text="Windows"::: equipos en el :::no-loc text="Log Analytics"::: servicio en :::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows). En este artículo se proporciona información detallada sobre los pasos para implementar el Agente para , :::no-loc text="Log Analytics"::: * instrucciones para obtener el **Id. del** área de trabajo y la clave _ *_primary_** :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: para conectar dispositivos a la implementación y :::no-loc text="Log Analytics"::: los pasos para comprobar la conectividad del agente a la instancia.:::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows":::

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Generar eventos de :::no-loc text="Microsoft Teams Rooms"::: ejemplo

Después de implementar :::no-loc text="Microsoft Monitoring"::: el agente en los dispositivos de prueba, compruebe que los datos de registro de eventos necesarios se recopilan por :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Reinicie el dispositivo después de la :::no-loc text="Microsoft Monitoring"::: instalación del agente :::no-loc text="Microsoft Teams Rooms"::: y asegúrese de que la aplicación Reunión está iniciada, de modo que pueda generar nuevos eventos en el registro de eventos.

1.  Inicie sesión en el [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) y vaya a y :::no-loc text="Log Analytics"::: seleccione su área de trabajo.

2.  Enumerar los eventos de latido generados por un :::no-loc text="Microsoft Teams Rooms"::: dispositivo:
    1.  Seleccione el área de trabajo y vaya a **Registros** y use una consulta para recuperar los registros de latidos que tendrán los campos personalizados para :::no-loc text="Microsoft Teams Rooms":::.
    2.  Consulta de ejemplo: `Event | where Source == "SRS-App" and EventID == 2000`

3.  Asegúrese de que la consulta devuelve registros de registro que incluyen eventos generados por la :::no-loc text="Microsoft Teams Rooms"::: aplicación reuniones.

4.  Genere un problema de hardware y valide que los eventos necesarios hayan iniciado sesión :::no-loc text="Azure Log Analytics":::.
    1.  Desenchufe uno de los dispositivos periféricos del sistema de :::no-loc text="Microsoft Teams Rooms"::: prueba. Esto podría ser la cámara, el altavoz, el micrófono o la pantalla de la sala frontal
    2.  Espere 10 minutos hasta que el registro de eventos se rellene en :::no-loc text="Azure Log Analytics":::.
    3.  Use una consulta para enumerar eventos de error de hardware: `Event | where Source == "SRS-App" and EventID == 3001`

5.  Genere un problema de aplicación y valide que se registran los eventos necesarios.
    1.  Modifique la :::no-loc text="Microsoft Teams Rooms"::: configuración de la cuenta y escriba un par de correo electrónico y contraseña incorrectos.
    2.  Espere 10 minutos hasta que el registro de eventos se rellene en :::no-loc text="Azure Log Analytics":::.
    3.  Use una consulta para enumerar los eventos de error de la aplicación: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Estos registros de eventos de ejemplo son necesarios antes de que se puedan configurar campos personalizados. No continúe con el paso siguiente hasta que haya recopilado los registros de eventos necesarios.

## <a name="map-custom-fields"></a>Asignar campos personalizados
<a name="Custom_fields"> </a>

Use campos personalizados para extraer datos específicos de los registros de eventos. Debe definir campos personalizados que se usarán más adelante con los mosaicos, las vistas del panel y las alertas. Vea [Campos personalizados en :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) y familiarícese con los conceptos antes de empezar a crear los campos personalizados.

Para extraer los campos personalizados de los registros de eventos capturados, siga estos pasos:

1.  Inicie sesión en el [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) y vaya a y :::no-loc text="Log Analytics"::: seleccione su área de trabajo.

2. Enumerar los eventos generados por un :::no-loc text="Microsoft Teams Rooms"::: dispositivo:
   1.  Vaya a **Registros** y use una consulta para recuperar los registros que tendrán el campo personalizado.
   2.  Consulta de ejemplo: `Event | where Source == "SRS-App" and EventID == 2000`

3. Seleccione uno de los registros, seleccione el botón de la izquierda e inicie el asistente de extracción de campos.
4. Resalte los datos que desea extraer de la RenderedDescription y proporcione un título de campo. Los nombres de campo que debe usar se proporcionan en la Tabla 1.
5. Use las asignaciones que se muestran en *la Tabla 1*. :::no-loc text="Log Analytics":::anexará automáticamente la **cadena\_ CF** al definir el nuevo campo.

> [!IMPORTANT]
> Recuerde que todos los campos y :::no-loc text="Log Analytics"::: JSON distinguen entre mayúsculas y minúsculas.
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
| Estado de pantalla frontal del salón     | SRSFORDStatus               | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |
| Estado del sensor de movimiento             | SRSMotionSensorStatus       | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |
| Estado de ingestión de HDMI               | SRSHDMIIngestStatus         | **3001**     | Evento \| donde Source == "SRS-App" y EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Definir las vistas :::no-loc text="Microsoft Teams Rooms"::: en :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Después de recopilar datos y asignar campos personalizados, puede usar el Diseñador de vistas para desarrollar un panel que contenga varios mosaicos para supervisar eventos :::no-loc text="Microsoft Teams Rooms"::: . Use Diseñador de vistas para crear los siguientes iconos. Para obtener más información, vea [Crear vistas personalizadas con el Diseñador de vistas en :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Los pasos anteriores de esta guía deberían haber sido completados para que los mosaicos del panel funcionen correctamente.
>
> [!IMPORTANT]
> [View Designer en Azure Monitor](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) se retirará el 31 de agosto de 2023 y las funciones de creación y clonación se deshabilitaron el 30 de noviembre de 2020. Los libros se pueden usar en su lugar. Para obtener más información sobre la guía de transición del diseñador de vistas a los libros, vea [Inicio rápido con plantillas de diseñador de vistas predefinidas](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates).

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Crear manualmente Salas de Microsoft Teams panel

Como alternativa, puede crear su propio panel y agregar solo los mosaicos que desee supervisar.

#### <a name="configure-the-overview-tile"></a>Configurar el icono Información general

1.  Abra **el Diseñador de vistas**.
2.  Seleccione **Mosaico Información general** y, a continuación, **seleccione Dos números** de la galería.
3.  Asigne un nombre al icono **:::no-loc text="Microsoft Teams Rooms":::**.
4.  Definir el **primer icono**:<br>
    **Leyenda:** Dispositivos que enviaron un pulso al menos una vez en el último mes<br>
    **Consulta:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Definir el **segundo mosaico**:<br>
    **Leyenda:** Dispositivos activos que enviaron un pulso en la última hora<br>
    **Consulta:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Seleccione **Aplicar**.

### <a name="create-a-tile-that-displays-active-devices"></a>Crear un icono que muestre dispositivos activos

1.  Seleccione **Ver panel** para empezar a agregar los mosaicos.
2.  Seleccione **Número & lista de la** galería
3.  Definir las **propiedades generales** :<br>
    **Título del grupo:** Estado del latido del corazón<br>
    **Nuevo grupo:** Seleccionado
4.  Definir las **propiedades de** mosaico:<br>
    **Leyenda:** Dispositivos activos (pulso enviado en los últimos 20 minutos)<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definir las **propiedades de** la lista:<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definir **títulos de columna**:<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Last Heartbeat
7.  Definir **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar** y, a continuación **, Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Crear un icono que muestre dispositivos con problemas de conectividad

1.  Seleccione **Número & lista** de la galería y, a continuación, agregue un nuevo icono.
2.  Definir las **propiedades generales** :<br>
    **Título del grupo:** Dejar vacío<br>
    **Nuevo grupo:** No seleccionado
3.  Definir las **propiedades de** mosaico:<br>
    **Leyenda:** Dispositivos inactivos (sin mensaje de latido enviado en los últimos 20 minutos)<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definir las **propiedades de** la lista:<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definir **títulos de columna**:<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Last Heartbeat
6.  Definir **consulta de navegación**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Seleccione **Aplicar** y, a continuación **, Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Crear un icono que muestre los dispositivos que tienen un error de hardware

1.  Seleccione **Número & lista** de la galería y, a continuación, agregue un nuevo icono.
2.  Definir las **propiedades generales** :<br>
    **Título del grupo:** Estado del hardware<br>
    **Nuevo grupo:** Seleccionado
3.  Definir las **propiedades de** mosaico:<br>
    **Leyenda:** Dispositivos que experimentaron un error de hardware en la última hora<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definir las **propiedades de** la lista:<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **títulos de columna**:<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último error
6.  Definir **consulta de navegación**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Seleccione **Aplicar** y, a continuación **, Cerrar**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Crear un icono que muestre las versiones :::no-loc text="Microsoft Teams Rooms"::: del sistema operativo

1.  Seleccione **Donut & lista de** la galería y, a continuación, agregue un nuevo icono.
2.  Definir las **propiedades generales** :<br>
    **Título del grupo:** Detalles del sistema operativo<br>
    **Nuevo grupo:** Seleccionado
3.  Definir las **propiedades de encabezado** :<br>
    **Título:** Versiones del sistema operativo<br>
    **Subtítulo:** Dispositivos que ejecutan versiones específicas del sistema operativo
4.  Definir las **propiedades de la dona** :<br>
    **Consulta:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Centrar texto:** Dispositivos<br>
    **Operación:** Suma
5.  Definir las **propiedades de** lista.<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar Graph:** Seleccionado<br>
    **Habilitar minigráficos:** No seleccionado
6.  Definir **títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Dejar vacío
7.  Definir **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar** y, a continuación **, Cerrar**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Crear un icono que muestre las versiones :::no-loc text="Microsoft Teams Rooms"::: de la aplicación

1.  Seleccione **Donut & lista de** la galería y, a continuación, agregue un nuevo icono.
2.  Definir las **propiedades generales** :<br>
    **Título del grupo:** :::no-loc text="Microsoft Teams Rooms"::: detalles de la aplicación<br>
    **Nuevo grupo:** Seleccionado
3.  Definir las **propiedades de encabezado** :<br>
    **Título:** Versiones de la aplicación<br>
    **Subtítulo:** Dispositivos que ejecutan versiones de aplicaciones específicas
4.  Definir las **propiedades de la dona** :<br>
    **Consulta:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Centrar texto:** Dispositivos<br>
    **Operación:** Suma
5.  Definir las **propiedades de** lista.<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar Graph:** Seleccionado<br>
    **Habilitar minigráficos:** No seleccionado
6.  Definir **títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Dejar vacío
7.  Definir **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar** y, a continuación **, Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Crear un icono que muestre los dispositivos que tienen un error de aplicación

1.  Seleccione **Número & lista** de la galería y, a continuación, agregue un nuevo icono.
2.  Defina las **propiedades Generales** .<br>
    **Título del grupo:** Dejar vacío<br>
    **Nuevo grupo:** No seleccionado
3.  Defina las **propiedades de** mosaico.<br>
    **Leyenda:** Dispositivos que experimentaron un error de aplicación en la última hora<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definir las **propiedades de** lista.<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último error
6.  Definir **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Seleccione **Aplicar** y, a continuación **, Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Crear un icono que muestre los dispositivos que se han reiniciado

1.  Seleccione **Número & lista** de la galería y, a continuación, agregue un nuevo icono.
2.  Defina las **propiedades Generales** .<br>
    **Título del grupo:** Dejar vacío<br>
    **Nuevo grupo:** No seleccionado
3.  Defina las **propiedades de** mosaico.<br>
    **Leyenda:** Dispositivos en los que se ha reiniciado la aplicación en las últimas 24 horas y el número de reinicios<br>
    **Consulta de icono:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Definir las **propiedades de** lista.<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definir **títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Número de reinicios
6.  Definir **consulta de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Seleccione **Aplicar** y, a continuación **, Cerrar**.
8.  Seleccione **Guardar** para guardar el panel.

Ahora ha completado la creación de las vistas.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Configurar alertas en :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: puede generar alertas para notificar a los administradores cuando una :::no-loc text="Microsoft Teams Rooms"::: consola encuentra un problema.

:::no-loc text="Azure Monitor"::: incluye un mecanismo de alerta integrado que se ejecuta a través de búsquedas de registro programadas a intervalos regulares. Si los resultados de la búsqueda de registro coinciden con algunos criterios específicos, se crea un registro de alertas.

A continuación, la regla puede ejecutar automáticamente una o varias acciones para notificarle proactivamente de la alerta o invocar otro proceso. Las posibles opciones con alertas son:
-   Enviar un correo electrónico
-   Invocar un proceso externo a través de una solicitud HTTP POST
-   Iniciar un runbook en el :::no-loc text="Azure Automation"::: servicio

Vea [Iniciar sesión en alertas :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log) para obtener más información sobre las alertas en :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Los ejemplos siguientes envían alertas de correo electrónico cuando :::no-loc text="Microsoft Teams Rooms"::: un dispositivo genera un hardware o un error de aplicación.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Configurar una alerta de correo electrónico para problemas :::no-loc text="Microsoft Teams Rooms"::: de hardware

Configure una regla de alerta que comprueba si :::no-loc text="Microsoft Teams Rooms"::: hay dispositivos que han encontrado problemas de hardware en la última hora.
1.  Inicie sesión en el [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) y vaya a y :::no-loc text="Log Analytics"::: seleccione su área de trabajo.

2. Vaya a su área :::no-loc text="Log Analytics"::: de trabajo, seleccione **Alertas** y, a continuación **, seleccione Nueva regla de alertas**

3. Seleccione **Agregar condición y** , a continuación, **Búsqueda de registro personalizada**

4.  Escriba la consulta siguiente en el cuadro de texto Buscar consulta.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configurar la configuración de lógica de alerta:<br>
    **Basado en:** Número de resultados<br>
    **Condición:** Mayor que<br>
    **Umbral:** 0<br>

6. Configure la configuración de evaluación y seleccione **Listo**: <br>
    **Punto (en minutos):** 60<br>
    **Frecuencia (en minutos):** 60<br>

7. Configurar grupos de acciones:
    1.  Seleccione **Crear nuevo**
    2.  Proporcione nombres adecuados para los *campos Nombre del grupo acción* y *Nombre* corto.
    3.  Especifique un nombre *de acción único y* **seleccione Correo electrónico/SMS/Push/Voice** y, a continuación, **seleccione Editar detalles**.
    4.  Seleccione la **casilla Correo** electrónico y proporcione la dirección de correo electrónico de la persona o grupo que recibirá las alertas.
    5.  También puede proporcionar su número de teléfono para recibir una notificación con SMS, una llamada de voz o ambos.
    6. Seleccione **Aceptar**.

8. **Personalice acciones** si desea invalidar la línea de asunto de los correos electrónicos de alerta.

9. Especifique un nombre de regla y una descripción.<br>
    **Nombre de regla:** :::no-loc text="Microsoft Teams Rooms"::: Alerta de error de hardware<br>
    **Descripción:** Lista de dispositivos que encontraron un problema de hardware en la última hora<br>

10. Seleccione la gravedad deseada y asegúrese de que la regla está habilitada.

11. Seleccione **Crear regla de alerta**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Configurar una alerta de correo electrónico para problemas :::no-loc text="Microsoft Teams Rooms"::: de aplicación

Repita el mismo procedimiento, pero use la consulta siguiente para enumerar los dispositivos que han encontrado problemas de aplicación en la última hora.

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

Ahora ha completado la definición de alertas. Puede definir alertas adicionales con los ejemplos anteriores.

Cuando se genera una alerta, recibe un correo electrónico que enumera los dispositivos que se han encontrado con un problema en la última hora.

! [Correo electrónico :::no-loc text="Azure Monitor"::: de alerta de ejemplo](.. /media/Deploy-Azure-Monitor-6.png "Correo electrónico de :::no-loc text="Azure Monitor"::: alerta de ejemplo")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Configurar todos los dispositivos para :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a> Una vez configurados los paneles y las alertas, :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: puede configurar y configurar el agente en todos los dispositivos para completar la implementación de supervisión.

Aunque puede instalar y configurar el :::no-loc text="Microsoft Monitoring"::: agente manualmente en cada dispositivo, le recomendamos que aproveche las herramientas y métodos de implementación de software existentes.

Si va a crear sus dispositivos :::no-loc text="Microsoft Teams Rooms"::: por primera vez, :::no-loc text="Microsoft Monitoring"::: es posible que desee incluir los pasos de configuración y configuración del agente como parte del proceso de compilación. Para obtener más información, vea [Instalar el agente con la línea de comandos](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Implementar un :::no-loc text="Microsoft Monitoring"::: agente mediante un objeto de directiva de grupo (GPO)

Si ya implementó los dispositivos :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring":::antes de implementarlo, puede usar el script :::no-loc text="Active Directory"::: proporcionado para configurar y configurar los agentes mediante objetos de directiva de grupo.

1.  Cree una ruta de red compartida y conceda acceso de lectura al grupo **Equipos de** dominio.

2.  Descargar la versión de 64 bits del :::no-loc text="Microsoft Monitoring"::: Agente desde :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extraiga el contenido del paquete de configuración en el recurso compartido de red.
    1.  Abra una ventana del símbolo del sistema y, a continuación **, ejecuteMMASetup-AMD64.exe /c**
    2.  Especifique el recurso compartido que acaba de crear y extraiga el contenido.

4.  Cree un nuevo objeto de directiva de grupo y asígnelo a la unidad organizativa donde :::no-loc text="Microsoft Teams Rooms"::: se encuentran las cuentas de equipo.

5.  Configurar la directiva de ejecución de PowerShell:
    1.  Edite el objeto de directiva de grupo recién creado y vaya a Componentes de plantillas \\ \\ administrativas de directivas de configuración del equipo \\ \\ :::no-loc text="Windows"::: :::no-loc text="Windows PowerShell":::
    2.  Habilite la **opción Activar ejecución de script** y establezca **la directiva de ejecución** para **permitir scripts locales**.

6.  Configurar el script de inicio:
    1.  Copie el siguiente script y guárdelo como Install-MMAgent.ps1.
    2.  Modifique los parámetros WorkspaceId, WorkspaceKey y SetupPath para que coincidan con la configuración.
    3.  Edite el mismo objeto de directiva de grupo y vaya a Directivas \\ \\ :::no-loc text="Windows"::: de configuración del equipo Configuración \\ scripts (inicio/apagado)
    4.  Haga doble clic para seleccionar **Inicio** y, a continuación, seleccione **Scripts de PowerShell**.
    5.  Seleccione **Mostrar archivos** y, a continuación **, copie elInstall-MMAgent.ps1** archivo en esa carpeta.
    6.  Seleccione **Agregar** y, a continuación, **Examinar**.
    7.  Seleccione el script de ps1 que acaba de copiar.

7.  :::no-loc text="Microsoft Teams Rooms"::: debe instalar y configurar el :::no-loc text="Microsoft Monitoring"::: agente con el segundo reinicio.

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
> Puede hacer referencia [:::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/agent-manage) al artículo Administrar y mantener el agente cuando necesite volver a configurar un agente, moverlo a otro área de trabajo o modificar la configuración de proxy después de la instalación inicial.

## <a name="additional-solutions"></a>Soluciones adicionales
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: proporciona soluciones de administración integradas a través de su galería [de soluciones](/azure/azure-monitor/insights/solutions) para ayudarle a supervisar aún más su entorno. Le recomendamos que agregue soluciones [de administración de alertas](/azure/azure-monitor/platform/alert-management-solution) [:::no-loc text="Azure Log Analytics"::: y estado](/azure/azure-monitor/insights/solution-agenthealth) del agente también a su área de trabajo.

> [!NOTE]
> La solución Estado :::no-loc text="Microsoft Monitoring"::: del agente puede ayudarle a identificar agentes obsoletos o rotos dentro de su entorno, y la solución administración de alertas proporciona detalles sobre las alertas que se han elevado en un período determinado.

## <a name="see-also"></a>Vea también

[Administración de :::no-loc text="Microsoft Teams Rooms"::: planes con :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Administrar :::no-loc text="Microsoft Teams Rooms"::: dispositivos con :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
