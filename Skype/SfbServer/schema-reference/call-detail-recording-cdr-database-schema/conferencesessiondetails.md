---
title: Vista de ConferenceSessionDetails
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: La vista ConferenceSessionDetails almacena información acerca de las sesiones con varios participantes. Cada registro representa una sesión de conferencia, que podría ser la sesión con el foco o la sesión con un servidor de conferencia específica. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 8e81f33a68fc90a589f4d3574f9ca3070076c479
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="conferencesessiondetails-view"></a>Vista de ConferenceSessionDetails
 
La vista ConferenceSessionDetails almacena información acerca de las sesiones con varios participantes. Cada registro representa una sesión de conferencia, que podría ser la sesión con el foco o la sesión con un servidor de conferencia específica. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora de la solicitud de sesión. Se utiliza junto con SessionIdSeq para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con SessionIdTime para identificar una sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**InviteTime** <br/> |datetime  <br/> |Hora de la primera solicitud de invitación. Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información).  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conferencia.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |URI de tipo de conferencia. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Identificador que distingue entre instancias de conferencias periódicas. Cada instancia de conferencia periódica tiene el mismo ConferenceURI pero un valor diferente de ConfInstance.  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |URI del servidor de conferencias.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del servidor de conferencias. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI del usuario implicado en la sesión.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario cuya formaba parte de la sesión. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Inquilinos del usuario cuya formaba parte de la sesión. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificador único del usuario cuya formaba parte de la sesión.  <br/> |
|**Hora de finalización** <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Versión de servidor de conferencia.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Tipo de servidor de conferencia. Consulte la [tabla de UserAgentDef](useragentdef.md) para obtener más información. <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |Categoría de servidor de conferencia.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versión de cliente utilizada por el usuario que participaron en la sesión.  <br/> |
|**UserClientType** <br/> |int  <br/> |Cliente utilizado por el usuario que participaron en la sesión. Consulte la [tabla de UserAgentDef](useragentdef.md) para obtener más detalles. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nombre de la categoría del cliente utilizado por el usuario que formaba parte de la sesión.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI del usuario en cuyo nombre se inició la sesión.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario en cuyo nombre se inició la sesión. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Inquilinos del usuario cuya en nombre se inició la sesión. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI del usuario que a que se refiere la sesión.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI del usuario que a que se refiere la sesión. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Inquilino del usuario que a que se refiere la sesión. Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID de SIP El formato es  <br/> : diálogo de etiqueta; para etiqueta  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Número de ID para identificar el cuadro de diálogo que se ha reemplazado por la sesión actual. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Número de identificación para identificar la sesión. Se utiliza junto con ReplaceDialogIdTime para identificar una sesión que es reemplazada por esta sesión. Consulte la [tabla de Skype para Business Server 2015 los cuadros de diálogo](dialogs.md) para obtener más información. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |ID de diálogo sustituye a la sesión del SIP. El formato de la es:  <br/> diálogo de etiqueta; para etiqueta  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |Indica si la sesión ha sido iniciada por el servidor de conferencia.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |Indica si la sesión ha terminado por el servidor de conferencia.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |Indica si el usuario inició sesión desde la red interna.  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Hora de la respuesta al primer mensaje de invitación. Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de respuesta SIP a la invitación de sesión. Normalmente, este campo se rellena con datos generados desde el mensaje de invitación inicial en la sesión. Si no aparece ningún mensaje de invitación se rellena el campo con la fecha y hora de la primer mensaje SIP pertinente (BYE, Cancelar, mensaje o información).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |Id. de diagnóstico captura de sesión encabezados SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo de contenido de la sesión.  <br/> |
|**Front-end** <br/> |nvarchar(256)  <br/> |FQDN del servidor Front-End que capturan los datos de la sesión.  <br/> |
|**Grupo de servidores** <br/> |nvarchar(256)  <br/> |FQDN del grupo que captura los datos de la sesión.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Utilizado por el usuario que participaron en la sesión de un servidor de mediación.  <br/> |
|**Puerta de enlace** <br/> |nvarchar(256)  <br/> |Puerta de enlace utilizada por el usuario en la que participaron la sesión.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del servidor de borde utilizado por el usuario que participaron en la sesión.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |Indica los atributos del usuario que participaron en la sesión. Las siguientes definiciones de atributo permite:  <br/> 0 x 01 - integrado con el teléfono de escritorio  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica los atributos de la llamada. Se permiten las siguientes definiciones de atributo:  <br/> 0 x 01 - vuelve a intentar Session0  <br/> x02-una llamada realizada por el agente en nombre de un grupo de respuesta  <br/> |
   

