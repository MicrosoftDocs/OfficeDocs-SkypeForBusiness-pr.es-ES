---
title: Tabla MediaLine
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Cada registro representa una línea multimedia. (Una sesión de audio normalmente contiene una línea de medios de audio. Una sesión de audio y vídeo (A/V) normalmente contiene una línea de medios de audio y una línea de medios de vídeo, aunque la sesión puede contener dos líneas de medios de vídeo si se usa un dispositivo de conferencia o si se usa la vista Galería.
ms.openlocfilehash: 99a54fe7a4ee4e91506069873c98d423b9069f06
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802770"
---
# <a name="medialine-table"></a>Tabla MediaLine
 
Cada registro representa una línea multimedia. (Una sesión de audio normalmente contiene una línea de medios de audio. Una sesión de audio y vídeo (A/V) normalmente contiene una línea de medios de audio y una línea de medios de vídeo, aunque la sesión puede contener dos líneas de medios de vídeo si se usa un dispositivo de conferencia o si se usa la vista Galería.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal  <br/> |A la que se hace referencia desde [la tabla Session](session.md).  <br/> |
|**SessionSeq** <br/> |entero  <br/> |Principal  <br/> |A la que se hace referencia desde [la tabla Session](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |0 es el audio principal, 1 es vídeo principal y 2 es vídeo panorámico, 3 es uso compartido de aplicaciones/escritorio, 16 es uso compartido de pantalla basado en vídeo (VbSS). Esta etiqueta debe ser única en una sola sesión.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Esta columna está presente pero no se usa en Microsoft Lync Server 2013. La información sobre la conectividad usada para una línea de medios se captura en las columnas CallerConnectivityICE y CalleeConnectivityICE.  <br/> |
|**CallerIceWarningFlags** <br/> |entero  <br/> | <br/> |Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en marcas de bits. Para obtener más información, consulte la especificación del protocolo de servidor de supervisión de calidad de  *la experiencia,*  disponible para su descarga. <br/> |
|**CalleeIceWarningFlags** <br/> |entero  <br/> | <br/> |Igual que CallerIceWarningFlags, pero en el lado del destinatario de la llamada. Para obtener más información, consulte la especificación del protocolo de servidor de supervisión de calidad de  *la experiencia,*  disponible para su descarga. <br/> |
|**Seguridad** <br/> |tinyint  <br/> | <br/> |El perfil de seguridad en uso. 0 es NONE, 1 es SRTP, 2 es V1.  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 es UDP, 1 es TCP.  <br/> |
|**CallerIPAddr** <br/> |entero  <br/> |Externo  <br/> |Dirección IP del autor de la llamada. Vea la [tabla IPAddress para](ipaddress.md) obtener más información. <br/> |
|**CallerPort** <br/> |entero  <br/> | <br/> | Puerto del autor de la llamada. <br/> |
|**CallerSubnet** <br/> |entero  <br/> | Externo <br/> |Subred del autor de la llamada. Vea la [tabla IPAddress para](ipaddress.md) obtener más información. <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |El valor 1 significa que el autor de la llamada está dentro de la red de empresa, 0 significa que se encuentra fuera.  <br/> |
|**CallerMacAddress** <br/> |entero  <br/> |Externo  <br/> |La dirección mac del autor de la llamada, a la que se hace referencia desde [la tabla MacAddress](macaddress.md).  <br/> |
|**CallerRelayIPAddr** <br/> |entero  <br/> |Externo  <br/> |Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Vea la [tabla IPAddress para](ipaddress.md) obtener más información. <br/> |
|**CallerRelayPort** <br/> |entero  <br/> | <br/> |Puerto usado en el servicio perimetral A/V por el autor de la llamada.  <br/> |
|**CallerCaptureDev** <br/> |entero  <br/> |Externo  <br/> |Dispositivo de captura usado por el autor de la llamada. A la que se hace referencia desde [la tabla Dispositivo](device.md).  <br/> |
|**CallerRenderDev** <br/> |entero  <br/> |Externo  <br/> |Dispositivo de representación usado por el autor de la llamada. A la que se hace referencia desde [la tabla Dispositivo](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |entero  <br/> |Externo  <br/> |Controlador del dispositivo de captura del autor de la llamada, al que se hace referencia desde la [tabla DeviceDriver](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |entero  <br/> |Externo  <br/> |Controlador del dispositivo de representación del autor de la llamada, al que se hace referencia desde la [tabla DeviceDriver](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Externo  <br/> |Indica cómo se conectó el autor de la llamada a la red. Los valores se obtienen de la [tabla NetworkConnectionDetail](networkconnectiondetail.md). Los valores típicos son 0 para una conexión cableada' 1 para una conexión WiFi; y 3 para una conexión Ethernet.  <br/> |
|**CallerBssid** <br/> |entero  <br/> |Externo  <br/> |BSSID del autor de la llamada si se usa conexión inalámbrica. Se hace referencia desde [la tabla MacAddress](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||El vínculo del autor de la llamada. El valor 1 indica una red privada virtual (VPN) y 0, otra red diferente.  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||La velocidad del vínculo de red, en bps, para el extremo del autor de la llamada.  <br/> |
|**CalleeIPAddr** <br/> |entero  <br/> |Externo  <br/> |Dirección IP del receptor de llamadas. Vea la [tabla IPAddress para](ipaddress.md) obtener más información. <br/> |
|**CalleePort** <br/> |bit  <br/> ||Puerto usado por el receptor de llamadas.  <br/> |
|**CalleeSubnet** <br/> |entero  <br/> |Externo  <br/> |Subred del destinatario de la llamada. Vea la [tabla IPAddress para](ipaddress.md) obtener más información. <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 significa que el receptor de llamadas está dentro de la red de empresa, 0 significa que el receptor de llamadas está fuera de la red.  <br/> |
|**CalleeMacAddress** <br/> |entero  <br/> |Externo  <br/> |Dirección Mac del destinatario de la llamada. A la que se hace referencia desde [la tabla MacAddress](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |entero  <br/> |Externo  <br/> |Dirección IP del servicio perimetral A/V usado por el receptor de llamadas. Vea la [tabla IPAddress para](ipaddress.md) obtener más información. <br/> |
|**CalleeRelayPort** <br/> |entero  <br/> | <br/> |Puerto usado en el servicio perimetral A/V por el receptor de llamadas.  <br/> |
|**CalleeCaptureDev** <br/> |entero  <br/> |externo  <br/> |Dispositivo de captura usado por el receptor de llamadas. A la que se hace referencia desde [la tabla Dispositivo](device.md).  <br/> |
|**CalleeRenderDev** <br/> |entero  <br/> |Externo  <br/> |Dispositivo de representación usado por el receptor de llamadas. A la que se hace referencia desde [la tabla Dispositivo](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |entero  <br/> |Externo  <br/> |Controlador del dispositivo de captura del receptor de llamadas. Referencia desde la [tabla DeviceDriver](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |Externo  <br/> |Controlador del dispositivo de representación del receptor de llamadas. Referencia desde la [tabla DeviceDriver](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Externo  <br/> |Indica cómo se conectó el destinatario de la llamada a la red. Los valores se obtienen de la [tabla NetworkConnectionDetail](networkconnectiondetail.md). Los valores típicos son 0 para una conexión cableada' 1 para una conexión WiFi; y 3 para una conexión Ethernet.  <br/> |
|**CalleeBssid** <br/> |entero  <br/> |Externo  <br/> |BSSID del destinatario de la llamada si se usa una conexión inalámbrica. Se hace referencia desde [la tabla MacAddress](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |El vínculo del receptor de llamadas; 1 es una red privada virtual (VPN), 0 no es VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |La velocidad del vínculo de red, en bps, para el extremo del receptor de llamadas.  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).  <br/> |
|**AppliedBandwidthLimit** <br/> |entero  <br/> ||Este es el ancho de banda real que se aplica a la secuencia del lado de envío dadas varias configuraciones de directiva (TURN, API, SDP, Servidor de directivas, entre otros). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Origen del límite de ancho de banda impuesto. Describe de dónde viene el límite de ancho de banda ("Servidor de directivas", "Servidor TURN", "Modalidad", y así sucesivamente). Referencia de la [tabla AppliedBandwidthSource](appliedbandwidthsource.md).  <br/> |
|**Caller** <br/> |bit  <br/> | <br/> |Indica si se recibieron métricas del autor de la llamada; 1 es sí, un valor nulo es no.  <br/> |
|**Destinatario de la llamada** <br/> |bit  <br/> | <br/> |Indica si se recibieron métricas del receptor de llamadas; 1 es sí, un valor nulo es no.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Indica si el informe es para una parte de la sesión o para la sesión completa.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Indica si una llamada se ha clasificado como mala (valor de 1) o como una buena llamada (0).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerReiveLocalIPAddr** <br/> |entero  <br/> |Externo  <br/> |Dirección IP reflexiva del usuario que ha realizado la llamada. En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |entero  <br/> |Externo  <br/> |Descripción del dispositivo para el controlador wi-fi empleado por el usuario que llamó.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |entero  <br/> |Externo  <br/> |Número de versión del controlador de WiFi empleado por el usuario que llamó.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleReiveLocalIPAddr** <br/> |entero  <br/> |Externo  <br/> |Dirección IP reflexiva del usuario que recibió la llamada. En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |entero  <br/> |Externo  <br/> |Descripción del dispositivo para el controlador wi-fi empleado por el usuario que recibió la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |entero  <br/> |Externo  <br/> |Número de versión del controlador de WiFi empleado por el usuario que recibió la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

