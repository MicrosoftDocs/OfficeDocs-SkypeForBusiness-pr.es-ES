---
title: Tabla Session
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Cada registro representa una sesión que implica audio o audio y vídeo. Contiene información general acerca de la sesión. Una sesión se define como un cuadro de diálogo de protocolo de inicio de sesión (SIP) de audio o vídeo entre dos extremos.
ms.openlocfilehash: 24acf23d2dab2dbc4b6586e40aa49cba632d6a68
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="session-table"></a>Tabla Session
 
Cada registro representa una sesión que implica audio o audio y vídeo. Contiene información general acerca de la sesión. Una sesión se define como un cuadro de diálogo de protocolo de inicio de sesión (SIP) de audio o vídeo entre dos extremos.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Se hace referencia desde el [cuadro de diálogo](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Se hace referencia desde el [cuadro de diálogo](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Externa  <br/> |Clave de la conferencia. Referencia de la [mesa de conferencias](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Externa  <br/> |Clave de correlación. Referencia de la [tabla SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Categoría del cuadro de diálogo; 0 es Skype para Business Server pierna de servidor de mediación; 1 es el servidor de mediación pierna de puerta de enlace PSTN.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Marcador que indica si la llamada se ha omitido o no.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Este campo, si está presente, indica por qué una llamada no se ha omitido aunque identificadores correspondía a la omisión. Skype para Business Server, se define un único valor.  <br/> 0 x 0001 - ID de omisión desconocido para el adaptador de red predeterminado.  <br/> |
|**Hora de inicio** <br/> |datetime  <br/> | <br/> |Tiempo de inicio de llamada.  <br/> |
|**Hora de finalización** <br/> |datetime  <br/> | <br/> |Llame a hora de finalización.  <br/> |
|**CallerPool** <br/> |int  <br/> |Externa  <br/> |El grupo del llamador. Referencia de la [tabla de grupo](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Externa  <br/> |El grupo del receptor de la llamada. Referencia de la [tabla de grupo](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Externa  <br/> |URI del SIP en el SIP afirmado p identidad (PAI) del extremo receptor. Referencia de la [tabla de usuario](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Externa  <br/> |Llamador del identificador URI. Referencia de la [tabla de usuario](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Externa  <br/> |Extremo del llamador. Referencia de la [tabla de extremo](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Externa  <br/> |Agente de usuario del llamador. Referencia de la [tabla UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||La prioridad de esta llamada.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Esta columna está desusada y no se utiliza en Skype para Business Server. En su lugar, esta información se informa sobre las bases de una línea de por medio. Consulte la [tabla de MediaLine](medialine-0.md) para obtener más información. <br/> |
|**CallerPAI** <br/> |int  <br/> |Externa  <br/> |P-afirmado-identidad del usuario que realizó la llamada. La identidad afirmado P (PAI) se utiliza para transmitir la verdadera identidad del usuario que realizó la llamada.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Externa  <br/> |Extremo que recibe la llamada.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Externa  <br/> |Agente de usuario empleada por el usuario que ha recibido la llamada. Agentes de usuario representan el dispositivo de extremo de cliente.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Externa  <br/> |URI de SIP del usuario que ha recibido la llamada.  <br/> |
   

