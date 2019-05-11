---
title: Tabla IMReportSummary en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: El IMReportSummaryTable proporciona un informe general en la se conserva en una organización de las sesiones de mensajería instantánea. En esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 3611243e49821e5fae211ce55858cdee555dd383
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901048"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Tabla IMReportSummary en Skype para Business Server 2015
 
El IMReportSummaryTable proporciona un informe general en la se conserva en una organización de las sesiones de mensajería instantánea. En esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |Fecha y hora en que comenzó la sesión de mensajería instantánea.  <br/> |
|**TimePeriod** <br/> |Char (1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primary  <br/> |Nombre de dominio completo del grupo de servidores que hospeda la sesión.  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |Prioridad (por ejemplo, urgente o no urgente) de la llamada. Información de prioridad se almacena en la [tabla CallPriorities en Skype para Business Server 2015](callpriorities.md).  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Número total de mensajes instantáneos intercambiados durante la sesión.  <br/> |
   

