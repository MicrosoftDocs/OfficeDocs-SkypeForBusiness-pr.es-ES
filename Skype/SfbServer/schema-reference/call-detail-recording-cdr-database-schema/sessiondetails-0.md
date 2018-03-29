---
title: Vista de SessionDetails
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: La vista SessionDetails almacena información acerca de las sesiones de peer-to-peer, que puede ser una llamada de teléfono VoIP VoIP, sesión de mensajería instantánea de dos partes u otro tipo de sesión. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: b13b0b184d13273c339f1ca3fa09a68687d26889
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="sessiondetails-view"></a>Vista de SessionDetails
 
La vista SessionDetails almacena información acerca de las sesiones de peer-to-peer, que puede ser una llamada de teléfono VoIP VoIP, sesión de mensajería instantánea de dos partes u otro tipo de sesión. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se utiliza junto con SessionIdSeq para identificar una sesión. Consulte la tabla [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con SessionIdTime para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**InviteTime** <br/> |datetime  <br/> |Hora de la primera solicitud de invitación. Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información). Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información).  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI del usuario que inició la sesión.  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI del usuario que ha unido a la sesión.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que inició la sesión. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que ha unido a la sesión. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |Inquilinos del usuario que inició la sesión. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |El inquilino del usuario que se incorporó a la sesión. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del extremo del usuario que inició la sesión.  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del extremo del usuario que ha unido a la sesión.  <br/> |
|**Hora de finalización** <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Número de mensajes enviados por el usuario que inició la sesión.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Número de mensajes enviados por el usuario al que se unió a la sesión.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Versión de cliente utilizada por el usuario que inició la sesión.  <br/> |
|**FromClientType** <br/> |int  <br/> |Cliente utilizado por el usuario que inició la sesión. Consulte la [tabla de UserAgentDef](useragentdef.md) para obtener más detalles. <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de la categoría del cliente utilizado por el usuario que inició la sesión.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Versión de cliente utilizada por el usuario que se incorporó a la sesión  <br/> |
|**ToClientType** <br/> |int  <br/> |Cliente utilizado por el usuario, que se incorporó a la sesión. Consulte la [tabla de UserAgentDef](useragentdef.md) para obtener más detalles. <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de la categoría del cliente utilizado por el usuario que se incorporó a la sesión.  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |URI del usuario de la sesión de destino.  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |Tipo de URI del usuario de destino para la sesión. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI del usuario en cuyo nombre se inició la sesión.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario en cuyo nombre se inició la sesión. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Inquilinos del usuario cuya en nombre se inició la sesión. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI del usuario que a que se refiere la sesión.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que a que se refiere la sesión. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que a que se refiere la sesión. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de SIP El formato es:  <br/> diálogo de etiqueta; para etiqueta  <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> |GUID utilizado para correlacionar múltiples sesiones.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Hora del cuadro de diálogo que se ha reemplazado por la sesión. Se utiliza junto con ReplaceDialogIdSeq para identificar un cuadro de diálogo que se reemplaza por la sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con ReplaceDialogIdTime para identificar un cuadro de diálogo que se reemplaza por la sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |ID de diálogo sustituye a la sesión del SIP. El formato es:  <br/> diálogo de etiqueta; para etiqueta  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Hora de la respuesta al primer mensaje de invitación. Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de respuesta SIP a la invitación de sesión. Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID. de diagnóstico capturada de encabezados SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo de contenido de la sesión.  <br/> |
|**Front-end** <br/> |nvarchar(256)  <br/> |FQDN del servidor Front-End que capturan los datos de la sesión.  <br/> |
|**Grupo de servidores** <br/> |nvarchar(256)  <br/> |FQDN del grupo que captura los datos de la sesión.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor de borde utilizado por el usuario que inició la sesión.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor de borde utilizado por el usuario que inició la sesión  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Indica si el usuario que inició la sesión iniciado sesión desde la red interna.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Indica si el usuario que se incorporó a la sesión de una sesión desde la red interna.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Llame a la prioridad de la sesión.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Indica los atributos del usuario que inició la sesión. Se permiten las siguientes definiciones de atributo:  <br/> 0 x 01 - integrado con el teléfono de escritorio  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Indica los atributos del usuario que inició la sesión. Se permiten las siguientes definiciones de atributo:  <br/> 0 x 01 - integrado con el teléfono de escritorio  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica los atributos de la llamada. Se permiten las siguientes definiciones de atributo:  <br/> 0 x 01 - reintenta la sesión  <br/> 0 x 02 - una llamada realizada por el agente en nombre de un grupo de respuesta  <br/> |
|**Ubicación** <br/> |varchar (max)  <br/> |Ubicación de llamada de emergencia.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> |Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   

