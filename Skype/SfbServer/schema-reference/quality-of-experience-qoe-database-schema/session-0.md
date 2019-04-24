---
title: Vista de sesión
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: La vista de sesión almacena información acerca de las sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: c72773b4ff87786ab5b4e73b67e89032dc393fa1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212105"
---
# <a name="session-view"></a>Vista de sesión
 
La vista de sesión almacena información acerca de las sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Referencia de la tabla MediaLine.  <br/> |
|URI de conferencia  <br/> |nvarchar(450)  <br/> |Si se trata de una conferencia, o DialogID, si este de URI de conferencia es una sesión de punto a punto.  <br/> |
|Correlación  <br/> |varchar (max)  <br/> |Identificador de correlación de la sesión.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoría del diálogo; 0 es Skype para Business Server tramo de servidor de mediación; 1 es el servidor de mediación tramo de puerta de enlace de RTC.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indica si la llamada se pasó.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |En este campo, si está presente, indica ¿por qué una llamada no se pasó incluso si el desvío de los identificadores de coinciden. Para Skype para Business Server, se define un solo valor:  <br/> 0 x 0001 - identificador de omisión desconocido para el adaptador de red predeterminado  <br/> |
|StartTime  <br/> |datetime  <br/> |Hora de inicio de la llamada.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de finalización de llamadas.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de autor de la llamada.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de destinatario de la llamada.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |Identidad afirmada del autor de la llamada URI.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |Identidad afirmada del destinatario de la llamada URI.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo del autor de la llamada.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo del autor de la llamada.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario del autor de la llamada.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario del autor de la llamada. Consulte la [tabla UserAgent](useragent.md) para obtener información detallada. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoría de agente de usuario del autor de la llamada. Consulte la [tabla UserAgentDef (QoE)](useragentdef-qoe.md) para obtener información detallada. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario de destinatario de la llamada.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario para el destinatario de la llamada. Consulte la [tabla UserAgent](useragent.md) para obtener información detallada. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoría de agente de usuario para el destinatario de la llamada. Consulte la [tabla UserAgentDef (QoE)](useragentdef-qoe.md) para obtener información detallada. <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |Del autor de la URI.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |Del destinatario de la URI.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Prioridad de la llamada.  <br/> |
   

