---
title: Tabla Session
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Cada registro representa una sesión que incluye audio, audio y vídeo. Contiene información general sobre la sesión. Una sesión se define como un cuadro de diálogo de protocolo de inicio de sesión (SIP) de audio o vídeo entre dos puntos de conexión.
ms.openlocfilehash: e0cd6a4523b09d8bcb7f74d6c796b46bf99ece8e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294673"
---
# <a name="session-table"></a>Tabla Session
 
Cada registro representa una sesión que incluye audio, audio y vídeo. Contiene información general sobre la sesión. Una sesión se define como un cuadro de diálogo de protocolo de inicio de sesión (SIP) de audio o vídeo entre dos puntos de conexión.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla de diálogo](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla de diálogo](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Extranjero  <br/> |Tecla de conferencia. Se hace referencia a ella desde la [tabla de conferencia](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Extranjero  <br/> |Clave de correlación. Se hace referencia a ella desde la [tabla SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Categoría de cuadro de diálogo; 0 es la pierna del servidor de Skype empresarial Server. 1 es el servidor de mediación para la puerta de la puerta de enlace RTC.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Marcador que indica si la llamada se ha omitido o no.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Este campo, si está presente, indica por qué no se omitió una llamada, incluso si los identificadores de omisión coinciden. En Skype empresarial Server, solo se define un valor.  <br/> 0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |Hora de inicio de la llamada.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Hora de finalización de la llamada.  <br/> |
|**CallerPool** <br/> |int  <br/> |Extranjero  <br/> |El grupo de la persona que llama. Se hace referencia a ella desde la [tabla Pool](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Extranjero  <br/> |La piscina del receptor de la llamada. Se hace referencia a ella desde la [tabla Pool](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Extranjero  <br/> |URI de SIP en la identidad declarada por SIP (PAI) del punto final de recepción. Se hace referencia a ella desde la [tabla de usuario](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Extranjero  <br/> |URI de la persona que llama. Se hace referencia a ella desde la [tabla de usuario](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Extranjero  <br/> |Extremo de la persona que llama. Se hace referencia a ella desde la [tabla de extremos](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Extranjero  <br/> |Agente de usuario del autor de la llamada. Se hace referencia a ella desde la [tabla UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||La prioridad de esta llamada.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Esta columna ha quedado obsoleta y no se usa en Skype empresarial Server. En su lugar, esta información se notifica en una base de líneas por medios. Para obtener más información, consulte la [tabla MediaLine](medialine-0.md) . <br/> |
|**CallerPAI** <br/> |int  <br/> |Extranjero  <br/> |P-asserted-identidad del usuario que realizó la llamada. La identidad de aserción de P (PAI) se usa para transmitir la verdadera identidad del usuario que realizó la llamada.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Extranjero  <br/> |Extremo que recibió la llamada.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Extranjero  <br/> |Agente de usuario empleado por el usuario que recibió la llamada. Los agentes de usuario representan el dispositivo de extremo cliente.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Extranjero  <br/> |URI SIP del usuario que recibió la llamada.  <br/> |
   

