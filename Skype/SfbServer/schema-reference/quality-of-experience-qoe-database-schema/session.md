---
title: Tabla Session
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
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Cada registro representa una sesión que implica audio o audio y vídeo. Contiene información general sobre la sesión. Una sesión se define como un cuadro de diálogo de protocolo de inicio de sesión (SIP) de audio o vídeo entre dos extremos.
ms.openlocfilehash: cdf639e7360248e02378c66eb68a60d49acb9749
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802680"
---
# <a name="session-table"></a>Tabla Session
 
Cada registro representa una sesión que implica audio o audio y vídeo. Contiene información general sobre la sesión. Una sesión se define como un cuadro de diálogo de protocolo de inicio de sesión (SIP) de audio o vídeo entre dos extremos.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal  <br/> |A la que se hace referencia desde [la tabla Dialog](dialog.md).  <br/> |
|**SessionSeq** <br/> |entero  <br/> |Principal  <br/> |A la que se hace referencia desde [la tabla Dialog](dialog.md).  <br/> |
|**ConferenceKey** <br/> |entero  <br/> |Externo  <br/> |Clave de conferencia. Se hace referencia a la [tabla Conferencia](conference.md).  <br/> |
|**CorrelationKey** <br/> |entero  <br/> |Externo  <br/> |Clave de correlación. A la que se hace referencia [desde la tabla SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Categoría de cuadro de diálogo; 0 es la parte de Skype Empresarial Server al servidor de mediación; 1 es la parte de servidor de mediación a puerta de enlace RTC.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Marca que indica si la llamada se omitió o no.  <br/> |
|**MediaBypassWarningFlag** <br/> |entero  <br/> ||Este campo (si existe) indica por qué la llamada no se pasó, aun cuando los identificadores de omisión coincidían. Para Skype Empresarial Server, solo se define un valor.  <br/> 0x0001 - Identificador de desvío desconocido para el adaptador de red predeterminado.  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |Hora de inicio de la llamada.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Hora de finalización de la llamada.  <br/> |
|**CallerPool** <br/> |entero  <br/> |Externo  <br/> |El grupo del autor de la llamada. Se hace referencia desde la [tabla Grupo de servidores](pool.md).  <br/> |
|**CalleePool** <br/> |entero  <br/> |Externo  <br/> |El grupo de servidores del receptor de llamadas. Se hace referencia desde la [tabla Grupo de servidores](pool.md).  <br/> |
|**CalleePAI** <br/> |entero  <br/> |Externo  <br/> |URI de SIP en la identidad p-asserted de SIP (PAI) del extremo de recepción. A la que se hace referencia desde [la tabla Usuario](user-0.md).  <br/> |
|**CallerURI** <br/> |entero  <br/> |Externo  <br/> |URI del autor de la llamada. A la que se hace referencia desde [la tabla Usuario](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |entero  <br/> |Externo  <br/> |Extremo del autor de la llamada. Se hace referencia desde la [tabla Endpoint](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Externo  <br/> |Agente de usuario del autor de la llamada. A la que se hace referencia desde [la tabla UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||La prioridad de esta llamada.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Esta columna está en desuso y no se usa en Skype Empresarial Server. En su lugar, esta información se notifica en una base de línea por medio. Consulta la tabla [MediaLine para](medialine-0.md) obtener más información. <br/> |
|**CallerPAI** <br/> |entero  <br/> |Externo  <br/> |P-Asserted-Identity del usuario que ha realizado la llamada. P-Asserted-Identity (PAI) se usa para transmitir la verdadera identidad del usuario que ha realizado la llamada.  <br/> |
|**CalleeEndpoint** <br/> |entero  <br/> |Externo  <br/> |Extremo que recibió la llamada.  <br/> |
|**CalleeUserAgent** <br/> |entero  <br/> |Externo  <br/> |Agente de usuario empleado por el usuario que recibió la llamada. Los agentes de usuario representan el dispositivo de extremo de cliente.  <br/> |
|**CalleeUri** <br/> |entero  <br/> |Externo  <br/> |URI de SIP del usuario que recibió la llamada.  <br/> |
   

