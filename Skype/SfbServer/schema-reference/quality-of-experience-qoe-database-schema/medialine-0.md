---
title: Tabla MediaLine
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Cada registro representa una línea de medios. (Una sesión de audio normalmente contiene una línea multimedia de audio. Una sesión de audio y vídeo (A/V) normalmente contiene una línea de medio de audio y una línea de medio de vídeo, aunque la sesión podría contener dos líneas de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería.
ms.openlocfilehash: f9ededade35e5654a89b68343f44094f4319ae70
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294897"
---
# <a name="medialine-table"></a>Tabla MediaLine
 
Cada registro representa una línea de medios. (Una sesión de audio normalmente contiene una línea multimedia de audio. Una sesión de audio y vídeo (A/V) normalmente contiene una línea de medio de audio y una línea de medio de vídeo, aunque la sesión podría contener dos líneas de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla sesión](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla sesión](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0 es el audio principal, 1 es el vídeo principal y 2 es vídeo panorámico, 3 es uso compartido de aplicaciones y escritorio, 16 es pantalla compartida basada en vídeo (VbSS). Esta etiqueta debe ser única dentro de una sola sesión.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Esta columna está presente pero no se usa en Microsoft Lync Server 2013. La información sobre la conectividad usada para una línea de medios se captura en las columnas CallerConnectivityICE y CalleeConnectivityICE.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en marcas de bits. Para obtener más información, consulte la *especificación de protocolo de servidor calidad de la supervisión* , disponible para descargar. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Igual que CallerIceWarningFlags, pero en el lado del destinatario de la llamada. Para obtener más información, consulte la *especificación de protocolo de servidor calidad de la supervisión* , disponible para descargar. <br/> |
|**Seguridad** <br/> |tinyint  <br/> | <br/> |Perfil de seguridad en uso. 0 es ninguno, 1 es SRTP, 2 es v1.  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 es UDP, 1 es TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Extranjero  <br/> |Dirección IP del autor de la llamada. Para obtener más información, consulte la [tabla dirección IP](ipaddress.md) . <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Puerto usado por el autor de la llamada. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Extranjero <br/> |La subred de la persona que llama. Para obtener más información, consulte la [tabla dirección IP](ipaddress.md) . <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 significa que la persona que llama está dentro de la red de la empresa, 0 significa que la persona que llama está fuera de la red.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Extranjero  <br/> |Dirección Mac de la persona que llama, a la que se hace referencia desde la [tabla MacAddress](macaddress.md).  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Extranjero  <br/> |Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Para obtener más información, consulte la [tabla dirección IP](ipaddress.md) . <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Puerto usado en el servicio de borde de A/V por el autor de la llamada.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Extranjero  <br/> |Dispositivo de captura usado por el autor de la llamada. Se hace referencia a ella desde la [tabla de dispositivos](device.md).  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Extranjero  <br/> |Dispositivo de representación usado por la persona que llama. Se hace referencia a ella desde la [tabla de dispositivos](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Extranjero  <br/> |Controlador para el dispositivo de captura de la persona que llama, al que se hace referencia desde la [tabla DeviceDriver](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Extranjero  <br/> |Controlador del dispositivo de representación de la persona que llama, al que se hace referencia desde la [tabla DeviceDriver](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Extranjero  <br/> |Indica cómo se conectó a la red. Los valores se obtienen de la [tabla NetworkConnectionDetail](networkconnectiondetail.md). Los valores típicos son 0 para una conexión cableada ' 1 para una conexión WiFi; y 3 para una conexión Ethernet.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Extranjero  <br/> |BSSID del autor de la llamada si se usa una conexión inalámbrica. Se hace referencia desde la [tabla MacAddress](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||Vínculo de la persona que llama. 1 es una red privada virtual (VPN) y 0 no es una VPN.  <br/> |
|**CallerLinkSpeed** <br/> |decimal (18; 0)  <br/> ||La velocidad del vínculo de red, en bps, para el punto final de la llamada.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Extranjero  <br/> |Dirección IP del receptor de la llamada. Para obtener más información, consulte la [tabla dirección IP](ipaddress.md) . <br/> |
|**CalleePort** <br/> |bit  <br/> ||Puerto usado por el receptor de la llamada.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Extranjero  <br/> |Subred del destinatario de la llamada. Para obtener más información, consulte la [tabla dirección IP](ipaddress.md) . <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 significa que el receptor de llamadas está dentro de la red empresarial, 0 significa que el receptor de la llamada está fuera de la red.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Extranjero  <br/> |Dirección Mac de la llamada. Se hace referencia a ella desde la [tabla MacAddress](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Extranjero  <br/> |Dirección IP del servicio perimetral A/V que usa el receptor de la llamada. Para obtener más información, consulte la [tabla dirección IP](ipaddress.md) . <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Puerto usado en el servicio de borde A/V por el receptor de la llamada.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |extranjero  <br/> |Dispositivo de captura usado por el receptor de la llamada. Se hace referencia a ella desde la [tabla de dispositivos](device.md).  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Extranjero  <br/> |Dispositivo de representación usado por el receptor de la llamada. Se hace referencia a ella desde la [tabla de dispositivos](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Extranjero  <br/> |Controlador para el dispositivo de captura del receptor de la llamada. Se hace referencia desde la [tabla DeviceDriver](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |VARCHAR (256)  <br/> |Extranjero  <br/> |Controlador del dispositivo de representación del receptor de la llamada. Se hace referencia desde la [tabla DeviceDriver](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Extranjero  <br/> |Indica cómo el destinatario de la llamada está conectado a la red. Los valores se obtienen de la [tabla NetworkConnectionDetail](networkconnectiondetail.md). Los valores típicos son 0 para una conexión cableada ' 1 para una conexión WiFi; y 3 para una conexión Ethernet.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Extranjero  <br/> |BSSID del destinatario de la llamada si se usa la tecnología inalámbrica. Se hace referencia desde la [tabla MacAddress](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |Vínculo del receptor de la llamada; 1 es una red privada virtual (VPN) y 0 no es una VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |decimal (18; 0)  <br/> | <br/> |La velocidad del vínculo de red, en bps, para el extremo del receptor de la llamada.  <br/> |
|**ConversationalMOS** <br/> |decimal (3, 2)  <br/> | <br/> |OP de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Este es el ancho de banda real aplicado a la transmisión de la parte de envío proporcionada, que proporciona varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.). Esto no se debe confundir con el ancho de banda efectivo porque puede haber un ancho de banda más bajo según el cálculo de ancho de banda. Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Este es el origen del límite de ancho de banda que se impone. Describe dónde viene el límite de ancho de banda ("servidor de directivas", "TURN Server", "Modación", etc.). Se hace referencia a ella desde la [tabla AppliedBandwidthSource](appliedbandwidthsource.md).  <br/> |
|**Autor de llamada** <br/> |bit  <br/> | <br/> |Indica si se recibieron las métricas de la persona que llama; 1 es sí, un valor nulo es no.  <br/> |
|**Destinatario de la llamada** <br/> |bit  <br/> | <br/> |Indica si se han recibido métricas del receptor de la llamada; 1 es sí, un valor nulo es no.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Indica si el informe es para una parte de la sesión o para la sesión completa.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Indica si una llamada se ha clasificado como una llamada deficiente (valor de 1) o como una buena llamada (0).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Indica si la persona que llama se ha conectado a la red mediante el protocolo ICE (establecimiento de conectividad de Internet).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Indica si la persona que llama se ha conectado a la red mediante el protocolo ICE (establecimiento de conectividad de Internet).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Extranjero  <br/> |Dirección IP reflexiva del usuario que realizó la llamada. En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Extranjero  <br/> |Descripción del dispositivo para el controlador WiFi empleado por el usuario que realizó la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Extranjero  <br/> |Número de versión del controlador WiFi empleado por el usuario que realizó la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Extranjero  <br/> |Dirección IP reflexiva del usuario que recibió la llamada. En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Extranjero  <br/> |Descripción del dispositivo para el controlador WiFi empleado por el usuario que recibió la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Extranjero  <br/> |Número de versión del controlador WiFi empleado por el usuario que recibió la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

