---
title: Vista de registro
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: La vista de registro almacena información acerca del registro de usuario. Esta vista se introdujo en Lync Server 2013.
ms.openlocfilehash: 820e99296b93743d13709e5296ed1c317079be3b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930661"
---
# <a name="registration-view"></a>Vista de registro
 
La vista de registro almacena información acerca del registro de usuario. Esta vista se introdujo en Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se utiliza en forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con SessionIdTime para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**RegisterTime** <br/> |datetime  <br/> |Hora en que ocurrió el registro.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI del usuario que se registró.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que se registró. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que se registró. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**Valor EndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del extremo del usuario registrado con.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |Identificador único que se usa para diferenciar los registros con el mismo usuario y el mismo extremo.  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |Hora en que la anulación de registro se ha producido.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Motivo de la anulación de registro.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente usado por el usuario que se registró.  <br/> |
|**TipoCliente** <br/> |int  <br/> |Cliente usado por el usuario que se registró. Consulte la [tabla UserAgentDef](useragentdef.md) para obtener más detalles. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Categoría del cliente usado por el usuario que se registró.  <br/> |
|**IpAddress** <br/> |nvarchar(256)  <br/> |El usuario registrado con la dirección IP. Esto puede ser una dirección IPv4 o IPv6.  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |Identificador del cuadro de diálogo SIP. El formato de la es:  <br/> cuadro de diálogo; de etiqueta; para etiqueta  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de respuesta SIP a la invitación a la sesión. Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |Identificador de diagnóstico capturado del encabezado SIP.  <br/> |
|**Registrador** <br/> |nvarchar(256)  <br/> |FQDN del registrador.  <br/> |
|**Grupo** <br/> |nvarchar(256)  <br/> |FQDN del grupo de servidores que captura los datos de la sesión.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor perimetral usado por el usuario que se registró.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Indica si el usuario se conectó desde la red interna.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Indica si el UserService estaba disponible en el momento del registro.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Indica si el registro se realizó con el registrador principal.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |Dirección MAC del dispositivo registrado.  <br/> |
|**Entradas DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Fabricante del dispositivo registrado. Consulte la [tabla de los fabricantes de Skype para Business Server 2015](manufacturers.md) para obtener más información. <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Versión de hardware del dispositivo registrado. Consulte la [tabla HardwareVersions en Skype para Business Server 2015](hardwareversions.md) para obtener más información. <br/> |
   

