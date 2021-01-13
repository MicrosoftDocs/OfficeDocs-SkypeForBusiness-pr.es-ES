---
title: Tabla IMReportSummary en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: La IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea mantenidas en una organización. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 6a80918376440c13d60e059744d88c09c2705853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821530"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Tabla IMReportSummary en Skype Empresarial Server 2015
 
La IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea mantenidas en una organización. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Principal  <br/> |Fecha y hora en que comenzó la sesión de mensajería instantánea.  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Principal  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Principal  <br/> |Nombre de dominio completo del grupo de servidores que hospeda la sesión.  <br/> |
|**AuthType** <br/> |entero  <br/> |Principal  <br/> |Prioridad (por ejemplo, urgente o no urgente) de la llamada. La información de prioridad se almacena [en la tabla CallPriorities en Skype Empresarial Server 2015.](callpriorities.md)  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Número total de mensajes instantáneos intercambiados durante la sesión.  <br/> |
   

