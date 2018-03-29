---
title: Tabla MediaLine
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Cada registro representa una línea de media. (Normalmente una sesión de audio contiene una línea de audio multimedia. Uno de audio y vídeo (A / V) sesión normalmente contiene una línea de media audio y una línea de vídeo multimedia, aunque la sesión puede contener dos líneas de vídeo si se utiliza un dispositivo de conferencias o si se utiliza la vista Galería.
ms.openlocfilehash: 03da40b97c6a067f13a9855cd51b1bbb4780f2ad
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="medialine-table"></a>Tabla MediaLine
 
Cada registro representa una línea de media. (Normalmente una sesión de audio contiene una línea de audio multimedia. Uno de audio y vídeo (A / V) sesión normalmente contiene una línea de media audio y una línea de vídeo multimedia, aunque la sesión puede contener dos líneas de vídeo si se utiliza un dispositivo de conferencias o si se utiliza la vista Galería.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Referencia de la [tabla de sesiones](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referencia de la [tabla de sesiones](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0 es audio principal 1 vídeo principal y 2 es el vídeo panorámica, es 3 es de aplicación o escritorio compartido. Esta etiqueta debe ser única dentro de una sola sesión.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Esta columna está presente pero no se utilizan en Microsoft Lync Server 2013. Se captura información acerca de la conectividad utilizada para una línea de media en las columnas CallerConnectivityICE y CalleeConnectivityICE.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en indicadores de bits. Para obtener más información, consulte la *Calidad de la experiencia de supervisión Server especificación del protocolo* , disponible para su descarga. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Igual que CallerIceWarningFlags, pero en el lado del destinatario. Para obtener más información, consulte la *Calidad de la experiencia de supervisión Server especificación del protocolo* , disponible para su descarga. <br/> |
|**Seguridad** <br/> |tinyint  <br/> | <br/> |El perfil de seguridad en uso. 0 es NONE, 1 es SRTP, 2 es V1.  <br/> |
|**Transporte** <br/> |tinyint  <br/> | <br/> |0 es UDP, 1 es TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Externa  <br/> |Dirección IP de la persona que llama. Consulte la [tabla de dirección IP](ipaddress.md) para obtener más información. <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Puerto utilizado por el llamador. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Externa <br/> |Subred del llamador. Consulte la [tabla de dirección IP](ipaddress.md) para obtener más información. <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 significa llamador está dentro de la red empresarial, 0 significa que el llamador está fuera de la red.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Externa  <br/> |Dirección mac del llamador, referenciada de [tabla de dirección MAC](macaddress.md).  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Externa  <br/> |Dirección IP del servicio V perimetral se utiliza por el llamador. Consulte la [tabla de dirección IP](ipaddress.md) para obtener más información. <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Puerto que se utiliza en el A / V borde de servicio por el llamador.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Externa  <br/> |Capturar los dispositivos utilizados por el llamador. Referencia de la [tabla del dispositivo](device.md).  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Externa  <br/> |Representar los dispositivos utilizados por el llamador. Referencia de la [tabla del dispositivo](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Externa  <br/> |Controlador para dispositivo de captura del llamador, referenciado de la [tabla DeviceDriver](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Externa  <br/> |Controlador para dispositivo de representación del llamador, hace referenciado en la [tabla DeviceDriver](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Externa  <br/> |Indica cómo el llamador conectado a la red. Los valores se obtienen de la [tabla NetworkConnectionDetail](networkconnectiondetail.md). Los valores típicos son 0 para una conexión por cable ' 1 para una conexión WiFi; y 3 para una conexión Ethernet.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Externa  <br/> |Llamador 's BSSID si se utiliza wireless. Referencia de [tabla de dirección MAC](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||Vínculo del llamador. 1 es una red privada virtual (VPN), 0 es no VPN.  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||La velocidad de vínculo de red, en bps, para el extremo del llamador.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Externa  <br/> |Dirección IP del receptor de la llamada. Consulte la [tabla de dirección IP](ipaddress.md) para obtener más información. <br/> |
|**CalleePort** <br/> |bit  <br/> ||Puerto utilizado por el receptor de la llamada.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Externa  <br/> |Subred del destinatario de la llamada. Consulte la [tabla de dirección IP](ipaddress.md) para obtener más información. <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 receptor de la llamada está dentro de la red empresarial 0 significa, que el receptor de la llamada está fuera de la red.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Externa  <br/> |Dirección Mac de destinatario. Referencia de la [tabla de dirección MAC](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Externa  <br/> |Dirección IP de la A / servicio perimetral V usados por el receptor de la llamada. Consulte la [tabla de dirección IP](ipaddress.md) para obtener más información. <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Puerto que se utiliza en el A / V borde de servicio por el receptor de la llamada.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |externa  <br/> |Capturar los dispositivos usados por el receptor de la llamada. Referencia de la [tabla del dispositivo](device.md).  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Externa  <br/> |Representar los dispositivos usados por el receptor de la llamada. Referencia de la [tabla del dispositivo](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Externa  <br/> |Controlador para dispositivo de captura del receptor de la llamada. Referencia de la [tabla DeviceDriver](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar (256)  <br/> |Externa  <br/> |Controlador para dispositivo de procesamiento del receptor de la llamada. Referencia de la [tabla DeviceDriver](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Externa  <br/> |Indica cómo el destinatario conectado a la red. Los valores se obtienen de la [tabla NetworkConnectionDetail](networkconnectiondetail.md). Los valores típicos son 0 para una conexión por cable ' 1 para una conexión WiFi; y 3 para una conexión Ethernet.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Externa  <br/> |Destinatario de la llamada 's BSSID si se utiliza wireless. Referencia de [tabla de dirección MAC](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |Enlace del receptor de la llamada; 1 es una red privada virtual (VPN), 0 es no VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |La velocidad de vínculo de red, en bps, extremo del receptor de la llamada.  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |MOS conversación de banda estrecha de las sesiones de audio (basadas en dos secuencias de audio).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Esto es el ancho de banda real que se aplica a la secuencia de lado de envío determinado dada las distintas configuraciones de directivas (TURN, API, SDP, Policy Server etc.). Esto no es debe confundirse con el ancho de banda eficaz porque puede haber un menor ancho de banda efectivo según la estimación del ancho de banda. Se trata, básicamente, el ancho de banda máximo que se puede tomar la secuencia de envío a excepción de los límites impuestos por la estimación del ancho de banda.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Éste es el origen de la tapa del ancho de banda que se impuso. Describe el límite de ancho de banda procedencia ("Servidor de directivas", "Apagar el servidor", "Modalidad" y así sucesivamente). Referencia de la [tabla AppliedBandwidthSource](appliedbandwidthsource.md).  <br/> |
|**Autor de llamada** <br/> |bit  <br/> | <br/> |Indica si se han recibido métricas desde el llamador; 1 es Sí, es un valor nulo no.  <br/> |
|**Destinatario de la llamada** <br/> |bit  <br/> | <br/> |Indica si se han recibido métricas desde el receptor de la llamada; 1 es Sí, es un valor nulo no.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Indica si el informe es una parte de la sesión o para toda la sesión.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Indica si una llamada fue clasificada como una llamada deficiente (valor 1) o como una buena llamada (0).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Indica si el llamador conectado a la red mediante el protocolo de HIELO (establecimiento de conectividad de Internet).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Indica si el llamador conectado a la red mediante el protocolo de HIELO (establecimiento de conectividad de Internet).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Externa  <br/> |Dirección IP reflexiva del usuario que realizó la llamada. En organizaciones que utilizan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Externa  <br/> |Descripción de dispositivo del controlador WiFi empleadas por el usuario que realizó la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Externa  <br/> |Número de versión del controlador WiFi empleadas por el usuario que realizó la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Externa  <br/> |Dirección IP reflexiva del usuario que ha recibido la llamada. En organizaciones que utilizan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Externa  <br/> |Descripción de dispositivo del controlador WiFi empleadas por el usuario que recibe la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Externa  <br/> |Número de versión del controlador WiFi empleadas por el usuario que recibe la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

