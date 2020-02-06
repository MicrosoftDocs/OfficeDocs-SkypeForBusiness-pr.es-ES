---
title: Tabla VoipDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Cada registro representa una llamada de fiesta de 1 2 en la que al menos un usuario es un usuario de VoIP.
ms.openlocfilehash: 65bf3b4d7a815434b21b761030a7ac514d9bd803
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814788"
---
# <a name="voipdetails-table"></a>Tabla VoipDetails
 
Cada registro representa una llamada de fiesta de 1 2 en la que al menos un usuario es un usuario de VoIP.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Hora de la solicitud de sesión. Se usa en conjunción con **SessionIdSeq** para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Número de identificación para identificar la sesión. Se usa en conjunción con **SessionIdTime** para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**FromNumberId** <br/> |int  <br/> |Extranjero  <br/> |**PhoneId** de la persona que llama. Para obtener más información, consulte la [tabla teléfonos](phones.md) . Si no es NULL y **FromGatewayId** no es null, la persona que llama era un usuario de la RTC. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Extranjero  <br/> |**PhoneId** del receptor de la llamada. Para obtener más información, consulte la [tabla teléfonos](phones.md) . Si no es NULL y **ToGatewayId** no es null, el receptor de la llamada fue un usuario de la RTC. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Extranjero  <br/> |El servidor de mediación del que procede la llamada. Para obtener más información, consulte la [tabla MediationServers](mediationservers.md) . <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Extranjero  <br/> |El servidor de mediación llamado es el. Para obtener más información, consulte la [tabla MediationServers](mediationservers.md) . <br/> |
|**FromGatewayId** <br/> |int  <br/> |Extranjero  <br/> |Puerta de enlace de la cual procede la llamada. Para obtener más información, consulte la [tabla de puertas de enlace en Skype empresarial Server 2015](gateways.md) . <br/> |
|**ToGatewayId** <br/> |int  <br/> |Extranjero  <br/> |Puerta de enlace a la que va la llamada. Para obtener más información, consulte la [tabla de puertas de enlace en Skype empresarial Server 2015](gateways.md) . <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Extranjero  <br/> |URI del usuario que desconectó la llamada, si el usuario tiene un URI. Para obtener más información, consulte la [tabla usuarios](users.md) . <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Extranjero  <br/> |El identificador del teléfono que desconectó la llamada se desconectó de un teléfono. Para obtener más información, consulte la [tabla teléfonos](phones.md) . <br/> |
|**LastModifiedTime** <br/> |Fechas  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype empresarial Server 2015.  <br/> |
   

