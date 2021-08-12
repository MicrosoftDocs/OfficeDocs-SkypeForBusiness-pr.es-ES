---
title: Tabla de sesión
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
description: Cada registro representa una sesión que implica audio o audio y vídeo. Contiene información general sobre la sesión. Una sesión se define como un cuadro de diálogo del Protocolo de inicio de sesión (SIP) de audio o vídeo entre dos puntos de conexión.
ms.openlocfilehash: 749f151def046abdb5169b39ccbd81ea5f07f5d4ee3d1c971ac112a2d4b90cce
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340036"
---
# <a name="session-table"></a>Tabla de sesión
 
Cada registro representa una sesión que implica audio o audio y vídeo. Contiene información general sobre la sesión. Una sesión se define como un cuadro de diálogo del Protocolo de inicio de sesión (SIP) de audio o vídeo entre dos puntos de conexión.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal  <br/> |A la que se hace referencia desde la [tabla Dialog](dialog.md).  <br/> |
|**SessionSeq** <br/> |Entero  <br/> |Principal  <br/> |A la que se hace referencia desde la [tabla Dialog](dialog.md).  <br/> |
|**ConferenceKey** <br/> |Entero  <br/> |Externo  <br/> |Clave de conferencia. A la que se hace referencia desde [la tabla Conferencia](conference.md).  <br/> |
|**CorrelationKey** <br/> |Entero  <br/> |Externo  <br/> |Clave de correlación. Se hace referencia a la [tabla SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Categoría de cuadro de diálogo; 0 se Skype Empresarial Server al servidor de mediación; 1 es Servidor de mediación a puerta de enlace RTC.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Marca que indica si la llamada se omitió o no.  <br/> |
|**MediaBypassWarningFlag** <br/> |Entero  <br/> ||Este campo (si existe) indica por qué la llamada no se pasó, aun cuando los identificadores de omisión coincidían. Por Skype Empresarial Server, solo se define un valor.  <br/> 0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |Hora de inicio de la llamada.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Hora de finalización de la llamada.  <br/> |
|**CallerPool** <br/> |Entero  <br/> |Externo  <br/> |El grupo de servidores del autor de la llamada. A la que se hace referencia desde [la tabla Pool](pool.md).  <br/> |
|**CalleePool** <br/> |Entero  <br/> |Externo  <br/> |El grupo de servidores del receptor de llamadas. A la que se hace referencia desde [la tabla Pool](pool.md).  <br/> |
|**CalleePAI** <br/> |Entero  <br/> |Externo  <br/> |URI de SIP en la identidad de sip (PAI) del extremo de recepción. A la que se hace referencia desde [la tabla User](user-0.md).  <br/> |
|**CallerURI** <br/> |Entero  <br/> |Externo  <br/> |URI del autor de la llamada. A la que se hace referencia desde [la tabla User](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |Entero  <br/> |Externo  <br/> |Punto de conexión del autor de la llamada. A la que se hace referencia desde la [tabla Endpoint](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Externo  <br/> |Agente de usuario del autor de la llamada. A la que se hace referencia desde [la tabla UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||La prioridad de esta llamada.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Esta columna ha quedado en desuso y no se usa en Skype Empresarial Server. En su lugar, esta información se notifica en una base de línea por medios. Consulte la [tabla MediaLine para](medialine-0.md) obtener más información. <br/> |
|**CallerPAI** <br/> |Entero  <br/> |Externo  <br/> |P-Asserted-Identity del usuario que ha realizado la llamada. La P-Asserted-Identity (PAI) se usa para transmitir la verdadera identidad del usuario que ha realizado la llamada.  <br/> |
|**CalleeEndpoint** <br/> |Entero  <br/> |Externo  <br/> |Extremo que recibió la llamada.  <br/> |
|**CalleeUserAgent** <br/> |Entero  <br/> |Externo  <br/> |Agente de usuario empleado por el usuario que recibió la llamada. Los agentes de usuario representan el dispositivo de extremo de cliente.  <br/> |
|**CalleeUri** <br/> |Entero  <br/> |Externo  <br/> |URI de SIP del usuario que recibió la llamada.  <br/> |
   

