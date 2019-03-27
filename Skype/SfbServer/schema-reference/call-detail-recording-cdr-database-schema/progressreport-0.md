---
title: Vista ProgressReport
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: La vista ProgressReport almacena información sobre sesiones completadas. Informes de progreso se escribirá sólo para las llamadas y las sesiones que Lync Server 2013 determina podría ser útil con fines de diagnóstico. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 5f7cbba2580b83a65dbce00588f3c567317f4df4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891120"
---
# <a name="progressreport-view"></a>Vista ProgressReport
 
La vista ProgressReport almacena información sobre sesiones completadas. Informes de progreso se escribirá sólo para las llamadas y las sesiones que Lync Server 2013 determina podría ser útil con fines de diagnóstico. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq necesariamente no hacen referencia a errores, sino a mensajes que indican el estado de las llamadas o los mensajes. 
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Hora de error se ha producido. Se utiliza junto con ErrorReportSeq para identificar de forma única un error.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Número de identificador para identificar el error. Se utiliza junto con ErrorTime para identificar de forma única un error.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Identificador para identificar el informe de progreso. Se usa para distinguir los informes de progreso de la misma informe de errores.  <br/> |
|**MsDiagId** <br/> |int  <br/> |Identificador de diagnóstico para el informe de errores.  <br/> |
|**Origen** <br/> |nvarchar(256)  <br/> |Nombre del servidor que originó el error (si el informe se envió desde un componente de servidor).  <br/> |
|**Aplicación** <br/> |nvarchar(256)  <br/> |Nombre de aplicación que originó el error (si el informe se envió desde un componente de servidor).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificador único que correlaciona la información de hora para los diferentes componentes que participan en una conferencia.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Tiempo (en milisegundos) necesario para que un componente específico para unirse a una conferencia.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Información adicional del error.  <br/> |
   

