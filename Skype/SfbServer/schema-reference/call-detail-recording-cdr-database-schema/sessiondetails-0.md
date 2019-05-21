---
title: Vista SessionDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: La vista SessionDetails almacena información sobre sesiones de punto a punto, que podrían ser una llamada de teléfono VoIP-VoIP, una sesión de mensajería instantánea de dos proveedores u otro tipo de sesión. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 627d038389098583b5e42f73e8dd0a1cc339d014
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295849"
---
# <a name="sessiondetails-view"></a>Vista SessionDetails
 
La vista SessionDetails almacena información sobre sesiones de punto a punto, que podrían ser una llamada de teléfono VoIP-VoIP, una sesión de mensajería instantánea de dos proveedores u otro tipo de sesión. Esta vista se presentó en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión. Para obtener más información, consulte la tabla [de cuadros de diálogo en la tabla de Skype empresarial Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se usa en conjunción con SessionIdTime para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**InviteTime** <br/> |datetime  <br/> |Hora de la primera solicitud de invitación. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información). Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |Identificador URI del usuario que inició la sesión.  <br/> |
|**ToUr** <br/> |nvarchar (450)  <br/> |Identificador URI del usuario que se unió a la sesión.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que inició la sesión. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que se unió a la sesión. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**FromTenant** <br/> |nvarchar (450)  <br/> |Espacio empresarial del usuario que inició la sesión. Para obtener más información, consulte la [tabla](tenants.md) de inquilinos. <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |El inquilino del usuario que se unió a la sesión. Para obtener más información, consulte la [tabla](tenants.md) de inquilinos. <br/> |
|**FromEndpointId** <br/> |identificador  <br/> |Identificador único del extremo del usuario que inició la sesión.  <br/> |
|**ToEndpointId** <br/> |identificador  <br/> |Identificador único del extremo del usuario que se unió a la sesión.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Número de mensajes enviados por el usuario que inició la sesión.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Número de mensajes enviados por el usuario que se unió a la sesión.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente usada por el usuario que inició la sesión.  <br/> |
|**FromClientType** <br/> |int  <br/> |Cliente usado por el usuario que inició la sesión. Para obtener más información, consulta la [tabla UserAgentDef](useragentdef.md) . <br/> |
|**FromClientCategory** <br/> |nvarchar (64)  <br/> |Nombre de la categoría del cliente que ha usado el usuario que inició la sesión.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Versión de cliente usada por el usuario que se unió a la sesión  <br/> |
|**ToClientType** <br/> |int  <br/> |Cliente usado por el usuario que se unió a la sesión. Para obtener más información, consulta la [tabla UserAgentDef](useragentdef.md) . <br/> |
|**ToClientCategory** <br/> |nvarchar (64)  <br/> |Nombre de la categoría del cliente que ha usado el usuario que se unió a la sesión.  <br/> |
|**TargetUri** <br/> |nvarchar (450)  <br/> |URI del usuario de destino de la sesión.  <br/> |
|**TargetUriType** <br/> |nvarchar (450)  <br/> |Tipo de URI del usuario de destino de la sesión. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)  <br/> |URI del usuario en cuyo nombre se inició la sesión.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario en cuyo nombre se inició la sesión. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario cuyo en nombre se ha iniciado la sesión. Para obtener más información, consulte la [tabla](tenants.md) de inquilinos. <br/> |
|**ReferredByUri** <br/> |nvarchar (450)  <br/> |Identificador URI del usuario que remitió la sesión.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que ha remitido la sesión. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Espacio empresarial del usuario que remitió la sesión. Para obtener más información, consulte la [tabla](tenants.md) de inquilinos. <br/> |
|**DialogId** <br/> |VARCHAR (775)  <br/> |IDENTIFICACIÓN del cuadro de diálogo SIP. El formato es:  <br/> cuadro de diálogo; desde: etiqueta; to-Tag  <br/> |
|**CorrelationId** <br/> |identificador  <br/> |GUID que se usa para correlacionar varias sesiones.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Hora del cuadro de diálogo que se ha sustituido por la sesión. Se usa junto con ReplaceDialogIdSeq para identificar de forma exclusiva un cuadro de diálogo que se reemplaza por la sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se usa junto con ReplaceDialogIdTime para identificar de forma exclusiva un cuadro de diálogo que se reemplaza por la sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**ReplacesDialogId** <br/> |VARCHAR (775)  <br/> |IDENTIFICACIÓN del cuadro de diálogo SIP que reemplaza la sesión. El formato es:  <br/> cuadro de diálogo; desde: etiqueta; to-Tag  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Hora de la respuesta al primer mensaje de invitación. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de respuesta SIP a la invitación de la sesión. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |IDENTIFICACIÓN de diagnóstico capturada de encabezados SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo de contenido de la sesión.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN del servidor front-end que capturó los datos para la sesión.  <br/> |
|**Grupo** <br/> |nvarchar(256)  <br/> |FQDN del grupo de servidores que ha capturado los datos de la sesión.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor perimetral usado por el usuario que inició la sesión.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor perimetral usado por el usuario que inició la sesión  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Indica si el usuario que inició la sesión inició sesión en la red interna.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Indica si el usuario que se unió a la sesión ha iniciado sesión en la red interna.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Prioridad de la llamada de la sesión.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Indica los atributos del usuario que inició la sesión. Se permiten las siguientes definiciones de atributo:  <br/> 0x01: integrado con un teléfono de escritorio  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Indica los atributos del usuario que inició la sesión. Se permiten las siguientes definiciones de atributo:  <br/> 0x01: integrado con un teléfono de escritorio  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica los atributos de la llamada. Se permiten las siguientes definiciones de atributo:  <br/> 0x01-reintento de sesión  <br/> 0x02: una llamada realizada por el agente en nombre de un grupo de respuesta  <br/> |
|**Ubicación** <br/> |VARCHAR (Max)  <br/> |Ubicación de la llamada de emergencia.  <br/> |
|**LastModifiedTime** <br/> |Fechas  <br/> |Para uso interno del servicio de supervisión.  <br/> Este campo se introdujo en Skype empresarial Server 2015.  <br/> |
   

