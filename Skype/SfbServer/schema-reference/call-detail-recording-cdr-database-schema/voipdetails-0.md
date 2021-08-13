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
description: Cada registro representa una llamada de dos partes en la que al menos un usuario es un usuario VoIP.
ms.openlocfilehash: 2314317f23db8edc4d0c2e0cc203cb74104168c472fa81cdfacc1a6595619278
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336423"
---
# <a name="voipdetails-table"></a>Tabla VoipDetails
 
Cada registro representa una llamada de dos partes en la que al menos un usuario es un usuario VoIP.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal  <br/> |Hora de la solicitud de sesión. Se usa junto con **SessionIdSeq** para identificar una sesión de manera exclusiva. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Principal  <br/> |Número del identificador para identificar la sesión. Se usa en combinación con **SessionIdTime** para identificar de forma única una sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**FromNumberId** <br/> |Entero  <br/> |Externo  <br/> |**PhoneId** del autor de la llamada. Consulta la [tabla Teléfonos](phones.md) para obtener más información. Si no es NULL y **FromGatewayId** no es NULL, el autor de la llamada era un usuario RTC. <br/> |
|**ConnectedNumberId** <br/> |Entero  <br/> |Externo  <br/> |**PhoneId** del receptor de llamadas. Consulta la [tabla Teléfonos](phones.md) para obtener más información. Si no es NULL y **ToGatewayId** no es NULL, el receptor de llamadas era un usuario RTC. <br/> |
|**FromMediationServerId** <br/> |Entero  <br/> |Externo  <br/> |El servidor de mediación desde el que viene la llamada. Vea la [tabla MediationServers](mediationservers.md) para obtener más información. <br/> |
|**ToMediationServerId** <br/> |Entero  <br/> |Externo  <br/> |Se va a llamar al servidor de mediación. Vea la [tabla MediationServers](mediationservers.md) para obtener más información. <br/> |
|**FromGatewayId** <br/> |Entero  <br/> |Externo  <br/> |Puerta de enlace desde la que viene la llamada. Vea la tabla Puertas de enlace [de Skype Empresarial Server 2015](gateways.md) para obtener más información. <br/> |
|**ToGatewayId** <br/> |Entero  <br/> |Externo  <br/> |Puerta de enlace a la que se va a llamar. Vea la tabla Puertas de enlace [de Skype Empresarial Server 2015](gateways.md) para obtener más información. <br/> |
|**DisconnectedbyURIId** <br/> |Entero  <br/> |Externo  <br/> |URI del usuario que desconectó la llamada, si el usuario tiene un URI. Consulta la [tabla Usuarios](users.md) para obtener más información. <br/> |
|**DisconnectedbyPhoneId** <br/> |Entero  <br/> |Externo  <br/> |El identificador del teléfono que desconectó la llamada se desconectó de un teléfono. Consulta la [tabla Teléfonos](phones.md) para obtener más información. <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype Empresarial Server 2015.  <br/> |
   

