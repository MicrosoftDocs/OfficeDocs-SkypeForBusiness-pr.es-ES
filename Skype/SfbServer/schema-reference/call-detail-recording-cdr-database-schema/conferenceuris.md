---
title: Tabla ConferenceUris en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La tabla ConfereneUris es una tabla de soporte que almacena una lista de los distintos URI de conferencia que participaron en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla representa un URI de conferencia.
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815318"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Tabla ConferenceUris en Skype empresarial Server 2015
 
La tabla ConfereneUris es una tabla de soporte que almacena una lista de los distintos URI de conferencia que participaron en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla representa un URI de conferencia.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primary  <br/> |Marca de tiempo, usada internamente.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este URI de conferencia.  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> ||URI de la Conferencia.  <br/> |
|**Comprobación** <br/> |int  <br/> ||Suma de comprobación de ConferenceUri. Se usa para aumentar la velocidad de las búsquedas de bases de datos.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Extranjero  <br/> |Tipo de URI, como conf: chat para conferencias de mensajería instantánea o conf: audio-video para conferencias de audio y vídeo. Para obtener más información, consulte la tabla de la [tabla UriTypes](uritypes.md) . <br/> |
   

