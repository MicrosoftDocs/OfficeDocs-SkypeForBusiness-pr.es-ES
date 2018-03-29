---
title: tblComplianceParticipant
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contiene a los participantes actuales por canal y por servidor.
ms.openlocfilehash: ba488f377592b48845880acaeed61074bc31ccd2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant contiene a los participantes actuales por canal y por servidor.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), no nulo  <br/> |Canal identificador de recursos uniforme (URI).  <br/> |
|ID de usuario  <br/> |int, no nulo  <br/> |Identificador principal del participante (correspondiente a la tabla de tblPrincipal.prinID).  <br/> |
|joinedAt  <br/> |bigint, no nulo  <br/> |Marca de tiempo del evento que se va a unir.  <br/> |
|partedAt  <br/> |bigint  <br/> |Null si todavía está unido participante. La marca de tiempo del canal dejando el evento si no es null.  <br/> Estas entradas más tarde se eliminan cuando todos los traductores procesan el evento.  <br/> |
|userUri  <br/> |nvarchar (255), no nulo  <br/> |URI del usuario.  <br/> |
|serverID  <br/> |int  <br/> |Identidad del servidor (como en la tabla de tblServerIdentity.serverID).  <br/> |
|Id. de sesión  <br/> |bigint  <br/> |Sesión del servidor. Se trata de un número aleatorio que se genera cada vez que se inicia un servicio de charla. Sirve para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<channelUri, joinedAt, Id.\>  <br/> |Clave principal.  <br/> |
   

