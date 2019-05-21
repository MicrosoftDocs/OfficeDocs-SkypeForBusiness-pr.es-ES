---
title: Vista ProgressReport
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: La vista ProgressReport almacena información sobre las sesiones completadas. Los informes de progreso solo se escribirán para las llamadas y las sesiones que la 2013 determina Lync Server puede resultar útil para propósitos de diagnóstico. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: e5ad388c2845be63926f2172f944abc08f58481e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295961"
---
# <a name="progressreport-view"></a>Vista ProgressReport
 
La vista ProgressReport almacena información sobre las sesiones completadas. Los informes de progreso solo se escribirán para las llamadas y las sesiones que la 2013 determina Lync Server puede resultar útil para propósitos de diagnóstico. Esta vista se presentó en Microsoft Lync Server 2013.
  
> [!NOTE]
> Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no hacen referencia a errores sino a mensajes que indican el estado de las llamadas o los mensajes. 
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Hora de error. Se usa junto con ErrorReportSeq para identificar de forma única un error.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Número de identificación para identificar el error. Se usa junto con ErrorTime para identificar de forma única un error.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |IDENTIFICADOR para identificar el informe de progreso. Se usa para distinguir los informes de progreso del mismo informe de errores.  <br/> |
|**MsDiagId** <br/> |int  <br/> |IDENTIFICADOR de diagnóstico del informe de errores.  <br/> |
|**Origen** <br/> |nvarchar(256)  <br/> |Nombre del servidor que originó el error (si el informe fue enviado desde un componente de servidor).  <br/> |
|**Aplicación** <br/> |nvarchar(256)  <br/> |Nombre de la aplicación que originó el error (si el informe fue enviado desde un componente de servidor).  <br/> |
|**TelemetryId** <br/> |identificador  <br/> |Identificador único que correlaciona información de tiempo de Unión para los distintos componentes implicados en una conferencia.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Tiempo (en milisegundos) necesario para que un componente específico se una a una conferencia.  <br/> |
|**MsDiagHeader** <br/> |VARCHAR (Max)  <br/> |Información de error adicional.  <br/> |
   

