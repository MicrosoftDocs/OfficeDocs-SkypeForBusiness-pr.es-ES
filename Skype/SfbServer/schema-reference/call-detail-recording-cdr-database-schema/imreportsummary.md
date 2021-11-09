---
title: Tabla IMReportSummary en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: La IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea mantenidas en una organización. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 438b6f7e7093cba3e7f2c1d0b9a82a592128b86c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845023"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Tabla IMReportSummary en Skype Empresarial Server 2015
 
La IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea mantenidas en una organización. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Principal  <br/> |Fecha y hora en que comenzó la sesión de mensajería instantánea.  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Principal  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Principal  <br/> |Nombre de dominio completo del grupo de servidores que hospeda la sesión.  <br/> |
|**AuthType** <br/> |Entero  <br/> |Principal  <br/> |Prioridad (por ejemplo, urgente o no urgente) de la llamada. La información de prioridad se almacena en [la tabla CallPriorities en Skype Empresarial Server 2015](callpriorities.md).  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Número total de mensajes instantáneos intercambiados durante la sesión.  <br/> |
   

