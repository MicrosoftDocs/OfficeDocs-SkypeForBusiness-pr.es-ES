---
title: Vista de ProgressReport
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: La vista ProgressReport almacena información acerca de sesiones completadas. Informes de progreso se escribirán sólo para llamadas y sesiones que Lync Server 2013 determina que puede resultar útil para propósitos de diagnóstico. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 7dab41202eb098e2e49e5d4960b0c7b4e4c6570d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="progressreport-view"></a>Vista de ProgressReport
 
La vista ProgressReport almacena información acerca de sesiones completadas. Informes de progreso se escribirán sólo para llamadas y sesiones que Lync Server 2013 determina que puede resultar útil para propósitos de diagnóstico. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> Los campos de ErrorTime, ErrorReportSeq y ProgressReportSeq necesariamente no hacen referencia a errores, pero a los mensajes que indican el estado de llamadas o mensajes. 
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Se ha producido el momento del error. Se utiliza junto con ErrorReportSeq para identificar un error.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Número de ID para identificar el error. Se utiliza junto con ErrorTime para identificar un error.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |ID para identificar el informe de progreso. Se utiliza para distinguir los informes de progreso del mismo informe de error.  <br/> |
|**MsDiagId** <br/> |int  <br/> |Id. de diagnóstico para el informe de errores.  <br/> |
|**Origen** <br/> |nvarchar(256)  <br/> |Nombre del servidor que se originó el error (si se ha enviado desde un componente de servidor).  <br/> |
|**Aplicación** <br/> |nvarchar(256)  <br/> |Nombre de la aplicación que originó el error (si se ha enviado desde un componente de servidor).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificador único correlacionando la información de tiempo de participación de los diferentes componentes implicados en una conferencia.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Tiempo (en milisegundos) necesario para que un determinado componente para unirse a una conferencia.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Información de error adicional.  <br/> |
   

