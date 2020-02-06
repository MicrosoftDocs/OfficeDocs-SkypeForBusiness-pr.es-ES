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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: El IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea que se mantienen en una organización. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: f845a882bb8bd6ba5ca434ffc42a34725cfeac51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815148"
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
   

