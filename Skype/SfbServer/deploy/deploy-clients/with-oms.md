---
title: Implementar la administración de Sistemas de salas de Skype v2 con OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: En este artículo se describe cómo implementar la administración de dispositivos de sistemas de salas de Skype v2 de manera integrada, end-to-end usando Microsoft Operations Management Suite.
ms.openlocfilehash: 0d0490d92a5513dad38a9ff6348a957204274878
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>Implementar la administración de Sistemas de salas de Skype v2 con OMS
 
En este artículo se describe cómo implementar la administración de dispositivos de sistemas de salas de Skype v2 de manera integrada, end-to-end usando Microsoft Operations Management Suite. 
  
Microsoft Operations Management Suite (OMS) se puede configurar para proporcionar telemetría básica que le ayude a administrar los dispositivos de salas de reuniones de Skype. A medida que se desarrolle la solución de administración, podrá comprar más funciones de administración y datos para crear una vista más detallada del rendimiento de los dispositivos.
  
A un mayor nivel, debe realizar las siguientes tareas:
  
1. [Configurar dispositivos para la administración de OMS ](with-oms.md#config_devices)
    
2. [Asignar campos personalizados](with-oms.md#Custom_fields)
    
3. [Definir las vistas de SRS v2 en OMS](with-oms.md#Views)
    
## <a name="find-and-record-device-locations-capabilities-and-configurations"></a>Buscar y registrar las ubicaciones, las funcionalidades y las configuraciones de los dispositivos
<a name="find_devices"> </a>

El primer paso consiste en crear una base de datos con detalles de todo el equipo del sistema, sus funcionalidades y su configuración, además de su ubicación. En el caso de empresas medianas o pequeñas, basta con una hoja de cálculo, pero si trabaja en una organización más grande, es posible que tenga que usar herramientas de administración de activos y servicios de terceros. Lo importante es que registre la ubicación y todos los detalles relevantes de cada dispositivo.
  
Cuando este trabajo esté hecho, podrá usar esta información para distribuir técnicos y administrar actualizaciones y revisiones de los dispositivos.
  
## <a name="configure-devices-for-oms-management"></a>Configurar dispositivos para la administración de OMS 
<a name="config_devices"> </a>

Para cada dispositivo SRS, siga las instrucciones que se encuentra en [equipos de Windows conectarse al servicio de análisis de registro en Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).
  
## <a name="configure-oms-to-collect-device-event-logs"></a>Configurar OMS para recopilar registros de eventos de dispositivos
<a name="config_devices"> </a>

Debe configurar específicamente OMS para recopilar los registros de sucesos desde dispositivos SRS siguiendo los pasos en [orígenes de datos de registro de sucesos de Windows en análisis de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events). El registro de sucesos SRS que seleccione es "Sistema de sala de Skype" y debería comprobar los cuadros de opción para todos los tipos: Error, advertencia e información.
  
## <a name="map-custom-fields"></a>Asignar campos personalizados
<a name="Custom_fields"> </a>

Antes de que se pueden utilizar los mosaicos creados en las [vistas de definir el v2 SRS de OMS](with-oms.md#Views) , necesitará crear campos personalizados para la vista. ver [campos personalizados en el registro de análisis](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) para obtener información detallada sobre la creación de campos personalizados.
  
Utilice las asignaciones que se muestra a continuación, OMS agregará automáticamente el _CF al definir el nuevo campo. 
  
> [!IMPORTANT]
> Recuerde que en todos los campos JSON y OMS se distingue entre mayúsculas y minúsculas. 
  
**Asignación de campos personalizados**

|**Campo JSON**|**Campo personalizado de OMS**|
|:-----|:-----|
|Descripción  <br/> |SRSEventDescription_CF  <br/> |
|ResourceState  <br/> |SRSResourceState_CF  <br/> |
|OperationName  <br/> |SRSOperationName_CF  <br/> |
|OperationResult  <br/> |SRSOperationResult_CF  <br/> |
|OS  <br/> |SRSOSVersion_CF  <br/> |
|OSVersion  <br/> |SRSOSLongVersion_CF  <br/> |
|Alias  <br/> |SRSAlias_CF  <br/> |
|DisplayName  <br/> |SRSDisplayName_CF  <br/> |
|AppVersion  <br/> |SRSAppVersion_CF  <br/> |
|IPv4Address  <br/> |SRSIPv4Address_CF  <br/> |
|IPv6Address  <br/> |SRSIPv6Address_CF  <br/> |
   
## <a name="define-the-srs-v2-views-in-oms"></a>Definir las vistas de SRS v2 en OMS
<a name="Views"> </a>

Una vez que los datos se recopilan y se asignan los campos personalizados, puede utilizar OMS Ver diseñador para desarrollar una consola con mosaicos para supervisar los sucesos SRS v2. Utilizar el Diseñador de vistas para crear los siguientes mosaicos, consulte [Utilizar el Diseñador de vistas para crear vistas personalizadas de análisis de registro](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) según sea necesario.
  
### <a name="create-a-tile-that-shows-healthy-devices"></a>Crear un icono que muestre los dispositivos en buen estado

1. Defina el caso:  
    
    Este icono muestra todos los dispositivos que han enviado un mensaje de latido en los últimos 10 minutos.
    
2. Asigne el título del grupo.  
    
   ```
   SRS v2
   ```

3. Active la casilla de grupo nuevo
    
4. Agregue el texto de la leyenda del icono.
    
   ```
   All healthy devices (Heartbeat sent in last 10 minutes)
   ```

5. Introduzca la consulta del icono.
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" TimeGenerated >NOW-10MINUTES|measure count() by SRSDisplayName_CF 
   ```

6. Introduzca la consulta de lista.
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by SRSDisplayName_CF |Where LastHB>NOW-10MINUTES
   ```

7. Defina el nombre de los títulos de columna.
    
   ```
   Display Name
   ```

8. Definir el valor de los títulos de columna
    
   ```
   Last HB
   ```

9. Introduzca la consulta de navegación.
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat"|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="create-the-tile-that-shows-devices-with-connectivity-issues"></a>Crear el icono que muestra los dispositivos con problemas de conectividad

1. Defina el caso:  
    
    Este icono muestra todos los dispositivos que no han enviado un mensaje de latido en los últimos 10 minutos. Estos dispositivos pueden estar experimentando problemas con la conectividad de red, la conectividad de Exchange o la conectividad de Skype Empresarial.
    
2. Asigne el título del grupo.  
    
   ```
   SRS v2
   ```

3. No active el cuadro del grupo nuevo. Ya lo hizo cuando creó el icono 1 y no es necesario hacerlo de nuevo.
    
4. Agregue el texto de la leyenda del icono.
    
   ```
   Devices no longer sending Heartbeat messages
   ```

5. Introduzca la consulta del icono.
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

6. Introduzca la consulta de lista.
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

7. Defina el nombre de los títulos de columna.
    
   ```
   Device Name
   ```

8. Defina el valor de los títulos de columna.  
    
   ```
   Last HB
   ```

9. Introduzca la consulta de navegación.
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-a-hardware-error"></a>Enumerar dispositivos con un error de hardware 

1. Defina el caso:  
    
   Esta ficha muestra todos los dispositivos que envían un mensaje que indica un uno o más problemas de componentes de hardware en los últimos 10 minutos. 
    
2. Asigne el título del grupo.  
    
   ```
   SRS v2
   ```

3. No active el cuadro del grupo nuevo. Ya lo hizo cuando creó el icono 1 y no es necesario hacerlo de nuevo.
    
4. Leyenda del mosaico:  
    
   ```
   Devices with a Hardware Error
   ```

5. Consulta de icono
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure count() by SRSDisplayName_CF
   ```

6. Consulta de lista:
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by SRSDisplayName_CF
   ```

7. Nombre de los títulos de columna:  
    
   ```
   Display Name
   ```

8. Valor de títulos de columna:  
    
   ```
   Last Error
   ```

9. Consulta de navegación:  
    
   ```
   {selected item}  EventLevelName:Error EventID:3001|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-an-app-error"></a>Enumerar dispositivos con un error de aplicación  

1. Defina el caso: 
    
   Este icono muestra todos los dispositivos de SRS que notifican uno o varios errores en los componentes de las aplicaciones en los últimos 10 minutos.
    
2. Asigne el título del grupo.  
    
   ```
   SRS v2
   ```

3. No active el cuadro del grupo nuevo. Ya lo hizo cuando creó el icono 1 y no es necesario hacerlo de nuevo.
    
4. Leyenda del mosaico:  
   ``` 
    Device with App Errors (in prior 10 minutes)
   ``` 
5. Consulta de icono:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure count() by Computer
   ```

6. Consulta de lista:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by Computer
   ```

7. Nombre de los títulos de columna:  
    
   ```
   Device Name
   ```

8. Valor de títulos de columna:  
    
   ```
   Last Error
   ```

9. Consulta de navegación:
    
   ```
   {selected item} EventLevelName:Error|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-requiring-a-restart"></a>Enumerar los dispositivos que se deben reiniciar

1. Defina el caso: 
    
   Este icono muestra todos los dispositivos de SRS que se han reiniciado en las últimas 24 horas y el número de reinicios.
    
2. Asigne el título del grupo.  
    
  ```
  SRS v2
  ```

3. No active el cuadro del grupo nuevo. Ya lo hizo cuando creó el icono 1 y no es necesario hacerlo de nuevo.
    
4. Leyenda del mosaico:  
    
   ```
   Devices with App restarted (past 24 hours)
   ```

5. Consulta de icono:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count() by Computer
   ```

6. Consulta de lista:  
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count(EventID) by SRSDisplayName_CF
   ```

7. Nombre de los títulos de columna:  
    
   ```
   Display Name
   ```

8. Valor de títulos de columna:  
    
   ```
   Number of restarts
   ```

9. Consulta de navegación:  
    
   ```
   {selected item} EventID:4000 TimeGenerated >NOW-24HOURS|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

Con esto finaliza la creación de vistas. Todas las alertas que están disponibles en este momento están reflejadas en uno o en varios de estos iconos.
## <a name="see-also"></a>Vea también
<a name="Views"> </a>

#### 

[Planear la administración de sistemas de salas de Skype v2 con OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[Administrar dispositivos de sistemas de salas de Skype v2 con OMS](../../manage/skype-room-systems-v2/oms.md)

