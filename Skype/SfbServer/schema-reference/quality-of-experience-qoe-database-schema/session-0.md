---
title: Vista de sesión
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: La vista de sesión almacena información sobre las sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 34619c1555fac5935563dd72895f52d045c388ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802700"
---
# <a name="session-view"></a>Vista de sesión
 
La vista de sesión almacena información sobre las sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Se obtiene de la tabla MediaLine.  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |ConferenceURI, si se trata de una conferencia, o DialogID, si es una sesión punto a punto.  <br/> |
|Correlation  <br/> |varchar(max)  <br/> |Id. de correlación de la sesión.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoría de cuadro de diálogo; 0 es la parte de Skype Empresarial Server al servidor de mediación; 1 es la parte de servidor de mediación a puerta de enlace RTC.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indica si la llamada se pasó o no.  <br/> |
|MediaBypassWarningFlag  <br/> |entero  <br/> |Este campo (si existe) indica por qué la llamada no se pasó, aun cuando los identificadores de omisión coincidían. Para Skype Empresarial Server, solo se define un valor:  <br/> 0x0001 - Id. de desvío desconocido para el adaptador de red predeterminado  <br/> |
|StartTime  <br/> |datetime  <br/> |Hora de inicio de la llamada.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de finalización de la llamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de autores de llamadas.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de destinatarios de la llamada  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |URI de identidad p-asserted del autor de la llamada.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |URI de identidad p-asserted del destinatario de la llamada.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo del autor de la llamada.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo del autor de la llamada.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario del autor de la llamada.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario del autor de la llamada. Consulte la [tabla UserAgent para](useragent.md) obtener más información. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoría del agente de usuario del autor de la llamada. Consulte la [tabla UserAgentDef (QoE) para](useragentdef-qoe.md) obtener más información. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario del destinatario de la llamada.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo del agente de usuario del destinatario de la llamada. Consulte la [tabla UserAgent para](useragent.md) obtener más información. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoría del agente de usuario del destinatario de la llamada. Consulte la [tabla UserAgentDef (QoE) para](useragentdef-qoe.md) obtener más información. <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |URI del autor de la llamada.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |URI del destinatario de la llamada.  <br/> |
|CallPrioirty  <br/> |entero  <br/> |Prioridad de la llamada.  <br/> |
   

