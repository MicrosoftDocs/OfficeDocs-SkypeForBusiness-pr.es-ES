---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: la tabla tblComplianceData contiene los eventos de cumplimiento que aún no se han procesado por el adaptador de cumplimiento.
ms.openlocfilehash: 88319da90c1f3e03b6ca3e441259972f51d0bcf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929934"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
la tabla tblComplianceData contiene los eventos de cumplimiento que aún no se han procesado por el adaptador de cumplimiento.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, no es nulo  <br/> |Identificador de evento.  <br/> |
|entryDate  <br/> |smalldatetime, no es nulo  <br/> |Hora de inserción (puede estar lejos en el futuro para cmplType = 9 porque la entrada es un marcador de posición en ese caso).  <br/> |
|cmplType  <br/> |int, no es nulo  <br/> | Tipo de evento de cumplimiento: <br/>  1: conversaciones <br/>  2: backchat <br/>  3: descarga de archivos <br/>  4: carga de archivos <br/>  9: transferencia de archivo provisional <br/>  10: conversaciones eliminación (con reemplazo) <br/>  11: depuración de chats <br/> |
|cmplTime  <br/> |bigint, no es nulo  <br/> |Marca de tiempo para el evento.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), no es nulo  <br/> |Identificador de canal uniforme de recursos (URI).  <br/> |
|cmplChatID  <br/> |bigint  <br/> |Identificador de Chat (correspondiente a la tabla tblChat.chatId).  <br/> |
|cmplUserID  <br/> |int, no es nulo  <br/> |Identificador de entidad del póster (correspondiente a la tabla tblPrincipal.prinID).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), no es nulo  <br/> |URI del usuario.  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |Mensaje (codificación depende de cmplType).  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|cmplEventID  <br/> |Clave principal.  <br/> |
   

