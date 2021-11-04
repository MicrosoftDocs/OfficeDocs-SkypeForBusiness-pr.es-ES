---
title: Vista VoIPDetails
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vista VoIPDetails almacena información sobre sesiones punto a punto, donde al menos un usuario es un usuario voIP. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 8e647f79953efc507e63aa4f19e6f1deba53d7a1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765088"
---
# <a name="voipdetails-view"></a>Vista VoIPDetails
 
La vista VoIPDetails almacena información sobre sesiones punto a punto, donde al menos un usuario es un usuario voIP. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista VoIPDetails contiene todas las columnas de la [vista SessionDetails](sessiondetails-0.md) además de las columnas que se enumeran a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |Teléfono URI del usuario que inició la sesión.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |Teléfono URI del usuario que se unió a la sesión.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |URI del usuario que desconectó la sesión.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que desconectó la sesión. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que desconectó la sesión.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |Teléfono URI del usuario que desconectó la sesión.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediación usado por el usuario que inició la sesión.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediación usado por el usuario que se unió a la sesión.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Puerta de enlace usada por el usuario que inició la sesión.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Puerta de enlace usada por el usuario que se unió a la sesión.  <br/> |
   

