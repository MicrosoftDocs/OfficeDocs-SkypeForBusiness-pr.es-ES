---
title: Vista MediaLine
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: La vista MediaLine almacena información acerca de cada línea de medios en la base de datos. Normalmente, una sesión de audio contiene una línea de medios de audio. Uno de audio y vídeo (A / V) sesión normalmente contiene una línea de medios de audio y una única línea de medios de vídeo. Sin embargo, la sesión puede contener dos líneas de medios de vídeo si se usa un dispositivo para conferencias o si se usa la vista de galería. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 4fcfa22c17cc47c37e33d1f68bdab9815840c332
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920141"
---
# <a name="medialine-view"></a>Vista MediaLine
 
La vista MediaLine almacena información acerca de cada línea de medios en la base de datos. Normalmente, una sesión de audio contiene una línea de medios de audio. Uno de audio y vídeo (A / V) sesión normalmente contiene una línea de medios de audio y una única línea de medios de vídeo. Sin embargo, la sesión puede contener dos líneas de medios de vídeo si se usa un dispositivo para conferencias o si se usa la vista de galería. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**detalles**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Información sobre el proceso de establecimiento interactivo de conectividad (ICE) describe en bits indicadores para el autor de la llamada. Para obtener información detallada, consulte la calidad de experiencia Monitoring Server especificación del protocolo.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Información sobre el proceso de establecimiento interactivo de conectividad (ICE) describe en bits indicadores para el destinatario de la llamada. Para obtener información detallada, consulte la calidad de experiencia Monitoring Server especificación del protocolo.  <br/> |
|Seguridad  <br/> |tinyint  <br/> |Perfil de seguridad en uso. 0 es NONE, 1 es SRTP, 2 es V1.  <br/> |
|Transport  <br/> |tinyint  <br/> |Tipo de transporte. 0 es UDP, 1 es TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Dirección IP del autor de la llamada. Esto puede ser la dirección de un IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Puerto usado por el autor de la llamada.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica si el autor de la llamada está dentro de la red de la organización. 1 significa que el autor de la llamada está dentro de la red de empresa. 0 significa que el autor de la llamada está fuera de la red.  <br/> |
|CallerMacAddress  <br/> |varchar (256)  <br/> |Dirección MAC de la interfaz de red utilizado por el autor de la llamada.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Dirección IP del servicio perimetral A/v utilizado por el autor de la llamada. Vea la [tabla IPAddress](ipaddress.md) para obtener más información. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Puerto usado en el servicio perimetral A/v utilizado por el autor de la llamada.  <br/> |
|CallerReflexiveIPAddr  <br/> |var(50)  <br/> |Dirección IP de autor de la llamada tal como notificaron el / servicio perimetral A/v. Esta dirección puede ser diferente que el CallerIPAddr si el cliente se encuentra detrás de un dispositivo NAT por ejemplo.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nombre de dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nombre del dispositivo de presentación de autor de la llamada.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de presentación del autor de la llamada.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |Descripción del controlador Wifi del autor de la llamada.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar (256)  <br/> |Versión del controlador Wifi del autor de la llamada.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |Detalles de conexión de red del autor de la llamada. Consulte la [tabla NetworkConnectionDetail](networkconnectiondetail.md) para obtener más información. <br/> |
|CallerBssid  <br/> |varchar (256)  <br/> |Identificador de conjunto de servicio básico había usado por los autores de llamadas de conexión WiFi.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica si el autor de la llamada se conectó a través de una red privada virtual. 1 es una red privada virtual (VPN), 0 es diferente de VPN.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Dirección IP del destinatario de la llamada. Esto puede ser la dirección de un IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Puerto usado por el destinatario de la llamada.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica si el destinatario de la llamada está dentro de la red de la empresa. 1 significa destinatario de la llamada está dentro de la red de empresa, 0 significa que el destinatario está fuera de la red.  <br/> |
|CalleeMacAddress  <br/> |varchar (256)  <br/> |Dirección MAC de la interfaz de red utilizada por el destinatario de la llamada.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Dirección IP del servicio perimetral A/v que usa el destinatario de la llamada. Vea la [tabla IPAddress](ipaddress.md) para obtener más información. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Puerto usado en el servicio perimetral A/v que usa el destinatario de la llamada.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var(50)  <br/> |Dirección IP de destinatario de la llamada tal como notificaron el / servicio perimetral A/v. Esta dirección puede ser diferente que el CalleeIPAddr si el cliente se encuentra detrás de un dispositivo NAT por ejemplo.  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |Nombre de dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nombre del dispositivo de presentación del destinatario de la llamada.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de presentación del destinatario de la llamada.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar (256)  <br/> |Descripción del controlador Wifi del destinatario de la llamada.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |Versión del controlador Wifi del destinatario de la llamada.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |Detalles de conexión de red del destinatario de la llamada. Consulte la [tabla NetworkConnectionDetail](networkconnectiondetail.md) para obtener más información. <br/> |
|CalleeBssid  <br/> |varchar (256)  <br/> |Servicio de identificador de conjunto básico usado por conexión WiFi de destinatario de la llamada.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica si el destinatario de la llamada se conectó a través de una red privada virtual. 1 es una red privada virtual (VPN), 0 es diferente de VPN.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS de conversación de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Este es el ancho de banda real que se aplica a la secuencia de lado de envío determinado dada distintas configuraciones de directivas (activar, API, SDP, servidor de directivas, etcetera). Esto no se debe para confundir con el ancho de banda eficaz debido a que puede haber un ancho de banda eficaz inferior en función de la estimación del ancho de banda. Esto es, básicamente, el ancho de banda máximo que se puede realizar la secuencia de envío a excepción de los límites de impuestas por la estimación del ancho de banda.  <br/> |
|AppliedBandwidthSource  <br/> |varchar (256)  <br/> |Origen de la punta de ancho de banda que se imponen. Describe el límite de ancho de banda procedencia (por ejemplo, "Servidor de directivas de", "Activar el servidor" o "Modalidad").  <br/> |
|Autor de llamada  <br/> |bit  <br/> |Indica si se han recibido métricas desde el autor de la llamada; 1 es Sí, 0 es no.  <br/> |
|Destinatario de la llamada  <br/> |bit  <br/> |Indica si se han recibido métricas desde el destinatario de la llamada; 1 es Sí, 0 es no.  <br/> |
|MidCallReport  <br/> |bit  <br/> |Indica si el informe es para una parte de la llamada o para la llamada completa.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |Indica si una llamada se clasificó como una llamada deficiente (1) o como una buena llamada (0).  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Indica si el autor de la llamada se conectó a la red con el protocolo de (conectividad ICE).  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Indica si el usuario llamado se conectó a la red con el protocolo de (conectividad ICE).  <br/> |
   

