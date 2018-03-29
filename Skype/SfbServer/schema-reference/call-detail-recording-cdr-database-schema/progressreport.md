---
title: Tabla ProgressReport
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Informes de progreso se basan en los datos cargados por el cliente a la base de datos al finalizar una llamada o sesión. Informes de progreso se escribirán sólo para llamadas y sesiones de Skype para Business Server 2015 determina que puede resultar útil para propósitos de diagnóstico.
ms.openlocfilehash: 9acf54e7fb00917ad8263d4c40e534beb29b628c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="progressreport-table"></a>Tabla ProgressReport
 
Informes de progreso se basan en los datos cargados por el cliente a la base de datos al finalizar una llamada o sesión. Informes de progreso se escribirán sólo para llamadas y sesiones de Skype para Business Server 2015 determina que puede resultar útil para propósitos de diagnóstico.
  
Los campos de ErrorTime, ErrorReportSeq y ProgressReportSeq necesariamente no hacen referencia a errores, pero a los mensajes que indican el estado de llamadas o mensajes.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Fecha y hora del informe de error de progreso que contiene este informe de progreso. Consulte la [tabla de ErrorReport en Skype para Business Server 2015](errorreport.md) para obtener más información. <br/> |
|**Identificador del error** <br/> |int  <br/> |Principal, externa  <br/> |Número de ID que se utiliza junto con ErrorTime, ProgressReportSeq para identificar un informe de progreso. Consulte la [tabla de ErrorReport en Skype para Business Server 2015](errorreport.md) para obtener más información. <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de ID que identifica el informe de errores. ErrorReporSeq se utiliza para identificar un informe de errores junto con ErrorTime. Consulte la [tabla de ErrorReport en Skype para Business Server 2015](errorreport.md) para obtener más información <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primary  <br/> |Número de ID para identificar el informe de progreso. Se utiliza junto con ErrorTime y ErrorReportSeq para identificar un informe de progreso.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||ID. del informe de progreso de diagnóstico.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SourceId** <br/> |int  <br/> |Externa  <br/> |Servidor que ha enviado el informe de errores (si el informe se ha enviado desde un componente de servidor). Consulte la [tabla de servidores](servers.md) para obtener más información. Este campo se introdujo en Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |int  <br/> ||El proceso de Lync Server que hace referencia el informe. Consulte la tabla de aplicación para obtener más información.  <br/> |
|**Detalle** <br/> |imagen  <br/> ||Detalles del informe de progreso, almacenados en formato binario para ahorrar espacio. Estos datos se pueden convertir a formato de texto utilizando esta sintaxis:  <br/> conversión de tipos (cast (detalles como varbinary(max)) como varchar(max))  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificador único que correlaciona unir la información de tiempo de los diferentes componentes implicados en una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tiempo (en milisegundos) para un componente específico para unirse a una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
   

