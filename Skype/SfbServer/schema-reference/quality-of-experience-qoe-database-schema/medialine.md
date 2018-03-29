---
title: Vista de MediaLine
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: La vista MediaLine almacena información acerca de cada línea de medios en la base de datos. Una sesión de audio normalmente contiene una línea de audio multimedia. Uno de audio y vídeo (A / V) sesión normalmente contiene una línea de media audio y una línea de vídeo; Sin embargo, la sesión puede contener dos líneas de vídeo si se utiliza un dispositivo de conferencias o si se utiliza la vista Galería. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 11905ae9ccc67bb166702f4d43f19d1b52bfbe7b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="medialine-view"></a>Vista de MediaLine
 
La vista MediaLine almacena información acerca de cada línea de medios en la base de datos. Una sesión de audio normalmente contiene una línea de audio multimedia. Uno de audio y vídeo (A / V) sesión normalmente contiene una línea de media audio y una línea de vídeo; Sin embargo, la sesión puede contener dos líneas de vídeo si se utiliza un dispositivo de conferencias o si se utiliza la vista Galería. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**detalles**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Ofrece información sobre el proceso de establecimiento interactivo de conectividad (ICE) en bits indicadores para el llamador. Para obtener información detallada, consulte la calidad de experiencia Supervisar servidor especificación del protocolo.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Ofrece información sobre el proceso de establecimiento interactivo de conectividad (ICE) en bits indicadores para el destinatario. Para obtener información detallada, consulte la calidad de experiencia Supervisar servidor especificación del protocolo.  <br/> |
|Seguridad  <br/> |tinyint  <br/> |Perfil de seguridad en uso. 0 es NONE, 1 es SRTP, 2 es V1.  <br/> |
|Transport  <br/> |tinyint  <br/> |Tipo de transporte. 0 es UDP, 1 es TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Dirección IP de la persona que llama. Esto puede ser la dirección IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Puerto utilizado por el llamador.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica si el llamador está dentro de la red de la organización. 1 significa que el llamador está dentro de la red empresarial. 0 significa que el llamador está fuera de la red.  <br/> |
|CallerMacAddress  <br/> |varchar (256)  <br/> |Dirección MAC de la interfaz de red utilizada por el llamador.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Dirección IP del servicio V perimetral se utiliza por el llamador. Consulte la [tabla de dirección IP](ipaddress.md) para obtener más información. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Puerto que se utiliza en el servicio V perimetral se utiliza por el llamador.  <br/> |
|CallerReflexiveIPAddr  <br/> |var(50)  <br/> |Dirección IP del llamador notifica el A / servicio V perimetral. Esta dirección puede ser diferente que la CallerIPAddr si el cliente se encuentra detrás de un NAT por ejemplo.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nombre de dispositivo de captura del llamador.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nombre de dispositivo de representación del llamador.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de captura del llamador.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de representación del llamador.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |Descripción del controlador del llamador Wifi.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar (256)  <br/> |Versión del controlador de Wifi del llamador.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |Detalles de conexión de red del llamador. Consulte la [tabla de NetworkConnectionDetail](networkconnectiondetail.md) para obtener más información. <br/> |
|CallerBssid  <br/> |varchar (256)  <br/> |Basic Service Set Identifier había utilizado por llamadores de conexión WiFi.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica si el llamador conectados a través de una red privada virtual. 1 es una red privada virtual (VPN), 0 es no VPN.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Dirección IP del destinatario de la llamada. Esto puede ser la dirección IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Puerto utilizado por el destinatario.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica si el destinatario está dentro de la red de la empresa. 1 significa que es el destinatario de la llamada dentro de la red empresarial, 0 significa que el destinatario está fuera de la red.  <br/> |
|CalleeMacAddress  <br/> |varchar (256)  <br/> |Dirección MAC de la interfaz de red utilizada por el destinatario.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Dirección IP del servicio V perimetral se utiliza por el destinatario. Consulte la [tabla de dirección IP](ipaddress.md) para obtener más información. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Puerto que se utiliza en el servicio V perimetral se utiliza por el destinatario.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var(50)  <br/> |Dirección IP del destinatario notifica el A / servicio V perimetral. Esta dirección puede ser diferente que la CalleeIPAddr si el cliente se encuentra detrás de un NAT por ejemplo.  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |Nombre de dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nombre del destinatario de la llamada del dispositivo de representación.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de render del destinatario de la llamada.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar (256)  <br/> |Descripción del destinatario de la llamada del controlador de Wifi.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |Versión del controlador de Wifi del destinatario de la llamada.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |Detalles de conexión de red del destinatario. Consulte la [tabla de NetworkConnectionDetail](networkconnectiondetail.md) para obtener más información. <br/> |
|CalleeBssid  <br/> |varchar (256)  <br/> |Basic Service Set Identifier utilizado por la conexión del WiFi del destinatario de la llamada.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica si el destinatario conectados a través de una red privada virtual. 1 es una red privada virtual (VPN), 0 es no VPN.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS conversación de banda estrecha de las sesiones de audio (basadas en dos secuencias de audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Esto es el ancho de banda real que se aplica a la secuencia de lado de envío determinado dada diversas configuraciones de directiva (activar, API, SDP, Policy Server, etcetera). Esto no se debe para confundir con el ancho de banda eficaz porque puede haber un menor ancho de banda efectivo según la estimación del ancho de banda. Se trata, básicamente, el ancho de banda máximo que se puede tomar la secuencia de envío a excepción de los límites impuestos por la estimación del ancho de banda.  <br/> |
|AppliedBandwidthSource  <br/> |varchar (256)  <br/> |Origen de la tapa del ancho de banda que se impuso. Describe el límite de ancho de banda procedencia (por ejemplo, "Servidor de directivas", "Apagar el servidor" o "Modalidad").  <br/> |
|Autor de llamada  <br/> |bit  <br/> |Indica si se han recibido métricas desde el llamador; 1 es Sí, 0 es no.  <br/> |
|Destinatario de la llamada  <br/> |bit  <br/> |Indica si se han recibido métricas desde el receptor de la llamada; 1 es Sí, 0 es no.  <br/> |
|MidCallReport  <br/> |bit  <br/> |Indica si el informe es una parte de la llamada o para la llamada completa.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |Indica si una llamada fue clasificada como una llamada deficiente (1) o como una buena llamada (0).  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Indica si el llamador conectado a la red mediante el protocolo de HIELO (establecimiento de conectividad de Internet).  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Indica si la llamada al usuario conectado a la red mediante el protocolo de HIELO (establecimiento de conectividad de Internet).  <br/> |
   

