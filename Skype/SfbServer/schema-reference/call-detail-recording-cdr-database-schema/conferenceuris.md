---
title: Tabla ConferenceUris en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La tabla ConferenceUris es una tabla auxiliar donde se guarda una lista de las diversas URI de conferencia que han participado en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla corresponde a una URI de conferencia.
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816140"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Tabla ConferenceUris en Skype Empresarial Server 2015
 
La tabla ConferenceUris es una tabla auxiliar donde se guarda una lista de las diversas URI de conferencia que han participado en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla corresponde a una URI de conferencia.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Principal  <br/> |Marca de tiempo, interna utilizada.  <br/> |
|**ConferenceUriId** <br/> |entero  <br/> |Principal  <br/> |Número único que identifica esta URI de conferencia.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||URI de conferencia.  <br/> |
|**Suma de comprobación** <br/> |entero  <br/> ||Suma de comprobación de ConferenceUri. Se utiliza para acelerar las búsquedas en bases de datos.  <br/> |
|**UriTypeId** <br/> |entero  <br/> |Externo  <br/> |Tipo de URI, como por ejemplo conf:chat para conferencia de mensajería instantánea, o conf:audio-video para conferencia A/V. Vea la [tabla UriTypes para](uritypes.md) obtener más información. <br/> |
   

