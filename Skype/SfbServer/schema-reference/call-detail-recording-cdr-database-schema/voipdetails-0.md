---
title: Tabla VoipDetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Cada registro representa una llamada entre dos participantes en que al menos un usuario es un usuario de VoIP.
ms.openlocfilehash: 304efbd8148c363afaa792abe97d0b15ab5a34fd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879675"
---
# <a name="voipdetails-table"></a>Tabla VoipDetails
 
Cada registro representa una llamada entre dos participantes en que al menos un usuario es un usuario de VoIP.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Hora de la solicitud de sesión. Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**FromNumberId** <br/> |int  <br/> |Externa  <br/> |**PhoneId** del autor de la llamada. Vea la [tabla de teléfonos](phones.md) para obtener más información. Si no NULL y **FromGatewayId** no es nulo, el autor de la llamada era un usuario de RTC. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Externa  <br/> |**PhoneId** del destinatario de la llamada. Vea la [tabla de teléfonos](phones.md) para obtener más información. Si no NULL y **ToGatewayId** no es nulo, el destinatario de la llamada era un usuario de RTC. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Externa  <br/> |El servidor de mediación que proviene la llamada. Consulte la [tabla MediationServers](mediationservers.md) para obtener más información. <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Externa  <br/> |Se trata del servidor de mediación denominado. Consulte la [tabla MediationServers](mediationservers.md) para obtener más información. <br/> |
|**FromGatewayId** <br/> |int  <br/> |Externa  <br/> |Puerta de enlace de la llamada es procedentes de. Consulte la [tabla de puertas de enlace de Skype para Business Server 2015](gateways.md) para obtener más información. <br/> |
|**ToGatewayId** <br/> |int  <br/> |Externa  <br/> |Puerta de enlace de la llamada se va a. Consulte la [tabla de puertas de enlace de Skype para Business Server 2015](gateways.md) para obtener más información. <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Externa  <br/> |URI del usuario que ha desconectado la llamada, si el usuario tiene un identificador URI. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Externa  <br/> |Identificador del teléfono que ha desconectado la llamada se desconectó desde un teléfono. Vea la [tabla de teléfonos](phones.md) para obtener más información. <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   

