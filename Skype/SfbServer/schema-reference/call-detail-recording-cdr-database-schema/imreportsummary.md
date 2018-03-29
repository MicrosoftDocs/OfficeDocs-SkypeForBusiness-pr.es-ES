---
title: Tabla IMReportSummary en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: El IMReportSummaryTable proporciona un informe general sobre la celebrada en una organización de sesiones de mensajería instantánea. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: f716a7406f4cf3562e2fa9244e8a766ef8537f53
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Tabla IMReportSummary en Skype para Business Server 2015
 
El IMReportSummaryTable proporciona un informe general sobre la celebrada en una organización de sesiones de mensajería instantánea. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Hora de inicio** <br/> |datetime  <br/> |Primary  <br/> |Fecha y hora en que comenzó la sesión de mensajería instantánea.  <br/> |
|**TimePeriod** <br/> |Char (1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primary  <br/> |Nombre de dominio completo del grupo host de la sesión.  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |Prioridad (por ejemplo, urgente o no urgente) de la llamada. Información de prioridad se almacena en la [tabla CallPriorities en Skype para Business Server 2015](callpriorities.md).  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Número total de mensajes instantáneos intercambiados durante la sesión.  <br/> |
   

