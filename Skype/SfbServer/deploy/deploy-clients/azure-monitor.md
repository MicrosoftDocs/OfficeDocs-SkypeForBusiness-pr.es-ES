---
title: Implementar la administración de salas de equipos de Microsoft con el Monitor de Azure
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: En este artículo se explica cómo implementar la administración de dispositivos de Microsoft salones de los equipos de una manera integrada, end-to-end mediante el Monitor de Azure.
ms.openlocfilehash: 599cbb7abce2b20dac27ffebacb041062a254905
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013112"
---
# <a name="deploy-microsoft-teams-rooms-management-with-azure-monitor"></a>Implementar la administración de salas de equipos de Microsoft con el Monitor de Azure

En este artículo se describe cómo configurar e implementar administración integrada, end-to-end de dispositivos de salas de equipos de Microsoft con el Monitor de Azure.

Puede configurar análisis de registro dentro de Monitor de Azure para proporcionar básico telemetry y alertas que le ayudarán a administración las salas de los equipos de Microsoft dispositivos de sala de la reunión. A medida que crezca la solución de administración, decide implementar datos adicionales y capacidades de administración para crear una vista más detallada de la disponibilidad de dispositivos y el rendimiento.

Siguiendo esta guía, puede usar un panel similar al ejemplo siguiente para obtener el estado detallado de informes de disponibilidad de dispositivo, aplicación y mantenimiento de hardware y aplicación de salas de equipos de Microsoft y distribución de la versión de sistema operativo.

![Vista de análisis de registro de ejemplo para salas de equipos de Microsoft] (../../media/Deploy-Azure-Monitor-1.png "Vista de análisis de registro de ejemplo para salas de equipos de Microsoft")

A un mayor nivel, debe realizar las siguientes tareas:


1.  [Validar la configuración del análisis de registro](azure-monitor.md#validate_LogAnalytics)
2.  [Configurar dispositivos de prueba para el programa de instalación de administración de análisis de registro](azure-monitor.md#configure_test_devices)
3.  [Asignar campos personalizados](azure-monitor.md#Custom_fields)
4.  [Definir las vistas de salas de equipos de Microsoft en el registro de análisis](azure-monitor.md#Define_Views)
5.  [Definir alertas](azure-monitor.md#Alerts)
6.  [Configurar todos los dispositivos de supervisión](azure-monitor.md#configure_all_devices)
7.  [Configurar las soluciones de Monitor de Azure adicionales](azure-monitor.md#Solutions)

> [!IMPORTANT]
> Aunque con la configuración mínima, análisis de registro del Monitor de Azure puede supervisar un equipo que ejecute un sistema operativo Windows, aún hay algunos pasos Microsoft Teams salones específicas que se deben tomar antes de iniciar la implementación de agentes a todos los Teams Microsoft Dispositivos de salas.
> Por lo tanto, se recomienda encarecidamente que realizar todos los pasos de configuración en el orden correcto para un controlado el programa de instalación y configuración. La calidad del resultado final depende mucho de la calidad de la configuración inicial.

## <a name="validate-log-analytics-configuration"></a>Validar la configuración del análisis de registro
<a name="validate_LogAnalytics"> </a>

Debe tener un área de trabajo de análisis de registro para iniciar la recopilación de registros de dispositivos de salas de equipos de Microsoft. Un área de trabajo es un entorno de análisis de registro único con su propio repositorio de datos, orígenes de datos y soluciones. Si ya tiene un área de trabajo de análisis de registro existente, puede utilizarlo para supervisar la implementación de salas de equipos de Microsoft o de forma alternativa, puede crear un área de trabajo de análisis de registro dedicado específico para sus salones de los equipos de Microsoft necesidades de monitoreo.

Si necesita crear una nueva área de trabajo de análisis de registro, siga las instrucciones que aparecen en el artículo [crear un área de trabajo de análisis de registro en el portal de Azure](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Para usar el análisis de registro con el Monitor de Azure, debe tener una suscripción de Azure activa. Si no dispone de una suscripción de Azure, puede crear [una suscripción de prueba gratuita](https://azure.microsoft.com/free) como punto de partida.

### <a name="configure-log-analytics-to-collect-microsoft-teams-rooms-event-logs"></a>Configurar el registro de análisis para recopilar los registros de eventos de salas de equipos de Microsoft

Análisis de registro sólo recopila eventos de los registros de eventos de Windows que se especifican en la configuración. Para cada registro, se recopilan sólo los eventos con los niveles de gravedad seleccionados.

Debe configurar el registro de análisis para recopilar los registros necesarios para supervisar el estado de dispositivo y la aplicación de salas de equipos de Microsoft. Los dispositivos de salas de equipos de Microsoft usan el registro de eventos **Del sistema de sala de Skype** .

Para configurar el registro de análisis para recopilar los eventos de salas de equipos de Microsoft, vea [orígenes de datos de registro de eventos de Windows en el Monitor de Azure](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Configuración del registro de eventos] (../../media/Deploy-Azure-Monitor-2.png "Configuración del registro de eventos")

> [!IMPORTANT]
> Configurar las opciones de registro de eventos de Windows y escriba **Del sistema de sala de Skype** como nombre de registro de eventos y, a continuación, seleccione las casillas de verificación **Error**, **Advertencia**e **información** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurar dispositivos de prueba para la supervisión de Azure
<a name="configure_test_devices"> </a>

Debe preparar análisis de registro para poder supervisar los eventos relacionados con salas de equipos de Microsoft. Para empezar con, deberá implementar Microsoft Monitoring agentes a uno o dos dispositivos de salas de equipos de Microsoft que tienen acceso físico a y obtenerlos dispositivos de prueba generar algunos datos e inserción al área de trabajo de análisis de registro.

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a>Instalar los agentes de Microsoft Monitoring para los dispositivos de prueba

Implementar al agente de Microsoft Monitoring en los dispositivos de prueba mediante el uso de las instrucciones proporcionadas en [equipos Windows conectarse al servicio de registro de análisis de Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). En este artículo se proporciona información detallada sobre los pasos para la implementación de supervisión de Microsoft Agent para Windows, instrucciones para obtener el ***Identificador del área de trabajo*** de análisis de registro y la ***clave principal*** para obtener los dispositivos de salas de equipos de Microsoft conectado a su implementación de Monitor de Azure y los pasos para comprobar la conectividad del agente a instancia de análisis de registro.

### <a name="generate-sample-microsoft-teams-rooms-events"></a>Generar eventos de ejemplo salones de los equipos de Microsoft

Después de que el agente de Microsoft Monitoring se implementa en los dispositivos de prueba, compruebe que se recopilan los datos de registro de eventos necesarios por el Monitor de Azure.

> [!NOTE]
> Reiniciar el dispositivo tras la instalación del agente Microsoft Monitoring y asegúrese de que esa aplicación de reunión de salas de equipos de Microsoft se ha iniciado, por lo que puede generar eventos de nuevo en el registro de eventos.

1.  Inicie sesión el [portal de Microsoft Azure](https://portal.azure.com) y vaya al análisis de registro y seleccione el área de trabajo.

2.  Se enumeran los eventos de latido generados por un dispositivo de salas de equipos de Microsoft:
    1.  Seleccione el área de trabajo y vaya a **registros** y usar una consulta para recuperar los registros de latido que tendrán los campos personalizados para salas de equipos de Microsoft.
    2.  Consulta de ejemplo:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Asegúrese de que la consulta devuelve los registros de registro que incluyen los eventos generados por la aplicación de las reuniones de salas de equipos de Microsoft.

4.  Generar un problema de hardware y validar que se registran los eventos necesarios en análisis de registro de Azure.
    1.  Desconecte uno de los dispositivos periféricos en la prueba del sistema de salas de equipos de Microsoft. Podría tratarse de la cámara, altavoz, micrófono o para mostrar de la sala de frente
    2.  Espere 10 minutos para el registro de eventos se rellene de análisis de registro de Azure.
    3.  Utilizar una consulta para los eventos de error de hardware de lista:`Event | where Source == "SRS-App" and EventID == 3001`

5.  Generar un problema de la aplicación y validar que se registran los eventos necesarios.
    1.  Modificar la configuración de la aplicación de salas de equipos de Microsoft, y escriba un par de dirección y contraseña de protocolo de inicio de sesión (SIP) incorrecta.
    2.  Espere 10 minutos para el registro de eventos se rellene de análisis de registro de Azure.
    3.  Utilizar una consulta para los eventos de error de aplicación de lista:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Estos registros de eventos de ejemplo se requieren antes de que se pueden configurar los campos personalizados. No continúe con el siguiente paso hasta que haya recopilado los registros de eventos necesarios.

## <a name="map-custom-fields"></a>Asignar campos personalizados
<a name="Custom_fields"> </a>

Usar campos personalizados para extraer datos específicos de los registros de eventos. Debe definir los campos personalizados que se usará más adelante con los mosaicos, vistas de panel y alertas. Vea [campos personalizados de análisis de registro de](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) y a familiarizarse con los conceptos antes de empezar a crear los campos personalizados.

Para extraer los campos personalizados fuera de los registros de eventos capturados, siga estos pasos:

1.  Inicie sesión el [portal de Microsoft Azure](https://portal.azure.com) y vaya al análisis de registro y seleccione el área de trabajo.

2. Se enumeran los eventos generados por un dispositivo de salas de equipos de Microsoft:
   1.  Vaya a **registros** y usar una consulta para recuperar los registros que va a tener el campo personalizado.
   2.  Consulta de ejemplo:`Event | where Source == "SRS-App" and EventID == 2000`

3. Seleccione uno de los registros, seleccione el botón situado a la izquierda e iniciar al Asistente para la extracción de campo.
4. Resalte los datos que le gustaría extraer el RenderedDescription y proporcione un título de campo. Se proporcionan los nombres de campo que se deben usar en la tabla 1.

   ![Definición de campos personalizados] (../../media/Deploy-Azure-Monitor-4.png "Definición de campos personalizados")

5. Use las asignaciones que se muestra en la *tabla 1*. Análisis de registro se anexará automáticamente la ** \_CF** al definir el nuevo campo de cadena.

> [!IMPORTANT]
> Recuerde que todos los campos de análisis de registro y JSON distinguen mayúsculas de minúsculas.
> 
> Preste atención a las consultas requeridas para cada campo personalizado en la tabla siguiente. Debe utilizar las consultas de análisis de registro correctas para extraer correctamente los valores de campo personalizado.
> 
 ![Definición de campos personalizados] (../../media/Deploy-Azure-Monitor-5.png "Definición de campos personalizados")

**Tabla 1**

| **Campo JSON**                   | **Campo personalizado de análisis de registro** | **Nivel del** | **Para usar con la extracción de consulta**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Descripción                      | SRSEventDescription         | **2000**     | Evento \| de origen donde == "SRS-App" y EventID == 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Evento \| de origen donde == "SRS-App" y EventID == 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Evento \| de origen donde == "SRS-App" y EventID == 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Evento \| de origen donde == "SRS-App" y EventID == 2000 |
| Sistema operativo                               | SRSOSVersion                | **2000**     | Evento \| de origen donde == "SRS-App" y EventID == 2000 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | Evento \| de origen donde == "SRS-App" y EventID == 2000 |
| Alias                            | SRSAlias                    | **2000**     | Evento \| de origen donde == "SRS-App" y EventID == 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Evento \| de origen donde == "SRS-App" y EventID == 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Evento \| de origen donde == "SRS-App" y EventID == 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Evento \| de origen donde == "SRS-App" y EventID == 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Evento \| de origen donde == "SRS-App" y EventID == 2000 |
| Estado de micrófono de conferencia     | SRSConfMicrophoneStatus     | **3001**     | Evento \| de origen donde == "SRS-App" y EventID == 3001 |
| Estado de altavoz de conferencia        | SRSConfSpeakerStatus        | **3001**     | Evento \| de origen donde == "SRS-App" y EventID == 3001 |
| Estado del altavoz predeterminado           | SRSDefaultSpeakerStatus     | **3001**     | Evento \| de origen donde == "SRS-App" y EventID == 3001 |
| Estado de la cámara                    | SRSCameraStatus             | **3001**     | Evento \| de origen donde == "SRS-App" y EventID == 3001 |
| Parte delantera del estado de visualización de salón     | SRSFORDStatus               | **3001**     | Evento \| de origen donde == "SRS-App" y EventID == 3001 |
| Estado del Sensor de movimiento             | SRSMotionSensorStatus       | **3001**     | Evento \| de origen donde == "SRS-App" y EventID == 3001 |
| Estado de ingesta HDMI               | SRSHDMIIngestStatus         | **3001**     | Evento \| de origen donde == "SRS-App" y EventID == 3001 |


## <a name="define-the-microsoft-teams-rooms-views-in-log-analytics"></a>Definir las vistas de salas de equipos de Microsoft en el registro de análisis
<a name="Define_Views"> </a>

Una vez que se recopilan los datos y se asignan los campos personalizados, puede usar el Diseñador de vistas para desarrollar un panel que contiene varios mosaicos para supervisar los eventos de salas de equipos de Microsoft. Use Diseñador de vistas para crear los siguientes iconos. Para obtener más información, vea [crear vistas personalizadas mediante el Diseñador de vista de análisis de registro](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Deben haber completado los pasos anteriores en esta guía para que los mosaicos del panel funcionen correctamente.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Crear un panel de salas de equipos de Microsoft mediante el método de importación

Puede importar un panel de salas de equipos de Microsoft e iniciar supervisión rápidamente sus dispositivos. Lleve a cabo los siguientes pasos para importar el panel:

1.  Obtenga el archivo del panel de [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) .
2.  Inicie sesión el [portal de Microsoft Azure](https://portal.azure.com) y vaya al análisis de registro y seleccione el área de trabajo.
3.  Abra el **Diseñador de vistas**.
4.  Seleccione **Importar**y, a continuación, seleccione el archivo **SkypeRoomSystems_v2.omsview** .
5.  Seleccione **Guardar**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Crear un panel de salas de equipos de Microsoft de forma manual

Como alternativa, puede crear su propio escritorio y agregar sólo los mosaicos que desea supervisar.

#### <a name="configure-the-overview-tile"></a>Configurar el icono de información general

1.  Abra el **Diseñador de vistas**.
2.  Seleccione el **Icono de información general sobre**y, a continuación, seleccione **dos números** de la galería.
3.  Nombre el mosaico **Salones de los equipos de Microsoft**.
4.  Definir el **primer mosaico**:<br>
    **Leyenda:** Dispositivos que se ha enviado un latido al menos una vez dentro del último mes<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Defina el **segundo icono**:<br>
    **Leyenda:** Dispositivos activos que envían un latido dentro de la última hora<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Seleccione **Aplicar**.

### <a name="create-a-tile-that-displays-active-devices"></a>Crear un icono que muestra los dispositivos de activos

1.  Seleccione el **Panel de vista** para empezar a agregar los mosaicos.
2.  Seleccione la **lista & de número** de la Galería
3.  Definir las propiedades **generales** :<br>
    **Título de grupo:** Estado del latido<br>
    **Nuevo grupo:** Seleccionado
4.  Definir las propiedades de **icono** :<br>
    **Leyenda:** Dispositivos activos (latido enviado en los últimos 20 minutos)<br>
    **Consulta de icono: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definir las propiedades de **lista** :<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definir **los títulos de columna**:<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último latido
7.  Definir **consultas de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar**y, a continuación, en **Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Crear un icono que muestra los dispositivos que tienen problemas de conectividad

1.  Seleccione **lista & de número** de la galería y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** :<br>
    **Título de grupo:** Deje en blanco<br>
    **Nuevo grupo:** No seleccionado
3.  Definir las propiedades de **icono** :<br>
    **Leyenda:** Dispositivos inactivos (ningún mensaje de latido enviado en los últimos 20 minutos)<br>
    **Consulta de icono: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definir las propiedades de **lista** :<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definir **los títulos de columna**:<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último latido
6.  Definir **consultas de navegación**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Seleccione **Aplicar**y, a continuación, en **Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Crear un icono que muestra los dispositivos que tienen un error de hardware

1.  Seleccione **lista & de número** de la galería y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** :<br>
    **Título de grupo:** Estado de hardware<br>
    **Nuevo grupo:** Seleccionado
3.  Definir las propiedades de **icono** :<br>
    **Leyenda:** Dispositivos que ha experimentado un error de hardware en la última hora<br>
    **Consulta de icono: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definir las propiedades de **lista** :<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **los títulos de columna**:<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último Error
6.  Definir **consultas de navegación**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Seleccione **Aplicar**y, a continuación, en **Cerrar**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-operating-system-versions"></a>Crear un icono que muestra las versiones del sistema operativo de salas de equipos de Microsoft

1.  Seleccione **lista de & rosquilla** desde la Galería de y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** :<br>
    **Título de grupo:** Detalles del sistema operativo<br>
    **Nuevo grupo:** Seleccionado
3.  Definir las propiedades de **encabezado** :<br>
    **Título:** Versiones de sistema operativo<br>
    **Subtítulo:** Dispositivos que ejecutan versiones específicas del sistema operativo
4.  Definir las propiedades de **anillo** :<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Del centro de texto:** Dispositivos<br>
    **Operación:** Suma
5.  Definir las propiedades de la **lista** .<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar gráfico:** Seleccionado<br>
    **Habilitar minigráficos:** No seleccionado
6.  Definir **los títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Deje en blanco
7.  Definir **consultas de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar** y, a continuación, en **Cerrar**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-application-versions"></a>Crear un icono que muestra las versiones de la aplicación de salas de equipos de Microsoft

1.  Seleccione **lista de & rosquilla** desde la Galería de y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** :<br>
    **Título de grupo:** Detalles de la aplicación de salas de equipos de Microsoft<br>
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
    **Nombre:** Nombre del equipo<br>
    **Valor:** Deje en blanco
7.  Definir **consultas de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Seleccione **Aplicar** y, a continuación, en **Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Crear un icono que muestra los dispositivos que tienen un error de aplicación

1.  Seleccione **lista & de número** de la galería y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** .<br>
    **Título de grupo:** Deje en blanco<br>
    **Nuevo grupo:** No seleccionado
3.  Definir las propiedades de **mosaico** .<br>
    **Leyenda:** Dispositivos que se produjo un error de aplicación en la última hora<br>
    **Consulta de icono: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definir las propiedades de la **lista** .<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **los títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Último Error
6.  Definir **consultas de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Seleccione **Aplicar** y, a continuación, en **Cerrar**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Crear un icono que muestra los dispositivos que se haya reiniciado

1.  Seleccione **lista & de número** de la galería y, a continuación, agregue un nuevo mosaico.
2.  Definir las propiedades **generales** .<br>
    **Título de grupo:** Deje en blanco<br>
    **Nuevo grupo:** No seleccionado
3.  Definir las propiedades de **mosaico** .<br>
    **Leyenda:** Dispositivos donde se ha reiniciado la aplicación en el último 24 horas y el número de reinicios<br>
    **Consulta de icono: ** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Definir las propiedades de la **lista** .<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definir **los títulos de columna**.<br>
    **Nombre:** Nombre del equipo<br>
    **Valor:** Número de reinicios
6.  Definir **consultas de navegación**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Seleccione **Aplicar** y, a continuación, en **Cerrar**.
8.  Seleccione **Guardar** para guardar el panel.

Ahora ha completado la creación de las vistas.

## <a name="configure-alerts-in-azure-monitor"></a>Configurar las alertas en el Monitor de Azure
<a name="Alerts"> </a>

Monitor de Azure puede generar alertas para notificar a los administradores, cuando encuentra un problema con una consola de salas de equipos de Microsoft.

El Monitor de Azure incluye un mecanismo de alerta integrado que se ejecuta a través de las búsquedas de registro programadas a intervalos regulares. Si los resultados de la búsqueda de registro coinciden con algunos criterios determinados, se crea un registro de alerta.

La regla, a continuación, puede ejecutar automáticamente una o más acciones para informarle de la alerta de manera proactiva o invocar otro proceso. Las opciones posibles con las alertas son:
-   Enviar un correo electrónico
-   Invocación de un proceso externo a través de una solicitud HTTP POST
-   Iniciar un runbook en servicios de automatización de Azure

Vea [iniciar las alertas en el Monitor de Azure](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) para obtener más información acerca de las alertas en el Monitor de Azure.

> [!NOTE]
> Los siguientes ejemplos envían alertas de correo electrónico cuando un dispositivo de salas de equipos de Microsoft genera un hardware o un error de aplicación.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-hardware-issues"></a>Configurar una alerta de correo electrónico para problemas de hardware de salas de equipos de Microsoft

Configurar una regla de alerta que comprueba para dispositivos de salas de equipos de Microsoft que se encontraron problemas de hardware dentro de la última hora.
1.  Inicie sesión el [portal de Microsoft Azure](https://portal.azure.com) y vaya al análisis de registro y seleccione el área de trabajo.

2. Navegue hasta el área de trabajo de análisis de registro y seleccione **las alertas** y, a continuación, seleccione **nueva regla de alerta**

3. Seleccione **Agregar condición** y, a continuación, la **búsqueda de registro personalizada**

4.  Escriba la siguiente consulta en el cuadro de texto de consulta de búsqueda.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configurar las opciones de alerta lógica:<br>
    **Basado en:** Número de resultados<br>
    **Condición:** A continuación, mayor<br>
    **Umbral:** 0<br>

6. Configurar las opciones de evaluación y seleccione **hecho**: <br>
    **Período (en minutos):** 60<br>
    **Frecuencia (en minutos):** 60<br>

7. Configurar grupos de acciones:
    1.  Seleccione **crear nuevos**
    2.  Proporcionar nombres adecuados para los campos *nombre de grupo de acción* y el *Nombre corto* .
    3.  Especificar un único *Nombre de la acción* y seleccione **Correo electrónico o SMS/inserción/voz**y, a continuación, seleccione **Editar detalles**.
    4.  Seleccione la casilla de verificación de correo electrónico y proporcione la dirección de correo electrónico de la persona o grupo que va a recibir las alertas.
    5.  También puede proporcionar su número de teléfono para recibir una notificación con SMS, una llamada de voz o ambos.
    6. Haga **clic en Aceptar**.

8. **Personalizar acciones** si desea invalidar la línea de asunto de los correos electrónicos de alerta.

9. Especifique un nombre de la regla y una descripción.<br>
    **Nombre de la regla:** Alerta de error de Hardware de salas de equipos de Microsoft<br>
    **Descripción:** Lista de los dispositivos que se encuentra un problema de hardware dentro de la última hora<br>

10. Seleccione la gravedad prevista y asegúrese de que la regla está habilitada.

11. Seleccione **Crear regla de alertas**.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-application-issues"></a>Configurar una alerta de correo electrónico para problemas de aplicaciones de salas de equipos de Microsoft

Repita el mismo procedimiento, pero use la siguiente consulta en los dispositivos de lista que se encontraron problemas de aplicaciones dentro de la última hora.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

Ahora ha completado las alertas de definición. Puede definir alertas adicionales mediante el uso de los ejemplos anteriores.

Cuando se genera una alerta, obtendrá un correo electrónico que se enumera los dispositivos que encontraron un problema durante la última hora.

![Correo electrónico de alerta de Monitor de Azure de ejemplo] (../../media/Deploy-Azure-Monitor-6.png "Correo electrónico de alerta de Monitor de Azure de ejemplo")

## <a name="configure-all-devices-for-azure-monitoring"></a>Configurar todos los dispositivos para la supervisión de Azure
<a name="configure_all_devices"></a> Una vez configuradas los paneles y las alertas, puede configurar y configurar el agente de Microsoft Monitoring en todos los dispositivos de salas de equipos de Microsoft para llevar a cabo la implementación de supervisión.

Aunque se puede instalar y configurar al agente de Microsoft Monitoring manualmente en cada dispositivo, se recomienda encarecidamente que aprovechar los métodos y herramientas de implementación de software existente.

Si va a crear los dispositivos de salas de equipos de Microsoft por primera vez, es posible que desee incluir los pasos del programa de instalación y configuración del agente de Microsoft Monitoring como parte del proceso de compilación. Para obtener más información, vea [instalar al agente mediante la línea de comandos](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Implementar el agente de Microsoft Monitoring mediante el uso de un objeto de directiva de grupo (GPO)

Si ya ha implementado los dispositivos de salas de equipos de Microsoft antes de implementar la supervisión de Azure, puede usar la secuencia de comandos para instalar y configurar a los agentes mediante el uso de objetos de directiva de grupo de Active Directory.

1.  Crear una ruta de acceso de red compartida y conceder acceso de lectura al grupo de **Equipos del dominio** .

2.  Descargar la versión de 64 bits de Microsoft supervisión agente para Windows desde<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extraiga el contenido del paquete del programa de instalación en el recurso compartido de red.
    1.  Abra una ventana del símbolo del sistema y, a continuación, ejecutar **MMASetup-AMD64.exe /c**
    2.  Especifique el recurso compartido que acaba de crear y extraiga el contenido.

4.  Crear un nuevo objeto de directiva de grupo y asignar a la unidad organizativa donde se encuentran las cuentas de máquina de salas de equipos de Microsoft.

5.  Configurar la directiva de ejecución de PowerShell:
    1.  Editar el objeto de directiva de grupo recién creada y vaya a configuración del equipo \\ directivas \\ plantillas administrativas \\ componentes de Windows \\ Windows PowerShell
    2.  Habilite la **activar la ejecución del Script** y establecer la **Directiva de ejecución** para **Permitir que los Scripts de Local**.

6.  Configurar el script de inicio:
    1.  Copie la siguiente secuencia de comandos y guárdelo como Install-MMAgent.ps1.
    2.  Modificar parámetros WorkspaceId, WorkspaceKey y SetupPath para que coincida con la configuración.
    3.  Editar el mismo objeto de directiva de grupo y vaya a configuración del equipo \\ directivas \\ configuración de Windows \\ secuencias de comandos (inicio/apagado)
    4.  Haga doble clic para seleccionar el **Inicio**y, a continuación, seleccione **Las secuencias de comandos de PowerShell**.
    5.  Seleccione **Mostrar archivos**y, a continuación, copie el archivo de **Instalación MMAgent.ps1** a esa carpeta.
    6.  Seleccione **Agregar**y, a continuación, **busque**.
    7.  Seleccione la secuencia de comandos ps1 que acaba de copiar.

7.  Dispositivos de salas de equipos de Microsoft deben instalar y configurar al agente de Microsoft Monitoring con el segundo reinicio.

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
> Puede consultar el artículo de [administrar y mantener al agente de análisis de registro](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) cuando es necesario volver a configurar a un agente, moverlo a un área de trabajo diferente, o modificar la configuración de proxy después de la instalación inicial.

## <a name="additional-solutions"></a>Soluciones adicionales
<a name="Solutions"> </a>

Monitor de Azure proporciona soluciones de administración integradas a través de su [Galería de soluciones](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) que aún más, le ayudarán a supervisar el entorno. Se recomienda que agregue las soluciones de [Administración de alertas](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) y [Mantenimiento del agente de análisis de Azure registro](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) a su área de trabajo.

> [!NOTE]
> La solución de mantenimiento de agente puede ayudar a identificar a anticuados o rotos agentes Microsoft Monitoring dentro de su entorno y la solución de administración de alertas proporciona información detallada acerca de las alertas que se han desencadenado dentro de un período determinado.

## <a name="see-also"></a>Consulte también

[Planeación de la administración de salas de equipos de Microsoft con el Monitor de Azure](../../plan-your-deployment/clients-and-devices/azure-monitor.md)

[Administrar dispositivos de salas de equipos de Microsoft con el Monitor de Azure](../../manage/skype-room-systems-v2/azure-monitor.md)