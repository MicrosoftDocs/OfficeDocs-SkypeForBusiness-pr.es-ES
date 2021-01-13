---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: La tabla tblComplianceData contiene los eventos de cumplimiento que aún no procesó el adaptador de cumplimiento.
ms.openlocfilehash: e4ceda662b2f601660c144319a4231cebeea39ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809860"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
La tabla tblComplianceData contiene los eventos de cumplimiento que aún no procesó el adaptador de cumplimiento.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, no NULL  <br/> |Id. del evento.  <br/> |
|entryDate  <br/> |smalldatetime, no NULL  <br/> |Hora de inserción (puede estar lejos en el futuro para cmplType=9 porque la entrada solo es un marcador de posición en ese caso).  <br/> |
|cmplType  <br/> |int, no NULL  <br/> | Tipo de evento de cumplimiento: <br/>  1: Chat <br/>  2: Backchat <br/>  3: Descarga de archivos <br/>  4: Carga de archivos <br/>  9: Transferencia de archivo provisional <br/>  10: Eliminación de chats (con reemplazo) <br/>  11: Depuración de chats <br/> |
|cmplTime  <br/> |bigint, no NULL  <br/> |Marca de tiempo del evento.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), no NULL  <br/> |Identificador uniforme de recursos (URI) del canal.  <br/> |
|cmplChatID  <br/> |bigint  <br/> |Identificador de chat (correspondiente a la tabla tblChat.chatId).  <br/> |
|cmplUserID  <br/> |int, no NULL  <br/> |Identificador de entidad de seguridad del póster (correspondiente a la tabla tblPrincipal.prinID).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), no NULL  <br/> |URI del usuario.  <br/> |
|cmplMessage  <br/> |nvarchar (máx.)  <br/> |Mensaje (la codificación depende de cmplType).  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|cmplEventID  <br/> |Clave principal.  <br/> |
   

