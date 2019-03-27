---
title: Tabla ConferenceSessionDetails en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Cada registro representa una sesión de conferencia, que podría ser la sesión con foco o la sesión con un servidor de conferencia específico.
ms.openlocfilehash: ab51ff0c75ba5ea9c6164fdee00be65ff5538c73
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885715"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Tabla ConferenceSessionDetails en Skype para Business Server 2015
 
Cada registro representa una sesión de conferencia, que podría ser la sesión con foco o la sesión con un servidor de conferencia específico.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Fecha y hora  <br/> |Principal, externa  <br/> |Tiempo de solicitud de sesión; se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una sesión de conferencia. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar de forma exclusiva una sesión de conferencia. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Externa  <br/> |URI de conferencia de foco relacionados con esta sesión. Consulte la [tabla ConferenceUris en Skype para Business Server 2015](conferenceuris.md) para obtener más información. Este URI es un URI de conferencia basadas en foco. <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||Identificador que diferencia entre instancias de conferencias periódicas. Cada instancia de conferencia periódica tiene el mismo ConferenceURI, pero un valor distinto de ConfInstance.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Externa  <br/> |Conferencia de servidor de conferencia URI relacionados con esta sesión. Consulte la [tabla ConferenceUris en Skype para Business Server 2015](conferenceuris.md) para obtener más información. Este URI es la conferencia basada en servidor URI de conferencia. Para las sesiones de conferencia de foco, esta columna será null. <br/> |
|**UserId** <br/> |int  <br/> |Externa  <br/> |Identificador de un usuario en la sesión de conferencia. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||Un GUID para identificar la instancia del extremo. Por ejemplo, si un usuario inicia sesión en diferentes equipos con la misma cuenta, a continuación, cada máquina tendrá un identificador de extremo diferente.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Externa  <br/> |Indica el identificador del usuario de quién es el autor de la llamada en nombre. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**ReferredById** <br/> |int  <br/> |Externa  <br/> |Identificador del usuario por la que se conoce la llamada. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Externa  <br/> |Versión del cliente usado por el usuario de conferencia. Consulte la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md) para obtener más información. <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Externa  <br/> |Versión de cliente que usa el servidor de conferencia. Consulte la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md) para obtener más información. <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Externa  <br/> |Número de identificador para identificar el cuadro de diálogo que se ha sustituido por la sesión actual. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Externa  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con **ReplacesDialogIdTime** para identificar de forma exclusiva una sesión que se ha reemplazado por esta sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Indica si la sesión iniciada por el servidor de conferencia.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Indica si la sesión finalizó el servidor de conferencia.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Si usuario ha iniciado sesión desde interna o no.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de respuesta de protocolo de inicio (SIP) de sesión para la invitación a la sesión. Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Identificador de diagnóstico capturado del encabezado SIP.  <br/> |
|**ServerId** <br/> |int  <br/> |Externa  <br/> |Identificador del servidor front-end que se usará para esta sesión. Consulte la [tabla de servidores](servers.md) para obtener más información. <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |Identificador del grupo de servidores en el que se ha capturado la sesión. Vea la [tabla de grupos de servidores](pools.md) para obtener más información. <br/> |
|**MediationServerId** <br/> |int  <br/> |Externa  <br/> |El servidor de mediación que está usando la llamada. Consulte la [tabla MediationServers](mediationservers.md) para obtener más información. <br/> |
|**GatewayId** <br/> |int  <br/> |Externa  <br/> |Está usando la puerta de enlace de la llamada. Consulte la [tabla de puertas de enlace de Skype para Business Server 2015](gateways.md) para obtener más información. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Externa  <br/> |Está usando el servidor perimetral de la llamada. Consulte la [tabla EdgeServers en Skype para Business Server 2015](edgeservers.md) para obtener más información. <br/> |
|**ContentTypeId** <br/> |int  <br/> |Externa  <br/> |Tipo de contenido utilizado en la sesión. Vea la [tabla ContentTypes de Skype para Business Server 2015](contenttypes.md) para obtener más información. <br/> |
|**InviteTime** <br/> |datetime  <br/> ||Hora de la primera solicitud INVITE. Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||Hora de la primera respuesta SIP. Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO).  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||La hora cuando se finalizó la sesión.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Externa  <br/> |Contiene el valor de tipo de MCU URI de la [tabla UriTypes](uritypes.md). Este campo se usa para mejorar el rendimiento de las consultas.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || Un bit establecido indica los atributos de usuario. Aparecen las siguientes definiciones de atributo: <br/>  Integrado con el teléfono de escritorio: 1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || Un bit establecido indica los atributos de llamada. Aparecen las siguientes definiciones de atributo: <br/>  Sesión reintentada: 1 <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   
\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor de 1. Si iniciar varias sesiones al mismo tiempo, la SessionIdSeq para uno será 1, para otro va a ser 2 y así sucesivamente.
  

