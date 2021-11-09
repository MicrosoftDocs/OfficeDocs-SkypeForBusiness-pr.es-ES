---
title: Tabla ConferenceUris en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La tabla ConferenceUris es una tabla auxiliar donde se guarda una lista de las diversas URI de conferencia que han participado en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla corresponde a una URI de conferencia.
ms.openlocfilehash: 04867ec3e8c82b210e6f6f9663030b23879b996b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836188"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Tabla ConferenceUris en Skype Empresarial Server 2015
 
La tabla ConferenceUris es una tabla auxiliar donde se guarda una lista de las diversas URI de conferencia que han participado en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla corresponde a una URI de conferencia.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Principal  <br/> |Marca de tiempo, interna utilizada.  <br/> |
|**ConferenceUriId** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica esta URI de conferencia.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||URI de conferencia.  <br/> |
|**Suma de comprobación** <br/> |Entero  <br/> ||Suma de comprobación de ConferenceUri. Se utiliza para acelerar las búsquedas en bases de datos.  <br/> |
|**UriTypeId** <br/> |Entero  <br/> |Externo  <br/> |Tipo de URI, como por ejemplo conf:chat para conferencia de mensajería instantánea, o conf:audio-video para conferencia A/V. Vea la [tabla UriTypes para](uritypes.md) obtener más información. <br/> |
   

