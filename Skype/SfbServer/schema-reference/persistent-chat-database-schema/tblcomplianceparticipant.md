---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: La tabla tblComplianceParticipant contiene los participantes actuales por canal y por servidor.
ms.openlocfilehash: d28b81d6ce0169999297dbcde65b1d7fbde38780
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854074"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
La tabla tblComplianceParticipant contiene los participantes actuales por canal y por servidor.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), no NULL  <br/> |Identificador uniforme de recursos (URI) del canal.  <br/> |
|userId  <br/> |int, no NULL  <br/> |Identificador de la entidad de seguridad del participante (correspondiente a la tabla tblPrincipal.prinID).  <br/> |
|joinedAt  <br/> |bigint, no NULL  <br/> |Marca de tiempo del evento participante.  <br/> |
|partedAt  <br/> |bigint  <br/> |Nulo si el participante aún está participando. La marca de tiempo del canal que abandona el evento si no es nulo.  <br/> Estas entradas se quitan finalmente cuando todos los traductores procesan el evento.  <br/> |
|userUri  <br/> |nvarchar(255), no NULL  <br/> |URI del usuario.  <br/> |
|serverID  <br/> |Entero  <br/> |Identidad del servidor (como en la tabla tblServerIdentity.serverID).  <br/> |
|sessionId  <br/> |bigint  <br/> |Sesión del servidor. Es un número aleatorio que se genera cada vez que se inicia un servicio de chat. Sirve para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |Clave principal.  <br/> |
   

