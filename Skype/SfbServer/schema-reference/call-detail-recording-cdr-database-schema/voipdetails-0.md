---
title: Tabla VoipDetails
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Cada registro representa una llamada de dos partes en la que al menos un usuario es un usuario voIP.
ms.openlocfilehash: 900598c99965292e7d349520cc2dfa55443bb5a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813100"
---
# <a name="voipdetails-table"></a>Tabla VoipDetails
 
Cada registro representa una llamada de dos partes en la que al menos un usuario es un usuario voIP.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal  <br/> |Hora de la solicitud de sesión. Se usa junto con **SessionIdSeq** para identificar una sesión de manera exclusiva. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |entero  <br/> |Principal  <br/> |Número del identificador para identificar la sesión. Se usa en combinación con **SessionIdTime** para identificar de forma única una sesión. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**FromNumberId** <br/> |entero  <br/> |Externo  <br/> |**PhoneId del** autor de la llamada. Consulte la [tabla Teléfonos](phones.md) para obtener más información. Si no es NULL y **FromGatewayId** no es NULL, el autor de la llamada era un usuario RTC. <br/> |
|**ConnectedNumberId** <br/> |entero  <br/> |Externo  <br/> |**PhoneId del** receptor de llamadas. Consulte la [tabla Teléfonos](phones.md) para obtener más información. Si no es NULL y **ToGatewayId** no es NULL, el receptor de llamadas era un usuario RTC. <br/> |
|**FromMediationServerId** <br/> |entero  <br/> |Externo  <br/> |El servidor de mediación del que viene la llamada. Consulte la [tabla MediationServers](mediationservers.md) para obtener más información. <br/> |
|**ToMediationServerId** <br/> |entero  <br/> |Externo  <br/> |Se va a llamar al servidor de mediación. Consulte la [tabla MediationServers](mediationservers.md) para obtener más información. <br/> |
|**FromGatewayId** <br/> |entero  <br/> |Externo  <br/> |Puerta de enlace de la que viene la llamada. Consulte la [tabla Puertas de enlace de Skype Empresarial Server 2015](gateways.md) para obtener más información. <br/> |
|**ToGatewayId** <br/> |entero  <br/> |Externo  <br/> |Puerta de enlace a la que se va a llamar. Consulte la [tabla Puertas de enlace de Skype Empresarial Server 2015](gateways.md) para obtener más información. <br/> |
|**DisconnectedbyURIId** <br/> |entero  <br/> |Externo  <br/> |URI del usuario que desconectó la llamada, si el usuario tiene un URI. Vea la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**DisconnectedbyPhoneId** <br/> |entero  <br/> |Externo  <br/> |El identificador del teléfono que desconectó la llamada se desconectó de un teléfono. Consulte la [tabla Teléfonos](phones.md) para obtener más información. <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype Empresarial Server 2015.  <br/> |
   

