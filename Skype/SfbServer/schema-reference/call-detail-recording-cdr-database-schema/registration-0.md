---
title: Vista de registro
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
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: La vista de registro almacena información sobre el registro de usuarios. Esta vista se introdujo en Lync Server 2013.
ms.openlocfilehash: 12508e7efcd96bdb9e3956b4e62c1065235a3f60
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823130"
---
# <a name="registration-view"></a>Vista de registro
 
La vista de registro almacena información sobre el registro de usuarios. Esta vista se introdujo en Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |entero  <br/> |Número de identificador para identificar la sesión. Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**RegisterTime** <br/> |datetime  <br/> |Hora a la que ocurrió el registro.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI del usuario que se registró.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que se registró. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que se registró. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del extremo con el que se registró el usuario.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |Identificador único que se utiliza para diferenciar los registros con el mismo usuario y el mismo extremo.  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |Hora a la que ocurrió la anulación de registro.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Motivo de la anulación de registro.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente que utilizó el usuario que se registró.  <br/> |
|**ClientType** <br/> |entero  <br/> |Cliente que utilizó el usuario que se registró. Vea la [tabla UserAgentDef](useragentdef.md) para obtener más información. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Categoría del cliente que utilizó el usuario que se registró.  <br/> |
|**IpAddress** <br/> |nvarchar(256)  <br/> |Dirección IP con la que se registró el usuario. Puede ser una dirección IPv4 o IPv6.  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |Identificador del diálogo SIP. El formato es:  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseCode** <br/> |entero  <br/> |Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |entero  <br/> |Identificador de diagnóstico capturado del encabezado SIP.  <br/> |
|**Registrador** <br/> |nvarchar(256)  <br/> |FQDN del registrador.  <br/> |
|**Grupo** <br/> |nvarchar(256)  <br/> |FQDN del grupo de servidores que capturó los datos de la sesión.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor perimetral que utilizó el usuario que se registró.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Indica si el usuario inició sesión desde la red interna.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Indica si el UserService estaba disponible en el momento del registro.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Indica si el registro se realizó con el registrador principal.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |Dirección MAC del dispositivo registrado.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Fabricante del dispositivo registrado. Consulte la [tabla Fabricantes de Skype Empresarial Server 2015](manufacturers.md) para obtener más información. <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Versión del hardware del dispositivo registrado. Consulte la [tabla HardwareVersions en Skype Empresarial Server 2015](hardwareversions.md) para obtener más información. <br/> |
   

