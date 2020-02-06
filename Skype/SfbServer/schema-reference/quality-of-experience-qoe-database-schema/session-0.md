---
title: Vista de sesión
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: La vista de sesión almacena información sobre las sesiones que tienen registros en la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: cd304123022e0d4d921ecb1cd2599c636aaa9013
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805908"
---
# <a name="session-view"></a>Vista de sesión
 
La vista de sesión almacena información sobre las sesiones que tienen registros en la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Se hace referencia a ella desde la tabla MediaLine.  <br/> |
|ConferenceURI  <br/> |nvarchar (450)  <br/> |URI de conferencia si se trata de una conferencia o DialogID si se trata de una sesión de punto a punto.  <br/> |
|Correlación  <br/> |VARCHAR (Max)  <br/> |IDENTIFICADOR de correlación de la sesión.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoría de cuadro de diálogo; 0 es la pierna del servidor de Skype empresarial Server. 1 es el servidor de mediación para la puerta de la puerta de enlace RTC.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indica si se ha omitido la llamada.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Este campo, si está presente, indica por qué no se omitió una llamada, incluso si los identificadores de omisión coinciden. Para Skype empresarial Server, solo se define un valor:  <br/> 0x0001: identificador de omisión desconocido para el adaptador de red predeterminado  <br/> |
|StartTime  <br/> |datetime  <br/> |Hora de inicio de la llamada.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de finalización de la llamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de llamadas.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de destinatarios de la llamada.  <br/> |
|CallerPAI  <br/> |nvarchar (450)  <br/> |URI de identidad afirmada de la persona que llama.  <br/> |
|CalleePAI  <br/> |nvarchar (450)  <br/> |URI de identidad afirmada de la persona que llama.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del punto de conexión de la llamada.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del punto de conexión de la llamada.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario de la llamada.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario de la llamada. Consulte la [tabla UserAgent](useragent.md) para obtener más información. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoría del agente de usuario de la llamada. Para obtener más información, consulta la [tabla UserAgentDef (QoE)](useragentdef-qoe.md) . <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario de la persona que llama.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario para el destinatario de la llamada. Consulte la [tabla UserAgent](useragent.md) para obtener más información. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoría de agente de usuario para el destinatario de la llamada. Para obtener más información, consulta la [tabla UserAgentDef (QoE)](useragentdef-qoe.md) . <br/> |
|CallerURI  <br/> |nvarchar (450)  <br/> |URI de la persona que llama.  <br/> |
|CalleeURI  <br/> |nvarchar (450)  <br/> |URI de la persona que llama.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Prioridad de la llamada.  <br/> |
   

