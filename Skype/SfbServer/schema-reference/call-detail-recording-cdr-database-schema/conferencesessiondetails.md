---
title: Vista ConferenceSessionDetails
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
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: La vista ConferenceSessionDetails almacena información sobre sesiones con varios participantes. Cada registro representa una sesión de conferencia, que podría ser la sesión con Foco o la sesión con un servidor de conferencia específico. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: d11573f8911f02001101c2d6f2e13dd5ec2112017ada115282b9c0ed008176f1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337658"
---
# <a name="conferencesessiondetails-view"></a>Vista ConferenceSessionDetails
 
La vista ConferenceSessionDetails almacena información sobre sesiones con varios participantes. Cada registro representa una sesión de conferencia, que podría ser la sesión con Foco o la sesión con un servidor de conferencia específico. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |Entero  <br/> |Número de identificador para identificar la sesión. Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**InviteTime** <br/> |datetime  <br/> |Hora de la primera solicitud de invitación. Este campo se rellena normalmente con datos generados por el mensaje INVITE inicial en la sesión. Si no aparece ningún mensaje INVITE, el campo se rellena con la fecha y hora del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conferencia.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI de la conferencia. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Identificador que diferencia entre instancias de conferencias periódicas. Cada instancia de conferencia recurrente tiene el mismo ConferenceURI, pero un valor diferente de ConfInstance.  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |URI del servidor de conferencias.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del servidor de conferencias. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI del usuario que participó en la sesión.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que participó en la sesión. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que participó en la sesión. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del usuario que participó en la sesión.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Versión del servidor de conferencias.  <br/> |
|**ConferenceClientType** <br/> |Entero  <br/> |Tipo del servidor de conferencias. Consulte la [tabla UserAgentDef](useragentdef.md) para obtener más información. <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |Categoría del servidor de conferencias.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente usado por el usuario que participó en la sesión.  <br/> |
|**UserClientType** <br/> |Entero  <br/> |Cliente usado por el usuario que participó en la sesión. Consulta la [tabla UserAgentDef](useragentdef.md) para obtener más información. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de categoría del cliente usado por el usuario que participó en la sesión.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI del usuario en cuyo nombre se inició la sesión.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario en cuyo nombre se inició la sesión. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario en cuyo nombre se inició la sesión. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI del usuario que hizo referencia a la sesión.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que hizo referencia a la sesión. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que hizo referencia a la sesión. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |Id. del diálogo SIP. El formato es  <br/> :d ialog;from-tag;to-tag  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Número de identificador que identifica el cuadro de diálogo que se reemplazó por la sesión actual. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**ReplaceDialogIdSeq** <br/> |Entero  <br/> |Número de identificador que identifica la sesión. Se usa junto a ReplaceDialogIdTime para identificar únicamente una sesión que se reemplaza por esta sesión. Vea la [tabla Cuadros de diálogo de Skype Empresarial Server 2015](dialogs.md) para obtener más información. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |Id. del diálogo SIP que reemplaza esta sesión. El formato es:  <br/> dialog;from-tag;to-tag  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |Indica si el servidor de conferencias inició la sesión.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |Indica si el servidor de conferencias finalizó la sesión.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |Indica si el usuario ha iniciado sesión desde la red interna.  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Fecha y hora de la respuesta al primer mensaje INVITE. Este campo se suele rellenar con los datos generados a partir del mensaje INVITE inicial. Si no hay un mensaje INVITE, el campo se rellenará con la fecha y hora del primer mensaje SIP relevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**ResponseCode** <br/> |Entero  <br/> |Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |Entero  <br/> |Identificador de diagnóstico capturado de los encabezados SIP de la sesión.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo de contenido para la sesión.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN del servidor front-end que capturó los datos de la sesión.  <br/> |
|**Grupo** <br/> |nvarchar(256)  <br/> |FQDN del grupo que captura los datos de la sesión.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediación usado por el usuario que participó en la sesión.  <br/> |
|**Puerta de enlace** <br/> |nvarchar(256)  <br/> |Puerta de enlace usada por el usuario que participó en la sesión.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor perimetral usado por el usuario que participó en la sesión.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |Indica los atributos del usuario que participó en la sesión. Se permiten las siguientes definiciones de atributos:  <br/> 0x01 - Integrado con el teléfono de escritorio  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica los atributos de la llamada. Se permiten las siguientes definiciones de atributos:  <br/> 0x01 - Reintento de sesión0  <br/> x02 - Una llamada realizada por el agente en nombre de un grupo de respuestas  <br/> |
   

