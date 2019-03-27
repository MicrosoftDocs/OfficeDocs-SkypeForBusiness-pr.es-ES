---
title: Tabla SessionDetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Cada registro representa una sesión de punto a punto, que podría ser una llamada de teléfono VoIP-VoIP, sesión de mensajería instantánea entre dos participantes u otro tipo de sesión. Puede realizar una combinación de tabla con la tabla de medios para encontrar los detalles de cada medios implicados en esta sesión.
ms.openlocfilehash: e499c8d443742bacfcdbe9c129e884cae4dd96a0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889927"
---
# <a name="sessiondetails-table"></a>Tabla SessionDetails
 
Cada registro representa una sesión de punto a punto, que podría ser una llamada de teléfono VoIP-VoIP, sesión de mensajería instantánea entre dos participantes u otro tipo de sesión. Puede realizar una combinación de tabla con la [tabla de medios](media.md) para encontrar los detalles de cada medios implicados en esta sesión.
  
Tenga en cuenta que el IsUser1IntegratedWithDeskPhone y los campos de IsUser2IntegratedWithDeskPhone se han quitado de la tabla SessionDetails utilizada en Skype para Business Server 2015.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principal, externa  <br/> |Hora de la solicitud de sesión. Se utiliza en forma conjunta con **SessionIdSeq** para identificar de forma exclusiva una sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal, externa  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con **SessionIdTime** para identificar de forma única un session.*, vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> ||Un GUID para correlacionar varias sesiones.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Externa  <br/> |Número de identificador para identificar el cuadro de diálogo que se ha sustituido por la sesión actual. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Externa  <br/> |Número de identificador para identificar la sesión. Se utiliza junto con **ReplacesDialogIdTime** para identificar de forma exclusiva una sesión que se ha reemplazado por esta sesión. Vea la [tabla en Skype para Business Server 2015 Dialogs](dialogs.md) para obtener más información. <br/> |
|**User1Id** <br/> |int  <br/> |Externa  <br/> |Identificador de un usuario en la sesión. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**User2Id** <br/> |int  <br/> |Externa  <br/> |Identificador del otro usuario en la sesión. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID que identifica el extremo utilizado por el primer usuario en la sesión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID que identifica el extremo que utilizó el segundo usuario en la sesión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Externa  <br/> |El original al URI del usuario en la solicitud SIP. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**SessionStartedById** <br/> |int  <br/> |Externa  <br/> |Identificador del usuario que inició la sesión. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Externa  <br/> |Indica el identificador del usuario de quién es el autor de la llamada en nombre. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**ReferredById** <br/> |int  <br/> |Externa  <br/> |Identificador del usuario por la que se conoce la llamada. Consulte la [tabla de los usuarios](users.md) para obtener más información. <br/> |
|**ServerId** <br/> |int  <br/> |Externa  <br/> |Identificador del servidor front-end que se usará para esta sesión. Consulte la [tabla de servidores](servers.md) para obtener más información. <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |Identificador del grupo de servidores en el que se ha capturado la sesión. Vea la [tabla de grupos de servidores](pools.md) para obtener más información. <br/> |
|**ContentTypeID** <br/> |int  <br/> |Externa  <br/> |Tipo de contenido utilizado en la sesión. Vea la [tabla ContentTypes de Skype para Business Server 2015](contenttypes.md) para obtener más información. <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Externa  <br/> |Versión de cliente que usa User1. Consulte la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md) para obtener más información. <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Externa  <br/> |Versión de cliente usado por el usuario 2. Consulte la [tabla ClientVersions en Skype para Business Server 2015](clientversions.md) para obtener más información. <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Externa  <br/> |Servidor perimetral que usa User1. Consulte la [tabla EdgeServers en Skype para Business Server 2015](edgeservers.md) para obtener más información. <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Externa  <br/> |Servidor perimetral que usa el usuario 2. Consulte la [tabla EdgeServers en Skype para Business Server 2015](edgeservers.md) para obtener más información. <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||Si User1 ha iniciado sesión desde interna o no.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||Si el usuario 2 ha iniciado sesión desde interna o no.  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||Hora de la primera solicitud INVITE. Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO). Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||Hora de la respuesta para el primer mensaje invitar. Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de respuesta SIP a la invitación a la sesión. Este campo se rellena normalmente por datos generados a partir del mensaje INVITE inicial en la sesión. Si no hay ningún mensaje de invitar a continuación, se rellena el campo con la fecha y hora de la primer mensaje SIP relevante (BYE, Cancelar, mensaje o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Identificador de diagnóstico capturado del encabezado SIP.  <br/> |
|**CallPriority** <br/> |int  <br/> |Externa  <br/> |Prioridad de llamada. Consulte la [tabla CallPriorities en Skype para Business Server 2015](callpriorities.md) para obtener más información. <br/> |
|**User1MessageCount** <br/> |int  <br/> ||Número de mensajes que envió el usuario 1 durante la sesión.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||Número de mensajes enviados por el usuario 2 durante la sesión.  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Tiempo al final de la sesión.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Un bit establecido indica el tipo de medio de esta sesión. Enumerados son las definiciones de los tipos:  <br/> 1: MENSAJERÍA INSTANTÁNEA  <br/> 2 - FILE_TRANSFER  <br/> 4 - REMOTE_ASSISTANCE  <br/> 8 - APP_SHARING  <br/> 16 - AUDIO  <br/> 32 - VÍDEO  <br/> 64 - APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||Un bit establecido indica los atributos de User1. Aparecen las siguientes definiciones de atributo:  <br/> 0 x 01 - integrado con el teléfono de escritorio  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||Un bit establecido indica los atributos de usuario 2. Aparecen las siguientes definiciones de atributo:  <br/> 0 x 01 - integrado con el teléfono de escritorio  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||Un bit establecido indica los atributos de llamada. Aparecen las siguientes definiciones de atributo:  <br/> 0 x 01 - reintento de sesión  <br/> 0 x 02 - una llamada realizada por el agente en nombre de un grupo de respuesta  <br/> |
|**Procesar** <br/> |bit  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Fecha y hora  <br/> ||Para uso interno por el servicio de supervisión.  <br/> Este campo se introdujo en Skype para Business Server 2015.  <br/> |
   
\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor de 1. Si iniciar varias sesiones al mismo tiempo, la SessionIdSeq para uno será 1, para otro va a ser 2 y así sucesivamente.
  

