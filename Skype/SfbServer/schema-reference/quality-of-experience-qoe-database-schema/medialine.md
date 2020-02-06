---
title: Vista MediaLine
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: La vista MediaLine almacena información acerca de cada línea de medios de la base de datos. Una sesión de audio normalmente contiene una línea multimedia de audio. Una sesión de audio y vídeo (A/V) normalmente contiene una línea de medio de audio y una línea de medio de vídeo; sin embargo, la sesión podría contener dos líneas multimedia de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: b22408ddc40f1df6452895327e8a67800ef24eb9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41808198"
---
# <a name="medialine-view"></a>Vista MediaLine
 
La vista MediaLine almacena información acerca de cada línea de medios de la base de datos. Una sesión de audio normalmente contiene una línea multimedia de audio. Una sesión de audio y vídeo (A/V) normalmente contiene una línea de medio de audio y una línea de medio de vídeo; sin embargo, la sesión podría contener dos líneas multimedia de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería. Esta vista se presentó en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**sobre**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en indicadores de bits para la persona que llama. Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en marcas de bits para el destinatario de la llamada. Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.  <br/> |
|Seguridad  <br/> |tinyint  <br/> |Perfil de seguridad en uso. 0 es ninguno, 1 es SRTP, 2 es v1.  <br/> |
|Transport  <br/> |tinyint  <br/> |Tipo de transporte. 0 es UDP, 1 es TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Dirección IP del autor de la llamada. Puede ser una dirección IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Puerto usado por el autor de la llamada.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica si el autor de la llamada está dentro de la red de la organización. 1 significa que la persona que llama está dentro de la red empresarial. 0 significa que la persona que llama está fuera de la red.  <br/> |
|CallerMacAddress  <br/> |VARCHAR (256)  <br/> |Dirección MAC de la interfaz de red que llama.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Para obtener más información, consulte la [tabla dirección IP](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.  <br/> |
|CallerReflexiveIPAddr  <br/> |var (50)  <br/> |Dirección IP de la persona que llama según el servicio perimetral de A/V. Esta dirección puede ser diferente de la CallerIPAddr si el cliente se encuentra detrás de un NAT, por ejemplo.  <br/> |
|CallerCaptureDev  <br/> |VARCHAR (256)  <br/> |Nombre del dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDev  <br/> |VARCHAR (256)  <br/> |Nombre del dispositivo de representación del autor de la llamada.  <br/> |
|CallerCaptureDevDriver  <br/> |VARCHAR (256)  <br/> |Nombre del controlador del dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDevDriver  <br/> |VARCHAR (256)  <br/> |Nombre del controlador del dispositivo de representación del autor de la llamada.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |VARCHAR (256  <br/> |Descripción del controlador WIFI del autor de la llamada.  <br/> |
|CallerWifiDriverVersion  <br/> |VARCHAR (256)  <br/> |Versión del controlador WIFI del autor de la llamada.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |VARCHAR (256)  <br/> |Detalles de la conexión de red de la persona que llama. Para obtener más información, consulte la [tabla NetworkConnectionDetail](networkconnectiondetail.md) . <br/> |
|CallerBssid  <br/> |VARCHAR (256)  <br/> |Identificador del conjunto de servicios básicos usado por las personas que llaman conexión WiFi.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica si la persona que llama se ha conectado a través de una red privada virtual. 1 es una red privada virtual (VPN) y 0 no es una VPN.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Dirección IP del destinatario. Puede ser una dirección IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Puerto usado por el destinatario.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica si el destinatario de la llamada está dentro de la red empresarial. 1 significa que el destinatario de la llamada está dentro de la red de la empresa, 0 significa que el destinatario de la llamada está fuera de la red.  <br/> |
|CalleeMacAddress  <br/> |VARCHAR (256)  <br/> |Dirección MAC de la interfaz de red que usa el destinatario de la llamada.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Dirección IP del servicio perimetral A/V que usa el destinatario de la llamada. Para obtener más información, consulte la [tabla dirección IP](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Puerto usado en el servicio de borde A/V que usa el destinatario de la llamada.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var (50)  <br/> |Dirección IP del destinatario de la llamada tal y como lo indica el servicio A/V Edge. Esta dirección puede ser diferente de la CalleeIPAddr si el cliente se encuentra detrás de un NAT, por ejemplo.  <br/> |
|CalleeCaptureDev  <br/> |var (50)  <br/> |Nombre del dispositivo de captura de la persona que llama.  <br/> |
|CalleeRenderDev  <br/> |VARCHAR (256)  <br/> |Nombre del dispositivo de representación de la persona que llama.  <br/> |
|CalleeCaptureDevDriver  <br/> |VARCHAR (256)  <br/> |Nombre del controlador del dispositivo de captura.  <br/> |
|CalleeRenderDevDriver  <br/> |VARCHAR (256)  <br/> |Nombre del controlador del dispositivo de representación de la llamada.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |VARCHAR (256)  <br/> |Descripción del controlador WIFI de la persona que llama.  <br/> |
|CalleeWifiDriverVersion  <br/> |VARCHAR (256  <br/> |Versión del controlador WIFI de la persona que llama.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |VARCHAR (256)  <br/> |Detalles de la conexión de red de la persona que llama. Para obtener más información, consulte la [tabla NetworkConnectionDetail](networkconnectiondetail.md) . <br/> |
|CalleeBssid  <br/> |VARCHAR (256)  <br/> |Identificador del conjunto de servicios básicos usado por la conexión WiFi de la persona que llama.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica si el destinatario de la llamada se conecta a través de una red privada virtual. 1 es una red privada virtual (VPN) y 0 no es una VPN.  <br/> |
|ConversationalMOS  <br/> |decimal (3, 2)  <br/> |OP de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Este es el ancho de banda real que se aplica a la transmisión de la parte de envío proporcionada, dadas varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.). Esto no debe confundirse con el ancho de banda efectivo porque puede haber un ancho de banda más bajo en función de la estimación del ancho de banda. Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda.  <br/> |
|AppliedBandwidthSource  <br/> |VARCHAR (256)  <br/> |Origen del límite de ancho de banda que se impone. Describe de dónde viene el límite de ancho de banda (por ejemplo, "servidor de directivas", "convertir servidor" o "modalidad de moda").  <br/> |
|Autor de llamada  <br/> |bit  <br/> |Indica si se recibieron las métricas de la persona que llama; 1 es sí, 0 es no.  <br/> |
|Destinatario de la llamada  <br/> |bit  <br/> |Indica si se han recibido métricas del receptor de la llamada; 1 es sí, 0 es no.  <br/> |
|MidCallReport  <br/> |bit  <br/> |Indica si el informe es para una parte de la llamada o para la llamada completa.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |Indica si una llamada se ha clasificado como una llamada deficiente (1) o como una buena llamada (0).  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Indica si la persona que llama se ha conectado a la red mediante el protocolo ICE (establecimiento de conectividad de Internet).  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Indica si el usuario ha sido llamado conectado a la red mediante el protocolo ICE (establecimiento de conectividad de Internet).  <br/> |
   

