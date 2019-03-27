---
title: Vista SessionDetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: La vista SessionDetails almacena información acerca de las sesiones de punto a punto, que podría ser una llamada de teléfono VoIP-VoIP, sesión de mensajería instantánea entre dos participantes u otro tipo de sesión. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: c62f6e2c1bb505bf00d56898a562db2c00d298d0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896031"
---
# <a name="sessiondetails-view"></a>Vista SessionDetails
 
La vista SessionDetails almacena información acerca de las sesiones de punto a punto, que podría ser una llamada de teléfono VoIP-VoIP, sesión de mensajería instantánea entre dos participantes u otro tipo de sesión. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se utiliza en forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Vea la tabla de [cuadros de diálogo de tabla en Skype para Business Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con SessionIdTime para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**InviteTime** <br/> |datetime  <br/> |Hora de la primera solicitud INVITE. Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO). Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO).  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI del usuario que inició la sesión.  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI del usuario que ha iniciado la sesión.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que inició la sesión. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que ha iniciado la sesión. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |Inquilino del usuario que inició la sesión. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |El inquilino del usuario que se unió a la sesión. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del extremo del usuario que inició la sesión.  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del extremo del usuario que ha iniciado la sesión.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Número de mensajes enviados por el usuario que inició la sesión.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Número de mensajes enviados por el usuario que ha iniciado la sesión.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente usado por el usuario que inició la sesión.  <br/> |
|**FromClientType** <br/> |int  <br/> |Cliente usado por el usuario que inició la sesión. Consulte la [tabla UserAgentDef](useragentdef.md) para obtener más detalles. <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de la categoría del cliente usado por el usuario que inició la sesión.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente usado por el usuario que ha iniciado la sesión  <br/> |
|**ToClientType** <br/> |int  <br/> |Cliente usado por el usuario que ha iniciado la sesión. Consulte la [tabla UserAgentDef](useragentdef.md) para obtener más detalles. <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de la categoría del cliente usado por el usuario que ha iniciado la sesión.  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |URI del usuario de destino de la sesión.  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |Tipo de URI del usuario de destino para la sesión. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI del usuario en cuyo nombre se inició la sesión.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario en cuyo nombre se inició la sesión. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario cuyas en nombre se inició la sesión. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI del usuario que hizo referencia a la sesión.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que hizo referencia a la sesión. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que hizo referencia a la sesión. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |Identificador del cuadro de diálogo SIP. El formato es:  <br/> cuadro de diálogo; de etiqueta; para etiqueta  <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> |Identificador único global usado para correlacionar varias sesiones.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Hora del cuadro de diálogo que se ha sustituido por la sesión. Se utiliza junto con ReplaceDialogIdSeq para identificar de forma única un cuadro de diálogo que se ha reemplazado por la sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con ReplaceDialogIdTime para identificar de forma única un cuadro de diálogo que se ha reemplazado por la sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |Identificador de diálogo reemplaza la sesión del SIP. El formato es:  <br/> cuadro de diálogo; de etiqueta; para etiqueta  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Hora de la respuesta para el primer mensaje invitar. Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de respuesta SIP a la invitación a la sesión. Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |Identificador de diagnóstico capturado de los encabezados SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo de contenido para la sesión.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN del servidor Front-End que captura los datos de la sesión.  <br/> |
|**Grupo** <br/> |nvarchar(256)  <br/> |FQDN del grupo de servidores que captura los datos de la sesión.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor perimetral usado por el usuario que inició la sesión.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor perimetral usado por el usuario que inició la sesión  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Indica si el usuario que inició la sesión se conectó desde la red interna.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Indica si el usuario que ha iniciado la sesión se conectó desde la red interna.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Prioridad de llamada de la sesión.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Indica los atributos del usuario que inició la sesión. Se permiten las siguientes definiciones de atributo:  <br/> 0 x 01 - integrado con el teléfono de escritorio  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Indica los atributos del usuario que inició la sesión. Se permiten las siguientes definiciones de atributo:  <br/> 0 x 01 - integrado con el teléfono de escritorio  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica los atributos de llamada. Se permiten las siguientes definiciones de atributo:  <br/> 0 x 01 - reintento de sesión  <br/> 0 x 02 - una llamada realizada por el agente en nombre de un grupo de respuesta  <br/> |
|**Ubicación** <br/> |varchar (max)  <br/> |Ubicación de llamada de emergencia.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> |Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   

