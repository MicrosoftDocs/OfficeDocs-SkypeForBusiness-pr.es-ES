---
title: Vista ConferenceSessionDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: La vista ConferenceSessionDetails almacena información acerca de las sesiones entre varias partes. Cada registro representa una sesión de conferencia, que podría ser la sesión con foco o la sesión con un servidor de conferencia específico. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 21c0bf2f68cabf5077c4bc975a84a57da4eeb188
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901076"
---
# <a name="conferencesessiondetails-view"></a>Vista ConferenceSessionDetails
 
La vista ConferenceSessionDetails almacena información acerca de las sesiones entre varias partes. Cada registro representa una sesión de conferencia, que podría ser la sesión con foco o la sesión con un servidor de conferencia específico. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se utiliza en forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con SessionIdTime para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**InviteTime** <br/> |datetime  <br/> |Hora de la primera solicitud INVITE. Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO).  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conferencia.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |URI de tipo de conferencia. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Identificador que diferencia entre instancias de conferencias periódicas. Cada instancia de conferencia periódica tiene el mismo ConferenceURI, pero un valor distinto de ConfInstance.  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |URI del servidor de conferencia.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del servidor de conferencia. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI del usuario que participó en la sesión.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que participó en la sesión. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que participó en la sesión. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del usuario que participó en la sesión.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Versión del servidor de conferencias.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Tipo de servidor de conferencia. Consulte la [tabla UserAgentDef](useragentdef.md) para obtener más información. <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |Categoría de servidor de conferencia.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente usado por el usuario que participó en la sesión.  <br/> |
|**UserClientType** <br/> |int  <br/> |Cliente usado por el usuario que participó en la sesión. Consulte la [tabla UserAgentDef](useragentdef.md) para obtener más detalles. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de la categoría del cliente usado por el usuario que forman parte de la sesión.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI del usuario en cuyo nombre se inició la sesión.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario en cuyo nombre se inició la sesión. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario cuyas en nombre se inició la sesión. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI del usuario que hizo referencia a la sesión.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que hizo referencia a la sesión. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que hizo referencia a la sesión. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |Identificador del cuadro de diálogo SIP. El formato es  <br/> : diálogo; de etiqueta; para etiqueta  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Número de identificador para identificar el cuadro de diálogo que se ha sustituido por la sesión actual. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con ReplaceDialogIdTime para identificar de forma exclusiva una sesión que se ha reemplazado por esta sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |Identificador de diálogo reemplaza la sesión del SIP. El formato de la es:  <br/> cuadro de diálogo; de etiqueta; para etiqueta  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |Indica si la sesión ha sido iniciada por el servidor de conferencia.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |Indica si el servidor de conferencia finalizó la sesión.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |Indica si el usuario se conectó desde la red interna.  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Hora de la respuesta para el primer mensaje invitar. Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de respuesta SIP a la invitación a la sesión. Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |Identificador de diagnóstico había capturado de sesión de los encabezados SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo de contenido para la sesión.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN del servidor Front-End que captura los datos de la sesión.  <br/> |
|**Grupo** <br/> |nvarchar(256)  <br/> |FQDN del grupo de servidores que captura los datos de la sesión.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediación usado por el usuario que participó en la sesión.  <br/> |
|**Puerta de enlace** <br/> |nvarchar(256)  <br/> |Puerta de enlace usada por el usuario que participó la sesión.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor perimetral usado por el usuario que participó en la sesión.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |Indica los atributos del usuario que participó en la sesión. Las siguientes definiciones de atributo permitidas:  <br/> 0 x 01 - integrado con el teléfono de escritorio  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica los atributos de llamada. Se permiten las siguientes definiciones de atributo:  <br/> 0 x 01 - reintento de sesión0  <br/> x02-una llamada realizada por el agente en nombre de un grupo de respuesta  <br/> |
   

