---
title: Tabla Session
ms.reviewer: ''
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
ms.openlocfilehash: 7a0ea3f9753529c22299ef46017b863c314319b5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212379"
---
# <a name="session-table"></a>Tabla Session
 
Cada registro representa una sesión que implica audio o audio y vídeo. Contiene información general acerca de la sesión. Una sesión se define como un cuadro de diálogo de protocolo de inicio de sesión (SIP) de audio o vídeo entre dos extremos.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Referencia de la [tabla del cuadro de diálogo](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referencia de la [tabla del cuadro de diálogo](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Externa  <br/> |Clave de conferencia. Referencia de la [mesa de conferencia](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Externa  <br/> |Clave de correlación. Referencia de la [tabla SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Categoría del diálogo; 0 es Skype para Business Server tramo de servidor de mediación; 1 es el servidor de mediación tramo de puerta de enlace de RTC.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Marca que indica si la llamada se pasó o no.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||En este campo, si está presente, indica ¿por qué una llamada no se pasó incluso si el desvío de los identificadores de coinciden. Para Skype para Business Server, se define un solo valor.  <br/> 0 x 0001 - identificador de omisión desconocido para el adaptador de red predeterminado.  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |Hora de inicio de la llamada.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Hora de finalización de llamadas.  <br/> |
|**CallerPool** <br/> |int  <br/> |Externa  <br/> |El grupo de autor de la llamada. Referencia de la [tabla de grupo de servidores](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Externa  <br/> |El grupo de servidores del destinatario de la llamada. Referencia de la [tabla de grupo de servidores](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Externa  <br/> |URI del SIP de SIP afirmada identity (PAI) del extremo receptor. Referencia de la [tabla de usuario](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Externa  <br/> |Del autor de la URI. Referencia de la [tabla de usuario](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Externa  <br/> |Extremo del autor de la llamada. Referencia de la [tabla de extremo](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Externa  <br/> |Agente de usuario del autor de la llamada. Referencia de la [tabla UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||La prioridad de esta llamada.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Esta columna ha quedado obsoleto y no se usa en Skype para Business Server. En su lugar, esta información se informa sobre las bases de por medio de una línea. Hacer referencia a la [tabla MediaLine](medialine-0.md) para obtener más información. <br/> |
|**CallerPAI** <br/> |int  <br/> |Externa  <br/> |P-Asserted-Identity del usuario que realizó la llamada. P-Asserted-Identity (PAI) se usa para transmitir la identidad del usuario que realizó la llamada es true.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Externa  <br/> |Extremo que recibió la llamada.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Externa  <br/> |Agente de usuario utilizado por el usuario que recibió la llamada. Agentes de usuario representan el dispositivo de extremo de cliente.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Externa  <br/> |URI del SIP del usuario que recibió la llamada.  <br/> |
   

