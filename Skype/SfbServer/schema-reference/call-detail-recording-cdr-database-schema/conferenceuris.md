---
title: Tabla ConferenceUris en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: En la tabla de ConfereneUris es una tabla de apoyo que almacena una lista de la conferencia distintos de los identificadores URI que han participado en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla representa un URI de conferencia.
ms.openlocfilehash: 70cb3ccecf1c63dd128cbffd6ac205e77c771835
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901069"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Tabla ConferenceUris en Skype para Business Server 2015
 
En la tabla de ConfereneUris es una tabla de apoyo que almacena una lista de la conferencia distintos de los identificadores URI que han participado en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla representa un URI de conferencia.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primary  <br/> |Marca de tiempo, interna utilizada.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este URI de conferencia.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||URI de conferencia.  <br/> |
|**Suma de comprobación** <br/> |int  <br/> ||Suma de comprobación de URI de conferencia. Usado para aumenta la velocidad de las búsquedas de la base de datos.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Externa  <br/> |Tipo de URI, como conf:chat para conferencia de mensajería instantánea o conf:audio-vídeo para conferencias de audio y vídeo. Vea la tabla de la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
   

