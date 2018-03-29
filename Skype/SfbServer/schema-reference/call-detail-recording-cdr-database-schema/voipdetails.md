---
title: Vista de VoIPDetails
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vista VoIPDetails almacena información acerca de las sesiones de peer-to-peer, donde al menos un usuario es un usuario de VoIP. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 93c2afb6383817a4d3941d5b427565fb1d0db098
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="voipdetails-view"></a>Vista de VoIPDetails
 
La vista VoIPDetails almacena información acerca de las sesiones de peer-to-peer, donde al menos un usuario es un usuario de VoIP. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista VoIPDetails contiene todas las columnas en la [vista SessionDetails](sessiondetails-0.md) además las columnas enumeradas a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |Teléfono URI del usuario que inició la sesión.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |URI del usuario que ha unido a la sesión del teléfono.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |URI del usuario que se ha desconectado la sesión.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que se ha desconectado la sesión. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Inquilinos del usuario que ha desconectado la sesión.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |URI del usuario que se ha desconectado la sesión del teléfono.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediación utilizado por el usuario que inició la sesión.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediación utilizado por el usuario al que se unió a la sesión.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Puerta de enlace utilizada por el usuario que inició la sesión.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Puerta de enlace utilizada por el usuario al que se unió a la sesión.  <br/> |
   

