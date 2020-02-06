---
title: Vista ConferenceSessionDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: La vista ConferenceSessionDetails almacena información sobre las sesiones de varias partes. Cada registro representa una sesión de conferencia, que puede ser la sesión con el foco o la sesión con un servidor de conferencia específico. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 3dc345c10836a34f99baa4d6a088ab152b23427d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815338"
---
# <a name="conferencesessiondetails-view"></a>Vista ConferenceSessionDetails
 
La vista ConferenceSessionDetails almacena información sobre las sesiones de varias partes. Cada registro representa una sesión de conferencia, que puede ser la sesión con el foco o la sesión con un servidor de conferencia específico. Esta vista se presentó en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se usa en conjunción con SessionIdTime para identificar de forma única una sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**InviteTime** <br/> |datetime  <br/> |Hora de la primera solicitud de invitación. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URI de la Conferencia.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |URI de tipo de conferencia. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**ConfInstance** <br/> |identificador  <br/> |Identificador que diferencia entre instancias de conferencias periódicas. Cada instancia de conferencia periódica tiene el mismo ConferenceURI pero un valor diferente de ConfInstance.  <br/> |
|**McuConferenceUri** <br/> |nvarchar (450)  <br/> |URI del servidor de conferencia.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del servidor de conferencia. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |URI del usuario implicado en la sesión.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que formaba parte de la sesión. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Espacio empresarial del usuario que formaba parte de la sesión. Para obtener más información, consulte la [tabla de inquilinos](tenants.md) . <br/> |
|**UserEndpointId** <br/> |identificador  <br/> |Identificador único del usuario que forma parte de la sesión.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Versión del servidor de conferencia.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Tipo de servidor de conferencia. Para obtener más información, consulte la [tabla UserAgentDef](useragentdef.md) . <br/> |
|**ConferenceCategory** <br/> |nvarchar (64)  <br/> |Categoría servidor de conferencia.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versión del cliente utilizada por el usuario que participó en la sesión.  <br/> |
|**UserClientType** <br/> |int  <br/> |Cliente usado por el usuario que participó en la sesión. Para obtener más información, consulta la [tabla UserAgentDef](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |Nombre de la categoría del cliente que ha usado el usuario que forma parte de la sesión.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)  <br/> |URI del usuario en cuyo nombre se inició la sesión.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario en cuyo nombre se inició la sesión. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario cuyo en nombre se ha iniciado la sesión. Para obtener más información, consulte la [tabla de inquilinos](tenants.md) . <br/> |
|**ReferredByUri** <br/> |nvarchar (450)  <br/> |Identificador URI del usuario que remitió la sesión.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que ha remitido la sesión. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Espacio empresarial del usuario que remitió la sesión. Para obtener más información, consulte la [tabla de inquilinos](tenants.md) . <br/> |
|**DialogId** <br/> |varstring (775)  <br/> |IDENTIFICACIÓN del cuadro de diálogo SIP. El formato es  <br/> :d ialog; de-etiqueta; to-Tag  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Número de identificación para identificar el cuadro de diálogo que se reemplazó por la sesión actual. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se usa junto con ReplaceDialogIdTime para identificar de forma única una sesión que se reemplaza por esta sesión. Para obtener más información, consulte la [tabla cuadros de diálogo en Skype empresarial Server 2015](dialogs.md) . <br/> |
|**ReplacesDialogId** <br/> |VARCHAR (775)  <br/> |IDENTIFICACIÓN del cuadro de diálogo SIP que reemplaza la sesión. El formato de es:  <br/> cuadro de diálogo; desde: etiqueta; to-Tag  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |Indica si la sesión ha sido iniciada por el servidor de conferencia.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |Indica si el servidor de conferencia finalizó la sesión.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |Indica si el usuario ha iniciado sesión en la red interna.  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Hora de la respuesta al primer mensaje de invitación. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de respuesta SIP a la invitación de la sesión. Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión. Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |IDENTIFICADOR de diagnóstico capturado de los encabezados de SIP de la sesión.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo de contenido de la sesión.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN del servidor front-end que capturó los datos para la sesión.  <br/> |
|**Grupo** <br/> |nvarchar(256)  <br/> |FQDN del grupo de servidores que ha capturado los datos de la sesión.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediación usado por el usuario que participó en la sesión.  <br/> |
|**Puerta** <br/> |nvarchar(256)  <br/> |Puerta de enlace usada por el usuario que participó la sesión.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor perimetral usado por el usuario que participó en la sesión.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |Indica los atributos del usuario que participó en la sesión. Se permiten las siguientes definiciones de atributos:  <br/> 0x01: integrado con un teléfono de escritorio  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica los atributos de la llamada. Se permiten las siguientes definiciones de atributo:  <br/> 0x01-reintento Session0  <br/> x02: una llamada realizada por el agente en nombre de un grupo de respuesta  <br/> |
   

