---
title: tblComplianceData
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contiene los eventos de cumplimiento de normas que aún no se ha procesado por el adaptador de cumplimiento de normas.
ms.openlocfilehash: 6fcee20a96a83a69a3671fe9255f1336590b42de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData contiene los eventos de cumplimiento de normas que aún no se ha procesado por el adaptador de cumplimiento de normas.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, no nulo  <br/> |ID de evento.  <br/> |
|entryDate  <br/> |smalldatetime, no nulo  <br/> |Hora de inserción (puede ser el momento en el futuro para cmplType = 9, porque la entrada es un marcador de posición en este caso).  <br/> |
|cmplType  <br/> |int, no nulo  <br/> | Tipo de evento de conformidad: <br/>  1: chat <br/>  2: backchat <br/>  3: Descargar archivo <br/>  4: carga de archivos <br/>  9: transferencia de archivos provisionales <br/>  10: chat eliminación (con reemplazar) <br/>  11: purga de charla <br/> |
|cmplTime  <br/> |bigint, no nulo  <br/> |Marca de tiempo para el evento.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), no nulo  <br/> |Canal identificador de recursos uniforme (URI).  <br/> |
|cmplChatID  <br/> |bigint  <br/> |Charla ID (correspondiente a la tabla de tblChat.chatId).  <br/> |
|cmplUserID  <br/> |int, no nulo  <br/> |Identificador principal del póster (correspondiente a la tabla de tblPrincipal.prinID).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), no nulo  <br/> |URI del usuario.  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |Mensajes (codificación depende de cmplType).  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|cmplEventID  <br/> |Clave principal.  <br/> |
   

