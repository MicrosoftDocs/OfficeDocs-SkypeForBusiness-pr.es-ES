---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: la tabla tblComplianceParticipant contiene a los participantes actuales por canal y por servidor.
ms.openlocfilehash: a3d18c4a78af2892a837e1105a435a3ce46ea14b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212954"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
la tabla tblComplianceParticipant contiene a los participantes actuales por canal y por servidor.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), no es nulo  <br/> |Identificador de canal uniforme de recursos (URI).  <br/> |
|userId  <br/> |int, no es nulo  <br/> |Identificador de entidad del participante (correspondiente a la tabla tblPrincipal.prinID).  <br/> |
|joinedAt  <br/> |bigint, no es nulo  <br/> |Marca de tiempo del evento participante.  <br/> |
|partedAt  <br/> |bigint  <br/> |Null si aún está unido participante. La marca de tiempo del canal dejando evento si no es nulo.  <br/> Estas entradas se quitan finalmente cuando todos los traductores procesan el evento.  <br/> |
|userUri  <br/> |nvarchar (255), no es nulo  <br/> |URI del usuario.  <br/> |
|serverID  <br/> |int  <br/> |Identidad del servidor (como se muestra en la tabla tblServerIdentity.serverID).  <br/> |
|sessionId  <br/> |bigint  <br/> |Sesión de servidor. Este es un número aleatorio generado cada vez que se inicia un servicio de Chat. Se usa para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |Clave principal.  <br/> |
   

