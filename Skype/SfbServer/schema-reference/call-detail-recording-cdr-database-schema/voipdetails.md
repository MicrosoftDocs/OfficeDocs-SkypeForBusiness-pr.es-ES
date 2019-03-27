---
title: Vista VoIPDetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vista VoIPDetails almacena información acerca de las sesiones de punto a punto, donde al menos un usuario es un usuario de VoIP. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 940c3874d5ce8eb8a4d2261de56b8988b6d3a4c9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875556"
---
# <a name="voipdetails-view"></a>Vista VoIPDetails
 
La vista VoIPDetails almacena información acerca de las sesiones de punto a punto, donde al menos un usuario es un usuario de VoIP. Esta vista se introdujo en Microsoft Lync Server 2013.
  
> [!NOTE]
> La vista VoIPDetails contiene todos los de las columnas de la [SessionDetails view](sessiondetails-0.md) además las columnas enumeradas a continuación.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |URI de teléfono del usuario que inició la sesión.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |URI de teléfono del usuario que ha iniciado la sesión.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |URI del usuario que ha desconectado la sesión.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que ha desconectado la sesión. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que ha desconectado la sesión.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |URI de teléfono del usuario que ha desconectado la sesión.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediación usado por el usuario que inició la sesión.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediación usado por el usuario que ha iniciado la sesión.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Puerta de enlace usada por el usuario que inició la sesión.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Puerta de enlace usada por el usuario que ha iniciado la sesión.  <br/> |
   

