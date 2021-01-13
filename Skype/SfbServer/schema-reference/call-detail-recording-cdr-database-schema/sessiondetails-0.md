---
title: Vista SessionDetails
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
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: La vista SessionDetails almacena información sobre sesiones punto a punto, que podrían ser una llamada telefónica VoIP-VoIP, una sesión de mensajería instantánea (MI) entre dos partes o cualquier otro tipo de sesión. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 71875dd1f3399b382c1fac3754436ada052873af
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809960"
---
# <a name="sessiondetails-view"></a>Vista SessionDetails
 
La vista SessionDetails almacena información sobre sesiones punto a punto, que podrían ser una llamada telefónica VoIP-VoIP, una sesión de mensajería instantánea (MI) entre dos partes o cualquier otro tipo de sesión. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Consulte la [tabla Cuadros de diálogo de la tabla de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |entero  <br/> |Número de identificador para identificar la sesión. Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**InviteTime** <br/> |datetime  <br/> |Fecha y hora de la primera solicitud INVITE. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no existe el mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO). Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no existe el mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI del usuario que inició la sesión.  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI del usuario que se unió a la sesión.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que inició la sesión. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que se unió a la sesión. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |Inquilino del usuario que inició la sesión. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que se unió a la sesión. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del extremo del usuario que inició la sesión.  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del extremo del usuario que se unió a la sesión.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Fecha y hora de finalización de la sesión.  <br/> |
|**FromMessageCount** <br/> |entero  <br/> |Número de mensajes que envió el usuario que inició la sesión.  <br/> |
|**ToMessageCount** <br/> |entero  <br/> |Número de mensajes que envió el usuario que se unió a la sesión.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Versión de cliente que usa el usuario que inició la sesión.  <br/> |
|**FromClientType** <br/> |entero  <br/> |Cliente que usa el usuario que inició la sesión. Vea la [tabla UserAgentDef](useragentdef.md) para obtener más información. <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de la categoría del cliente que usa el usuario que inició la sesión.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Versión de cliente que usa el usuario que se unió a la sesión  <br/> |
|**ToClientType** <br/> |entero  <br/> |Cliente que usa el usuario que se unió a la sesión. Vea la [tabla UserAgentDef](useragentdef.md) para obtener más información. <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de la categoría del cliente que usa el usuario que se unió a la sesión.  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |URI del usuario destinatario de la sesión.  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |Tipo de URI del usuario destinatario de la sesión. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI del usuario en cuyo nombre se inició la sesión.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario en cuyo nombre se inició la sesión. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario en cuyo nombre se inició la sesión. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI del usuario que hizo referencia a la sesión.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que hizo referencia a la sesión. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que hizo referencia a la sesión. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |Identificador del diálogo SIP. El formato es:  <br/> dialog;from-tag;to-tag  <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> |Identificador único global usado para correlacionar varias sesiones.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Fecha y hora del diálogo que se sustituyó por la sesión. Se usa en combinación con ReplaceDialogIdSeq para identificar de forma exclusiva un diálogo que se sustituye con la sesión. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**ReplaceDialogIdSeq** <br/> |entero  <br/> |Número de identificador de la sesión. Se usa en combinación con ReplaceDialogIdTime para identificar de forma exclusiva un diálogo que se sustituye con la sesión. Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |El identificador de diálogo SIP que sustituye la sesión. El formato es:  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Fecha y hora de la respuesta al primer mensaje INVITE. Este campo se suele rellenar con los datos generados a partir del mensaje INVITE inicial. Si no hay un mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseCode** <br/> |entero  <br/> |Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |entero  <br/> |Identificador de diagnóstico capturado de los encabezados SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo de contenido de la sesión.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN del servidor front-end que capturó los datos de la sesión.  <br/> |
|**Grupo** <br/> |nvarchar(256)  <br/> |FQDN del grupo que capturó los datos de la sesión.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor perimetral que usa el usuario que inició la sesión.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor perimetral que usa el usuario que inició la sesión  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Indica si el usuario que inició la sesión se conectó desde la red interna.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Indica si el usuario que se unió a la sesión se conectó desde la red interna.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Prioridad de llamada de la sesión.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Indica los atributos del usuario que inició la sesión. Las definiciones de atributos permitidas son las siguientes:  <br/> 0x01 - Integrado en teléfono de escritorio  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Indica los atributos del usuario que inició la sesión. Las definiciones de atributos permitidas son las siguientes:  <br/> 0x01 - Integrado en teléfono de escritorio  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica los atributos de llamada. Se permiten las siguientes definiciones de atributo:  <br/> 0x01 - Reintento de sesión  <br/> 0x02 - Una llamada realizada por un agente en nombre de un Grupo de respuesta  <br/> |
|**Location** <br/> |varchar(max)  <br/> |Ubicación de una llamada de emergencia.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> |Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype Empresarial Server 2015.  <br/> |
   

