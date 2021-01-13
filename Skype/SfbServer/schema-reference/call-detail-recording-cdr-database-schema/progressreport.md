---
title: Tabla ProgressReport
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Los informes de progreso se basan en datos cargados por el cliente en la base de datos tras completarse una llamada o sesión. Los informes de progreso se escribirán solo para llamadas y sesiones que Skype Empresarial Server 2015 determine que pueden ser útiles para fines de diagnóstico.
ms.openlocfilehash: 4169ab029c0ce491b77b39735e309e102ac6e356
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823180"
---
# <a name="progressreport-table"></a>Tabla ProgressReport
 
Los informes de progreso se basan en datos cargados por el cliente en la base de datos tras completarse una llamada o sesión. Los informes de progreso se escribirán solo para llamadas y sesiones que Skype Empresarial Server 2015 determine que pueden ser útiles para fines de diagnóstico.
  
Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no necesariamente hacen referencia a errores, sino a mensajes que indican el estado de las llamadas o mensajes.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Principal, Exterior  <br/> |Fecha y hora del informe de errores de progreso que contiene este informe de progreso. Consulte la [tabla ErrorReport en Skype Empresarial Server 2015](errorreport.md) para obtener más información. <br/> |
|**ErrorId** <br/> |entero  <br/> |Principal, Exterior  <br/> |Número de identificación usado junto con ErrorTime, ProgressReportSeq para identificar de manera única un informe de progreso. Consulte la [tabla ErrorReport en Skype Empresarial Server 2015](errorreport.md) para obtener más información. <br/> |
|**ErrorReportSeq** <br/> |entero  <br/> |Principal, Exterior  <br/> |Número de id. que identifica el informe de errores. ErrorReporSeq se usa junto con ErrorTime para identificar de manera única un informe de errores. Consulte la [tabla ErrorReport en Skype Empresarial Server 2015](errorreport.md) para obtener más información <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |entero  <br/> |Principal  <br/> |Número de identificación usado para identificar el informe de progreso. Se utiliza junto con ErrorTime y ErrorReportSeq para identificar de manera única un informe de progreso.  <br/> |
|**MsDiagId** <br/> |entero  <br/> ||Id. de diagnóstico del informe de progreso.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SourceId** <br/> |entero  <br/> |Externo  <br/> |Servidor que envió el informe de errores (si el informe se envió desde un componente de servidor). Vea la [tabla Servidores para](servers.md) obtener más información. Este campo se introdujo en Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |entero  <br/> ||El proceso de Lync Server al que se refiere el informe. Vea la tabla de aplicaciones para obtener más información.  <br/> |
|**Detalle** <br/> |imagen  <br/> ||Detalles del informe de progreso, almacenados en formato binario para ahorrar espacio. Estos datos pueden convertirse en formato de texto usando esta sintaxis:  <br/> cast(cast(Detail as varbinary(max)) as varchar(max))  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificador único que correlaciona información de hora de conexión para los diferentes componentes que participan en una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |entero  <br/> ||Tiempo (en milisegundos) para que un componente específico se una a una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
   

