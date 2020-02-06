---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contiene los participantes actuales por canal y por servidor.
ms.openlocfilehash: 8f4b90cd7e8949451c2b6c1b9bc3cfabbab826e9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814648"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant contiene los participantes actuales por canal y por servidor.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), not null  <br/> |Identificador uniforme de recursos (URI) del canal.  <br/> |
|Iddeusuario  <br/> |int, not null  <br/> |IDENTIFICADOR principal del participante (correspondiente a la tabla tblPrincipal. prinID).  <br/> |
|joinedAt  <br/> |BIGINT, not null  <br/> |Marca de tiempo del evento de Unión.  <br/> |
|partedAt  <br/> |BIGINT  <br/> |NULL si el participante aún se ha unido. Marca de tiempo del canal dejando el evento si no es NULL.  <br/> Estas entradas se eliminan en algún momento cuando todos los traductores procesan el evento.  <br/> |
|userUri  <br/> |nvarchar (255), not null  <br/> |URI de usuario.  <br/> |
|serverID  <br/> |int  <br/> |Identidad del servidor (como en la tabla tblServerIdentity. serverID).  <br/> |
|Identificador  <br/> |BIGINT  <br/> |Sesión de servidor. Este es un número aleatorio generado cada vez que se inicia un servicio de chat. Se usa para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |Clave principal.  <br/> |
   

