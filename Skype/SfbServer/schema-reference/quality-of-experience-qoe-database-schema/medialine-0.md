---
title: Tabla MediaLine
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Cada registro representa una línea de medios. (Normalmente, una sesión de audio contiene una línea de medios de audio. Uno de audio y vídeo (A / V) sesión normalmente contiene una línea de medios de audio y una línea de medios de vídeo, aunque la sesión puede contener dos líneas de medios de vídeo si se usa un dispositivo para conferencias o si se usa la vista de galería.
ms.openlocfilehash: 11c309091211ce0bc480fa032e0f1dbbbbf533cd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212547"
---
# <a name="medialine-table"></a>Tabla MediaLine
 
Cada registro representa una línea de medios. (Normalmente, una sesión de audio contiene una línea de medios de audio. Uno de audio y vídeo (A / V) sesión normalmente contiene una línea de medios de audio y una línea de medios de vídeo, aunque la sesión puede contener dos líneas de medios de vídeo si se usa un dispositivo para conferencias o si se usa la vista de galería.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Referencia de la [tabla de sesión](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referencia de la [tabla de sesión](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0 es audio principal, 1 es vídeo principal y 2 es vídeo panorámico, 3 es el uso compartido de aplicaciones y escritorio, 16 es vídeo en función de pantalla de uso compartido (VbSS). Esta etiqueta debe ser única dentro de una sola sesión.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Esta columna está presente pero no se utilizan en Microsoft Lync Server 2013. Información acerca de la conectividad utilizada para una línea de medios se captura en las columnas CallerConnectivityICE y CalleeConnectivityICE.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Información sobre el proceso de establecimiento interactivo de conectividad (ICE) que se describe en los indicadores de bits. Para obtener información detallada, consulte la *Calidad de experiencia Monitoring Server especificación del protocolo* , disponible para su descarga. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Igual que CallerIceWarningFlags, pero en el lado del destinatario de la llamada. Para obtener información detallada, consulte la *Calidad de experiencia Monitoring Server especificación del protocolo* , disponible para su descarga. <br/> |
|**Seguridad** <br/> |tinyint  <br/> | <br/> |El perfil de seguridad en uso. 0 es NONE, 1 es SRTP, 2 es V1.  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 es UDP, 1 es TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Externa  <br/> |Dirección IP del autor de la llamada. Vea la [tabla IPAddress](ipaddress.md) para obtener más información. <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Puerto usado por el autor de la llamada. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Externa <br/> |Subred del autor de la llamada. Vea la [tabla IPAddress](ipaddress.md) para obtener más información. <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 significa que es autor de la llamada dentro de la red de empresa, 0 significa que el autor de la llamada está fuera de la red.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Externa  <br/> |Dirección mac del autor de la llamada, de [MacAddress table](macaddress.md).  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Externa  <br/> |Dirección IP del servicio perimetral A/v utilizado por el autor de la llamada. Vea la [tabla IPAddress](ipaddress.md) para obtener más información. <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Puerto usado en el servicio perimetral A/v por el autor de la llamada.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Externa  <br/> |Capturar dispositivo utilizado por el autor de la llamada. Referencia de la [tabla del dispositivo](device.md).  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Externa  <br/> |Dispositivo usado por el autor de la llamada de la presentación. Referencia de la [tabla del dispositivo](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Externa  <br/> |Controlador de dispositivo de captura del autor de la llamada, de la [tabla DeviceDriver](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Externa  <br/> |Controlador de dispositivo de presentación del autor de la llamada, de la [tabla DeviceDriver](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Externa  <br/> |Indica cómo el autor de la llamada se conecta a la red. Los valores se obtienen de la [tabla NetworkConnectionDetail](networkconnectiondetail.md). Los valores típicos son 0 para una conexión por cable ' 1 para una conexión WiFi; y 3 para una conexión Ethernet.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Externa  <br/> |Del autor de la BSSID si se usan inalámbricos. Referencia de [MacAddress table](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||Vínculo el autor de la llamada. 1 es una red privada virtual (VPN), 0 es diferente de VPN.  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||La velocidad de vínculo de red, en bps, para el extremo del llamador.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Externa  <br/> |Dirección IP del destinatario de la llamada. Vea la [tabla IPAddress](ipaddress.md) para obtener más información. <br/> |
|**CalleePort** <br/> |bit  <br/> ||Puerto usado por el destinatario de la llamada.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Externa  <br/> |Subred del destinatario de la llamada. Vea la [tabla IPAddress](ipaddress.md) para obtener más información. <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 significa destinatario de la llamada está dentro de la red de empresa, 0 significa que el destinatario de la llamada está fuera de la red.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Externa  <br/> |Dirección Mac de destinatario de la llamada. Referencia de la [tabla MacAddress](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Externa  <br/> |Dirección IP del servicio perimetral A/v que usa el destinatario de la llamada. Vea la [tabla IPAddress](ipaddress.md) para obtener más información. <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Puerto usado en el servicio perimetral A/v por el destinatario de la llamada.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |externa  <br/> |Capturar dispositivo utilizado por el destinatario de la llamada. Referencia de la [tabla del dispositivo](device.md).  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Externa  <br/> |Dispositivo usado por el destinatario de la llamada de la presentación. Referencia de la [tabla del dispositivo](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Externa  <br/> |Controlador de dispositivo de captura del destinatario de la llamada. Referencia de [DeviceDriver table](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar (256)  <br/> |Externa  <br/> |Controlador de dispositivo de presentación del destinatario de la llamada. Referencia de [DeviceDriver table](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Externa  <br/> |Indica cómo el destinatario de la llamada se conecta a la red. Los valores se obtienen de la [tabla NetworkConnectionDetail](networkconnectiondetail.md). Los valores típicos son 0 para una conexión por cable ' 1 para una conexión WiFi; y 3 para una conexión Ethernet.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Externa  <br/> |Del destinatario de la BSSID si se usan inalámbricos. Referencia de [MacAddress table](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |Vínculo del destinatario de la llamada; 1 es una red privada virtual (VPN), 0 es diferente de VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |La velocidad de vínculo de red, en bps, para el extremo del destinatario de la llamada.  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |MOS de conversación de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Este es el ancho de banda real que se aplica a la secuencia de lado de envío determinado dada distintas configuraciones de directivas (activar, API, SDP, servidor de directivas y así sucesivamente). Esto no es debe confundirse con el ancho de banda eficaz debido a que puede haber un ancho de banda eficaz inferior en función de la estimación del ancho de banda. Esto es, básicamente, el ancho de banda máximo que se puede realizar la secuencia de envío a excepción de los límites de impuestas por la estimación del ancho de banda.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Éste es el origen de la punta de ancho de banda que se imponen. Describe el límite de ancho de banda procedencia ("Servidor de directivas de", "Activar el servidor", "Modalidad" y así sucesivamente). Referencia de la [tabla AppliedBandwidthSource](appliedbandwidthsource.md).  <br/> |
|**Autor de llamada** <br/> |bit  <br/> | <br/> |Indica si se han recibido métricas desde el autor de la llamada; 1 es Sí, es un valor nulo no.  <br/> |
|**Destinatario de la llamada** <br/> |bit  <br/> | <br/> |Indica si se han recibido métricas desde el destinatario de la llamada; 1 es Sí, es un valor nulo no.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Indica si el informe es para una parte de la sesión o para toda la sesión.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Indica si una llamada se clasificó como una llamada deficiente (valor 1) o como una buena llamada (0).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Indica si el autor de la llamada se conectó a la red con el protocolo de (conectividad ICE).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Indica si el autor de la llamada se conectó a la red con el protocolo de (conectividad ICE).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Externa  <br/> |Dirección IP reflexiva del usuario que realizó la llamada. En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Externa  <br/> |Descripción de dispositivo del controlador WiFi utilizado por el usuario que realizó la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Externa  <br/> |Número de versión del controlador WiFi utilizado por el usuario que realizó la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Externa  <br/> |Dirección IP reflexiva del usuario que recibió la llamada. En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Externa  <br/> |Descripción de dispositivo del controlador WiFi utilizado por el usuario que recibió la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Externa  <br/> |Número de versión del controlador WiFi utilizado por el usuario que recibió la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

