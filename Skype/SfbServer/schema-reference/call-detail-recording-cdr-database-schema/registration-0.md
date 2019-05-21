---
title: Vista registro
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: La vista de registro almacena información sobre el registro de usuarios. Esta vista se presentó en Lync Server 2013.
ms.openlocfilehash: 6202e40e6385fd243f55badd25dbe196452c890a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295870"
---
# <a name="registration-view"></a>Vista registro
 
La vista de registro almacena información sobre el registro de usuarios. Esta vista se presentó en Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se usa en conjunción con SessionIdTime para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**RegisterTime** <br/> |datetime  <br/> |Hora en la que se realizó el registro.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |Identificador URI del usuario que se registró.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que se registró. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que se registró. Para obtener más información, consulte la [tabla](tenants.md) de inquilinos. <br/> |
|**EndpointId** <br/> |identificador  <br/> |Identificador único del extremo del usuario registrado con.  <br/> |
|**EndpointEra** <br/> |identificador  <br/> |Identificador único que se usa para diferenciar los registros que implican al mismo usuario y al mismo punto de conexión.  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |Hora en la que se produjo la anulación de inscripción.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Motivo de la anulación del registro.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente que usó el usuario que se registró.  <br/> |
|**Tipocliente** <br/> |int  <br/> |Cliente usado por el usuario que registró. Para obtener más información, consulta la [tabla UserAgentDef](useragentdef.md) . <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Categoría del cliente que ha usado el usuario que registró.  <br/> |
|**Dirección IP** <br/> |nvarchar(256)  <br/> |Dirección IP con la que el usuario se registró. Puede ser una dirección IPv4 o IPv6.  <br/> |
|**DialogId** <br/> |varstring (775)  <br/> |IDENTIFICACIÓN del cuadro de diálogo SIP. El formato de es:  <br/> cuadro de diálogo; desde: etiqueta; to-Tag  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de respuesta SIP a la invitación de la sesión. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |IDENTIFICACIÓN de diagnóstico capturada del encabezado de SIP.  <br/> |
|**Registrador** <br/> |nvarchar(256)  <br/> |FQDN del registrador.  <br/> |
|**Grupo** <br/> |nvarchar(256)  <br/> |FQDN del grupo de servidores que ha capturado los datos de la sesión.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor perimetral usado por el usuario que registró.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Indica si el usuario ha iniciado sesión en la red interna.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Indica si el UserService estaba disponible en el momento del registro.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Indica si el registro se realizó con el registrador principal.  <br/> |
|**DeviceMacAddress** <br/> |BIGINT  <br/> |Dirección MAC del dispositivo registrado.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Fabricante del dispositivo registrado. Para obtener más información, consulte la [tabla de fabricantes en Skype empresarial Server 2015](manufacturers.md) . <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Versión de hardware del dispositivo registrada. Para obtener más información, consulte la [tabla HardwareVersions en Skype empresarial Server 2015](hardwareversions.md) . <br/> |
   

