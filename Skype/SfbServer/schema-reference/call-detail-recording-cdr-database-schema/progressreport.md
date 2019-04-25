---
title: Tabla ProgressReport
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Informes de progreso se basan en los datos cargados por el cliente a la base de datos después de que se complete una llamada o una sesión. Informes de progreso se escribirá sólo para las llamadas y las sesiones de Skype para Business Server 2015 determina podría ser útil con fines de diagnóstico.
ms.openlocfilehash: 6d638411f39956664c977e87785a1269ee788a5f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212869"
---
# <a name="progressreport-table"></a>Tabla ProgressReport
 
Informes de progreso se basan en los datos cargados por el cliente a la base de datos después de que se complete una llamada o una sesión. Informes de progreso se escribirá sólo para las llamadas y las sesiones de Skype para Business Server 2015 determina podría ser útil con fines de diagnóstico.
  
Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq necesariamente no hacen referencia a errores, sino a mensajes que indican el estado de las llamadas o los mensajes.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Fecha y hora del informe de errores de progreso que contiene este informe de progreso. Vea la [tabla ErrorReport en Skype para Business Server 2015](errorreport.md) para obtener más información. <br/> |
|**Identificador del error** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificador que se usa junto con ErrorTime, ProgressReportSeq para identificar de forma única un informe de progreso. Vea la [tabla ErrorReport en Skype para Business Server 2015](errorreport.md) para obtener más información. <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificador que identifica el informe de errores. ErrorReporSeq se usa en combinación con ErrorTime para identificar de forma única un informe de errores. Vea la [tabla ErrorReport en Skype para Business Server 2015](errorreport.md) para obtener más información <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primary  <br/> |Número de identificador para identificar el informe de progreso. Se utiliza junto con ErrorTime y ErrorReportSeq para identificar de forma única un informe de progreso.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||Identificador de diagnóstico del informe de progreso.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SourceId** <br/> |int  <br/> |Externa  <br/> |Servidor que ha enviado el informe de errores (si el informe se envió desde un componente de servidor). Consulte la [tabla de servidores](servers.md) para obtener más información. Este campo se introdujo en Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |int  <br/> ||El proceso de Lync Server que hace referencia el informe. Vea la tabla de la aplicación para obtener más información.  <br/> |
|**Detalle** <br/> |imagen  <br/> ||Detalles del informe de progreso, almacenados en formato binario para ahorrar espacio. Estos datos pueden convertirse a formato de texto con esta sintaxis:  <br/> CAST (cast (Detail as varbinary como varchar  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificador único que correlaciona información de tiempo para los diferentes componentes que participan en una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tiempo (en milisegundos) para un componente específico para unirse a una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
   

