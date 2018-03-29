---
title: Vista de sesión
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: La vista de sesión almacena información acerca de las sesiones que tengan registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 056067b0c0e06b3ce9eb862898345fe4c8ff131c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="session-view"></a>Vista de sesión
 
La vista de sesión almacena información acerca de las sesiones que tengan registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Referencia de la tabla MediaLine.  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |Conferencia URI si se trata de una conferencia o DialogID si esta es una sesión de peer-to-peer.  <br/> |
|Correlación  <br/> |varchar (max)  <br/> |Id. de correlación de la sesión.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoría del cuadro de diálogo; 0 es Skype para Business Server pierna de servidor de mediación; 1 es el servidor de mediación pierna de puerta de enlace PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indica si se ha omitido la llamada.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Este campo, si está presente, indica por qué una llamada no se ha omitido aunque identificadores correspondía a la omisión. Para Skype para Business Server, se define un solo valor:  <br/> 0 x 0001 - ID de omisión desconocido para el adaptador de red predeterminado  <br/> |
|Hora de inicio  <br/> |datetime  <br/> |Tiempo de inicio de llamada.  <br/> |
|Hora de finalización  <br/> |datetime  <br/> |Llame a hora de finalización.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de llamador.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de destinatario.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |Afirmado p URI de identidad del llamador.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |Afirmado p URI de identidad del destinatario.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo del llamador.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo del llamador.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario del llamador.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario del llamador. Consulte la [tabla UserAgent](useragent.md) para obtener más detalles. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoría de agente de usuario del llamador. Consulte la [tabla UserAgentDef (QoE)](useragentdef-qoe.md) para obtener más detalles. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario del destinatario de la llamada.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario para el destinatario. Consulte la [tabla UserAgent](useragent.md) para obtener más detalles. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoría de agente de usuario para el destinatario. Consulte la [tabla UserAgentDef (QoE)](useragentdef-qoe.md) para obtener más detalles. <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |Llamador del identificador URI.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |Destinatario del identificador URI.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Prioridad de la llamada.  <br/> |
   

