---
title: Tabla IMReportSummary en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: El IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea que se mantienen en una organización. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296129"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Tabla IMReportSummary en Skype empresarial Server 2015
 
El IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea que se mantienen en una organización. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |Fecha y hora en que comenzó la sesión de mensajería instantánea.  <br/> |
|**TimePeriod** <br/> |Char (1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar (257)  <br/> |Primary  <br/> |Nombre de dominio completo del grupo que hospeda la sesión.  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |Prioridad (por ejemplo, urgente o no urgente) de la llamada. La información de prioridad se almacena en la [tabla CallPriorities en Skype empresarial Server 2015](callpriorities.md).  <br/> |
|**SessionCount** <br/> |BIGINT  <br/> |||
|**MsgCount** <br/> |BIGINT  <br/> ||Número total de mensajes instantáneos intercambiados durante la sesión.  <br/> |
   

