---
title: Tabla VoipDetails
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Cada registro representa una llamada de dos partes en que al menos un usuario es un usuario de VoIP.
ms.openlocfilehash: 8f28ec3ac1d4049f24c5af5b768026bdd8a98486
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="voipdetails-table"></a>Tabla VoipDetails
 
Cada registro representa una llamada de dos partes en que al menos un usuario es un usuario de VoIP.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Hora de la solicitud de sesión. Se utiliza junto con **SessionIdSeq** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**FromNumberId** <br/> |int  <br/> |Externa  <br/> |**PhoneId** del llamador. Consulte la [tabla de teléfonos](phones.md) para obtener más información. Si no NULL y **FromGatewayId** no es NULL, el llamador era un usuario PSTN. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Externa  <br/> |**PhoneId** del receptor de la llamada. Consulte la [tabla de teléfonos](phones.md) para obtener más información. Si no NULL y **ToGatewayId** no es NULL, el receptor de la llamada era un usuario PSTN. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Externa  <br/> |El servidor de mediación que proviene la llamada. Consulte la [tabla de MediationServers](mediationservers.md) para obtener más información. <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Externa  <br/> |El servidor de mediación llama va a. Consulte la [tabla de MediationServers](mediationservers.md) para obtener más información. <br/> |
|**FromGatewayId** <br/> |int  <br/> |Externa  <br/> |Procedente de la puerta de enlace de la llamada. Consulte la [tabla de puertas de enlace de Skype para Business Server 2015](gateways.md) para obtener más información. <br/> |
|**ToGatewayId** <br/> |int  <br/> |Externa  <br/> |Va a la puerta de enlace de la llamada. Consulte la [tabla de puertas de enlace de Skype para Business Server 2015](gateways.md) para obtener más información. <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Externa  <br/> |URI del usuario que ha desconectado la llamada, si el usuario tiene un identificador URI. Consulte la [tabla de usuarios](users.md) para obtener más información. <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Externa  <br/> |Se desconectó la ID del teléfono que desconectó la llamada desde un teléfono. Consulte la [tabla de teléfonos](phones.md) para obtener más información. <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   

