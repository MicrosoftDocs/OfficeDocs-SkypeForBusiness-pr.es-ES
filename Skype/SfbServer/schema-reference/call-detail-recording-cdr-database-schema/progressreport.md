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
description: Los informes de progreso se basan en datos cargados por el cliente en la base de datos tras completarse una llamada o sesión. Los informes de progreso solo se escribirán para llamadas y sesiones que Skype Empresarial Server 2015 determine que pueden ser útiles para fines de diagnóstico.
ms.openlocfilehash: 6429700f902caec80db02f3db6c78420b5c108ce6a39383da8914955df16f80d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286229"
---
# <a name="progressreport-table"></a>Tabla ProgressReport
 
Los informes de progreso se basan en datos cargados por el cliente en la base de datos tras completarse una llamada o sesión. Los informes de progreso solo se escribirán para llamadas y sesiones que Skype Empresarial Server 2015 determine que pueden ser útiles para fines de diagnóstico.
  
Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no hacen referencia necesariamente a errores, sino a mensajes que indican el estado de las llamadas o mensajes.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Principal, Exterior  <br/> |Fecha y hora del informe de errores de progreso que contiene este informe de progreso. Vea la [tabla ErrorReport de Skype Empresarial Server 2015](errorreport.md) para obtener más información. <br/> |
|**ErrorId** <br/> |Entero  <br/> |Principal, Exterior  <br/> |Número de identificación usado junto con ErrorTime, ProgressReportSeq para identificar de manera única un informe de progreso. Vea la [tabla ErrorReport de Skype Empresarial Server 2015](errorreport.md) para obtener más información. <br/> |
|**ErrorReportSeq** <br/> |Entero  <br/> |Principal, Exterior  <br/> |Número de id. que identifica el informe de errores. ErrorReporSeq se usa junto con ErrorTime para identificar de manera única un informe de errores. Vea la [tabla ErrorReport en Skype Empresarial Server 2015](errorreport.md) para obtener más información <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |Entero  <br/> |Principal  <br/> |Número de identificación usado para identificar el informe de progreso. Se utiliza junto con ErrorTime y ErrorReportSeq para identificar de manera única un informe de progreso.  <br/> |
|**MsDiagId** <br/> |Entero  <br/> ||Id. de diagnóstico del informe de progreso.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SourceId** <br/> |Entero  <br/> |Externo  <br/> |Servidor que envió el informe de error (si el informe se envió desde un componente de servidor). Vea la [tabla Servidores para](servers.md) obtener más información. Este campo se introdujo en Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |Entero  <br/> ||El proceso de Lync Server al que se refiere el informe. Vea la tabla de aplicaciones para obtener más información.  <br/> |
|**Detalle** <br/> |imagen  <br/> ||Detalles del informe de progreso, almacenados en formato binario para ahorrar espacio. Estos datos pueden convertirse en formato de texto usando esta sintaxis:  <br/> cast(cast(Detail as varbinary(max)) as varchar(max))  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificador único que correlaciona información de hora de conexión para los diferentes componentes que participan en una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |Entero  <br/> ||Tiempo (en milisegundos) para que un componente específico se una a una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
   

