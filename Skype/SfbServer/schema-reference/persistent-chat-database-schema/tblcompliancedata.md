---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contiene los eventos de conformidad que aún no ha procesado el adaptador de cumplimiento.
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295513"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData contiene los eventos de conformidad que aún no ha procesado el adaptador de cumplimiento.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |BIGINT, not null  <br/> |IDENTIFICADOR de evento.  <br/> |
|entryDate  <br/> |smalldatetime, not null  <br/> |Hora de inserción (puede ser muy próxima para cmplType = 9 porque la entrada es solo un marcador de posición en ese caso).  <br/> |
|cmplType  <br/> |int, not null  <br/> | Tipo de evento de conformidad: <br/>  1: chatear <br/>  2: chatear <br/>  3: descarga de archivos <br/>  4: carga de archivos <br/>  9: transferencia provisional de archivos <br/>  10: eliminación de chat (con Replace) <br/>  11: purgado de chat <br/> |
|cmplTime  <br/> |BIGINT, not null  <br/> |Marca de tiempo del evento.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), not null  <br/> |Identificador uniforme de recursos (URI) del canal.  <br/> |
|cmplChatID  <br/> |BIGINT  <br/> |IDENTIFICADOR de chat (corresponde a la tabla tblChat. chatId).  <br/> |
|cmplUserID  <br/> |int, not null  <br/> |IDENTIFICADOR principal del póster (correspondiente a la tabla tblPrincipal. prinID).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), not null  <br/> |URI de usuario.  <br/> |
|cmplMessage  <br/> |nvarchar (Max)  <br/> |Mensaje (la codificación depende de cmplType).  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|cmplEventID  <br/> |Clave principal.  <br/> |
   

