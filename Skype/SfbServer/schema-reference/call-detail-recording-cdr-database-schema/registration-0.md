---
title: Vista de registro
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: La vista de registro almacena información acerca del registro de usuario. Esta vista se introdujo en Lync Server 2013.
ms.openlocfilehash: e116c2609f1f26268eaaa3413c3a4491da096585
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="registration-view"></a>Vista de registro
 
La vista de registro almacena información acerca del registro de usuario. Esta vista se introdujo en Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se utiliza junto con SessionIdSeq para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con SessionIdTime para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**RegisterTime** <br/> |datetime  <br/> |Hora en que se produjo la inscripción.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI del usuario que ha registrado.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que ha registrado. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Inquilinos del usuario que esté registrado. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**Valor EndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del extremo del usuario registrado con.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |Identificador único que se utiliza para diferenciar los registros que implican el mismo usuario y el mismo extremo.  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |Tiempo en que la anulación de registro se ha producido.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Motivo de anulación.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versión de cliente utilizada por el usuario que esté registrado.  <br/> |
|**TipoCliente** <br/> |int  <br/> |Cliente utilizado por el usuario que esté registrado. Consulte la [tabla de UserAgentDef](useragentdef.md) para obtener más detalles. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Categoría del cliente utilizado por el usuario que esté registrado.  <br/> |
|**Dirección IP** <br/> |nvarchar(256)  <br/> |El usuario registrado con la dirección IP. Esto puede ser una dirección IPv4 o IPv6.  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID de SIP El formato de la es:  <br/> diálogo de etiqueta; para etiqueta  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de respuesta SIP a la invitación de sesión. Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID. de diagnóstico capturado de encabezado SIP.  <br/> |
|**Registrar** <br/> |nvarchar(256)  <br/> |FQDN del registrador.  <br/> |
|**Grupo de servidores** <br/> |nvarchar(256)  <br/> |FQDN del grupo que captura los datos de la sesión.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor de borde utilizado por el usuario que registró.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Indica si el usuario inició sesión desde la red interna.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Indica si la UserService estaba disponible en el momento de registro.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Indica si el registro fue con el registrador principal.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |Dirección MAC del dispositivo registrado.  <br/> |
|**Entradas DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Fabricante del dispositivo registrado. Consulte la [tabla de fabricantes en Skype para Business Server 2015](manufacturers.md) para obtener más información. <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Versión de hardware del dispositivo registrado. Consulte la [tabla HardwareVersions en Skype para Business Server 2015](hardwareversions.md) para obtener más información. <br/> |
   

