---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: La tabla tblComplianceParticipant contiene los participantes actuales por canal y por servidor.
ms.openlocfilehash: 4da7a5511caba65dc1ab4027647bed3262601dd4ef2e35949ae0bc0978451145
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351929"
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
   

