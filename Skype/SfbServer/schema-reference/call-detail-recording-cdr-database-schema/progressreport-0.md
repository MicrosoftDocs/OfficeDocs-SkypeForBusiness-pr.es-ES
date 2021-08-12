---
title: Vista ProgressReport
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: La vista ProgressReport almacena información sobre las sesiones finalizadas. Solo se escribirán informes de progreso de las llamadas y sesiones que Lync Server 2013 considere que puedan resultar útiles para realizar diagnósticos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: e119a10d82e21274b631d5d1107b4269868974d489dfd0aa9b4dfce929c050e3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284590"
---
# <a name="progressreport-view"></a>Vista ProgressReport
 
La vista ProgressReport almacena información sobre las sesiones finalizadas. Solo se escribirán informes de progreso de las llamadas y sesiones que Lync Server 2013 considere que puedan resultar útiles para realizar diagnósticos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no hacen referencia necesariamente a errores, sino a mensajes que indican el estado de las llamadas o mensajes. 
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Hora en que se produjo el error. Se usa en combinación con ErrorRportSeq para identificar el error de forma exclusiva.  <br/> |
|**ErrorReportSeq** <br/> |Entero  <br/> |Número para identificar el error. Se usa junto con ErrorTime como identificación única de un error.  <br/> |
|**ProgressReportSeq** <br/> |Entero  <br/> |Identificador del informe de progreso. Se usa para diferenciar informes de progreso del mismo informe de errores.  <br/> |
|**MsDiagId** <br/> |Entero  <br/> |Identificador de diagnóstico del informe de errores.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Nombre del servidor que originó el error (si el informe se envió desde un componente de servidor).  <br/> |
|**Aplicación** <br/> |nvarchar(256)  <br/> |Nombre de la aplicación que generó el error (si el informe se envió desde un componente de servidor).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificador único que correlaciona la información de la hora de unión de los componentes que participan en una conferencia.  <br/> |
|**SessionSetupTime** <br/> |Entero  <br/> |Tiempo (en milisegundos) necesario para que un componente específico se una a las conferencias.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Información adicional del error.  <br/> |
   

