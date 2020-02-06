---
title: Tabla ProgressReport
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Los informes de progreso se basan en los datos cargados por el cliente en la base de datos después de completarse una llamada o sesión. Los informes de progreso solo se escribirán para las llamadas y las sesiones que la 2015 de Skype empresarial Server determine pueden ser útiles para propósitos de diagnóstico.
ms.openlocfilehash: a6cd89d7ba7f8cc03b25dc9310bdb408c85b50cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814978"
---
# <a name="progressreport-table"></a>Tabla ProgressReport
 
Los informes de progreso se basan en los datos cargados por el cliente en la base de datos después de completarse una llamada o sesión. Los informes de progreso solo se escribirán para las llamadas y las sesiones que la 2015 de Skype empresarial Server determine pueden ser útiles para propósitos de diagnóstico.
  
Los campos ErrorTime, ErrorReportSeq y ProgressReportSeq no hacen referencia a errores sino a mensajes que indican el estado de las llamadas o los mensajes.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Principal, extranjero  <br/> |Fecha y hora del informe de errores de progreso que contiene este informe de progreso. Para obtener más información, consulte la [tabla errorreport en Skype empresarial Server 2015](errorreport.md) . <br/> |
|**ErrorId** <br/> |int  <br/> |Principal, extranjero  <br/> |Número de identificación usado en conjunción con ErrorTime, ProgressReportSeq para identificar de manera exclusiva un informe de progreso. Para obtener más información, consulte la [tabla errorreport en Skype empresarial Server 2015](errorreport.md) . <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Principal, extranjero  <br/> |Número de identificación que identifica el informe de errores. ErrorReporSeq se usa junto con ErrorTime para identificar de forma exclusiva un informe de errores. Para obtener más información, consulte la [tabla errorreport en Skype empresarial Server 2015](errorreport.md) <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primary  <br/> |Número de identificación para identificar el informe de progreso. Se usa junto con ErrorTime y ErrorReportSeq para identificar de manera única un informe de progreso.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||IDENTIFICADOR de diagnóstico del informe de progreso.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SourceId** <br/> |int  <br/> |Extranjero  <br/> |Servidor que ha enviado el informe de errores (si el informe se envió desde un componente de servidor). Para obtener más información, consulte la [tabla servidores](servers.md) . Este campo se introdujo en Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |int  <br/> ||El proceso de Lync Server sobre el que se encuentra el informe. Para obtener más información, consulte la tabla de la aplicación.  <br/> |
|**Detalle** <br/> |imagen  <br/> ||Detalles del informe de progreso, almacenado en formato binario, para ahorrar espacio. Estos datos se pueden convertir a formato de texto con esta sintaxis:  <br/> CAST (detallar como varbinary (Max)) como varchar (Max))  <br/> |
|**TelemetryId** <br/> |Identificador  <br/> ||Identificador único que correlaciona la información de tiempo de Unión para los distintos componentes implicados en una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tiempo (en milisegundos) para que un componente específico se una a una conferencia.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
   

